## fdisk command
- The `fdisk` command is a **disk partitioning tool** used to create, delete, and manage partitions on a hard disk.

## Syntax
```bash
harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ sudo fdisk -l
Disk /dev/loop0: 4 KiB, 4096 bytes, 8 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes

Disk /dev/nvme0n1: 238.49 GiB, 256060514304 bytes, 500118192 sectors
Disk model: SAMSUNG MZVLB256HBHQ-000L7              
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: gpt
Disk identifier: C2E1C3A7-1A1A-49ED-A90D-5B1F45A0AB7E

Device           Start       End   Sectors  Size Type
/dev/nvme0n1p1    2048   1050623   1048576  512M EFI System
/dev/nvme0n1p2 1050624 500117503 499066880  238G Linux filesystem

```
## Summary
Disk | mount point name | size | size in Bytes | Total sectors

---

## Options
- `-p`:	Print partition table
- `-n`:	Create a new partition
- `-d`:	Delete a partition
- `-t`:	Change partition type (e.g., swap, LVM)
- `-w`:	Write changes and exit
- `-q`:	Quit without saving