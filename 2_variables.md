# Variables

Variable names can contain only letters (a to z or A to Z), numbers ( 0 to 9) or the underscore character ( _).
By convention, Unix shell variables will have their names in UPPERCASE.
```bash
#!/bin/bash

VAR="var"
echo $VAR 
# name

VAR_2="var 2"
readonly VAR_2
# VAR_2="var 3" will cause an error


VAR_3="var 3"
unset VAR_3
echo $VAR_3 # will print nothing
```

# *Special* Variables

There are some special already defined variables.

| Variable | Description                                                                                                                                                                                                                                              | 
|----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| $n       | These variables correspond to the command line arguments with which a script was invoked. Here n is a positive integer representing the position of an argument ($0 is the actual script name, the first argument is $1, the second argument is $2 etc). |
| $#       | Number of command line arguments.                                                                                                                                                                                                                        |
| $@       | All arguments are double quoted (grouped as one). See below example.                                                                                                                                                                                     |
| $*       | All the arguments are **individually** double quoted. Also see below example.                                                                                                                                                                            |
| $?       | Exit status of last command.                                                                                                                                                                                                                             |
| $$       | The process number of the current shell.                                                                                                                                                                                                                 |                                                                                                                                                                                                     |

```bash
#!/bin/bash

echo "Script Name: $0"
echo "First Argument : $1"
echo "Second Argument : $2"
# etc ...

IFS=";"
# the IFS variable holds a string that is used between words. $* is a list of words and $@ is a single word. We do this override to highlight the difference between them.
echo "Quoted arguments together: $@"
echo "Quoted arguments individually: $*"
IFS=" "

echo "Total Number of Parameters : $#"
```

# Arrays

```bash
#!/bin/bash

ARR[0]="a"
ARR[1]="b"
ARR[2]="c"
ARR[3]="d"
ARR[4]="e"

echo "var at index 0: ${ARR[0]}"
echo "var at index 2: ${ARR[2]}"
echo "var at index 0: ${ARR[0]}"
echo "var at index 1: ${ARR[1]}"

# play around with IFS, see the difference
echo "All*: ${ARR[*]}"
echo "All@ ${ARR[@]}"
```

# Quoting vs double Quoting
```bash
X=variable

echo "$X"            # variable     # The $ works only under double quotes
echo '$X'            # $X

echo "'$X'"          # 'variable'
echo '"$X"'          # "$X"

ARR[0]="a"

echo "${ARR[0]}"      # a     # The $ works only under double quotes for arrays also
echo '${ARR[0]}'      # ${ARR[0]}

echo "`echo abcd`"    # abcd
echo '`echo abcd`'    # `echo abcd`
```