# 4.Execution_of_NetworkCommands

## AIM :
Use of Network commands in Real Time environment
## Software : 
Command Prompt And Network Protocol Analyzer
## Procedure: 
### To do this EXPERIMENT- follows these steps:

1. In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
2. All commands related to Network configuration which includes how to switch to privilege mode and normal mode and how to configure router interface and how to save this configuration to flash memory or permanent memory.

  This commands includes

    • Configuring the Router commands
    • General Commands to configure network
    • Privileged Mode commands of a router 
    • Router Processes & Statistics
    • IP Commands
    • Other IP Commands e.g. show ip route etc.

## Program
### Client
```.py
import socket
from pythonping import ping
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    hostname=c.recv(1024).decode()
    try:
        c.send(str(ping(hostname, verbose=False)).encode())
    except Exception as e:  # Catch all errors
        c.send(f"Error: {str(e)}".encode())
```

### Server
```.py
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter the website you want to ping ")
    s.send(ip.encode())
    print(s.recv(1024).decode())
```


## Output
### Client
<img width="1141" height="510" alt="image" src="https://github.com/user-attachments/assets/a7969f09-a65b-432c-83aa-bcda668a9b56" />

### Server
<img width="982" height="530" alt="image" src="https://github.com/user-attachments/assets/143cd8da-c420-42a4-b3d7-071d1df6f4b6" />

## Result
Thus Execution of Network commands Performed 
