## pgrep command
- The pgrep command in Linux is used to search for processes based on specific criteria (such as process name, user, or other attributes) and return their Process IDs (PIDs).
- It is a convenient and efficient way to find processes without having to use `ps` and `grep` together.

## Syntax
```bash
pgrep [options] pattern
```
## Options
1. **-u**: Filter processes by user (e.g., pgrep -u username).
1. **-f**: Match the full command line (not just the process name).
1. **-l**: List the process name along with the PID. (e.g., pgrep -l go )
1. **-n**: Return the newest (most recently started) process matching the criteria.
1. **-o**: Return the oldest (least recently started) process matching the criteria.
1. **-x**: Match the process name exactly (no partial matches).
1. **-c**: Return the count of matching processes instead of PIDs.
1. **-d**: Specify a delimiter for the output (default is a newline).

## Outputs
```bash
harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ pgrep go
2382
2386
2396

harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ pgrep -f go
2382
2386
2396
3557
3565
3567
3573
3574
...

harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ pgrep -u harekrushn
2330
2331
2336
2338
2342
2344
2361
2366
...

harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ pgrep -l go
2382 gvfs-goa-volume
2386 goa-daemon
2396 goa-identity-se

harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ pgrep -n go
2396

harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ pgrep -o go
2382

harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ pgrep -x go

harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ pgrep -c go
3

harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ pgrep -d "-" go
2382-2386-2396

harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ pgrep -d "," go
2382,2386,2396

harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ ps -p $(pgrep go)
    PID TTY      STAT   TIME COMMAND
   2382 ?        Ssl    0:00 /usr/libexec/gvfs-goa-volume-monitor
   2386 ?        Sl     0:00 /usr/libexec/goa-daemon
   2396 ?        Sl     0:00 /usr/libexec/goa-identity-service

harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ watch -n 1 'pgrep -l go'

```