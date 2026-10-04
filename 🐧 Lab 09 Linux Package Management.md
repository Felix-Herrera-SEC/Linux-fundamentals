# Linux Package Management

## Objectives

-Understand Linux packages and repositories.

-Understand the purpose of APT.

-Update the local package index.

-Search for available packages.

-Install software.

-Determine whether software is installed.

-Identify installed package versions.

-List installed packages.

-Upgrade packages.

-Remove software.

-Understand dependencies.

-Recognize why installed and outdated software matters during security investigations.

## Enviroment

Component	Environment

Host OS	Windows

Virtualization	VirtualBox

Guest OS	Ubuntu 24.04 LTS

Shell	Bash

Package manager	APT

## Tools used

-Bash commands: 

apt

sudo apt update

apt search

apt show

apt list --installed

apt list --upgradable

sudo apt install

sudo apt remove

## Steps performed and evidence (screenshots)

1- Used the sudo apt update command to see all packages and all the updated information the system has on them.

<img width="591" height="136" alt="image" src="https://github.com/user-attachments/assets/27825bc5-181b-4aae-bcd9-cdedb3e712c9" />


2- Used the apt search nmap command to see all info on nmap package, then used the apt show nmap commmand to inspect the package before installing.

<img width="647" height="342" alt="image" src="https://github.com/user-attachments/assets/5a6f168e-db88-438d-8eb2-cc304b14a9cd" />

And finally used sudo apt install nmap to install nmap on the computer.

<img width="316" height="102" alt="image" src="https://github.com/user-attachments/assets/2a4cd932-0f09-431e-89e3-149c6526acbb" />


3- Used the which command to verify that nmap exist on the computer and the used the dpkg -l | grep nmap command to verify the package.

<img width="300" height="35" alt="image" src="https://github.com/user-attachments/assets/ed8cd218-34b0-4a2b-b2a8-cea3da455492" />

<img width="767" height="205" alt="image" src="https://github.com/user-attachments/assets/ad89dba0-a11f-43cb-a7bc-2dacf23da6d6" />


4- Used the apt list --installed command to view all packages.

<img width="767" height="471" alt="image" src="https://github.com/user-attachments/assets/8071e825-ce72-471d-a281-32082f2aa38c" />


5- Used the apt list --upgradable command to check for available updates then used the sudo apt upgrade to update all the available packages.

<img width="525" height="212" alt="image" src="https://github.com/user-attachments/assets/56ed23b5-bbc9-496b-8bdd-e97e18a1fa9b" />


6- Used the sudo apt remove nmap command and the sudo apt install nmap command to reinstall it.

<img width="387" height="81" alt="image" src="https://github.com/user-attachments/assets/0e276471-7d81-40c3-8eb9-f822e6109b2e" />





## lessons learned

Learned  what a package is and how its different in windows machines, what the APT is (advanced package tool), learned how ubuntu manages packages using the apt command, learned how to check package data including versions etc, how to intall a package, how to remove a package, how to view all packages in the computer, the difference between update and upgrade, how to check for available upgrades, how to inspect a package, and query installed debian packages using the dpkg command.


## SOC relevance 

you might discover unexpected tools such as network scanners, remote-access utilities, tunneling software, or other applications that don't match the server's expected role.


Software provenance
Understanding repositories also helps you appreciate the difference between software obtained through an organization's approved package sources and software installed through other means.


