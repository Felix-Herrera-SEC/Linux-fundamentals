# Linux Permissions & ownership

## Objectives

-Read Linux file and directory permissions.

-Understand read (r), write (w), and execute (x) permissions.

-Understand the three permission categories: user/owner, group, and others.

-Use ls -l to inspect permissions and ownership.

-Modify permissions with chmod.

-Understand symbolic and numeric/octal permissions.

-Change file ownership with chown.

-Change group ownership with chgrp.

-Recognize insecure or unusual permissions during a security investigation.

-Understand how permissions affect what a user can access or execute.

## Enviroment

Host OS	Windows

Virtualization	VirtualBox

Guest OS	Ubuntu 24.04 LTS

Shell	Bash

## Tools used

-Bash commnands:

ls -l

chmod

chown

chgrp

id

groups

touch

mkdir

## Steps performed and evidence (screenshots)

1- Used the ls -l command to view to detailed file meta data was able to see the file type (in this case regular) indicated by the - at the start of the string, what the owner of the file was able to do,(in this case read,write but no excetute) represented by rw-, what the members of the group assigned to that file can do (in this case rw-) read, write but no excecute and what everyone else is able to do with the file, in this case only read represented by r--

<img width="542" height="36" alt="image" src="https://github.com/user-attachments/assets/6a0a984a-0e07-46f0-aa1e-a6b68f5b3703" />



2- Created a new directory called Permissions-lab using the mkdir command and switched to the cd command to switch to that directory.

<img width="422" height="37" alt="image" src="https://github.com/user-attachments/assets/75fca895-bb9b-4ec9-a7d0-4b115a917cbe" />


3- Using the touch command created 3 different files withing the directory, 2 .txt files and an .sh file.

<img width="532" height="62" alt="image" src="https://github.com/user-attachments/assets/4147a268-3515-46d0-843b-9af8775c4419" />

4- Used ls -l command to viw the permissions on the files inside the directory, was able to identity that the owner and group can read,write but not execute (rw-) and others can only read (r--)

<img width="492" height="95" alt="image" src="https://github.com/user-attachments/assets/efac571f-5839-4fce-97ab-9ffe661ab069" />

5- Gave the user permission to make the .sh file (script.sh) excecutable by using the chmod command chmod u+x script.sh and then used the same command to remove it chmod u-x script.sh.

<img width="447" height="152" alt="image" src="https://github.com/user-attachments/assets/095a7ec1-38e4-4b3a-8db0-666c0a733bd4" />


6- Modified group permissions (specifically for write w) using the chmod command chmod g+w for the .txt file and used chmod g-w to remove it. also learned how to write the changes in permissions depending if its user, group, others or all.

u = user/owner

g = group

o = others

a = all

<img width="515" height="216" alt="image" src="https://github.com/user-attachments/assets/a5e738ff-0a2e-414e-a2bd-a592f7f43583" />


7- Understanding and using numeric permissions:

read = 4

write = 2

Execute = 1

none = 0

practied this using the chmod 755 command on script.sh, which made it so the user can read,write and execute and the group and others to only be able to read and execute.

<img width="517" height="130" alt="image" src="https://github.com/user-attachments/assets/8bdee59d-f1e2-4d7a-a770-04948140be8a" />

8- To practice restrcited permissions I using the touch command created a new file called confidential.txt and using the echo command added a string of text that says "Confidential investigation notes", then using chmod 600 made it so only the owner can read and write on it but groups and others cant read write or execute it.

<img width="532" height="136" alt="image" src="https://github.com/user-attachments/assets/3cc13b3a-5d9d-407c-a221-7db61c1702bc" />

9- practice using the chgrp command to change the group of the report.txt file from vboxuser to adm group.

<img width="520" height="185" alt="image" src="https://github.com/user-attachments/assets/84d596df-3b68-45aa-af37-ca29f1c23fea" />

10 - did the same with chown


## lessons learned

Learned how to read a linux file and directory permissions, what the rwx mean when reasin the persmissions using the ls -l command as well as their numerical equivalents, 4 for read, 2 for write, 1 for execute and 0 for none.

Also learned how to change said permissions using the chmod command for user and groups.

Leanred the chown command to change the owner of a file and the chgrp command to change the group a file is assigned too.

Understood how to investigate a files permissions and who and what can they do with the file.

## SOC relevance 


Allowed me to answer the following questions:

- Who owns a suspicious file?
- Which group owns it?
- Who can read it?
- Who can modify it?
- Who can execute it?
- Are the permissions appropriate?
- Did an attacker modify permissions?
- Is a sensitive file accessible to unauthorized users?
- Was a malicious script made executable?
