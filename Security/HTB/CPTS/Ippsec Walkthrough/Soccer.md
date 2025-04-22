00:00 - Introduction
01:00 - Start of nmap, assuming the web app is NodeJS based upon a 404 message
04:20 - Running Gobuster and discovering Tiny File Manager
06:00 - Looking for the source code and finding a default password of admin@123
06:45 - Navigating to uploads and attempting to upload a php shell to the website
07:45 - Getting a reverse shell with our php shell
09:00 - Reverse shell returned
09:30 - Talking about hidepid=2 is set, so we can't see processes for other users
10:00 - Looking at nginx configuration to see what port 9091 is and discovering a new subdomain (soc-player.soccer.htb)
11:00 - Navigating to soc-player.soccer.htb and discovering a few more pages
12:00 - The /check endpoint looks like it is vulnerable to Boolean SQL Injection
13:00 - Intercepting the websocket in BurpSuite and showing 
15:20 - Using SQLMap to dump the database, first time I've used SQLMap with websockets
23:30 - Attempting to ssh with creds found in the database and logging in as player
26:50 - Running LinPEAS
30:50 - Looks like we can run doas, which is like sudo. Looking at the command we can run and seeing dstat
33:30 - Creating a dstat plugin, then executing it with doas


Goal is to get a shell and then find a website, use the websocket technology which is vuln to a boolean based SQL injection and then get credentials, login, be able to login into DOAS which is configured for you as root and be able to priv esc


he runs nmap
sees SSH - opensshz
port 80 - nginx
all requests are being redirected t soccer.htb
