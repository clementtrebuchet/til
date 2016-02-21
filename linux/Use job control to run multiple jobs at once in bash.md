# Use job control to run multiple jobs at once in bash

You can run tasks in the background in bash.

Put an ampersand (`&`) to move a task to the background:

```
$ long_running_command &
```

You can alternatively press Ctrl+Z with an already-running command. This runs the command in the background (called a *job*), and frees up the terminal for other commands. You can type other commands while it’s running.

Use `fg` and `bg` to shuffle jobs between the foreground and background, and use `jobs` to see the current list of background jobs.

([source](https://bash.cyberciti.biz/guide/Putting_jobs_in_background))