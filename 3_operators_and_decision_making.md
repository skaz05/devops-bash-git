# Operators

We'll go through basic arithmetic and logic operators on different variable types.
Bourne shell didn't originally have any mechanism to perform simple arithmetic operations, but it uses external programs, either **awk** or **expr**. We'll use expr.

```bash
#!/bin/bash
val=`expr 1 + 1`
# note the spacing, `expr 1+1` does not work (it returns 1+1)
# `expr 1 +1` and `expr 1+ 1` don't work either
echo "Sum : $val"
# 2
```

## Arithmetic operators

| Operator | Description                                                                     | 
|----------|---------------------------------------------------------------------------------|
| +        | Addition: `expr $x + $y` will give the sum of x and y.                          |
| -        | Subtraction: `expr $x - $y` will subtract y from x.                             |
| *        | Multiplication: `expr $x * $y` will give the produce of x and y.                |
| /        | Division: `expr $x / $y` will give the quotient of x divided by y.              |
| %        | Modulus: `expr $x % $y` will give the reminder of x divided by y.               |
| ==       | Equality: [ $x == $y ] will return true is x equals y, false otherwise.         |
| =        | Assignment: x = $y x takes the value of y.                                      |
| !=       | Negated Equality: [ $x != $y ] will return false is x equals y, true otherwise. |

## Relational operators

| Operator  | Description                                                                                      | 
|-----------|--------------------------------------------------------------------------------------------------|
| -eq       | Equals: [ $x -eq $y ] Same as [ $x == $y ]                                                       |
| -ne       | Not Equals [ $x -ne $y ] Same as [ $x != $y ]                                                    |
| -gt       | Greater than: [ $x -gt $y ] true if x holds a greater value than y.                              |
| -lt       | Lower than: [ $x -lt $y ] true if x holds a lower value than y.                                  |
| -ge       | Greater than or equal to: [ $x -ge $y ] true if x holds a greater value than y or if x equals y. |
| -le       | Lower than or equal to: [ $x -le $y ] true if x holds a lower value than y or if x equals y.     |                   


## Boolean operators

| Operator | Description                                                | 
|----------|------------------------------------------------------------|
| !        | Logical NOT [ ! false ] is true.                           |
| -o       | Logical OR [ $x -o $y ] is true if either x or y is true.  |
| -a       | Logical AND [ $x -a $y ] is true if either x or y is true. |

## Decision-making (if, case)

We use some of the above operators for decision-making. The syntax for **if** and **case** statements is illustrated bellow.
```text
if [ expression ] 
then 
   Statement(s) to be executed if expression is true 
fi
```
```text

if [ expression ]
then
   Statement(s) to be executed if expression is true
else
   Statement(s) to be executed if expression is not true
fi
```
```text
if [ expression 1 ]
then
   Statement(s) to be executed if expression 1 is true
elif [ expression 2 ]
then
   Statement(s) to be executed if expression 2 is true
elif [ expression 3 ]
then
   Statement(s) to be executed if expression 3 is true
else
   Statement(s) to be executed if no expression is true
fi
```
```text
case constant in
   pattern1)
      Statement(s) to be executed if pattern1 matches
      ;;
   pattern2)
      Statement(s) to be executed if pattern2 matches
      ;;
   pattern3)
      Statement(s) to be executed if pattern3 matches
      ;;
   *)
     Default condition to be executed
     ;;
esac
```

Sample script:
```bash
#!/bin/bash

a=10
b=20

# you can use all the relational operators here
if [ $a == $b ]
then
   echo "a is equal to b"
fi

WORD="a"

case "$WORD" in
   "a") echo "a" 
   ;;
   "b") echo "b" 
   ;;
   "c") echo "c" 
   ;;
esac
```

### Practice time