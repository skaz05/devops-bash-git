# Loops

Loops are powerful scripting tools that enable us to execute sets of commands repeatedly.

The main looping mechanisms are illustrated bellow:

### While
```text
while command
do
   Statement(s) to be executed if command is true
done
```
Example:
```bash
#!/bin/bash

a=0

while [ $a -lt 10 ]    # if this is false, the loop ends
do
   echo $a             # show the current value of a
   a=`expr $a + 1`     # increment the value of a
done
```

### For
```text
for var in word1 word2 ... wordN
do
   Statement(s) to be executed for every word.
done
```
Example:
```bash
#!/bin/bash

for var in 0 1 2 3 4 5 6 7 8 9
do
   echo $var
done

for var in `ls -a ~`
do
   echo $var
done

for var in `cat /etc/group`
do
   echo $var
done
```

## Loop control

There are some mechanisms we can use to alter loop control, such as **break** and **continue** statements.
Below are some examples:

### Break
```bash
#!/bin/bash

a=0

while [ $a -lt 10 ]
do
   echo $a
   if [ $a -eq 5 ]
   then
      break                 # leave the loop when a reaches 5. After break, control jumps to echo "Done" line
   fi
   a=`expr $a + 1`
done

echo "Done"
```
### Continue
```bash
#!/bin/bash

a=0

while [ $a -lt 10 ]
do
   a=`expr $a + 1`
   echo $a

   if [ `expr $a % 2` -eq 0 ]
   then
      echo "Number is even"
      continue                 # the rest of the loop statements are ignored and the loop continues with the first statement
   fi
   echo "Number is odd"
  
done
```