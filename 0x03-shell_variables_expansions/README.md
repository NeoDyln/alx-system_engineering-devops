# About #
This directory will list all existing commands as present here and what each does

### 0: 0-alias ###
- Here I created a shortcut function using the alias command to the remove all (rm *) and named it [ls].
- Syntax is alias name_desired="Command_wanted"

### 1: 1-hello_you ###
- Here I echoed out the text hello followed by the variable holder for the current user which is $USER
- Syntax is : echo 'hello $USER'

### 2: 2-path ##
- Here we needed to change the env PATH such that it finishes by looking through /action. I did this via the export command since $PATH cannot be edited normally
- Syntax is : export VARNAME_WITHOUT_DOLLAR=$PATH(Existing_Path):DIrectory_being_appended_at_end

### 3 Pending ###


### 4: 4-global_variables ###
- Here I used printenv to display environment variables
- Syntax: printenv

### 5 : 5-local_variables ###
- Here I used set to print all local variables as well as functions
- Syntax: set

### 6 : 6-create_local_variable ###
- Here I just created a variable as below
- Sytax: var_name=value

### 7 7-create_global_variable ###
- Here I used the export function to create a global variable like below
- Syntax : export Var_name=Value

### 8: 8-true_knowledge ###
- Here I added a variable to an number and echo out the result as below
- Syntax: echo $(($TRUEKNOWLEDGE + 128))

### 9: 9-divide_and_rule ###
- Here I used the $((expression)) command to display the result as below
- Syntax echo $(($POWER / $DIVIDE))
