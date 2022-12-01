- A repo bout the shell basics

# Note
- This code assummes you are running the programs on an Ubuntu 20.04 LTS System
- Linux based systems should be able to understand these commands
- If not on Linux, I'd advise to run this on a virtual machine like Vagrant maybe
- Wil include a link to a repo on how to set this up for Vagrant in windows OS

## The SheBang

- This is basically a line that tells the program to run using the contents in said directory
- It has the format of
```
# !#<directory_to_program>

# For example, assume you wanted a program to run using chrome
# If the directory of chrome on your PC is /Programs/chrome.exe, the shebang would be
!#/Programs/chrome.exe
```
- Notice that all files have this shebang inside as the first line in the program

## chmod u+x

- This is a command we are using on each and every program file we create like so

```
chmod u+x filename
```
- While I would like to go into details of what this actually does, the basic idea is that it converts the file into a executable. On widows, this would be a .exe file
- The reason for doing this is to allow the shebang we creaed in the first line to run
- Don't forget to do this

## man

- This is a command that one can use to view helpful descriptions ad possible use cases of a coommand they are unsure of
- For example, the ls command lists the files and directories in the current directorym but it can do more than that
- You can check by using
```
man ls
```

## Tasks
### 0-current_working_directory 
- Task: A script that prints the absolute path name of the current working directory
- This can be done using the pwd command. By default, it prints the path from th root folder hence the absolute path
- If you check the possible ways in which pwd can print a directory from the man page (Check in previous section), you will find that there are 2 possble options.
- One will print the path but without any symbolic links (Shortcuts) while the other will include the shortcuts
- We opted for the one that does not include the shortcuts
```
pwd -P
```

### 1-listit
- Task: Display the contents list of your current directory.
- This file contains the command to display a list of contents of the current working directory and the command is as so
```
ls
```

### 2-bring_me_home
- Task : a script that changes the working directory to the user’s home directory
- This is done by just having the cd command without anything else following it.
- YOu would run this command from the directory in which you want to use as your home directory
```
cd
```
