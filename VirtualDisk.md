
***Mount Virtual Disk***

[TYPE] is the type of RAM disk to use; either tmpfs or ramfs.
[SIZE] is the size to use for the file system. Remember that ramfs does not have a physical limit and is specified as a starting size.
[FSTYPE] is the type of RAM disk to use; either tmpfs, ramfs, ext4, etc.

```bash
mkdir /mnt/ramdisk
mount -t [TYPE] -o size=[SIZE] [FSTYPE] [MOUNTPOINT]
mount -t tmpfs -o size=512m tmpfs /mnt/ramdisk
```

You can add the mount entry into /etc/fstab to make the RAM disk persist over reboots. Remember however, that the data will disappear each time the machine i
s restarted.

```bash
tmpfs       /mnt/ramdisk tmpfs   nodev,nosuid,noexec,nodiratime,size=1024M   0 0
```
