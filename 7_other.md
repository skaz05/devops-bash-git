## command chaining with && || ;

```bash
cmd1 && cmd2 # execute cmd2 only if cmd1 completed successfully
cmd1 || cmd2 # execute cmd2 only if cmd1 completed with error
cmd1 ; cmd2  # execute cmd2 after cmd1, output of cmd1 doesn't matter
```

### Practice
- experiment with above operators

## crontab

For recurrent tasks, linux provides a daemon that can run scripts based on a fixed schedule defined with ```crontab -e```. You will find the syntax in the opened file.

### Practice
- add a new entry in with crontab, make it append the date to a file in ~ every minute
