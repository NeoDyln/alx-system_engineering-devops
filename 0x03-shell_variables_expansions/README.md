# About #
This directory will list all existing commands as present here and what each does

## Mandatory tasks start ##

### 0: 0-alias ###
- Here I created a shortcut function using the alias command to the remove all (rm *) and named it [ls].
- Syntax is alias name_desired="Command_wanted"

### 1: 1-hello_you ###
- Here I echoed out the text hello followed by the variable holder for the current user which is $USER
- Syntax is : echo 'hello $USER'

### 2: 2-path ##
- Here we needed to change the env PATH such that it finishes by looking through /action. I did this via the export command since $PATH cannot be edited normally
- Syntax is : export VARNAME_WITHOUT_DOLLAR=$PATH(Existing_Path):DIrectory_being_appended_at_end

### 3: 3-paths ###
- Here I first listed the values of $PATH then replaced : with \n to add line breaks then counted the number of resulting lines of directories
- Syntax : echo $PATH | tr ':' '\n' | wc -l

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

### 10 10-love_exponent_breath ###
- Here I used the $(($x**$y)) to symboize exponention as below
- Syntax: echo $(($BREATH**$LOVE))

### 11: 11-binary_to_decimal ###
- Here I used the binary to decimal convertor in linux as below
- Syntax: echo $((2#binary_value))

### 12: 12-expansions ###
- Here I used the brace expansion such that I was able to recursively output 2 random alpha lowecase characters. I excluded oo by using the grep -v function and filally, replaced spaces using tr function
- Syntax : echo {a..z}{a..z} | tr ' ' '\n' | grep -v oo

### 13: 13-print_float ###
- Here I used the printf function as well as the decimal to float converter to change into a float value
- Syntax: printf '%.2f\n' $variable_to_be_converted

## Advanced Tasks ##

### 14: 100-decimal_to_hexadecimal ###
- Here we use the printf function again together with the hexadecimal converter as below
- Syntax : printf '%x\n'$variable_to_convert