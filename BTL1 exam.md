Attacker timeline 
![](Assets/Pasted%20image%2020250225135739.png)


itadmin@ecorpgroup.co.uk
tywinlannister@ecorpgroup.co.uk


	200-econgroup pdf created time 2022-01-16 21:35:32 



1. mail.invoicehome.com
   
   
   
   ### **Investigation Summary: Florence Nightingale Phishing Incident**

#### **🚨 Incident Overview**

- Florence Nightingale received a **phishing email** impersonating **InvoiceHome.com**.
- The email contained a **malicious link** leading to **invoicehome.uk** (a spoofed domain).
- She downloaded **invoice.zip**, which contained a **malicious PDF**.
- The **PDF appeared blank**, but analysis showed **embedded malicious content**.

#### **🕵️‍♂️ Key Findings**

1. **Phishing Email & Malicious ZIP**
    
    - Email from **invoicehome.uk** delivered **invoice.zip**.
    - The ZIP contained **200-Ecorpgroup.pdf**, a blank PDF with possible obfuscated malware.
    - Florence complained about **not being able to open the file**, indicating execution attempts.
2. **Sensitive Files on Desktop**
    
    - Found **vpn password.txt** → Indicates stored **VPN credentials**.
    - Found **remoteworking_ecorpgroup.ovpn** → Could allow **trusted remote access** for attackers.
3. **VPN Connections Outside the UK**
    
    - Attackers may have used **stolen VPN credentials** for remote access.
    - **Splunk investigation needed** to identify the two **non-UK** login locations.
4. **Splunk Queries for Investigation**
    
    - **To find execution of invoice.zip**:
        
        spl
        
        CopyEdit
        
        `index=* sourcetype=XmlWinEventLog OR sourcetype=syslog "invoice.zip"`
        
    - **To check for VPN logins from outside the UK**:
        
        spl
        
        CopyEdit
        
        `index=* sourcetype=syslog OR sourcetype=XmlWinEventLog "vpn" "authentication success" NOT country="United Kingdom" | stats count by country`
        
    - **To track file execution & access**:
        
        spl
        
        CopyEdit
        
        `index=* sourcetype=XmlWinEventLog "200-Ecorpgroup.pdf"`
        
    - **To find potential exfiltration of sensitive files**:
        
        spl
        
        CopyEdit
        
        `index=* sourcetype=syslog OR sourcetype=exec "vpn password.txt"`
        

#### **🚀 Next Steps**

✅ **Confirm non-UK VPN logins** via Splunk.  
✅ **Verify if VPN credentials were accessed or exfiltrated**.  
✅ **Check for attacker persistence (new users, scheduled tasks, remote access tools)**.  
✅ **Determine if Florence’s machine was used for lateral movement**.

---

This **condenses all key findings** so you can **restart fresh** while keeping the critical insights! 🚀


[![Security Blue Team](https://d2y9h8w1ydnujs.cloudfront.net/assets/images/logo/new_sbt_logo.png)](https://elearning.securityblue.team/home)

- Current Exam:[**#NC7HKWGRR**- Blue Team Level 1 Exam](https://elearning.securityblue.team/home/exam/connect/28bc6060-b80b-4d14-b772-bdd2453dcb3c#)
- Time Left:**15:55:04**
- Reset Exam Environment

FullscreenClipboardInstructionsQuestionsHelp

### Questions

**Question 1 )**Initial Access - What is the domain name from the URL included in the phishing email that results in a file download in Florence's mailbox?Format: domain.tld
invoicehome.uk
**Question 2 )**Initial Access - What is the file that was downloaded to Florence's machine when visiting the phishing URL?Format: filename.extension
invoice.zip
**Question 3 )**Initial Access - What are the filenames of the two sensitive files found on Florence's Desktop that could have led to trusted remote access into the corporate environment?Format: filename.extension, filename.extension
vpn password.txt, remoteworking_ecorpgroup.ovpn
**Question 4 )**Initial Access - What are the two countries that have initiated VPN connections outside of the UK, as shown in the Splunk dashboard?Format: Country1, Country2
Spain, Maldova
**Question 5 )**Initial Access - Based on Florence’s mailbox, what legitimate domain is the phishing email attempting to impersonate?Format: domain.tld
 invoicehome.com
**Question 6 )**Execution - Looking in Splunk for traffic going to the public IP address (DestinationIP value) that hosts the phishing domain, what is the UtcTime timestamp of the first event that isn't related to Microsoft Edge or EM Client?Format: YYYY-MM-DD HH:MM:SS
2022-01-15 16:36:07
**Question 7 )**Execution - Looking in Splunk for traffic going to the public IP address that hosts the phishing domain, what file is beaconing out to the IP, and what is the destination port?Format: filename.extension, destinationPort
template.pdf, 4444
**Question 8 )**Execution - Using Splunk or Autopsy, identify what file the initial malicious PDF creates when it has been executed. Submit the SHA256 hash to VirusTotal on your host machine and look at the Behavior tab. Identify the IP address and port used for the reverse connection (Think about the IP of the malicious domain!)Format: X.X.X.X:Port
68.183.238.225:4444
**Question 9 )**Persistence - Using DeepBlueCLI, what is the user SID of the attacker-created account on the domain controller?Format: SID String

**Question 10 )**Discovery - Looking at the provided PCAPs, at what time does the TCP SYN network scan begin, originating from 172.16.0.2?Format: YYYY-MM-DD HH:MM:SS.XXXXXX

**Question 11 )**Lateral Movement - ECorpGroup IT Admins only ever connect to the domain controller locally. Using Splunk identify the time and date of the first suspicious network logon Windows event, and what is the target username on the Domain Controller?Format: M/DD/YY HH:MM:SS AM/PM, TargetUsername

**Question 12 )**Lateral Movement - What is the other account used to access the DC using RDP?Format: Target Username

**Question 13 )**Lateral Movement - Investigating the PCAPs, what is the FTP username and password that allowed the Attacker access to the FTP server?Format: username, password

**Question 14 )**Persistence - What is the registry key that is used to maintain persistence on the patient-zero host? Investigate Sysmon ID 13 events in SplunkFormat: registryhive\path\to\key

**Question 15 )**Persistence - What port is listening for incoming connections, based on analysis of registry edits on the domain controller?Format: Port Number

**Question 16 )**Command and Control - In Splunk, what is the DestinationHostname used by the crypto miner? (Try searching for the filename to see what logs are found!)Format: X.X.X.X.domain.tld

**Question 17 )**Action on Objectives - Considering the new account that was created on the domain controller, what is this user's folder that has been used by the threat actor to store both offensive tools and files they have collected for exfiltration? (It will be easier to check this locally on the system and navigate through their files)Format: Drive:\path\to\folder

**Question 18 )**Action on Objectives - What is the file name of the executable that has been renamed to hide in plain sight, that is actually the offensive tool SharpHound? Investigate cmdline logs in Splunk to find anything that mentions *sharphound*. Also include the Software ID for this tool, as stated on the MITRE ATT&CK website.Format: filename.exe, Mitre ATT&CK Software ID

**Question 19 )**Actions on Objectives - Investigate the installation location within /AppData/ of the cryptominer on the domain controller. Identify the Attacker's email address used in the configuration fileFormat: mailbox@domain.tld

**Question 20 )**Collection - How many UNIQUE confidential finance documents have likely been exfiltrated by the Attacker? Consider your answer for Question 17Format: Number of Sensitive Files (not including duplicates or folders)

  

You have unanswered questions!

Submit Exam

  

  

- 
- 
-