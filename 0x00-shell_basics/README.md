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
- As an alternative to running this command on a terminal, you can also run the same command on your browser and it should lead to a page with the same information

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
### 3-listfiles
- Task: Display current directory contents in a long format
- From the task description, this will use the command in task 1-listit but it won't be the same
- Notice they want it in long format. To do this, check out the man page of the command and you'll realize why the answer is this
```
ls -l
```

### 4-listmorefiles 
- Task: Display current directory contents, including hidden files (starting with .). Use the long format
- Like the task above, this also uses the ls command but check the man page of ls to understand why the command is like so
```
ls -la
```

### 5-listfilesdigitonly
- Task: Display current directory contents with:
	- Long format
	- with user and group IDs displayed numerically
	- And hidden files (starting with .)
- This again uses the ls command but make use of the man page to understand whu I chose this as my answer
```
ls -lna
```

### 6-firstdirectory
- Task: Create a script that creates a directory named my_first_directory in the /tmp/ directory.
- Here, the command I chose was the mkdir command. Check out the man page of that commad to understand why I chose this
```
mkdir /tmp/my_first_directory
```

### 7-movethatfile
- Task: Move the file betty from /tmp/ to /tmp/my_first_directory.
- Here the command I chose was the mv command. Use the man page to understand its use cases
```
mv /tmp/betty /tmp/my_first_directory
```

### 8-firstdelete
- Task: Delete the file betty.
	- The file betty is in /tmp/my_first_directory
- Here I chose to use the rm command. Check the man page for that to understand its use case
```
rm /tmp/my_first_directory/betty
```

### 9-firstdirdeletion
- Task: Delete the directory my_first_directory that is in the /tmp directory.
- Here I opted to use the rmdir command. CHeck its man page to understand it
```
rmdir /tmp/my_first_directory
```

### 10-back
- Task: Write a script that changes the working directory to the previous one.
- Here, the command used was cd but as to why I used it like so, check on the man page. I actually didn't know this until when I checked
```
cd -
```

### 11-lists
- Task: Write a script that lists all files (even ones with names beginning with a period character, which are normally hidden) in the current directory and the parent of the working directory and the /boot directory (in this order), in long format.
- This uses concepts from the cd command as well as the ls command so make sure to understand both commands
```
# The slashes that indicate a path can be ommitted in this case i.e I'd have written the command as
ls -Ula ./ ../ /boot
# But instead, I'll write it as
ls -Ula . .. /boot
```
