## About ##
- This file lists the various commands we shall use when performing shel redirections \n

### File 0-hello_world ###
- This file contains a simple command to output the words hello world to the stout. Echo and cat by default use stout to display output

### File 1 - Confused Smiley ###
- This script outpus a smiley face as its output by using the command "\"(Oo)'"
  -- The first backslash is to identify that the parentheses aren't special

### File 2 (2-hellofile)  Display /etc/passwd ###
- This is a script to display the contents of /etc/passwd file using the cat function

### File 3 (3-twofiles) ###
- This file is similar to file 2 but takes two or more files and outputs their contents using Cat

### File 4 (4-lastlines) ###
- This command uses the tail function to output the last 10 lines of the /etc/passwd file

### File 5 (5-firstlines) ###
- This command uses the head function to output the first 10 lines of the /etc/passwd file

### File 6 (6-thirdline) ###
- This command uses both head and tail functions to display a specific line number of text using head -z file | tail +z where z is the line we want to display

### File 7 (Create a file with some text in it) ###
- This command uses the output redirect to add text to a file

### File 8  (8-cwd_state) ###
- This command simply writes to a file called ls_cwd_state the contents of ls -la

### File 9 (9-duplicate_last_line) ###
- This command takes the last line of a specified file and duplicates it then sends it back into the file without overwriting everything else

### File 10 (10-no_more_js) ###
- This command removes all .js files in current and sub directories while making sure not to touch directories themselves

### File 11 (11-Directories) ###
- This command counts the number of current and sub-directories within the current directory

### File 12 (12-newest_files) ###
- This command displays the first 10 newest files in the current directory
