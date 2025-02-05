## netstat commad
- Short for Network Statistic
- Comman line tool that is used to display the current network connections and port activity on your computer
- To see what service may running on your computer or server and which ports are open
- The `netstat` command is a powerful networking tool used to display **network connections**, **routing tables**, **interface statistics**, **masquerade connections**, and **multicast memberships**. 
- It is available on most operating systems, including Linux, macOS, and Windows.

---

## Basic Syntax
```bash
netstat [options]
```

---

## Common Options
- `-a` or `--all`: Show all active connections and listening ports.
- `-t` or `--tcp`: Show TCP connections.
- `-u` or `--udp`: Show UDP connections.
- `-n` or `--numeric`: Display addresses and port numbers in numeric form (no DNS resolution).
- `-l` or `--listening`: Show only listening ports.
- `-p` or `--program`: Show the PID and name of the program to which each socket belongs.
- `-r` or `--route`: Display the kernel routing table.
- `-s` or `--statistics`: Show network statistics for each protocol.
- `-c` or `--continuous`: Continuously display network information (refresh in real-time).
- `-i` or `--interfaces`: Display a table of all network interfaces.

---

## Common Use Cases and Examples

### 1. **Show All Active Connections**
   ```bash
   netstat -a
   ```
   This displays all active connections (both TCP and UDP) and listening ports.

---

### 2. **Show TCP Connections**
   ```bash
   netstat -at
   ```
   This displays only TCP connections.

---

### 3. **Show UDP Connections**
   ```bash
   netstat -au
   ```
   This displays only UDP connections.

---

### 4. **Show Listening Ports**
   ```bash
   netstat -l
   ```
   This displays all ports that are currently listening for incoming connections.

---

### 5. **Show Listening TCP Ports**
   ```bash
   netstat -lt
   ```
   This displays only TCP ports that are listening.

---

### 6. **Show Listening UDP Ports**
   ```bash
   netstat -lu
   ```
   This displays only UDP ports that are listening.

---

### 7. **Show Numeric Addresses and Ports**
   ```bash
   netstat -n
   ```
   This displays addresses and port numbers in numeric form (no DNS or service name resolution).

---

### 8. **Show Program/PID Associated with Connections**
   ```bash
   netstat -p
   ```
   This displays the PID and name of the program to which each socket belongs. Requires root privileges.

---

### 9. **Show Routing Table**
   ```bash
   netstat -r
   ```
   This displays the kernel routing table, similar to the `route` command.

---

### 10. **Show Network Statistics**
   ```bash
   netstat -s
   ```
   This displays statistics for each protocol (e.g., TCP, UDP, ICMP).

---

### 11. **Show Network Interface Information**
   ```bash
   netstat -i
   ```
   This displays a table of all network interfaces and their statistics (e.g., packets sent/received, errors).

---

### 12. **Continuous Output**
   ```bash
   netstat -c
   ```
   This refreshes the output continuously, similar to `top` or `htop`.

---

## Advanced Usage

### 1. **Filter by Specific Protocol**
   ```bash
   netstat -at  # Show only TCP connections
   netstat -au  # Show only UDP connections
   ```

---

### 2. **Filter by Specific State**
   ```bash
   netstat -at | grep ESTABLISHED
   ```
   This shows only established TCP connections.

---

### 3. **Show IPv4 or IPv6 Connections Only**
   ```bash
   netstat -4  # Show IPv4 connections only
   netstat -6  # Show IPv6 connections only
   ```

---

### 4. **Combine Options**
   ```bash
   netstat -tuln
   ```
   This shows:
   - TCP (`-t`) and UDP (`-u`) connections.
   - Listening ports (`-l`).
   - Numeric addresses and ports (`-n`).

---

## Example Output
Here’s an example of `netstat -tuln` output:
```
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State      
tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN     
tcp        0      0 127.0.0.1:631           0.0.0.0:*               LISTEN     
udp        0      0 0.0.0.0:68              0.0.0.0:*                          
udp        0      0 0.0.0.0:123             0.0.0.0:*                          
```
- `Proto`: Protocol (TCP or UDP).
- `Local Address`: The local IP address and port.
- `Foreign Address`: The remote IP address and port.
- `State`: The state of the connection (e.g., `LISTEN`, `ESTABLISHED`).

---