## STDIN, STDOUT, STDERR
Most processes start with these 3 text data streams. They have a source and a destination:
 - you chose the source of **stdin**, the destination is your process
 - you chose the destination of **stdout** and **stderr**, the source is your process
 - these streams can be intentionally closed
 - they are essentially files, with file descriptors 0, 1  and 2

## UNIX Pipe |
From above, we notice we have control over these streams. The simplest change to these streams is to connect them. The output of one process can be the input of another.
- ```ps -aux | grep root```
- here, the output of the ps command is the input of the grep command
- we say they are **piped**, the | character si the UNIX Pipe

## IO Redirects

We can also redirect to/from other files:
```bash
ps -aux > all_processes.txt
grep root < all_processes.txt

ls -a >> all_processes.txt  # >> appends to the end of the file
```
The **>** redirects stdout by default. You can explicitly redirect stdout with **1>** and stderr with **2>**.
```bash
#!/bin/bash

echo "This will fail!"
cat non-existent-file.txt
```

### Practice
- Redirect stdout to a file and stderr to another file.

You can redirect both stdout and stderr to the same file:
```bash
./script.sh > file.txt 2>&1
```
This means that stream 2 (stderr) will be redirected to the same file 1 (stdout) is redirected to.

### Practice
- use 2>&1 with the above script
- play around with redirects
