**Paging | Non-Contiguous Memory Allocation**

1. **Issue with Dynamic Partitioning**
   - External fragmentation is a major drawback.
   - Can be removed using compaction, but at a high overhead cost.
   - Requires a more dynamic and flexible approach for memory allocation.

2. **Concept of Paging**
   - Allows non-contiguous allocation of memory.
   - Example: If memory has two non-contiguous 1KB free holes, a 2KB process cannot be allocated in contiguous allocation.
   - Solution: Divide the process into smaller fixed-size blocks that fit into available memory slots.

3. **Paging Mechanism**
   - A memory-management scheme that enables non-contiguous physical address space allocation.
   - Eliminates external fragmentation and avoids compaction.
   - **Key idea:**
     - Divide **physical memory** into fixed-sized blocks called **Frames**.
     - Divide **logical memory** into fixed-sized blocks called **Pages**.
     - **Page size = Frame size** (determined by the processor architecture, e.g., 4KB pages).
   - **Page Table:**
     - Data structure that stores page-to-frame mapping.
     - Contains the base address of each page in physical memory.
   - CPU-generated logical address is split into:
     - **Page number (p)**: Used as an index in the page table.
     - **Page offset (d)**: Specifies the exact location within a page.
   - Page table is stored in main memory, with its base address saved in the **Process Control Block (PCB)**.
   - **Page Table Base Register (PTBR)** points to the active page table, updated during context-switching.

   ![Image](https://github.com/user-attachments/assets/c5bda3a9-91bd-46c7-bb84-9b4c3a8d795e)

4. **How Paging Avoids External Fragmentation**
   - Non-contiguous page allocation allows memory allocation in available free frames.

5. **Why Paging is Slow & How to Improve Performance**
   - High memory reference overhead due to multiple lookups (logical-to-physical address translation).

6. **Translation Look-aside Buffer (TLB)**
   - A high-speed hardware cache that speeds up address translation.
   - Stores key-value pairs of page table mappings.
   - **Page table stored in main memory → Slow translation**
   - **TLB Optimization:**
     - Upon first access, the physical address is stored in the TLB.
     - Subsequent accesses retrieve data directly from TLB, bypassing page table lookup.
   - **TLB Hit:** Requested page is found in the TLB.
   - **Address Space Identifier (ASID):**
     - Uniquely identifies processes in TLB.
     - Ensures correct address mapping for multiple processes.
     - If ASID mismatch occurs, a TLB miss is triggered.
    
    ![Image](https://github.com/user-attachments/assets/00d21b44-bfdb-40df-98f4-d618e5d6c40f)