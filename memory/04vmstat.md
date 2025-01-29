## vmstat command
- The `vmstat` command in Linux is a powerful tool used to report information about system performance, including memory, processes, paging, block I/O, traps, and CPU activity.
- It provides a snapshot of the system's performance and can be used to identify bottlenecks or performance issues.

```bash
harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ vmstat
procs -----------memory---------- ---swap-- -----io---- -system-- ------cpu-----
 r  b   swpd   free   buff  cache   si   so    bi    bo   in   cs us sy id wa st
 1  0      0 8626036 113352 3638872    0    0   189    99  232  541  5  2 93  0  0
```

## Summary
1. Procs:
    - **r**: Number of runnable processes (processes waiting for CPU time).
    - **b**: Number of processes in uninterruptible sleep (usually waiting for I/O).
1. Memory:
    - **swpd**: Amount of virtual memory used (in KB).
    - **free**: Amount of idle memory (in KB).
    - **buff**: Amount of memory used as buffers (in KB).
    - **cache**: Amount of memory used as cache (in KB).
1. Swap:
    - **si**: Amount of memory swapped in from disk (in KB/s).
    - **so**: Amount of memory swapped out to disk (in KB/s).
1. I/O:
    - **bi**: Blocks received from a block device (blocks/s).
    - **bo**: Blocks sent to a block device (blocks/s).
1. System:
    - **in**: Number of interrupts per second.
    - **cs**: Number of context switches per second.
1. CPU:
    - **us**: Percentage of CPU time spent running non-kernel code (user processes).
    - **sy**: Percentage of CPU time spent running kernel code (system processes).
    - **id**: Percentage of CPU time spent idle.
    - **wa**: Percentage of CPU time spent waiting for I/O.
    - **st**: Percentage of CPU time stolen from a virtual machine (relevant in virtualized environments).

## Options
- Interval: Specify the delay between updates in seconds (e.g., vmstat 2 for updates every 2 seconds).
- Count: Specify the number of updates to display before exiting (e.g., vmstat 2 5 for 5 updates every 2 seconds).
- -a: Display active and inactive memory. (e.g., vmstat -a)
- -d: Display disk statistics. (e.g, vmstat -d)
- -p: Display partition-specific statistics. (e.g., vmstat -p /dev/sda1)
- -s: Display a summary of event counters and memory statistics. (e.g.,vmstat -s)
- -w: Wide output mode (better for wider screens). (e.g., vmstat -w)
- -t: Add a timestamp to each report. (e.g, vmstat -t 2 5)

```bash
harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ vmstat -d
disk- ------------reads------------ ------------writes----------- -----IO------
       total merged sectors      ms  total merged sectors      ms    cur    sec
loop0     14      0      34       0      0      0       0       0      0      0
loop1     50      0     730      10      0      0       0       0      0      0
loop2     45      0     698       5      0      0       0       0      0      0
loop3     58      0    2216      35      0      0       0       0      0      0
loop4   2216      0   53824      84      0      0       0       0      0      0
loop5     55      0    2146      11      0      0       0       0      0      0
loop6     43      0     702       6      0      0       0       0      0      0
loop7   2362      0  222416     315      0      0       0       0      0      7
nvme0n1  52510  13992 4613280   10710  55043 113561 4076570   77593      0     63
loop19     65      0    2226      12      0      0       0       0      0      0
loop20    471      0   14684      40      0      0       0       0      0      0
loop12     54      0    2164      12      0      0       0       0      0      0
loop13    227      0    6614      22      0      0       0       0      0      0
loop21     52      0    2164      10      0      0       0       0      0      0
loop10     43      0     696       4      0      0       0       0      0      0
loop22     65      0    2280      13      0      0       0       0      0      0
loop8     65      0    2218      12      0      0       0       0      0      0
loop9     54      0    2168      12      0      0       0       0      0      0
loop15     56      0    2146      10      0      0       0       0      0      0
loop11     50      0     728       5      0      0       0       0      0      0
loop14    625      0   45836      70      0      0       0       0      0      1
loop18    812      0   32014      89      0      0       0       0      0      1
loop16   1807      0   10926      31      0      0       0       0      0      0
loop17     54      0    2146      12      0      0       0       0      0      0
loop23     11      0      28       0      0      0       0       0      0      0
```

### Explanation of the Columns:
- **total**: Total number of reads or writes completed.
- **merged**: Number of merged reads or writes (operations combined for efficiency).
- **sectors**: Total number of sectors read or written (1 sector = 512 bytes).
- **ms**: Total time spent in milliseconds on reads or writes.
- **cur**: Number of current I/O operations in progress.
- **sec**: Time spent in seconds on I/O operations.

### What the "loop" Devices Mean:
- **loop0, loop1, loop2, etc.**: These are virtual devices created by the Linux kernel to allow files to be used as block devices. For example, if you mount an ISO file, it might use a `loop` device.
- The numbers under `reads` and `writes` indicate the I/O activity on these virtual devices. Since `loop` devices are typically used for read-only operations (like mounting ISO files), you'll often see more reads than writes.

### Why Are There So Many `loop` Devices?
- Each `loop` device corresponds to a separate file being used as a block device. If you have multiple ISO files or snapshots mounted, each will use its own `loop` device.
- Some `loop` devices might be used by system processes (e.g., Snap packages on Ubuntu use `loop` devices for their filesystems).