# Understanding the Linux File System

If you’re starting with Linux, one of the most important things to understand is the Linux file system.  
Linux uses a unique structure to organize files and directories, and understanding it makes working with Linux much easier.

One of the most powerful concepts in Linux is:

> “Everything is treated like a file.”

That includes:
- Documents
- Hard disks
- USB devices
- Processes
- Keyboards
- Network sockets
- Terminals

---

# What is the Linux File System?

The Linux file system is the structure Linux uses to organize and manage files and directories.

Everything starts from a single top-level directory called the **root directory**:

```bash
/
```

This `/` is the starting point of the entire operating system.

---

# Linux File System Structure

```text
/
├── bin
├── boot
├── dev
├── etc
├── home
├── lib
├── media
├── mnt
├── opt
├── proc
├── root
├── run
├── sbin
├── srv
├── sys
├── tmp
├── usr
└── var
```

---

# 1. `/` — Root Directory

This is the top-most directory in Linux.

Everything begins from here.

Examples:

```bash
/home/ajay
/etc/passwd
/var/log
```

---

# 2. `/home` — User Home Directories

This directory stores files for normal users.

Example:

```bash
/home/ajay
/home/user1
```

Contains:
- Documents
- Downloads
- Pictures
- Desktop files
- Project files

---

# 3. `/root` — Root User Home Directory

This is the home directory for the root (administrator) user.

```bash
/root
```

Important:

- `/` → filesystem root
- `/root` → root user’s personal folder

---

# 4. `/bin` — Essential User Commands

Contains basic Linux commands required by all users.

Examples:

```bash
/bin/ls
/bin/cat
/bin/cp
/bin/bash
```

When you type:

```bash
ls
```

Linux actually runs:

```bash
/bin/ls
```

---

# 5. `/sbin` — System Administration Commands

Contains system-level commands mainly used by administrators.

Examples:

```bash
/sbin/reboot
/sbin/fsck
/sbin/ip
```

---

# 6. `/etc` — Configuration Files

One of the most important directories in Linux.

Contains system configuration files.

Examples:

```bash
/etc/passwd
/etc/shadow
/etc/hosts
/etc/ssh/sshd_config
```

Useful commands:

```bash
cat /etc/passwd
cat /etc/hosts
```

---

# 7. `/var` — Variable Data

Stores files that frequently change.

Contains:
- Logs
- Cache
- Mail
- Queues
- Temporary application data

Important directories:

```bash
/var/log
/var/cache
/var/spool
```

Example log files:

```bash
/var/log/syslog
/var/log/auth.log
```

---

# 8. `/tmp` — Temporary Files

Applications store temporary files here.

Example:

```bash
/tmp/test.txt
```

Files inside `/tmp` may be deleted automatically after reboot.

---

# 9. `/dev` — Device Files

Linux treats hardware devices as files.

Examples:

```bash
/dev/sda
/dev/sdb
/dev/null
/dev/tty
```

Examples:

Primary hard disk:

```bash
/dev/sda
```

USB device:

```bash
/dev/sdb
```

Discard output:

```bash
/dev/null
```

Example:

```bash
echo "hello" > /dev/null
```

The output disappears.

---

# 10. `/proc` — Process Information

A virtual filesystem containing process and kernel information.

Examples:

```bash
/proc/cpuinfo
/proc/meminfo
/proc/1
```

Useful commands:

```bash
cat /proc/cpuinfo
cat /proc/meminfo
```

Each running process has its own directory inside `/proc`.

---

# 11. `/sys` — System and Kernel Information

Provides information about hardware devices and the Linux kernel.

Examples:

```bash
/sys/class
/sys/kernel
```

---

# 12. `/boot` — Boot Files

Contains files required to boot Linux.

Examples:

```bash
/boot/vmlinuz
/boot/grub
```

Contains:
- Linux kernel
- GRUB bootloader files

---

# 13. `/usr` — User Programs and Applications

Contains installed applications and utilities.

Subdirectories:

```bash
/usr/bin
/usr/sbin
/usr/lib
```

Examples:

```bash
/usr/bin/python
/usr/bin/firefox
```

---

# 14. `/lib` — Shared Libraries

Contains essential libraries needed by programs.

Example:

```bash
/lib/x86_64-linux-gnu
```

