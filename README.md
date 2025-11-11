# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>

## Program
## Client
```
import socket
from pythonping import ping

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
print("Server is listening...")
c, addr = s.accept()
print("Connected to", addr)

while True:
    hostname = c.recv(1024).decode()
    try:
        c.send(str(ping(hostname, verbose=False)).encode())
    except KeyError:
        c.send("Not Found".encode())
```
## Server
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    ip = input("Enter the website you want to ping: ")
    s.send(ip.encode())
    print(s.recv(1024).decode())

```

## TRACEROUTE COMMAND
```
from scapy.all import *

target = ["www.google.com"]
result, unans = traceroute(target, maxttl=32)
print(result, unans)
```

## Output
<img width="1920" height="1080" alt="Screenshot (8)" src="https://github.com/user-attachments/assets/21bbef8e-9538-4493-984b-1db65d4baa04" />
<img width="1920" height="1080" alt="Screenshot (9)" src="https://github.com/user-attachments/assets/01e74ad5-1bb8-4309-8e98-4f488d3f2bf7" />


## Result
Thus Execution of Network commands Performed 
