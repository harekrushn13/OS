## top command
- The  top  program  provides  a dynamic real-time view of a running system.
- It can display system summary information as well as a list of processes or threads currently being managed by the Linux kernel.

```bash
harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ top

top - 21:54:42 up 31 min,  1 user,  load average: 0.68, 0.88, 0.78
Tasks: 343 total,   1 running, 342 sleeping,   0 stopped,   0 zombie
%Cpu(s):  1.5 us,  0.8 sy,  0.0 ni, 97.3 id,  0.3 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :  15616.5 total,   7494.1 free,   3898.9 used,   4223.5 buff/cache
MiB Swap:   2048.0 total,   2048.0 free,      0.0 used.  10541.4 avail Mem 

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND                                                                                                                             
   5243 harekru+  20   0  817840  52476  38572 S   4.3   0.3   0:10.02 gnome-terminal-                                                                                                                     
    473 root     -51   0       0      0      0 S   3.7   0.0   0:52.64 irq/158-elan_i2                                                                                                                     
   1492 clickho+  20   0 9932400 664668 317608 S   3.7   4.2   1:08.26 clickhouse-serv                                                                                                                     
   2395 harekru+  20   0  542512  81796  46228 S   2.7   0.5   0:57.40 Xorg                                                                                                                                
   2530 harekru+  20   0 4687604 272872 105080 S   2.0   1.7   1:18.56 gnome-shell                                                                                                                         
   3440 harekru+  20   0   32.8g 371252 223420 S   0.7   2.3   1:26.19 chrome                                                                                                                              
   3926 harekru+  20   0 1161.7g 227712 137376 S   0.7   1.4   0:38.44 chrome                                                                                                                              
   4962 harekru+  20   0 1157.7g  95432  71440 S   0.7   0.6   0:01.57 code                                                                                                                                
    461 root      20   0       0      0      0 I   0.3   0.0   0:01.43 kworker/u16:5-writeback                                                                                                             
   3550 harekru+  20   0   32.4g 162720 105952 S   0.3   1.0   0:24.60 chrome                                                                                                                              
   4876 harekru+  20   0   32.5g 119828  85132 S   0.3   0.7   0:31.53 code                                                                                                                                
   4934 harekru+  20   0 1157.7g 100636  73648 S   0.3   0.6   0:05.84 code                                                                                                                                
   5844 root       0 -20       0      0      0 I   0.3   0.0   0:01.17 kworker/u17:0-i915_flip                                                                                                             
   5913 harekru+  20   0 1163.2g 118152  92312 S   0.3   0.7   0:01.36 chrome                                                                                                                              
   7404 harekru+  20   0 1161.6g 104164  82228 S   0.3   0.7   0:00.18 chrome                                                                                                                              
      1 root      20   0  168428  11892   8472 S   0.0   0.1   0:01.28 systemd                                                                                                                             
      2 root      20   0       0      0      0 S   0.0   0.0   0:00.00 kthreadd
.
.
.
```
## Summary
1. UPTIME and LOAD Averages
    - program or window name, depending on display mode current time and length of time since last boot total number of users system load avg over the last 1, 5 and 15 minutes

1. TASK and CPU States
    ```
    us, user    : time running un-niced user processes
    sy, system  : time running kernel processes
    ni, nice    : time running niced user processes
    id, idle    : time spent in the kernel idle handler
    wa, IO-wait : time waiting for I/O completion
    hi : time spent servicing hardware interrupts
    si : time spent servicing software interrupts
    st : time stolen from this vm by the hypervisor
    ```

1. MEMORY Usage
    - physical memory, classified as:
        - total, free, used and buff/cache

    - virtual memory, classified as:
        - total, free, used and avail (which is physical memory)

    ```
    KiB = kibibyte
    MiB = mebibyte
    GiB = gibibyte
    TiB = tebibyte
    PiB = pebibyte
    EiB = exbibyte
    ```
1. FIELDS / Columns
    - PID  --  Process Id
    - USER: User name of owner of task.
    - PR  --  Priority
    - NI  --  Nice Value
        - The nice value is used by the system to calculate the current priority of a running process. 
        - A negative nice value means higher priority, whereas a positive nice value means lower priority
    - VIRT  --  Virtual Memory Size (KiB)
    - RES  --  Resident Memory Size (KiB)
        - A subset of the virtual address space (VIRT) representing the non-swapped physical memory a task is currently using.
    - SHR  --  Shared Memory Size (KiB)
        - A subset of resident memory (RES) that may be used by other processes.
    - S  --  Process Status
        ```
        The status of the task which can be one of:
            D = uninterruptible sleep
            I = idle
            R = running
            S = sleeping
            T = stopped by job control signal
            t = stopped by debugger during trace
            Z = zombie
        ```
    - %CPU  --  CPU Usage
    - %MEM  --  Memory Usage (RES)
    - COMMAND: The name of the command that started the process.

## Command-Line Options
- -d delay: Set the delay between updates in seconds (e.g., top -d 2 for a 2-second delay).
- -n iterations: Limit top to a specific number of iterations before exiting (e.g., top -n 5).
- -p PID: Monitor only the specified process ID(s) (e.g., top -p 1234).
- -u username: Show only processes owned by the specified user (e.g., top -u root).
- -b: Run top in batch mode, useful for redirecting output to a file (e.g., top -b > top_output.txt)