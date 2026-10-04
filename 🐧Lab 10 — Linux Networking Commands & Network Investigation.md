# Linux Networking Commands & Network Investigation

## Objectives

-Identify a Linux machine's IP address.

-Identify its network interfaces.

-Understand loopback (127.0.0.1).

-Identify the default gateway.

-View the routing table.

-Test connectivity to another system.

-Understand basic DNS resolution.

-Resolve a domain to an IP address.

-Inspect listening TCP/UDP ports.

-Inspect active network connections.

-Associate network connections with processes.

-Recognize potentially suspicious connections or listening services.

-Perform a basic Linux network investigation.

## Enviroment

Component	Environment

Host OS	Windows

Virtualization	VirtualBox

Guest OS	Ubuntu 24.04 LTS

Shell	Bash

Network	VirtualBox NAT

## Tools used

-Bash Commands:

ip addr

ip route

ping

ss

dig

nslookup

## Steps performed and evidence (screenshots)

1- Used the ip addre command (also ip a can work) , here I was able to see information on lo (loop back) which is local network inside the network card and enp0s3 which is for external and LAN connections.

<img width="775" height="290" alt="image" src="https://github.com/user-attachments/assets/63e0196f-1128-4112-9ee8-40149e428cb9" />

Here I could identify:

the interface: enp0s3
Ipv4 address: 10.0.2.15
Loopback interface: lo
Ipv4: 127.0.0.1

Used the ip route command to open up routing table and was able to identify the default gateway is 10.0.2.0/24 through the Enp0s3 interface

<img width="575" height="62" alt="image" src="https://github.com/user-attachments/assets/2bfae5c2-9fb6-43c0-97fd-09ad7cf2f7d6" />

2- Tested connectivty using ping 8.8.8.8 and youtube.com command and make sure it was replying.

<img width="650" height="362" alt="image" src="https://github.com/user-attachments/assets/946695ca-d164-42c1-b03b-c757419b4671" />

3- Used nslookup command to get the DNS lookup information for youtube.com

<img width="371" height="387" alt="image" src="https://github.com/user-attachments/assets/94413053-b856-4c9b-8966-22ac0d1daf1e" />


4- Used ss - tuln command to view all the ports, here I can see all listening portss and all unconnected ports.

<img width="755" height="365" alt="image" src="https://github.com/user-attachments/assets/01f2bb30-dd58-4dc6-85ff-5aedf9af0c5a" />


5- Used sudo ss -tulnp to view all the ports and their assciated processes, then used ss -tun to view all current stablished connections.

<img width="736" height="390" alt="image" src="https://github.com/user-attachments/assets/c4a8edaa-91a6-47dc-8971-3df90a09641f" />


<img width="740" height="57" alt="image" src="https://github.com/user-attachments/assets/b49303d8-4224-412f-b3f9-6b5e0a94ad5d" />


6- used the sudo ss -tulpn | grep ssh command to filter the connections and ports for ssh.

<img width="767" height="92" alt="image" src="https://github.com/user-attachments/assets/31fefdf5-f72f-4ea8-a4de-af16f05a99db" />


## lessons learned

Learned how to view the machines network configurations with the ip a command, identify routing configuration using the ip route command, identify listening ports using the ss -tulp command.

Then using that information to identify associated processes with ports, investigate the process itself and the service itself, determine if it starts automatically. as well as looking up DNS for websites and such.

## SOC relevance 

Help me answer these questions: 

What's my IP?" → ip addr
"What's my default gateway?" → ip route
"Can I reach this host?" → ping
"What IP does this domain resolve to?" → dig / nslookup
"What ports are listening?" → ss -tuln
"What process owns that listening socket?" → sudo ss -tulpn
