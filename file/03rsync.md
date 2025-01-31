## rsync command
- The rsync command is a powerful tool for copying and synchronizing files and directories between two locations, either locally or over a network.
- It is highly efficient because it only transfers the differences between the source and destination files, reducing the amount of data sent. 
- It also supports compression, encryption (via SSH), and preserving file attributes.

## Syntax
```bash
harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ rsync -avz -e ssh dhyanesh@10.20.40.165:/home/dhyanesh/Desktop/rsync_d /home/harekrushn/Desktop/rsyncDemo
dhyanesh@10.20.40.165's password: 
receiving incremental file list
rsync_d/
rsync_d/A.txt
rsync_d/B.txt
rsync_d/b.txt
rsync_d/c.txt

sent 104 bytes  received 331 bytes  96.67 bytes/sec
total size is 22  speedup is 0.05
```

## Options
- `-a`:	Archive mode (preserves permissions, timestamps, symbolic links, etc.). Equivalent to -rlptgoD.
- `-v`:	Verbose mode (shows detailed output).
- `-z`:	Compress data during transfer.
- `-r`:	Recursively copy directories.
- `-P`:	Combines --progress (shows progress) and --partial (resumes interrupted transfers).
- `-e`:	Specify a remote shell to use (e.g., SSH).
- `--delete`:	Delete files in the destination that are not in the source.
- `-n` or -`-dry-run`:	Perform a trial run without making any changes.
- `-h`:	Human-readable output (e.g., file sizes in KB, MB, etc.).
- `--exclude`:	Exclude files or directories matching a pattern.
- `--include`:	Include files or directories matching a pattern.