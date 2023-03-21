# About
- A repo about shell redirections, pipelines, standard inputs and outputs and how to escape characters

## The shebang (#!)
- Alot of times you'll find the files begin with this symbols
``` shell
#!/path/path2
```
- The (#!) portion of it refers to a shebang which is essentially a way to tell the terminal that the lines after me are a path to a program that we will use to run the next lines of code

## chmoder
- This was a script I wrote that auto-adds execute permissions to the task files on run. To run it, I pass in the command as "./chmoder"

_ After all, ALL our task files have to be EXECUTABLE

## Outputs, Inputs and Pipelines
### Standard Inputs (<)
- Assuming we would like to have a command pick in input from a file or something like that. We make use of the < symbol like so.
- Say we wanted to have the results of the `ls` function passed into the `less` function. we could do this like so
``` shell
less < ls -l
```
- This way, the results of `ls -l` will be pushed into the less command and the proper output displayed

- Just a note that we can also use it to collect a file's contents as input like so
``` shell
ls -l < file_with_lists.txt
```

### Standard outputs
- Assuming we want to now output our command's results say to a file. We can either set it to write to (Replace everything in the file) or append to (Add on to the contents of the file) using > and >> respectively
- For example:
	- Writing to a file
	``` shell
	ls -l > listing_output.txt
	```
	- Appending to a file
	``` shell
	ls -l >> listing_with_existing_contents_file.txt
	```

### Pipelines and piping commands
- We've seen that we can collect inputs and outputs but what about when we want to perform a series of commands on a file? We can now use pipes (|) to do this.
- For example, say we wanted to list our current path's directories but only the top 10 earliest files. Pipelines help us do this by taking one command's output and passing it to the fillowing command as input arguments like so
``` shell
ls -lt | head
```

- It can keep taking as many commands as we wish as long as there's a valid input and output
` command1 | command2 | command3 | command4 `


## Tasks

### 0-hello_world
- Description
	- Write a script that prints “Hello, World”, followed by a new line to the standard output
- Here I made use of the echo function like so
`echo "Hello, World"`

### 1-confused_smiley
- Description
	- Write a script that displays a confused smiley "(Ôo)'
- Here, I still made use of the echo command but with the addition of the backslash (\)) ...Had to put 2 closing brackets since the backslash escapes whatever follows it
	``` shell
	echo "\"(Ôo)'"
	```

### 2-hellofile
- Description:
	- Display the content of the /etc/passwd file
- Here I made use of the `cat` command like so
	``` shell
	cat /etc/passwd
	```

### 3-twofiles
- Description:
	- Display the content of /etc/passwd and /etc/hosts
- Here I again made use of the cat command but I passed in 2 files like so
	```  shell
	cat /etc/passwd /etc/hosts
	```

### 4-lastlines
- Description
	- Display the last 10 lines of /etc/passwd
- Here, I first displayed the file's contents then from that output, retrieved the last 10 lines by passing it to the tail function using a pipeline like so

	``` shell
	cat /etc/passwd | tail -n 10
	```

### 5-firstlines
- Description
	- Display the first 10 lines of /etc/passwd
- Here I opted to use the cat command and from whatever it outputs, get the first 10 lines
``` shell
cat /etc/passwd | head -n 10
```

### 6-third_line
- Description:
	- Write a script that displays the third line of the file iacta
	- The file iacta will be in the working directory
	- You’re not allowed to use `sed`
	- Note: The output will differ, depending on the content of the file iacta
- Here I opted to follow the below steps
	- Display the whole file
	- Get the first 3 lines
	- Get the last line from the 3 lines above
	``` shell
	cat iacta | head -n 3 | tail -n 1
	```
