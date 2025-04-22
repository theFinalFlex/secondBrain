`which`- this tool returns the path to the file or link that should be executed

suid sgid can be used to enable users to run as privledged for certain programs 
like PIM in cloud 

stick bits - t, T

systemctl
journal ctl
ps -aux
enable
kill 9 
bg 
fg

systemmd is a service used in linux to start process and scripts at specific times. 
cron is also used to schedule and automate processes. 



| Type      | Meaning                                                           |
| --------- | ----------------------------------------------------------------- |
| `simple`  | Default. The service starts directly from the main process.       |
| `forking` | The service forks (e.g., daemonizes), and the parent exits early. |
| `oneshot` | The service runs a short task and exits.                          |
| `notify`  | The service sends a signal to systemd when it is ready.           |
| `dbus`    | Waits for the service to appear on the DBus bus.                  |
| `idle`    | Only runs when the system is idle.                                |
OPenSSH is a free opensource server that allows secure transmission of data and commands using SSH 

NFS permissions
![](../../../Assets/Pasted%20image%2020250415120613.png)
**URI:**  
`mailto:someone@example.com`  
– This is a URI, but **not a URL** (it doesn’t tell you how to fetch a file via HTTP).

**URL (also a URI):**  
`https://hackthebox.com/login`  
– This **is a URL**, and since it's a URL, it's also a **URI**.

**URN (also a URI):**  
`urn:isbn:0451450523`  
– This is **only** a URI. It names something (a book), but it doesn’t tell you where or how to get it.


php -S 127.0.0.0.0:8080
starting a php server

Rsync is a open source tool used for backups
Duplicity adds encryption to Rsync 
Deja Dup = simple GUI based backup solution 
Rsync_backup.sh 

Inodes are data structures that store metadata on files and folder structures


LXC is more for linux environments 
docker is more for application containerization

docker is easy to use
both can be privilege escalated 
LXC commands
![](../../../Assets/Pasted%20image%2020250421134413.png)


SELinux = secuirity enhanced linux
Apparmor for app security
TCP wrapper to control access to services based on IP addresses

lsof = to list open files 
ss = socket statistics
ELK stack = elastic search, logstash and kibana

