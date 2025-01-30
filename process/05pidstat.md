## pidstat command
- The `pidstat` command in Linux is a powerful tool used to monitor the activities of individual tasks (processes) or threads. 
- It is part of the sysstat package and provides detailed statistics about CPU usage, memory, I/O, and more for specific processes. 

## **Basic Syntax**
```bash
pidstat [options] [interval] [count]
```

- **Options**: Specify what type of statistics to display (e.g., CPU, memory, I/O).
- **Interval**: Time delay between each report (in seconds).
- **Count**: Number of reports to generate.

---

## **Common Options**
- `-u`: Report CPU usage (default).
- `-r`: Report memory usage.
- `-d`: Report I/O statistics.
- `-p <PID>`: Monitor a specific process by its PID.
- `-h`: Display all statistics in a human-readable format.
- `-t`: Include thread-level statistics.
- `-w`: Report task switching activity.

---

## **Example Command**
```bash
pidstat -u 2 5
```
- This command will display CPU usage statistics every 2 seconds for a total of 5 reports.

---

## **Output Explanation**
Here’s an example output of `pidstat -u`:

```
Linux 5.4.0-42-generic (hostname) 	09/15/2023 	_x86_64_	(4 CPU)

03:15:01 PM   UID       PID    %usr %system  %guest   %wait    %CPU   CPU  Command
03:15:03 PM  1000      1234    0.50    0.20    0.00    0.10    0.70     1  firefox
03:15:03 PM  1000      5678    1.00    0.50    0.00    0.20    1.50     2  bash
```

### **Columns Explained**
1. **Time**: The timestamp when the statistics were recorded.
2. **UID**: The user ID of the process owner.
3. **PID**: The process ID of the task being monitored.
4. **%usr**: Percentage of CPU time spent in user space (running application code).
5. **%system**: Percentage of CPU time spent in kernel space (system calls).
6. **%guest**: Percentage of CPU time spent running a virtual CPU (for virtualized environments).
7. **%wait**: Percentage of CPU time spent waiting for I/O operations to complete.
8. **%CPU**: Total percentage of CPU usage (sum of `%usr`, `%system`, and `%guest`).
9. **CPU**: The CPU core number where the process is running.
10. **Command**: The name of the command or process.

---

## **Other Examples**

### 1. **Monitor Memory Usage**
```bash
pidstat -r 2 5
```
- Output includes:
  - **minflt/s**: Minor page faults per second (no disk access required).
  - **majflt/s**: Major page faults per second (requires disk access).
  - **VSZ**: Virtual memory size (in KB).
  - **RSS**: Resident set size (physical memory used, in KB).
  - **%MEM**: Percentage of memory used by the process.

### 2. **Monitor I/O Statistics**
```bash
pidstat -d 2 5
```
- Output includes:
  - **kB_rd/s**: Kilobytes read per second.
  - **kB_wr/s**: Kilobytes written per second.
  - **kB_ccwr/s**: Kilobytes canceled due to writeback errors.

### 3. **Monitor a Specific Process**
```bash
pidstat -p 1234 2 5
```
- Monitors the process with PID `1234` for CPU usage.

### 4. **Monitor Thread-Level Statistics**
```bash
pidstat -t -p 1234 2 5
```
- Includes thread-level details for the specified process.

---