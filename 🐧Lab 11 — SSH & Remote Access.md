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

4- Used the pwd, whoami and hostname commands to verify the connection.

<img width="340" height="180" alt="image" src="https://github.com/user-attachments/assets/8eff695a-2265-4795-9d69-b81c5085804c" />


5- Used the who command to verify the remote session.

<img width="757" height="237" alt="image" src="https://github.com/user-attachments/assets/dfea44ef-f8c2-46af-a60e-2efda8faceeb" />


6- Used ss -tn to inspect the network connection.

<img width="885" height="122" alt="image" src="https://github.com/user-attachments/assets/3b8727b7-3b9b-4ae1-be77-1901b80ba3ec" />


7- Used the last command to examine the login history

<img width="897" height="292" alt="image" src="https://github.com/user-attachments/assets/dbfb9888-00eb-4be3-b5ac-8c335c23ed3f" />


8- Used the sudo journalctl -u ssh command to examine ssh logs

<img width="912" height="675" alt="image" src="https://github.com/user-attachments/assets/ea7a75c0-c0ac-4346-93d1-7b248d717397" />

9- Generated a controlled failed login using a non existent user trying to connect to the ubuntu vm

<img width="917" height="305" alt="image" src="https://github.com/user-attachments/assets/91362884-660d-4095-a51d-4ade591d3db1" />

then went back to ubuntu vm and used the command sudo journalctl -u ssh and found the failed login attempts

<img width="417" height="92" alt="image" src="https://github.com/user-attachments/assets/e8afb454-2556-4fc8-ae72-4928e9baf0a2" />

and compared it to the succesful connection from the real user.

<img width="427" height="106" alt="image" src="https://github.com/user-attachments/assets/7ef9733e-b7ea-4237-92a8-72478d916808" />

10 - created a public/private key connection using the ssh-keygen command

<img width="916" height="122" alt="image" src="https://github.com/user-attachments/assets/e4f3cb8d-0548-4df3-ab4d-f5b61cdad30b" />

## lessons learned

Learned how to establish a SSH tunnel from the windows host machin to the ubuntu VM using the ssh service inside ubuntu vm using the ssh user@host command, also to check if ssh is running and listening using systemctl status ssh and sudo ss -tulpn | grep :22 commands, who is currently connected using who commands, how to view list of last logins using last command, what ssh journal shows using sudo journalctl -u ssh command, and how to create a public/private key connection using the ssh-keygen command.


## SOC relevance 

SSH is particularly important for SOC analysts because it's a legitimate administrative tool that attackers can also abuse.

you can investigate: brute force attacks, password spraying ,compromised credentials and unexpected sources
