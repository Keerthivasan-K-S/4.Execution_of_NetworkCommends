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

## netstat
<img width="1174" height="445" alt="image" src="https://github.com/user-attachments/assets/95a96a8b-d7fd-4c9a-aa5f-6d9072411a57" />

## ipconfig
<img width="1288" height="669" alt="image" src="https://github.com/user-attachments/assets/de709554-a5f3-48d1-b5cc-c48d165d2036" />

## ping 
<img width="1307" height="764" alt="image" src="https://github.com/user-attachments/assets/27d0652d-243f-416d-a1ea-6d12926aabf5" />

## tracert
<img width="1296" height="328" alt="image" src="https://github.com/user-attachments/assets/ca47605c-8cff-4cbc-9c35-4df8180a4b31" />

## nslookup
<img width="1301" height="697" alt="image" src="https://github.com/user-attachments/assets/f92542c9-43f8-46ef-9440-9cdc47eb9527" />

## getmac
<img width="1302" height="154" alt="image" src="https://github.com/user-attachments/assets/c281d7fb-6442-4bdc-a441-0f68ea93d17c" />

## hostname
<img width="1297" height="63" alt="image" src="https://github.com/user-attachments/assets/66b67385-0a34-43f9-b694-f8823f2f8aed" />

## nbtstat
<img width="1300" height="589" alt="image" src="https://github.com/user-attachments/assets/32e895b2-aef3-4c2c-afdc-3a082c94d55b" />

## arp
<img width="1304" height="754" alt="image" src="https://github.com/user-attachments/assets/dcce7ae6-57dd-4923-b279-4255e87ace4a" />

## systeminfo
<img width="1322" height="910" alt="image" src="https://github.com/user-attachments/assets/920be8cb-da88-424a-a52f-0801372cdd63" />

## Result
Thus Execution of Network commands Performed 
