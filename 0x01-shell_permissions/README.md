# About
- This folder contains codes about Shell permissions and some sample tasks

## Pre-info
- When we use the `ls -l` command, the output below it shows us a number of important information
- Let's assume it outputted the below format
	- ![File details and permissioms](https://github.com/NeoDyln/alx-system_engineering-devops/blob/master/0x01-shell_permissions/file_listing_meanings.png)
- This is what the different sections mean but in our case we're concerned with the permissions section first

## Permissions
![Permissions](https://github.com/NeoDyln/alx-system_engineering-devops/blob/master/0x01-shell_permissions/file_permissions_meanings.png)

- The above shows the meanings behind the file permissions. Please note that if a file is a directory, the rwx usually have different implications

### Changing permissions with `chmod` using octal notations
- To change permissions, we make use of the octal notation formatting ie
	- If a file permission is set to rxw, assume that each non-blank permission represents a positive binary value hence \n rxw would have a notation of 111, r-w would be 101 and so on
	- Now if we convert those binary notations to decimal notations, rxw (111) would be 7, r-w (101) would be 5 and so on
	- Notice that there are 3 possible users (owner, group, everyone else) of the file so we need 3 notations for each user eg (111 111 111 => 777)
- We pass these decimal notations into the `chmod` command together with the file whose permissions we are trying to modify and that's it
``` shell
chmod 777 some_file
# This gives read write and execute permissions ( (rxw) = 7 per user) to all users of that file
```

# Tasks
## Task 1: 0-iam_betty
- Description: Create a script that switches the current user to the user betty.
	- You should use exactly 8 characters for your command (+1 character for the new line so 9 in total) (Use `tail -1 0-iam_betty | wc -c` to test) 
	- You can assume that the user betty will exist when we will run your script

- I had to man some commands to figure it out, and maybe do a bit of googling but this wasthe command I settled on:
	``` shell
	su betty
	# Run `man su` on your linux terminal/ google search it for better understanding
	```
## Task 2: 1-who_am_i
- Description:Write a script that prints the effective username of the current user.
	- I opted to use `whoami`

## Task 3: 2-groups
- Description: Write a script that prints all the groups the current user is part of.
- Here we are asked to print the groups but not just any groups, all that the current user is a part of
- I opted to first get the current user then pass that user into the groups per user function
``` shell
whoami | groups
```

## Task 4: 3-new_owner
- Description: Write a script that changes the owner of the file hello to the user betty
- Here it's making use of the `chown` command but rememberit can only be used with admin priviledges like `sudo`
``` shell
chown user file
```

## Task 5: 4-empty
- Description: Write a script that creates an empty file called hello.
- Here I believe the command to use is the `touch` command

## Task 6: 5-execute
- Description: Write a script that adds execute permission to the owner of the file hello.
	- The file hello will be in the working directory
	- Originally the file had permissions of rwx r-- r--
- Here I opted to use the `chmod 744 file` command so as to add executable permissions to the owner while maintaining permissions for the others


## Task 7: 6-multiple_permissions
- Description: Write a script that adds execute permission to the owner and the group owner, and read permission to other users, to the file hello.
	- The file hello will be in the working directory
	- Assume the current permissions of hello file were set to r-- r-- ---
- I opted to chmod and add the respective permissions while maintaining the existing which resulted in a permission set of 554 hence `chmod 554 hello`

## Task 8: 7-everybody
- Description: Write a script that adds execution permission to the owner, the group owner and the other users, to the file hello
	- hello originally has permissions set to rw- r-- ---
	- The file hello will be in the working directory
	- You are not allowed to use commas for this script
- I again used `chmod` to add the execute permissions while maintaing the original rights

## Task 9: 8-James_Bond (Funnily enough the answer is already here)
- Description: 
	- Write a script that sets the permission to the file hello as follows:
		- Owner: no permission at all (--- therefore 000 therefore 0)
		- Group: no permission at all (--- therefore  000 therefore  0)
		- Other users: all the permissions (rwx therefore 111 therefore 7)
	- The file hello will be in the working directory You are not allowed to use commas for this script

- Here they've more or less told me all the permissions I need to set with the octal notation so that I can `chmod` them. I just need to be sure about which permission goes where and I confirm this from the image I attached above

## Task 10: 9-John_Doe
- Description: Write a script that sets the mode of the file hello to this:
	```
	-rwxr-x-wx 1 julien julien 23 Sep 20 14:25 hello
	```
- The file hello will be in the working directory
- You are not allowed to use commas for this script

- Here I just need to `chmod` hello to have the permissions set above
