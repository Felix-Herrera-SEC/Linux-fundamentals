# Reading & Editing Files

## Objectives

-Reading Files

-Viewing portions of large files

-Editing Files

-Searching file contents

-Redirecting command output into files

## Enviroment

-Ubuntu VM

## Tools used

-Bash commands: 

cat

less

head

tail

nano

grep

echo


## Steps performed

1- Create a practice file

2- Put text into the files

3- Append additional information

4- Edit the file

5- View the beggining of a file

6- View the end of a file

7- Read a file interactively

8- Search the inside of a file


## evidence (screenshots)

1- created practice file called security_notes.txt <img width="767" height="137" alt="image" src="https://github.com/user-attachments/assets/69fd7371-3cc2-45d6-98db-e2295780e4f0" />

2- added a text string inside the created file using the echo command <img width="620" height="192" alt="image" src="https://github.com/user-attachments/assets/8dfa6d36-2547-4d61-8939-665d0d81aa05" />

3- appended extra text information into the file using echo and two >> <img width="657" height="117" alt="image" src="https://github.com/user-attachments/assets/4e4de5f1-763a-431a-b5c0-a19a200bda24" />

4-added an additional line of text using the nano command which lets you edit the file, then pressed Ctrl + O + Enter to save and Ctrl + X to exit the editor 

<img width="426" height="137" alt="image" src="https://github.com/user-attachments/assets/f19b0085-267f-4b0f-8b85-1bade2b529bf" />

5- used the head command to view to view te beggining of the test file 

<img width="427" height="90" alt="image" src="https://github.com/user-attachments/assets/e0e9ec86-1397-49d5-86e7-a077cca781e0" />

6- used the tail command to view the end of the test file 

<img width="442" height="95" alt="image" src="https://github.com/user-attachments/assets/3f70a19d-35b1-4fe1-bb40-7b306277d0bc" />

7- used the less commmand to view the test file interactevely 

<img width="432" height="627" alt="image" src="https://github.com/user-attachments/assets/08db5687-e516-4753-af25-140040de8563" />

8- usedd the grep command to look for the keyword: "Linux" inside the test file 

<img width="497" height="51" alt="image" src="https://github.com/user-attachments/assets/c5f3ab58-e862-44bf-b434-98b383b40e58" />





## lessons learned

Learned how to create, edit, and read files directly in the Linux terminal. Practiced using terminal text editors, appending text to files, and filtering specific information with grep.


## SOC relevance 

These file-analysis skills are directly applicable to SOC operations because analysts frequently inspect system, authentication, application, and security logs. Commands such as cat, tail, and grep can be used to quickly locate relevant events and identify suspicious activity.
