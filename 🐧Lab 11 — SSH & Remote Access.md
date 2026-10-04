# SSH & Remote Access

## Objectives

-Explain what SSH is and why it's used.

-Understand the basic client/server model.

-Understand that SSH commonly uses TCP port 22.

-Install and configure an SSH server.

-Determine whether SSH is running.

-Identify the Linux VM's IP address.

-Connect remotely to Linux using SSH.

-Understand username/password authentication.

-Understand the purpose of SSH keys.

-Understand public vs. private keys.

-Identify SSH network connections.

-Examine basic SSH authentication logs.

-Recognize failed/suspicious SSH authentication activity.

-Understand why SSH is important during SOC investigations.


## Enviroment

Component	Environment

Host	Windows

Virtualization	VirtualBox

SSH Server	Ubuntu 24.04 LTS VM

SSH Client	Windows OpenSSH

Shell	Bash / PowerShell

## Tools used

-Bash commands: 

ssh

ssh-keygen

systemctl

ss

ip

who

w

last

journalctl

## Steps performed and evidence (screenshots)

1- Started the ssh using the sudo systemctl start shh command then verified the port for this service (port 22) is listening using the command sudo ss -tlnpn | grepp :22 command

<img width="772" height="525" alt="image" src="https://github.com/user-attachments/assets/e11f76e3-e7d6-4669-a858-29e3e87aa323" />


2- Used ssh localhost to create a ssh connection with the localhost.

<img width="552" height="452" alt="image" src="https://github.com/user-attachments/assets/944b7b0e-501e-47e0-808e-50aeb8ee7b74" />


3- Used port fowarding rule that I created using port 2222 inside Virtualbox to conenct my windows host to my ubuntu machine using -p 2222 vboxuser@127.0.0.1 command

<img width="856" height="550" alt="image" src="https://github.com/user-attachments/assets/78be784b-76db-4b74-97e1-c08a86622c15" />

4- 

5- 

6- 

7- 

8- 


## lessons learned




## SOC relevance 