Programs inside `/bin` and `/usr/bin` depend on these libraries.

---

# 15. `/media` — Removable Media

Used when USB drives and CDs are automatically mounted.

Example:

```bash
/media/usb
```

---

# 16. `/mnt` — Manual Mounting

Used for manually mounting storage devices.

Example:

```bash
mount /dev/sdb1 /mnt
```

---

# 17. `/opt` — Optional Software

Used for third-party applications.

Examples:

```bash
/opt/google
/opt/zoom
```

---

# 18. `/run` — Runtime Data

Stores temporary runtime information.

Example:

```bash
/run/systemd
```

Contains:
- Process IDs
- Runtime service data

---

# 19. `/srv` — Service Data

Stores data served by services like:
- Web servers
- FTP servers

---

# Important Linux File Types

| Symbol | Type |
|---|---|
| `-` | Regular file |
| `d` | Directory |
| `l` | Symbolic link |
| `c` | Character device |
| `b` | Block device |
| `s` | Socket |
| `p` | Named pipe |

Example:

```bash
ls -l
```

Output:

```text
drwxr-xr-x
```

`d` means directory.

---

# Absolute Path vs Relative Path

## Absolute Path

Starts from `/`

Example:

```bash
/home/ajay/file.txt
```

## Relative Path

Starts from the current directory.

Example:

```bash
Documents/file.txt
```

---

# Inodes in Linux

Linux stores metadata about files using structures called **inodes**.

An inode stores:
- File permissions
- Owner
- Size
- Timestamps
- Disk location

But not the filename itself.

View inode numbers:

```bash
ls -i
```

---

# Mounting in Linux

Linux attaches storage devices to directories.

Example device:

```bash
/dev/sdb1
```

Can be mounted to:

```bash
/mnt/usb
```

After mounting, files become accessible through that directory.

---

# Linux File Permissions

Example:

```text
-rwxr-xr--
```

Breakdown:

| Symbol | Meaning |
|---|---|
| r | Read |
| w | Write |
| x | Execute |

Permission groups:

```text
Owner Group Others
```

Commands:

Change permissions:

```bash
chmod 755 file.sh
```

Change ownership:

```bash
chown user:user file.txt
```

---

# Common Linux File System Commands

| Command | Purpose |
|---|---|
| `pwd` | Show current directory |
| `ls` | List files |
| `cd` | Change directory |
| `mkdir` | Create directory |
| `touch` | Create file |
| `cp` | Copy files |
| `mv` | Move/Rename files |
| `rm` | Delete files |
| `find` | Search files |
| `cat` | View file |
| `less` | Read large files |
| `chmod` | Change permissions |
| `chown` | Change ownership |
| `df -h` | Disk usage |
| `du -sh` | Folder size |

---

# Important Linux Concept

## “Everything is a File”

In Linux:
- Hard disks are files
- USB devices are files
- Processes are files
- Terminals are files
- Network sockets are files

This design makes Linux powerful and flexible.

---

# Quick Memory Table

| Directory | Purpose |
|---|---|
| `/bin` | Basic commands |
| `/boot` | Boot files |
| `/dev` | Devices |
| `/etc` | Configuration files |
| `/home` | User files |
| `/root` | Root user home |
| `/tmp` | Temporary files |
| `/var` | Logs and variable data |
| `/proc` | Process information |
| `/usr` | Applications |
| `/lib` | Libraries |

---

# Conclusion

Knowing where Linux stores configuration, logs, user files, device information, and runtime data makes it easier to navigate a system and investigate its behavior. Directory details can vary across distributions and versions, so treat examples as common conventions rather than universal guarantees.

## Related Cybersecurity Learning Repositories

- [Main GitHub profile](https://github.com/Ajaydevs007)
- [SOC Analyst Journey](https://github.com/Ajaydevs007/soc-analyst-journey) — SOC investigations, Windows telemetry, SIEM, and detection notes
- [VAPT & Hack The Box walkthroughs](https://github.com/Ajaydevs007/VAPT) — authorized offensive-security labs
- [Networking Notes](https://github.com/Ajaydevs007/networking-notes) — protocols, services, and network fundamentals

`Linux` `LinuxFileSystem` `LinuxForBeginners` `LinuxCommands` `OperatingSystems` `OpenSource`
