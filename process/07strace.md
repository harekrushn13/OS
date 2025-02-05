## strace command
- The `strace` command in Linux is a powerful debugging tool used to **trace system calls and signals** made by a process. 
- It allows you to monitor the interactions between a program and the Linux kernel, such as file operations, network communication, memory allocation, and more. This makes it invaluable for diagnosing issues, understanding program behavior, and debugging.

---

### Basic Syntax
```bash
strace [options] [command]
```
- `command`: The program or process to trace.

---

### Common Options
- `-p [PID]`: Attach to a running process with the specified PID.
- `-c`: Count and summarize system calls.
- `-f`: Trace child processes (forked or cloned).
- `-e [expression]`: Filter system calls by name or group (e.g., `-e open` or `-e trace=file`).
- `-o [file]`: Write output to a file instead of the terminal.
- `-s [size]`: Set the maximum string size to display (default is 32 bytes).
- `-t`: Print timestamps for each system call.
- `-T`: Print the time spent in each system call.
- `-v`: Verbose output (show more details).

---

### Common Use Cases and Examples

#### 1. **Trace a Command**
   ```bash
   strace ls
   ```
   This traces the `ls` command and displays all system calls made by it.

---

#### 2. **Attach to a Running Process**
   ```bash
   strace -p 1234
   ```
   This attaches to the process with PID `1234` and traces its system calls.

---

#### 3. **Trace System Calls with Timestamps**
   ```bash
   strace -t ls
   ```
   This adds timestamps to each system call.

---

#### 4. **Trace System Calls with Time Spent**
   ```bash
   strace -T ls
   ```
   This shows the time spent in each system call.

---

#### 5. **Trace Child Processes**
   ```bash
   strace -f ./my_script.sh
   ```
   This traces the parent process and all its child processes.

---

#### 6. **Filter System Calls**
   ```bash
   strace -e open ls
   ```
   This traces only the `open` system call.

   You can also filter by groups:
   ```bash
   strace -e trace=file ls
   ```
   This traces all file-related system calls.

---

#### 7. **Count and Summarize System Calls**
   ```bash
   strace -c ls
   ```
   This counts and summarizes system calls made by the `ls` command.

   **Example Output**:
   ```
   % time     seconds  usecs/call     calls    errors syscall
   ------ ----------- ----------- --------- --------- ----------------
    50.00    0.000123         123         1           open
    30.00    0.000074          74         1           read
    20.00    0.000049          49         1           write
   ------ ----------- ----------- --------- --------- ----------------
   100.00    0.000246                     3           total
   ```

---

#### 8. **Write Output to a File**
   ```bash
   strace -o output.txt ls
   ```
   This writes the trace output to `output.txt`.

---

#### 9. **Increase String Size Limit**
   ```bash
   strace -s 100 ls
   ```
   This increases the maximum string size displayed to 100 bytes.

---