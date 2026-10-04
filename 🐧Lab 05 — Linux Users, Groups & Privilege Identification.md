# 🐧Lab 05 — Linux Users, Groups & Privilege Identification.md

## Objectives

-Identiy the current Linux User

-Understand UIDs and GIDs

-Identify a users group memberships

-Understand primary vs supplementary groups 

-Identify currently logged in users 

-Understand the purpose of /etc/passwd and etc/group

-Query specific groups members 

-Recognize how user/group information relates to Linux security and privileges.

## Enviroment

Host OS	Windows

Virtualization	VirtualBox

Linux OS	Ubuntu 24.04 LTS

Shell	Bash

Learning platform	TryHackMe

Primary learning material	Linux Fundamentals Part 2

Practice environment	Your own Ubuntu VM

Documentation	GitHub

## Tools used

-Linux commands (Bash): 

whoami

id

groups

who

w

cat

getent

-Linux Files:

/etc/passwd

/etc/group

## Steps performed and evidence (screenshots)

1- Used the whoami command to identify the current user:

<img width="291" height="47" alt="image" src="https://github.com/user-attachments/assets/ca88c758-cf97-4705-8407-406b36ee778a" />

2- Using the id command I was able to find the UID, GID, Primary group and supplementeary group for this user: 

UID: 1000 (vboxuser) , GID: 1000 (vboxuser), primary group: 1000(vboxuser), supplementary groups: 4(adm) 24(adm), 24(cdrom), 27(sudo), 30(dip), 46(plugdev) 100(users) 111 (lpadmin), 114(lxd), 974(vboxsf)

<img width="772" height="62" alt="image" src="https://github.com/user-attachments/assets/35da58d2-ed54-4ef9-95b7-f3c8f3c7afc5" />


3- Using the groups command I was able to see all available grooups in the system and was able to confirm that this user is part of all the groups.

<img width="502" height="40" alt="image" src="https://github.com/user-attachments/assets/cd3414f5-1bae-4c1e-808b-b79357c58475" />


4- Learn that using the who command does not work in modern desktop emulator enviroments, then used the w command to get information on who is currently logged in and what they currently doing

<img width="772" height="96" alt="image" src="https://github.com/user-attachments/assets/cb4fdbf3-5db5-4c75-8e9e-d8e1212e558a" />


5- opened the /etc/passwd/ file using the cat command to see essential account information this includes human users and system accounts

<img width="420" height="240" alt="image" src="https://github.com/user-attachments/assets/3fceed25-81f5-45f9-9b75-4fd18dd95688" />

Found my current user account and was able to see username, password represented by an x, UID, GIP, user meta data, the home directory for this user and the login shell.

<img width="442" height="26" alt="image" src="https://github.com/user-attachments/assets/2f72577b-8b5d-4138-9d62-0594fce9c688" />


6- Opened the /etc/group/ file using the cat command and was able to view all the groups in the system, their password, their group ID (GID) and the members inside of the group

<img width="352" height="112" alt="image" src="https://github.com/user-attachments/assets/ed2b3e8b-05c5-443d-8593-d7a1fd6b9f9c" />

for example I was able to view that in the group named "cdrom" and was able to see the group ID is 24 and it contained the user "vboxuser"

<img width="182" height="12" alt="image" src="https://github.com/user-attachments/assets/f5fed570-4871-4838-b389-c72b09cc122e" />

7- Used the getent command to query twow specifc groups "sude" and "cdrom" and was able to see the respective information. 

<img width="375" height="77" alt="image" src="https://github.com/user-attachments/assets/a6790842-fac4-43a6-b2ec-45fc0389f254" />


8- used the id and groups command and opened the /etc/passwd and /etc/group files to compare the information.

Noticed ID command give current user information while the /etc/passwd/ file contains information on all users and system accounts and that the groups command shows all groups in the system but does not give you any information on them, for information on groups you have to open the /etc/group file.

<img width="771" height="202" alt="image" src="https://github.com/user-attachments/assets/2bb6700c-3b8f-4b0b-83fa-0684c874cfc9" />



## lessons learned

Learned how to view current user information with ID command, and the groups inside the system using the groups command.

Also how to view all human user and system account information by reading the /etc/passwd/ file.

and lastly how to view all groups and their information using by reading the /etc/group/ file.


## SOC relevance 

User and group information is important during security investigations because account privileges can determine the impact of a compromise.

This becomes particularly important when investigating:

Compromised accounts
Privilege escalation
Unauthorized administrative access
Suspicious account creation
Lateral movement
Persistence
Authentication anomalies
