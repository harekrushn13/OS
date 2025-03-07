## /proc/meminfo
- The /proc/meminfo file in Linux provides detailed information about the system's memory usage.
- It is a virtual file that is dynamically generated by the kernel and contains a wealth of data about memory allocation, usage, and availability.

```bash
harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ cat /proc/meminfo
MemTotal:       15991308 kB
MemFree:         7722360 kB
MemAvailable:   10482848 kB
Buffers:          165124 kB
Cached:          3542284 kB
SwapCached:            0 kB
Active:          1279284 kB
Inactive:        5585948 kB
Active(anon):       2896 kB
Inactive(anon):  3976184 kB
Active(file):    1276388 kB
Inactive(file):  1609764 kB
Unevictable:      721020 kB
Mlocked:          278756 kB
SwapTotal:       2097148 kB
SwapFree:        2097148 kB
Dirty:             14936 kB
Writeback:            12 kB
AnonPages:       3878872 kB
Mapped:          1247728 kB
Shmem:            613416 kB
KReclaimable:     212668 kB
Slab:             387748 kB
SReclaimable:     212668 kB
SUnreclaim:       175080 kB
KernelStack:       36112 kB
PageTables:       138456 kB
NFS_Unstable:          0 kB
Bounce:                0 kB
WritebackTmp:          0 kB
CommitLimit:    10092800 kB
Committed_AS:   47585876 kB
VmallocTotal:   34359738367 kB
VmallocUsed:       67136 kB
VmallocChunk:          0 kB
Percpu:             7232 kB
HardwareCorrupted:     0 kB
AnonHugePages:         0 kB
ShmemHugePages:        0 kB
ShmemPmdMapped:        0 kB
FileHugePages:         0 kB
FilePmdMapped:         0 kB
HugePages_Total:       0
HugePages_Free:        0
HugePages_Rsvd:        0
HugePages_Surp:        0
Hugepagesize:       2048 kB
Hugetlb:               0 kB
DirectMap4k:      444940 kB
DirectMap2M:    10706944 kB
DirectMap1G:     6291456 kB
```
