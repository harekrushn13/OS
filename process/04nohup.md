## nohup command
- The `nohup` command in Linux is used to run a command or script in the background, even after you log out of the terminal.
- It prevents the command from being terminated when the session ends by ignoring the SIGHUP (hangup) signal. 
- This is particularly useful for long-running processes that need to continue executing after you disconnect from the system.

## Syntax
```bash
nohup [command] [arguments] &
```
- `command`: The command or script you want to run.
- `arguments`: Optional arguments for the command.
- `&:` Runs the command in the background.

## Summay
- **Ignore SIGHUP**: Prevents the command from being terminated when the terminal session ends.
- **Output Redirection**: By default, nohup redirects output to a file named nohup.out in the current directory (unless specified otherwise).
- **Background Execution**: Use & to run the command in the background.