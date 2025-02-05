## pmap command
- The `pmap` command in Linux is used to display the **memory map** of a process. 
- It provides detailed information about the memory usage of a specific process, including the size of each memory segment, permissions, and the mapped files or libraries. 
- This is particularly useful for debugging memory-related issues or analyzing the memory footprint of a process.

---

### Basic Syntax
```bash
pmap [options] PID
```
- `PID`: The process ID of the target process.

---

### Common Options
- `-x`: Display extended memory mapping information.
- `-d`: Display the device format (major and minor numbers).
- `-q`: Quiet mode (suppresses some headers and footers).
- `-A`: Limit the output to a specific range of addresses.
- `-p`: Display the full path of mapped files.

---

### Examples

#### 1. **Display Memory Map of a Process**
   ```bash
   pmap 1234
   ```
   This displays the memory map of the process with PID `1234`.

   **Example Output**:
   ```
   1234:   /usr/bin/some_process
   0000555555554000      4K r-x-- some_process
   0000555555755000      4K r---- some_process
   0000555555756000      4K rw--- some_process
   00007ffff7a00000   1024K r-x-- libc-2.31.so
   00007ffff7b00000   1024K r---- libc-2.31.so
   00007ffff7c00000     16K rw--- libc-2.31.so
   ...
   total             123456K
   ```
   - The first column shows the memory address range.
   - The second column shows the size of the memory segment.
   - The third column shows the permissions (`r` = read, `w` = write, `x` = execute, `p` = private, `s` = shared).
   - The fourth column shows the mapped file or library.

---

#### 2. **Display Extended Memory Information**
   ```bash
   pmap -x 1234
   ```
   This provides extended details, including:
   - `Address`: Memory address range.
   - `Kbytes`: Size of the memory segment in kilobytes.
   - `RSS`: Resident Set Size (the portion of memory held in RAM).
   - `Dirty`: The amount of dirty memory (modified but not yet written to disk).
   - `Mode`: Permissions.
   - `Mapping`: The mapped file or library.

   **Example Output**:
   ```
   Address           Kbytes     RSS   Dirty Mode  Mapping
   0000555555554000       4       4       0 r-x-- some_process
   0000555555755000       4       4       4 r---- some_process
   0000555555756000       4       4       4 rw--- some_process
   00007ffff7a00000    1024     512       0 r-x-- libc-2.31.so
   00007ffff7b00000    1024     512     512 r---- libc-2.31.so
   00007ffff7c00000      16      16      16 rw--- libc-2.31.so
   ...
   total             123456   65432    1234
   ```

---

#### 3. **Display Device Information**
   ```bash
   pmap -d 1234
   ```
   This includes the major and minor device numbers for mapped files.

---

#### 4. **Display Full Path of Mapped Files**
   ```bash
   pmap -p 1234
   ```
   This shows the full path of the files or libraries mapped into memory.

---

#### 5. **Quiet Mode**
   ```bash
   pmap -q 1234
   ```
   This suppresses some headers and footers, providing a cleaner output.

---

### Advanced Usage

#### 1. **Analyze Memory Usage of a Process**
   Use `pmap` to identify which parts of a process are consuming the most memory. For example:
   ```bash
   pmap -x 1234 | grep -i heap
   ```
   This filters the output to show only the heap memory usage.

---

#### 2. **Compare Memory Usage Over Time**
   Run `pmap` at different intervals to monitor changes in memory usage:
   ```bash
   pmap -x 1234 > memory_usage_before.txt
   # Perform some operations
   pmap -x 1234 > memory_usage_after.txt
   diff memory_usage_before.txt memory_usage_after.txt
   ```

---

#### 3. **Check for Memory Leaks**
   Use `pmap` to identify unusual memory growth in a process, which could indicate a memory leak.

---

### Example Use Case: Debugging a Memory-Intensive Process
Suppose you have a process with PID `5678` that is consuming a lot of memory. You can use `pmap` to analyze its memory usage:
```bash
pmap -x 5678
```
This will show you:
- Which libraries or files are consuming the most memory.
- Whether there are any large anonymous memory segments (indicating potential memory leaks).

---

### Limitations
- `pmap` only provides a snapshot of the memory usage at the time it is run.
- It does not provide real-time monitoring (use tools like `top` or `htop` for that).

---