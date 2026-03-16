# Disk and Storage Management in Linux

---

## Viewing Disk Information

| Command        | Description                                              |
| -------------- | -------------------------------------------------------- |
| `lsblk`        | Display all block devices (disks and partitions)         |
| `fdisk -l`     | List all disk partitions and details                     |
| `df -h`        | Show disk space usage in a human-readable format (GB/MB) |
| `du -sh /path` | Display the total size of a specific directory           |

---

## Formatting a Partition

| Command               | Description                                     |
| --------------------- | ----------------------------------------------- |
| `mkfs.ext4 /dev/sdX1` | Format a partition with the **ext4** filesystem |
| `mkfs.xfs /dev/sdX1`  | Format a partition with the **XFS** filesystem  |

> ⚠️ **Note:** Replace `/dev/sdX1` with your actual partition name (e.g., `/dev/sdb1`).

---

## Mounting and Unmounting Partitions

| Command                | Description                                    |
| ---------------------- | ---------------------------------------------- |
| `mount /dev/sdX1 /mnt` | Mount a partition to a directory (mount point) |
| `umount /mnt`          | Unmount a partition from its mount point       |

---

## Additional Tips

To view mounted file systems:

```bash
mount | column -t
```

To check disk usage of all mounted filesystems:

```bash
df -Th
```

To find large files/directories:

```bash
du -ah / | sort -rh | head -n 10
```

---

## Quick Example

```bash
# 1. List all disks
lsblk

# 2. Format the new partition as ext4
sudo mkfs.ext4 /dev/sdb1

# 3. Create a mount directory
sudo mkdir /mnt/data

# 4. Mount the partition
sudo mount /dev/sdb1 /mnt/data

# 5. Verify mount
df -h

# 6. Unmount when done
sudo umount /mnt/data
```

---

## 📘 Summary

* `lsblk`, `fdisk` → View disk details
* `df`, `du` → Check usage
* `mkfs.*` → Format partitions
* `mount`, `umount` → Manage mounts
