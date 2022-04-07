# Functions

We can write reusable pieces of code in our scripts. These are called functions.
```text
function_name () { 
   list of commands
}
```
```bash
#!/bin/bash

hello () {
   echo "Hello World"
}

# Invoke your function
hello
```
Functions can take parameters and return values:
```bash
#!/bin/bash

my_func () {
   echo "Hello $1 and $2"
   return 1
}

# Invoke your function
my_func ladies gentleman

# Capture value returned by our function
ret=$?

echo "$ret"
```

### Practice
- how do we pass the first argument of a script as the first argument of a function?
- show all the files/directories of a given directory recursively