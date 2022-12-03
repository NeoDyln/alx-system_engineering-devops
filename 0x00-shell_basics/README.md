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
# The slashes that indicate a path, can be ommitted in this case i.e I'd have written the command as
ls -la ./ ../ /boot
# But instead, I'll write it as
ls -la . .. /boot
```

### 12-file_type
- Task: Write a script that prints the type of the file named iamafile. The file iamafile will be in the /tmp directory when we will run your script.
- There's a command in shell to print the file type of a command called file. Man it to understand
```shell
file /tmp/iamafile
```

### 13-symbolic_link
- Task: Create a symbolic link to /bin/ls, named __ls__. The symbolic link should be created in the current working directory
- Here there's a command called ln that can do this for us. Man it to understand its use cases as well as why I opted for this answer
``` shell
ln -T /bin/ls __ls__

# The ln command created the link but as a program. Instead, I opted to use this alternative answer I found with the cp command
cp -s --symbolic-link /bin/ls __ls__
``` 

### 14-copy_html
- Task: 
	- Create a script that copies all the HTML files from the current working directory to the parent of the working directory, but only copy files that did not exist in the parent of the working directory or were newer than the versions in the parent of the working directory.
	- You can consider that all HTML files have the extension .html
- Here, we seem to be making use of the cp (copy) command but in an advanced way so let's man it first to know how we'll use it
- This was the answer I found from the man pages
``` shell
cp -u --update ./*.html ../
```

### 100-lets_move
- Task:
	- Create a script that moves all files beginning with an uppercase letter to the directory /tmp/u
	- You can assume that the directory /tmp/u will exist when we will run your script
- Here we seem to be making use of the mv command but also in an advancd manner so let's man it to see if we can find out how to use it in this case
- Well we are making use of the mv command but it will not help us select the files we want. Here we have to know the wildcards used in shell. Check out this link (http://www.learningaboutelectronics.com/Articles/Wildcards-in-linux.php) to understand why I close this.

```
mv [[:upper:]]*. /tmp/u 
```

### 101-clean_emacs
- Task: Create a script that deletes all files in the current working directory that end with the character ~.
- Here again, we are being tested on wildcard use in shell and how we can use it with the delete command in shell
```
rm *.~
```

### 102-tree
- Task: 
	- Create a script that creates the directories welcome/, welcome/to/ and welcome/to/school in the current directory.
	- You are only allowed to use two spaces (and lines) in your script, not more.
- This task has a slight simple trick to it. They want us to create 3 directories but with only 2 spaces
- Notice that the 3 directories are all within each other so if I created a folder called AS and I put in a folder called ZX, it would be the same as me creating a directory with the path AS/ZX hence my answer
- The command to create a directory is mkdir
```
mkdir welcome/to/ welcome/to/school
```

### 103-commas
- Task: Write a command that lists all the files and directories of the current directory ->ls  , separated by commas (,) -> m
	- Directory names should end with a slash (/) -> p
	- Files and directories starting with a dot (.) should be listed -> a
	- The listing should be alpha ordered, -> X 
		- except for the directories . and .. which should be listed at the very beginning -> --group-directories-first
	- Only digits and letters are used to sort; Digits should come first
	- You can assume that all the files we will test with will have at least one letter or one digit
	- The listing should end with a new line

- This seems like an advanced use case of the ls command. Notice how I've gone about adding the various options that I think wil achieve this
```
ls -mpaX --group-directories-first
```

