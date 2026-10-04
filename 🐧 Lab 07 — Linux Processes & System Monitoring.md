# Linux Processes & System Monitoring

## Objectives

- Understand what a Linux process is.
  
- Understand PID (Process ID) and PPID (Parent Process ID).

- List running processes.
  
- Identify which user owns a process.
  
- Monitor CPU and memory usage.
  
- Search for specific processes.
  
- Understand foreground and background processes.
  
- Start a process in the background.
  
- Terminate processes using their PID.
  
- Understand basic Linux signals such as SIGTERM and SIGKILL.
  
- Recognize potentially suspicious processes during a SOC investigation.

## Enviroment

Host OS	Windows

Virtualization	VirtualBox

Guest OS	Ubuntu 24.04 LTS

Shell	Bash

## Tools used

-Bash commands: 

ps

ps aux

top

pgrep

kill

jobs

bg

fg

## Steps performed and evidence (screenshots)

1- Used the ps command (process status) to check the active processes running on the current terminal session, this allowed me to see the process ID (PID), the terminal, CPU usage time and command which just lets you know the name of the program.

In this case the PID for bash is 10962, the terminal is TTY, the CPU usage is time is 0 and the cmd or pogram name is bash.

<img width="316" height="110" alt="image" src="https://github.com/user-attachments/assets/c3171b43-d4e8-4240-8af9-ddb70df29f6f" />


2- Used the ps aux command to view all the processes running accross the entire operating system. picked 3 processes from the list and identified the: User, PID, CPU usage, memory sage and the command/program name.

<img width="735" height="50" alt="image" src="https://github.com/user-attachments/assets/9bf08462-7e7e-4a68-a2e2-3c4aa3638200" />

process 1: user: Root, PID: 10, CPU usage 0.0, memory usage: 0.0, command name [kwoerker/0:0H-kblocked]

Process 2: user: Root, PID: 13, CPU usage 0.0, memory usage: 0.0, command name: [kworker/R-mm_percpu_wq]

Process 3: user: root, PID 13, CPU usage 0.0. memory usage: 0.0, command name: [ksoftirqd/0]


3- Use the ps aux | grep bash command line in the terminal to isolate the bash processes

<img width="735" height="65" alt="image" src="https://github.com/user-attachments/assets/ef6f0786-ce71-46f8-8ea5-5b0114dd86ba" />


4- Used pgrep bash and pgrep -a bash commands to further isolate information about the bash process.


<img width="290" height="100" alt="image" src="https://github.com/user-attachments/assets/90bebee7-2034-43e8-bce1-1ddb1299fb21" />


5- Used the top command to open the real time process monitor, picked out 2 processes and identified their user, PID, CPU usage, memory usage and command.


<img width="667" height="70" alt="image" src="https://github.com/user-attachments/assets/e513b82e-68d8-4148-8491-947bc73d2374" />


Process 1: User: vboxuser, PID: 11242, CPU usage: 1.3$, memory usage: 3.3%, command: ptyxis

Process 2: User: root, PID: 15, CPU usage: 0.3%, memory usage: 0%, command: rcu_preempt

6- created a process in the terminal and a background process using the sleep 300 and sleep 300 & command lines. 


<img width="357" height="125" alt="image" src="https://github.com/user-attachments/assets/5337c05d-a82b-49d9-800c-1afbf4cf9005" />



7- Used the pgrep -a command to view the PID of the process I just created, in this case the id is 11921 and then used the kill command to end the process.

<img width="347" height="110" alt="image" src="https://github.com/user-attachments/assets/76951e11-10fe-468b-a713-e635d7c62479" />


8- used sigterm (-15) to end another process I just created gracefully then created another process and used sigkill (-9) to terminate it

<img width="357" height="182" alt="image" src="https://github.com/user-attachments/assets/af4c6488-7690-4fb0-af07-a46af19b1d87" />

9- created a new process, the used c +z to stop it, vertified used the jobs command, then used the bg command to restart the process, then used the fg command to bring the process from the background and used control C to terminate it.

<img width="365" height="215" alt="image" src="https://github.com/user-attachments/assets/8402ca17-6695-4a32-92bb-cd560a055c20" />

10- Finally used ps aux to open all processes and picked one to identify the following again: PID, user, CPU and memory usage and command, used the pgrep -a psimon to isolate it.

<img width="282" height="57" alt="image" src="https://github.com/user-attachments/assets/c223a204-a097-489d-97f3-71da06646604" />


## lessons learned

Learn how to view background processes using ps command and top command, also identify the PID, user, CPU usage, MEMORY usage and command of a process inside of ps and top, also learned how to create a process in the terminal and a background process as well.

Learned how to end a process with either sigterm (-15) or sigkill (-9) by having their respective PIDS.

Also learn how to move a restart a process using bg command and how to bring it from the foreground to use in the terminal by using fg command and control c to terminate it again.


## SOC relevance

Help me answer the following questions:

What process is running?
        
What is its PID?
        
Which user owns it?
        
What command was executed?
        
How much CPU/memory is it consuming?
        
What process launched it?
        
Is the process expected?
