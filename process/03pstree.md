## pstree command
- The pstree command in Linux displays running processes in a tree-like format, showing the parent-child relationships between processes. 
- This makes it easier to visualize the hierarchy of processes and understand how they are related.

## Syntax
```bash
pstree
```
- This will show the process hierarchy starting from the root process **(usually systemd or init)**.


## Output
The output of `pstree` shows processes in a tree structure, with child processes indented under their parent processes.

```bash
systemd─┬─accounts-daemon───2*[{accounts-daemon}]
        ├─agetty
        ├─cron
        ├─dbus-daemon
        ├─nginx───2*[nginx]
        ├─sshd───sshd───bash───pstree
        └─systemd───(sd-pam)
```

- **`systemd`**: The root process (or `init` on older systems).
- **`─`**: Indicates a child process.
- **`*`**: Represents multiple instances of a process (e.g., `2*[nginx]` means two `nginx` processes).

## Options
Here are some of the most commonly used options with `pstree`:

1. **`-p`**: Display PIDs along with process names.
1. **`-a`**: Show command-line arguments for processes.
1. **`-h`**: Highlight the current process and its ancestors.
1. **`-n`**: Sort processes by PID instead of by name.sh
1. **`-u`**: Show the username of the process owner.sh
1. **`-G`**: Use VT100 line-drawing characters for a more graphical tree.sh
1. **`-s`**: Show the parent processes of a specific process.sh
1. **`-T`**: Hide threads (show only processes).sh
1. **`-Z`**: Display SELinux security context (if applicable).sh