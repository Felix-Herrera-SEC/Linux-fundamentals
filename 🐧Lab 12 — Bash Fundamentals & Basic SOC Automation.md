# 🐧 Lab 12 — Bash Fundamentals & Basic SOC Automation

## Objectives

Crete Linux SOC triage script.

Explain what Bash is.

Create and execute .sh scripts.

Understand the shebang (#!/bin/bash).

Create and use variables.

Read user input.

Use echo.

Understand basic conditional statements (if).

Understand basic loops.

Use pipes and output redirection inside scripts.

Use commands you've learned in previous Linux labs inside scripts.

Use grep to automatically filter information.

Make scripts executable using chmod.

Create a basic security/system triage script.

Save investigation results to a file.

Understand how scripting can reduce repetitive SOC work.

## Enviroment

Host OS	Windows

Virtualization	VirtualBox

Guest OS	Ubuntu 24.04 LTS

Shell	Bash

Editor	nano

## Tools used

-Bash commands: 

echo

read

if

then

else

fi

for

do

done

echo

read

if

then

else

fi

for

do

done

## Steps performed and evidence (screenshots)

1- Creted a new directory for the bash lab and inside created a a .sh file that I edited using the nano editor to add 2 strings of text 

<img width="365" height="165" alt="image" src="https://github.com/user-attachments/assets/ad21c52d-0ed9-4dd1-b335-afa94470ae6b" />


2- Using the chmod command gave persmission to everyone so they can execute the file and then executed it inside the terminal using the ./hello.sh command

<img width="436" height="175" alt="image" src="https://github.com/user-attachments/assets/cf27092b-d71b-48c6-97d7-044965d2e628" />


3- Creted a new .sh file called variables and added a few variables inside, then gave executable permissions to everyone and ran the script

<img width="332" height="195" alt="image" src="https://github.com/user-attachments/assets/b016bbce-6055-4554-b7d9-88afc9001cc9" />

<img width="512" height="126" alt="image" src="https://github.com/user-attachments/assets/66d43aae-f7fa-4b1b-aedf-262249ce9e6d" />


4- Edited the contents of the variables.sh file to include the following code and then ran it:

current_user=$(whoami)
hostname=$(hostname)

echo "Current User: $current_user"
echo "Hostname: $hostname"

<img width="396" height="140" alt="image" src="https://github.com/user-attachments/assets/cffbb982-6b82-4fe6-ae84-9e705b23de95" />


5- Created a new .sh file "user_inputs.sh" inside I put in the following code that include a read input on it, gave executable permission and ran it.

#!/bin/bash

echo "Enter username to investigate:"
read username

if id "$username" >/dev/null 2>&1
then
    echo "User exists."
else
    echo "User does not exist."
fi

<img width="415" height="160" alt="image" src="https://github.com/user-attachments/assets/85a75433-9617-4bbc-8f30-9f102decac69" />


6- Creted a new script file called real_user.sh to practice if, then and else inside it I use the following code, then gave executable permission to everyone and ran it

#!/bin/bash

echo "Enter username to investigate:"
read username

if id "$username" >/dev/null 2>&1
then
    echo "User exists."
else
    echo "User does not exist."
fi

<img width="397" height="250" alt="image" src="https://github.com/user-attachments/assets/52256e78-55fa-4567-9648-a64d506cd7a1" />


7- To practice for loops I created a new .sh file called loop.sh using nano function I wrote this code, then gave x permission for everyone and executed the file.

#!/bin/bash

for user in root nobody
do
    echo "Checking user: $user"
    id "$user"
done

<img width="475" height="130" alt="image" src="https://github.com/user-attachments/assets/e86644f6-d06a-47b0-8d54-fc24539c020c" />


8- To practice automating process checks I created a new file using nano command called process_check.sh and included the following code, gave x permissions and executed the file.

#!/bin/bash

echo "Enter process name:"
read process

echo "Searching for: $process"

ps aux | grep "$process"

<img width="766" height="250" alt="image" src="https://github.com/user-attachments/assets/7243a44e-10f7-4113-b1e1-0cc943b5d7b3" />

9- to create a network check script I created a new file called network_check.txt using nano I added the following code, gave x permissions and ran the script.

#!/bin/bash

echo "===== NETWORK INFORMATION ====="

echo
echo "IP ADDRESSES:"
ip addr

echo
echo "ROUTING TABLE:"
ip route

echo
echo "LISTENING CONNECTIONS:"
ss -tuln

<img width="741" height="356" alt="image" src="https://github.com/user-attachments/assets/945f06ec-b058-4a5b-a6ce-1af91c914528" />

10 - combined all these commands into a final script called Linux triage.sh, used the following code, gave it permissions and ran it.

#!/bin/bash

echo "================================="
echo "      LINUX SOC TRIAGE REPORT"
echo "================================="
echo

echo "Date:"
date

echo
echo "===== SYSTEM INFORMATION ====="
hostname

echo
echo "===== CURRENT USER ====="
whoami

echo
echo "===== LOGGED-IN USERS ====="
who

echo
echo "===== NETWORK CONFIGURATION ====="
ip addr

echo
echo "===== ROUTING TABLE ====="
ip route

echo
echo "===== LISTENING PORTS ====="
ss -tuln

echo
echo "===== RUNNING PROCESSES ====="
ps aux

echo
echo "===== RECENT LOGINS ====="
last -n 10


<img width="746" height="457" alt="image" src="https://github.com/user-attachments/assets/9ca58a1c-3261-4022-baca-dfbb9ea8792e" />

11- saved the report into a .txt file using the ./Linux_triage.sh > linux_triage.txt command

<img width="682" height="405" alt="image" src="https://github.com/user-attachments/assets/697b68a3-5284-4e8c-9446-cfd88c012cc9" />

12- added timestamps, ssh service and connections and failed ssh authentication attempts.

## lessons learned

Learned that Bash is a command-line shell and scripting language commonly used on Linux, learned how to use shebang so the computer knows to use bash interpreter and wrote some basic script using and combining all the commands Ive learned so far to create a script that summarizes all the information, very cool! 

Learned how to save the report using the > symbol, how to timestamp files so they dont repeat.


## SOC relevance 
I understand basic Bash scripting and can use it to automate repetitive Linux security-triage tasks.
