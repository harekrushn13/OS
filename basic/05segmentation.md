**Segmentation | Non-Contiguous Memory Allocation**

1. **Separation of User and Physical Memory**
   - Paging enforces a strict separation of user’s view from actual physical memory.
   - Segmentation provides a memory management technique that aligns with the user’s logical view of memory.

2. **Concept of Segmentation**
   - Logical address space consists of variable-sized segments based on the user's logical memory structure.
   - Each segment is identified by a **segment number** and **offset** (`<segment-number, offset>` or `{s,d}`).
   - A process is divided into meaningful segments rather than fixed-size pages.
   
   ![Image](https://github.com/user-attachments/assets/633f4048-f823-4b69-84f2-297897db63cd)

3. **Comparison with Paging**
   - Paging is more OS-centric, breaking processes into uniform pages, disregarding function boundaries.
   - The OS may place different parts of the same function in different pages, reducing efficiency.
   - Segmentation, on the other hand, groups functionally related parts into the same segment, improving execution efficiency.

4. **Advantages of Segmentation**
   - No internal fragmentation.
   - Each segment is allocated contiguously, ensuring efficient memory utilization.
   - Segment table size is generally smaller than page tables.
   - More efficient execution since related functions are kept together.

5. **Disadvantages of Segmentation**
   - Susceptible to **external fragmentation**.
   - Variable segment sizes make swapping more complex.

6. **Hybrid Approach**
   - Modern system architectures implement both segmentation and paging to combine their advantages.

