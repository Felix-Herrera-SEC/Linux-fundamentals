# Linux Services & System Management

## Objectives

-Understand what a Linux service is.

-Understand the basic role of systemd.

-Use systemctl to manage services.

-Determine whether a service is running.

-Start and stop services.

-Restart services.

-Enable and disable automatic startup.

-List running services.

-Understand the difference between active/inactive and enabled/disabled.

-Examine basic service information.

-Recognize why unexpected services can be security-relevant.


## Enviroment

Host OS	Windows

Virtualization	VirtualBox

Guest OS	Ubuntu 24.04 LTS

Shell	Bash

Service manager	systemd

## Tools used

Bash commands: 

systemctl

systemctl status


systemctl start

systemctl stop

systemctl restart

systemctl enable

systemctl disable

systemctl is-active

systemctl is-enabled

systemctl list-units

## Steps performed and evidence (screenshots)

1- Learned the difference between a service and process:

Process: an instance of a program running

Service: A background application managed by the operating system that provides some ongoing function.

also learned how Ubuntu manages services using systemmd and systemctl.

2- Used the systemctl list-units --type=service --state=running command to view all the services currently running.

<img width="756" height="295" alt="image" src="https://github.com/user-attachments/assets/8633003e-5b0b-40e4-aa26-329a0c9f4aa5" />

Used the systemctl status ssh command line to isolate the ssh process.

<img width="692" height="127" alt="image" src="https://github.com/user-attachments/assets/37b25381-20e5-4c42-8e70-d5d729b37138" />

Here I could see if this service was loaded and if it was active.

Then I used the systemctl is-active ssh command to verify if it was active, it was not

<img width="356" height="77" alt="image" src="https://github.com/user-attachments/assets/877ed061-cd69-4893-8d19-d54cf5fc88c7" />


3- Used the sudo systemctl stop ssh to terminate the service, verfied it has stop using both the systemctl status ssh and systemctl is-active ssh commands.

<img width="676" height="266" alt="image" src="https://github.com/user-attachments/assets/4787d8fa-abc8-43df-aaf0-741a779902b7" />


4- Used the systemctl start ssh command to activate the service and used the systemctl restart ssh command to restart it and verified using the systemctl status shh command.

<img width="721" height="482" alt="image" src="https://github.com/user-attachments/assets/66bf344d-d935-4287-abd7-98a9ebd8cb4a" />


5- Checked if the ssh process started automatically when the computer boots up using the systemctl is-enabled ssh.

<img width="350" height="75" alt="image" src="https://github.com/user-attachments/assets/0e0359a0-5ef0-4023-b019-05ef40c5c505" />

it said disabled.

6- To enable the service to start automatically when it boots up I used the command systemctl enable ssh and then used systemctl disable to turn it off again

7- <img width="765" height="182" alt="image" src="https://github.com/user-attachments/assets/00cf2259-60e8-42d4-a9a9-947d17a88d65" />

8- checked the status of another service using the systemctl statys cron to see if I was able to identify the following information: 

What is the service? cron.service 

Is it active? Yes

Is it enabled? Yes

What function does it provide? regurlar background progream processing daemon.

<img width="752" height="426" alt="image" src="https://github.com/user-attachments/assets/aa2c6acf-8945-4a27-a44f-b371703f7ab9" />


## lessons learned

Learn what a service is, and the difference between a process and service, also how ubuntu manages services using the systemctl command, learn how to view all current process working using the systemctl list-units --type=service --state=running command, then how to isolate a process using the systemctl status PROCESSname command, also how to start, restart  and stop a service using the systemctl start x, systemctl restart x and systemctl stop x services commands,

how how to view if a service is enabled or disabled to boot up when the computer starts, and how to change the status with the systemctl enable x or systemctl disable x commands and also to see if a service is active or not.


## SOC relevance 


Services are extremely relevant during endpoint investigations because they can provide both legitimate functionality and mechanisms attackers can abuse.
An analyst may investigate:
Unexpected service
A service appears that isn't normally installed on the machine.
Security service stopped
An attacker might attempt to disable logging, monitoring, or security software.
Persistence
An attacker could configure malicious software to start automatically.
