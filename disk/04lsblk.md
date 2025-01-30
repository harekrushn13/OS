## lsblk command
- The `lsblk` command displays information about block devices (hard drives, SSDs, USBs, partitions, etc.) in a tree-like format.

## Syntax
```bash
harekrushn@harekrushn-ThinkPad-T14s-Gen-1:~$ lsblk
NAME        MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
loop0         7:0    0     4K  1 loop /snap/bare/5
loop1         7:1    0  55.4M  1 loop /snap/core18/2846
loop2         7:2    0 346.3M  1 loop /snap/gnome-3-38-2004/119
loop3         7:3    0  49.9M  1 loop /snap/snapd/18357
loop4         7:4    0 349.7M  1 loop /snap/gnome-3-38-2004/143
loop5         7:5    0  73.9M  1 loop /snap/core22/1748
loop6         7:6    0  73.9M  1 loop /snap/core22/1722
loop7         7:7    0  44.4M  1 loop /snap/snapd/23545
loop8         7:8    0  12.2M  1 loop /snap/snap-store/1216
loop9         7:9    0  63.7M  1 loop /snap/core20/2434
loop10        7:10   0  63.3M  1 loop /snap/core20/1828
loop11        7:11   0 505.1M  1 loop /snap/gnome-42-2204/176
loop12        7:12   0  91.7M  1 loop /snap/gtk-common-themes/1535
loop13        7:13   0 164.8M  1 loop /snap/gnome-3-28-1804/198
loop14        7:14   0    46M  1 loop /snap/snap-store/638
loop15        7:15   0  64.5M  1 loop /snap/sublime-text/196
loop16        7:16   0     1G  1 loop /snap/intellij-idea-community/570
loop17        7:17   0   1.1G  1 loop /snap/goland/331
loop18        7:18   0     1G  1 loop /snap/intellij-idea-community/566
loop19        7:19   0   1.1G  1 loop /snap/goland/335
loop20        7:20   0  64.5M  1 loop /snap/sublime-text/187
loop21        7:21   0 101.1M  1 loop /snap/teams-for-linux/730
loop22        7:22   0 101.1M  1 loop /snap/teams-for-linux/741
nvme0n1     259:0    0 238.5G  0 disk 
├─nvme0n1p1 259:1    0   512M  0 part /boot/efi
└─nvme0n1p2 259:2    0   238G  0 part /
```

## Summary
Name | Maj:MIN | RM | SIZE | RO | TYPE | MOUNTPOINT
    -  Name = Name of the device
    -  MAJ:MIN = Major and Minor device number
    -  RM = 1 if device is removable 0 if not
    -  RO = Readonly flag
    -  Mountpoint = Directory where device is mounted on

## Options
- `-a`:	Show all devices (including empty ones)
- `-h`:	Human-readable sizes (KB/MB/GB)
- `-f`:	Show file system type, UUID, labels
- `-J`:	JSON output
- `-o`:	Customize output columns
- `-d`:	Show only disk devices (no partitions)