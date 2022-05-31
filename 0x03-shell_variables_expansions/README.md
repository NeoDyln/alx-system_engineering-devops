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

###4: 4-global_variables ###
- Here I used printenv to display environment variables
- Syntax: printenv