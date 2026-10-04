# 🐧 Linux Fundamentals for SOC Analysis

Hands-on Linux security labs focused on developing the command-line,
system administration, investigation, and automation skills used in
Security Operations Center (SOC) environments.

## 🛡️ Skills Demonstrated

- Linux command-line administration using Bash
- Linux filesystem navigation and file/directory management
- Log searching, filtering, and analysis using grep, find, pipes, and text-processing utilities
- User, group, UID/GID, and privilege analysis
- File permission and ownership management using chmod, chown, and chgrp
- Process monitoring and investigation using ps, top, PIDs, signals, and kill
- Service monitoring and troubleshooting using systemctl and journalctl
- Network configuration and connection analysis using ip, ss, ping, dig, and nslookup
- SSH remote administration and authentication activity analysis
- Package management using APT and dpkg
- Bash scripting using variables, conditionals, loops, command substitution, and redirection
- Basic Linux endpoint triage and security investigation
- Development of a Bash-based SOC triage script for automated system information collection

## 🔎 SOC-Relevant Experience

Through these labs, I practiced investigating Linux endpoints by:

- Identifying users, groups, privileges, and login activity
- Examining running processes and system services
- Identifying listening ports and active network connections
- Searching and filtering logs for security-relevant events
- Investigating SSH and authentication activity
- Collecting system, process, network, and user information during endpoint triage
- Automating repetitive triage tasks with Bash

## 🧪 Labs

| Lab | Topic |
|---|---|
| 01 | Terminal Basics & Navigation |
| 02 | Linux Filesystem Navigation |
| 03 | File & Directory Management |
| 04 | Reading, Editing & Searching Files |
| 05 | Users, Groups & Privilege Identification |
| 06 | File Permissions & Ownership |
| 07 | Processes & System Monitoring |
| 08 | Services & System Management |
| 09 | Package Management |
| 10 | Linux Networking |
| 11 | SSH & Remote Access |
| 12 | Bash & SOC Automation |

Each lab contains documentation of the objectives, environment,
commands used, steps performed, SOC relevance, lessons learned,
and screenshots demonstrating hands-on execution.

## 🛠️ Technologies & Tools

- Ubuntu Linux
- Bash
- VirtualBox
- SSH
- systemd / systemctl
- journalctl
- APT / dpkg
- TryHackMe

## 🚨 Featured Project — Linux SOC Triage Script

As the final Linux lab, I developed a Bash-based triage script that
automates the collection of initial endpoint information, including:

- System and hostname information
- Current and logged-in users
- Network configuration
- Routing information
- Listening ports
- Running processes
- Login history
- SSH service information

The project demonstrates how Bash can be used to make initial Linux
security investigations faster, consistent, and repeatable.

## 🎯 Objective

Build practical Linux skills applicable to entry-level SOC and
cybersecurity operations, with an emphasis on endpoint investigation,
log analysis, system administration, networking, and basic automation.
