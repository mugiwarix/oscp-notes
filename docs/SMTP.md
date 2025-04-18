- Useful SMTP command

```
nc -nv IP_ADDR 25 # open connection to SMTP server
VFRY root # verify e-mail address
EXPN MAILING_LIST # shows mailing list members
```

- Script to enumerate SMTP users (and so local users)

```
#!/usr/bin/python

import socket
import sys
if len(sys.argv) != 3:
        print("Usage: smtp_enum.py <user> <ip>")
        sys.exit(0)
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
ip = sys.argv[2]
connect = s.connect((ip,25))
banner = s.recv(1024)
user = (sys.argv[1]).encode()
s.send(b'VRFY ' + user + b'\r\n')
result = s.recv(1024)
print(result)
s.close()
```

- Enumerate SMTP user from PowerShell

```
Test-NetConnection -Port 25 IP_ADDR
```

- Install Telnet on Windows

```
dism /online /Enable-Feature /FeatureName:TelnetClient
```
