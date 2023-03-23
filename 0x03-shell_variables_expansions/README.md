# About
This folder contains shell scripts about shell variables, aliases, expansions, initialization files etc
Quite honestly, this was a little complex for me but I'll try to explain the best way I understood it

## chmodder
This is a shell script I created to help with adding executable permissions to my files that begin with a number

## Shell variables
In shell, there are 2 kinds of variables:
- Global / Environment variables
- Local variables

### Local variables 
These are variables that only remain active within the current login session.
Think of it like accessing an e-shop then placing things in the cart without a log in. If your internet disappears, so does your cart items so you'll have to re-select them in a new session

#### Creating a local variable
To create it, simply use the command
	``` shell
	VARNAME="variable_value"
	```

### Global/ Environment variables
These are variables that will always be accessible to all users of the system as they are global
Think of it like the `pwd` command that if used by anyone, will always produce the expected result regardless of where the user currently is in the system directories. In this sense, it's a global command because anyone can access it and it will produce the expected result
#### Creating global variables
We follow the format of creating local variables but simply add export before the command like so
	``` shell
	export VARNAME="Variable_value"
	```

## Shell aliases
In shell, there are commands like `ls` or `pwd` and so on which do specific things.
There are also long commmands like `git push` which send your files to your github repository.
Sometimes you may even have commands spanning more than one command like `ls -l | grep *.html`, a command that lists all html files
Typing all this everytime can be hectic so shell allows us to create a shortcut command that we can run to carry out these commands and we do so using the `alias` command

### Creating an alias
Alias creations follow the format of
	``` shell
	alias shortcut='command1; command2; ... commandN'; shortcut2='command1; command2; .... commandN'
	```
For example
	``` shell
	# Creating a shortcut for listing html files
	alias lhtml='ls -l | grep *.html'
	```
** Unfortunately though, aliases defined like this will be temporary **

Not to worry though, we can correct this by setting the aliases in the .bashrc files located in the /etc/.bashrc file for system wide uses and in /root/.bashrc for root users

** See the purpose of the .bashrc files in the Shell initialization files section **


## Tasks

### 0-alias
Description: Create a script that creates an alias.
- Name: ls
- Value: rm *

Here are the steps I followed:
- I used the `alias` function to create a shortcut named `ls` with value `rm *`

``` shell
alias ls='rm *'
```

### 1-hello_you
Description: Create a script that prints hello user, where user is the current Linux user.

Here are the steps I followed:
- The current user can be obtained with the `user` command then appended to a "hello " string in an `echo` command using expansions like so

``` shell
echo "hello $(users)"
```

### 2-path
Description: Add /action to the PATH. /action should be the last directory the shell looks into when looking for a program.

Here are the steps I followed:
- PATH is a system reserved variable which means it contains existing data so I need to add it in a way that it won't erase the data in it while also making sure it's a permanent addition using `export`
- PATH is also a colon separated list of paths so whatever I add has to be preceeded with a colon
- Like normal variable addiditons, I'll simply do something like `a = a + 1`
- In the context of shell variables though, I'll simply reset the PATH variable to have the new path plus the original path like so
``` shell
export PATH='$PATH:/action'
```
