# 4.Execution_of_NetworkCommands
## AIM :
Use of Network commands in Real Time environment
## Software : 
Command Prompt And Network Protocol Analyzer
## Procedure: 
To do this EXPERIMENT- follows these steps:
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

## Program:
```
server.py

import socket

dns_table = {
    "google.com": "142.250.190.78",
    "yahoo.com": "98.137.11.163",
    "openai.com": "104.18.12.123",
    "example.com": "93.184.216.34"
}

server_socket = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)

server_socket.bind(("127.0.0.1", 15353))

print("DNS Server running on port 5353...\n")

while True:
    message, client_address = server_socket.recvfrom(1024)
    domain = message.decode()
    print("Request received for:", domain)
    ip = dns_table.get(domain, "Domain not found")
    server_socket.sendto(ip.encode(), client_address)

```
```
client.py

import socket

client_socket = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
server_address = ("127.0.0.1", 15353)

domain = input("Enter domain name: ")

# Send request to server
client_socket.sendto(domain.encode(), server_address)

ip_address, server = client_socket.recvfrom(1024)

print("IP Address:", ip_address.decode())

client_socket.close()
```
## Output
server
<img width="1907" height="1015" alt="image" src="https://github.com/user-attachments/assets/80e5fafc-3f4e-40cb-bac2-24cd88d7cc5c" />
client
<img width="1904" height="1013" alt="image" src="https://github.com/user-attachments/assets/9063add1-db41-40e3-8dcf-de8a55902029" />
Traceroute command
<img width="897" height="316" alt="image" src="https://github.com/user-attachments/assets/3fa08a5d-9312-4a54-8d60-27e9458e87ae" />

## Result
Thus Execution of Network commands Performed 
