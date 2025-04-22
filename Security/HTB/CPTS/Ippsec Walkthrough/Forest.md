# HTB: Forest - CPTS Walkthrough via IppSec

Forest is an Active Directory (AD) box that demonstrates a full attack chain from initial enumeration to Domain Controller (DC) compromise. The steps below summarize the flow of the attack as performed in IppSec’s video.

## Recon

- Ran `nmap -v` on the target to get top 1,000 ports.
- Scheduled a full port scan with `sleep 300; nmap -p-` to avoid timing issues between two scans.
- Ports like 389 (LDAP), 445 (SMB), and 88 (Kerberos) were open — clear signs of an AD environment.

## LDAP Enumeration

- Used `ldapsearch` (null bind) to pull domain user data.
- Extracted full names, email addresses, login failures, and `sAMAccountName`.
- One of the users identified: santi rodrigues.
- Cleaned up the user list using `grep` and `awk` to isolate usernames.

## Wordlist Prep

- Created a custom password list using:
  - `rockyou.txt` as base
  - Seasonal words like Winter2023, Spring2024, etc.
  - Hashcat rules to generate ~40,000 candidates
- Excluded the guest account.
- Saved user list and password list for spraying.

## Password Policy + Spray

- Queried the domain password policy using `crackmapexec` with null authentication.
- Found the policy allowed a safe spray window.
- Initiated password spraying against SMB in the background.

## rpcclient Enumeration

- Used `rpcclient` with no credentials to dump more AD info.
- Retrieved group memberships, SID, and other domain metadata.

## AS-REP Roasting

- Ran `GetNPUsers.py` from Impacket to find accounts with Kerberos pre-auth disabled.
- Found svc-alfresco.
- Dumped AS-REP hash and cracked it using Hashcat.
- Recovered svc-alfresco's plaintext password.

## Initial Foothold

- Logged into the host using `evil-winrm` with svc-alfresco's credentials.
- Established an interactive shell on the box.

## SMB Share + WinPEAS

- Created an SMB share locally.
- Mapped it on the target using `New-PSDrive`.
- Ran `WinPEAS` to enumerate for local privilege escalation.

## BloodHound Enumeration

- Downloaded and executed SharpHound on the target.
- Transferred results back to attack box.
- Set up Neo4j locally and loaded results into BloodHound.

## Finding AD Attack Path

- BloodHound showed that svc-alfresco could reach the Account Operators group.
- This path could be used to escalate privileges.

## Creating New User

- Created a new domain user using `net user`.
- Added the user to a group with privileges (e.g., Exchange group).

## ACL Abuse

- Cloned the PowerSploit dev branch to get `Add-DomainObjectAcl`.
- Used it to give the new user DCSync privileges over the domain.

## DCSync via SecretsDump

- Used `secretsdump.py` to simulate a DC sync and extract:
  - NTLM hashes
  - Administrator hash
  - krbtgt hash

## Golden Ticket Attack

- Used `ticketer.py` to forge a Golden Ticket using the krbtgt hash.
- Exported a `.ccache` ticket on Linux.
- Ran `psexec.py` using the forged ticket to impersonate Administrator.

## Kerberos Time Fix

- Golden Ticket failed at first due to a 4-hour clock skew.
- Synced local time with domain time using `date -s`.
- Re-issued the ticket, succeeded in impersonating Administrator.

---

## Summary

- Enumerated users with LDAP and rpcclient
- Sprayed passwords using CrackMapExec
- AS-REP roasted svc-alfresco and got a shell with Evil-WinRM
- Ran BloodHound to identify attack path via ACL abuse
- Created a new domain user and gave it DCSync rights
- Extracted domain hashes with secretsdump
- Forged a Golden Ticket and got full domain access

