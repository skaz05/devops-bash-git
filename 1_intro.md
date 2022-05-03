# /bin/bash
Users can interact with Bash through the command line, and write scripts to automate tasks.
```bash
$ which bash
/usr/bin/bash            # or /bin/bash
```
Create new script file with nano:
```bash
$ nano hello_world.sh
```
Sample hello world script:
```bash
#!/bin/bash
echo "Hello World"
```
Make the script executable:
```bash
$ chmod +x hello_world.sh
```
Run the script:
```bash
$ ./hello_world.sh
Hello World
```