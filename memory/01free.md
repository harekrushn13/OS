## free command
- The `free` command in Linux is the one that facilitates with providing the overview of system memory utilization.
- It displays all the details regarding the RAM usage such as how is the total, what is used, and free memory including buffers and cached data, aiding in real-time monitoring of memory resources.

## Syntax
```bash
free [OPTION]
```
```bash
harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ free
              total        used        free      shared  buff/cache   available
Mem:       15991316     3254912     8949120      588888     3787284    11583300
Swap:       2097148           0     2097148
```

total = used + free + buffer + cache

## Summary 
1. Memory (RAM) Section:
    - total: Total installed memory (RAM).
    - used: Memory currently in use.
    - free: Unused memory.
    - shared: Memory used by tmpfs (temporary file systems).
    - buff/cache: Memory used by buffers and cache (can be freed if needed).
    - available: Estimate of memory available for starting new applications without swapping.
2. Swap Section:
    - total: Total swap space.
    - used: Swap space currently in use.
    - free: Unused swap space.

## Options
|Options	| Description|
|-----------|------------|
|-k, –kilo	| Displays memory usage in kilobytes (default).|
|-m, –mega	| Displays memory usage in megabytes.|
|-g, –giga	| Displays memory usage in gigabytes.|
|–tera	| Displays memory usage in terabytes.|
|-h, –human	|Automatically scales all output columns to the shortest three-digit unit and displays the units (B, K, M, G, T).|
|-c, –count	| Displays the output ‘c’ number of times; works with the -s option.|
|-l, –lohi	| Shows detailed low and high memory statistics.|
|-o, –old	| Disables the display of the buffer-adjusted line.|
|-s, –seconds	| Continuously displays the output after ‘s’ seconds delay. Uses the usleep system call for microsecond resolution delay times.|
|-t, –total	 |Adds an additional line in the output showing column totals.|
|–help	| Displays a help message and exits.|
|-V, –version	 | Displays version information and exits.|

## Output
```bash
harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ free -h
              total        used        free      shared  buff/cache   available
Mem:           15Gi       3.1Gi       8.6Gi       494Mi       3.5Gi        11Gi
Swap:         2.0Gi          0B       2.0Gi
```
```bash
harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ free -w
              total        used        free      shared     buffers       cache   available
Mem:       15991316     3299844     8805872      492196      153740     3731860    11653916
Swap:       2097148           0     2097148
```
```bash
harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ free -l
              total        used        free      shared  buff/cache   available
Mem:       15991316     3979460     7693684      687148     4318172    10788324
Low:       15991316     8297632     7693684
High:             0           0           0
Swap:       2097148           0     2097148
```
```bash
harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ free -s 3 -c 3
              total        used        free      shared  buff/cache   available
Mem:       15991316     4038316     7596876      725084     4356124    10723868
Swap:       2097148           0     2097148

              total        used        free      shared  buff/cache   available
Mem:       15991316     4019468     7636388      704212     4335460    10739876
Swap:       2097148           0     2097148

              total        used        free      shared  buff/cache   available
Mem:       15991316     4008728     7646836      704088     4335752    10750716
Swap:       2097148           0     2097148
```

## What is Swap Memory?
- Swap memory, also known as swap space, is a section of a computer's hard disk or SSD that the operating system (OS) uses to store inactive data from Random Access Memory (RAM). 
- This allows the OS to run even when RAM is full, preventing system slowdowns or crashes.