### 7-file
- Description:
	- Write a shell script that creates a file named exactly [ \*\\'"Best School"\'\\*$\?\*\*\*\*\*:) ] containing the text Best School ending by a new line
- Here I followed the below steps
	- create a file with the name given { \*\\'"Best School"\'\\*$\?\*\*\*\*\*:)  }
	- I did have to escape each special character for each to work
	- echo into that file the words "Best School"

### 8-cwd_state
- Description:
	- Write a script that writes into the file ls_cwd_content the result of the command ls -la. 
	- If the file ls_cwd_content already exists, it should be overwritten. 
	- If the file ls_cwd_content does not exist, create it.

- Here I opted for the below steps:
	- Run the command ls -la
	- Set its results to write into a file called ls_cwd_content

``` shell
ls -la > ls_cwd_content
```

### 9-duplicate_last_line
- Description:
	- Write a script that duplicates the last line of the file iacta
- Here are the steps I followed:
	- I first printed out all of iacta using `cat`
	- I then pulled out the last line using `tail`
	- I then passed that line back into iacta using >>

``` shell
cat iacta | tail -n 1 >> iacta
```

### 10-no_more_js
- Description:
	- Write a script that deletes all the regular files (not the directories) with a .js extension that are present in the current directory and all its subfolders.
- Here are the steps I followed
	- I made use of the `find` command to
		- Find all files of type file
		- That had an extension .js
		- and delete those files

	``` shell
	find -type f -name "*.js" -delete
	```
### 11-directories
- Description:
	- Write a script that counts the number of directories and sub-directories in the current directory.
		- The current and parent directories should not be taken into account
		- Hidden directories should be counted
- Here are the steps I followed
	- I used `ls` to list all the directories and their contents incuding the hidden ones with `-a` and the subdirectories with `-R`
	- I then used `find` to filter from this, directories alone
	- I then used `grep` to find all that began after the current directory ie Those with a /
	- I finally used `wc` to count the number of lines that resulted

``` shell
ls -aR | find -type d | grep / | wc -l
```

### 12-newest_files
- Description:
	- Create a script that displays the 10 newest files in the current directory
		- One file per line
		- Sorted from the newest to the oldest
- Here I opted to do the following:
	- List the files in order of their modification and each having its own line with `ls -tx`
	- pass the output to `head -n 10`

``` shell
ls -t | head -n 10
```

### 13-unique
- Description:
	- Create a script that takes a list of words as input and prints only words that appear exactly once.
		- Input format: One line, one word
		- Output format: One line, one word
		- Words should be sorted
- Here is the steps I followed:
	- I collected the input and auto-sorted it first using `sort -`
	- I then sent its results to `uniq` then obtained the only-occurring-once words

``` shell
sort -d - | uniq -u
```

### 14-findthatword
- Description:
	- Display lines containing the pattern “root” from the file /etc/passwd
- Here is what I did
	- I first displayed the contents of /etc/passwd with `cat`
	- I then used `grep` to find a matching pattern of "root"

``` shell
cat /etc/passwd | grep "root"
```

### 15-countthatword
- Description:
	- Display the number of lines that contain the pattern “bin” in the file /etc/passwd
- Here is what I did
	- I first listed the contents of /etc/passwd with `cat`
	- I then filtered out the "bin" pattern with `grep`
	- I then used `wc` to count the number of lines

``` shell
cat /etc/passwd | grep "bin" | wc -l
```

### 16-whatsnext
- Description:
	- Display lines containing the pattern “root” and 3 lines after them in the file /etc/passwd.
- Here is what I opted to do
	- First I displayed the file's contents with `cat`
	- Then I set the filter to find root and 3 lines after it then output the result
``` shell
cat /etc/passwd | grep "root" -A 3
```


### 17-hidethisword
- Description:
	- Display all the lines in the file /etc/passwd that do not contain the pattern “bin”.
- Here are the steps I followed
	- I first listed the file contents with `cat`
	- I then used `grep` to return non-matching patterns

``` shell
cat /etc/passwd | grep -v "bin"
```

### 18-letteronly
- Description
	- Display all lines of the file /etc/ssh/sshd_config starting with a letter
- Here are the steps I followed
	- I first displayed the contents of the file with `cat`
	- I then used `grep` to find all lines that begin with an alphabet

``` shell
cat /etc/ssh/sshd_config | grep [:alpha:]*
```


