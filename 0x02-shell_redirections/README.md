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
`echo "\"(Ôo)'"`

### 2-hellofile
- Description:
	- Display the content of the /etc/passwd file
- Here I made use of the `cat` command like so
` cat /etc/passwd`

### 3-twofiles
- Description:
	- Display the content of /etc/passwd and /etc/hosts
- Here I again made use of the cat command but I passed in 2 files like so
` cat /etc/passwd /etc/hosts`

### 4-lastlines
- Description
	- Display the last 10 lines of /etc/passwd
- Here, I first displayed the file's contents then from that output, retrieved the last 10 lines by passing it to the tail function using a pipeline like so

`cat /etc/passwd | tail -n 10`
