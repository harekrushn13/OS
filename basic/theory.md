#  Operating System
- An Operating System (OS) is a system software that manages computer hardware, software resources, and provides common services for computer programs.
- It acts as an interface between the user and the computer hardware.    

## Types of OS
- Batch OS
- Time-Sharing OS (Multitasking)
- Distributed OS
- Real-Time OS

## OSI Layer 
1. Physical layer
    - Deals with the physical transmission of data (e.g., cables, switches, and electrical signals). 
    - The OS manages drivers and hardware interfaces for network adapters (NICs) and ensures hardware resources are used efficiently.

1. Data-link Layer
    - Responsible for reliable data transfer between devices on the same local network. Includes MAC addressing and error detection.
    - The OS configures and manages the MAC address of the device's NIC and deals with ARP (Address Resolution Protocol).

1. Network layer
    - Handles routing and addressing (e.g., IP addresses) to ensure data reaches the correct destination.
    - The OS configures IP addresses, handles routing tables, and manages protocols like IPv4 and IPv6.

1. Transport layer
    - Ensures reliable data transfer (TCP) or fast delivery (UDP). Manages ports and connections.
    - The OS opens and manages ports for applications using protocols like TCP and UDP.

1. Session layer
    - Manages sessions between applications, handling setup, maintenance, and termination of connections.
    - The OS provides APIs and libraries (e.g., sockets) for session handling.

1. Presentation layer
    - Deals with data translation, encryption, and compression.
    - The OS supports libraries and APIs for encryption (e.g., OpenSSL), data encoding, and compression.

1. Application layer
    - Interfaces directly with end-user applications and handles protocols like HTTP, FTP, and DNS.
    - The OS enables applications to access network services like browsing and file sharing.

## Physical Memory
- Physical memory refers to the actual hardware-based memory resources available on a computer, typically implemented in the form of RAM (Random Access Memory) chips.
- It is the primary storage used by the system to run programs and hold data that is actively being processed.
- Operating systems manage this memory to ensure efficient and secure access to it by both hardware and software.

## Memory Hierarchy
- Registers: Small, extremely fast memory located inside the CPU.
- Cache Memory: Smaller, faster memory located closer to the CPU.
- Main Memory (RAM): Larger but slower than cache memory, typically where the operating system and running programs reside.
- Secondary Storage: Disk storage (HDD/SSD), slower than RAM, used for long-term storage.