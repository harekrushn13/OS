**Virtual Memory, Demand Paging, and Page Faults**

1. **Virtual Memory Overview**
   - Virtual memory allows execution of processes that are not completely in memory.
   - It creates an illusion of a larger main memory by utilizing secondary storage (swap-space).
   - Enables programs to be larger than physical memory.

2. **Advantages of Virtual Memory**
   - Programs are not limited by physical memory size.
   - More programs can run simultaneously, improving CPU utilization and throughput.
   - Users and the system benefit from increased flexibility.

3. **Demand Paging**
   - A technique of virtual memory management where pages least used are stored in secondary memory.
   - A page is loaded into memory only when required, triggering a **page fault**.
   - Uses **Lazy Swapper**, which brings pages into memory only when needed.
   - Pages are managed individually by a **Pager**, unlike a **Swapper** that moves entire processes.

4. **How Demand Paging Works**
   - When swapping in a process, the pager predicts which pages will be needed.
   - Instead of loading the full process, only necessary pages are loaded.
   - Reduces swap time and memory usage.
   - **Valid-Invalid Bit Scheme** is used:
     - `1` indicates the page is in memory and valid.
     - `0` means the page is either invalid or stored in secondary memory.

    ![Image](https://github.com/user-attachments/assets/5e97c287-cf64-495e-b668-b0725d0a9344)
   
5. **Handling a Page Fault**
   - If an invalid page is accessed, a **page fault** occurs.
   - OS checks if the access was valid:
     - If invalid, process throws an exception.
     - If valid, the required page is swapped in.
   - Steps to handle a page fault:
     1. Find a free frame from the free-frame list.
     2. Read the desired page from disk into the allocated frame.
     3. Update the page table to reflect that the page is in memory.
     4. Restart the interrupted instruction.

6. **Pure Demand Paging**
   - In extreme cases, execution starts with no pages in memory.
   - The first instruction triggers a page fault, bringing the required page into memory.
   - Relies on **locality of reference** for efficient performance.

7. **Advantages of Virtual Memory**
   - Increases degree of multiprogramming.
   - Enables large applications to run on limited physical memory.

8. **Disadvantages of Virtual Memory**
   - System may slow down due to frequent swapping.
   - **Thrashing** may occur if excessive paging happens.

