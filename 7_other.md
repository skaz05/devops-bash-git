## && || ;

```bash
cmd1 && cmd2 # execute cmd2 only if cmd1 completed successfully
cmd1 || cmd2 # execute cmd2 only if cmd1 completed with error
cmd1 ; cmd2 # execute cmd2 after cmd1, output of cmd1 doesn't matter
```

### Practice
- experiment with above operators

## .bashrc
We can add to the ~/.bashrc file functions and aliases that we want available for our user in every bash instance.

### Practice
- add a function to the ~/.bashrc file, restart the bash (```exec bash```)
- add a hello world function and make it so that it is called every time bash is started
- add an alias for ```ps -aux``` to the ~/.bashrc file, restart the bash (```exec bash```)

## crontab

For recurrent tasks, linux provides a daemon that can run scripts based on a fixed schedule defined with ```crontab -e```. You will find the syntax in the opened file.

### Practice
- add a new entry in with crontab, make it append the date to a file in ~ every 5 seconds
