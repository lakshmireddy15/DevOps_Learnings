

---

## inode

**inode** = Index node  
Stores **metadata** of the file (not content). Includes:

- File size
- File permissions
- Owner
- Group
- Pointers to actual file data blocks

> A **data block** is a chunk of disk space that holds part of your file content.

Each file and directory is assigned a **unique inode number**.

Commands:

```bash
ls -i <filename>      # View the inode number of a file
stat <filename>       # Detailed file info including inode
```

---

## File System

A **file system** is the system used for managing data on storage devices (e.g., hard disk, SSD).

---

## Hard Link

- A **hard link** is like an alias name or second name for an existing file.
- Multiple hard links can point to the same inode (file data).

Example:

```
file.txt <----> link.txt (hard link)
```

- Both point to the same data on disk.
- If `file.txt` is deleted, `link.txt` still accesses the data.
- Disk space is only freed when **all** hard links are deleted.

---
