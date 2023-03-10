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
