## dstat command
- The `dstat` command in Linux is a versatile and powerful tool for monitoring system resources in real-time.
- It combines the functionality of several other tools like vmstat, iostat, netstat, and ifstat into a single, easy-to-use interface. dstat provides a comprehensive overview of system performance, including CPU, memory, disk I/O, network activity, and more.

```bash
harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ dstat
You did not select any stats, using -cdngy by default.
--total-cpu-usage-- -dsk/total- -net/total- ---paging-- ---system--
usr sys idl wai stl| read  writ| recv  send|  in   out | int   csw 
  3   1  95   0   0| 386k 1010k|   0     0 |   0     0 |1082  2464 
  0   0  99   0   0|   0     0 |2841B    0 |   0     0 | 468   750 
  1   1  98   0   0|   0     0 |3990B    0 |   0     0 | 678  1172 
  1   0  99   0   0|   0   208k|2640B  282B|   0     0 | 557   969 
  1   0  99   0   0|8192B    0 |2853B    0 |   0     0 | 403   695 
  5   0  95   0   0|   0     0 |1803B    0 |   0     0 | 717  1524 
  2   1  97   1   0|   0   320k|  24k   25k|   0     0 | 738  1613
```

## Summary
1. CPU Usage:
    - **usr**: Percentage of CPU used by user processes.
    - **sys**: Percentage of CPU used by system processes.
    - **idl**: Percentage of CPU idle time.
    - **wai**: Percentage of CPU time spent waiting for I/O.    
    - **hiq**: Percentage of CPU time spent handling hardware interrupts.
    - **siq**: Percentage of CPU time spent handling software interrupts.
1. Disk I/O:
    - **read**: Total disk reads (in bytes per second).
    - **writ**: Total disk writes (in bytes per second).
1. Network Activity:
    - **recv**: Total network data received (in bytes per second).
    - **send**: Total network data sent (in bytes per second).
1. Paging:
    - **in**: Page-ins (pages swapped into memory per second).
    - **out**: Page-outs (pages swapped out of memory per second).
1. System:
    - **int**: Number of interrupts per second.
    - **csw**: Number of context switches per second.

## Options
- **-c**: Display CPU statistics.
- **-d**: Display disk I/O statistics.
- **-n**: Display network statistics.
- **-m**: Display memory usage statistics.
- **-p**: Display process statistics.
- **-s**: Display swap statistics.
- **-y**: Display system statistics (interrupts and context switches).
- **-a**: Display all statistics (equivalent to -cdngy).
- **-t**: Include a timestamp in the output.
- **--output**: Save the output to a CSV file (e.g., dstat --output /tmp/dstat.csv).
- **--top-cpu**: Show the most CPU-intensive processes.
- **--top-mem**: Show the most memory-intensive processes.
- **--top-io**: Show the most I/O-intensive processes.
- **--top-latency**: Show processes with the highest latency.