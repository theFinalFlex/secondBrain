00:00 - Intro
00:46 - Starting with nmap
02:15 - Enumerating the website to see links to the HelpDesk and Mattermost
03:40 - Attempting to enumerate the version of osTicket
05:45 - Searchsploit json output shows the date
06:30 - No exploits found, lets open a new ticket and see it gives us a way to update the ticket via email
08:40 - Creating an account on Mattermost with the email of the helpdesk to get the activation link
09:30 - Viewing the internal chat and seeing a password, then SSHing to the server
11:50 - Using hashcat to create a wordlist with its internal rule system
12:20 - Going over how Hashcat Rule files work
15:20 - Root #1: Running sucrack to bruteforce the root users password
19:50 - Root #2: Cracking the Mattermost Password
23:20 - Using hashcat to crack the Mattermost Password
26:45 - Going over how i set up the email server on this box
