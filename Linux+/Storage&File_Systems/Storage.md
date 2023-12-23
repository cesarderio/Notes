# Storage and File Systems

<br/>

## Linux Storage Concepts

<br/>

### Mass Storage Devices

In Linux, mass storage devices are referenced under the `/dev` directory. Examples include:

- `/dev/sda`
- `/dev/sdb`

Partitions on these devices start numbering at 1, for example:
- `/dev/sda1`
- `/dev/sdb1`

<br/>

### Disk Initialization Types

- **MBR (Master Boot Record):** Supports a maximum partition size of 2TB and a maximum of 4 partitions.
- **GPT (GUID Partition Table):** Offers no practical limits on disk size or the number of partitions.

**Note:** For software RAID (Redundant Array of Independent Disks), use `fdisk` to set the partition type to Linux RAID autodetect (Press 't', then 'fd').

<br/>

### Common Linux File System Types

- `ext2`, `ext3`, `ext4`: Extended file systems.
- `XFS`: A high-performance 64-bit journaling file system.
- `Reiser4`: Known for its efficiency with small files and metadata-intensive operations.

<br/>

### Linux Storage Management Tools

- `lsblk`: Lists block devices.
  - `lsblk --scsi`: Lists SCSI devices and shows how they are utilized.
- `fdisk`: Used for disk partitioning.
- `mkfs`: Creates a file system.
  - `mkfs.reiser4`: Specific for creating a Reiser4 file system.
- `mount`: Mounts a file system at a specified directory (mount point).

<br/>
<br/>

## The Linux File System Hierarchy

<br/>

### Filesystem Hierarchy Standard (FHS)

The FHS defines the standard directory structure for UNIX and Linux operating systems. While some Linux distributions may have slight variations, they generally follow this structure.

<br/>

#### Directory & Description

- `/`: Root filesystem; the base of the file system hierarchy. All files and directories from various storage devices are accessible here.
- `/bin/`: Contains essential binary command files such as `passwd`, `cat`, `grep`.
- `/boot/`: Holds boot loader files, typically for GRUB (GRand Unified Bootloader).
- `/dev/`: Device files, including those for hardware and special files like random number generators.
- `/etc/`: System-wide configuration files.
- `/home/`: User home directories, including the home directory of the root user.
- `/lib/`: Library files supporting system commands and services.
- `/media/`: Mount point for removable storage media.
- `/mnt/`: Temporary mount points for mounting file systems.
- `/var/`: Variable data files such as logs, spools, and temporary e-mail files.
- `/opt/`: Optional application software packages.
- `/sbin/`: Essential system binaries, e.g., `fdisk`, `useradd`, `mkfs`.
- `/srv/`: Service data such as data for FTP, HTTP servers.
- `/tmp/`: Temporary files, often cleared on reboot.
- `/usr/`: Secondary hierarchy for read-only user data; contains the majority of (multi-)user utilities and applications.
- `/proc/`: Virtual filesystem providing process and kernel information as files.

<br/>

#### FAQ

1. **Why are there `/media` and `/mnt` directories?**
   - `/media`: This directory is typically used for mounting removable media like CDs, DVDs, and USB drives. It's meant for temporary media attached to the system.
   - `/mnt`: Historically used as a temporary mount point for mounting file systems, such as network file systems or additional hard drives. It's more of a generic mount point.

2. **What's the difference between `/bin` and `/sbin`?**
   - `/bin`: Contains essential command binaries that need to be available for all users. These commands are used frequently and are necessary for the system to function properly.
   - `/sbin`: Contains system administration binaries. These are essential for booting, restoring, recovering, and/or repairing the system in addition to the commands in `/bin`.

3. **How do `/opt` differ from `/bin` and `/sbin`?**
   - `/opt`: This directory is reserved for the installation of add-on application software packages. It's a place for software that's not part of the default installation.
   - `/bin` and `/sbin`: These directories are for essential user and system binaries, respectively, and are part of the base system.


<br/>
<br/>

## Linux Storage Command Line Management Tools

<br/>

### Common Linux Storage Management Tools

Most of these tools require root privileges. You can use the `sudo` prefix to execute commands with administrative rights. The syntax of these commands may vary slightly between different Linux distributions.

#### Tool Descriptions and Usage

- **lsblk**
  - Description: Lists block storage devices.
  - Usage: Use the `--scsi` parameter to display only Small Computer System Interface (SCSI) devices.

- **fdisk**
  - Description: Manages disk partitions.
  - Usage: Use the `-l` parameter to list the partitions on a device. This tool is more frequently used with MBR disks.

- **mkfs**
  - Description: Formats a partition with a specified filesystem (e.g., ext4, ReiserFS).
  - Usage: Typically used as `mkfs -t [type] [device]`, where `[type]` is the filesystem type (e.g., `ext4`, `xfs`) and `[device]` is the partition (e.g., `/dev/sda1`).

- **parted**
  - Description: A versatile tool for managing disk partitions, including creating, resizing, deleting, and copying partitions.
  - Usage: Supports both MBR and GPT partition tables and is capable of resizing partitions without data loss.

- **partprobe**
  - Description: Instructs the kernel to re-read the partition table of a specified device.
  - Usage: Useful after making changes to partition tables to ensure the system recognizes the changes without rebooting.

<br/>

#### Additional Important Tools

- **mount**
  - Description: Mounts a filesystem to a specified directory (mount point).
  - Usage: Used to access the contents of a filesystem.

- **umount**
  - Description: Unmounts a mounted filesystem.
  - Usage: Ensures that changes to the filesystem are written and prevents data corruption.

- **df**
  - Description: Displays disk space usage for the file systems.
  - Usage: Useful for monitoring the amount of free space available.

- **du**
  - Description: Estimates file and directory space usage.
  - Usage: Helpful for identifying how much space individual files and directories are consuming.

<br/>

## Creating Linux File Systems

<br/>

### Tools and Commands for Managing File Systems

1. **Disks Tool (GUI)**
   - Description: A graphical utility for managing disk drives and partitions.
   - Usage: It allows you to format partitions, edit details (like labels and mount options), resize, run checks, repair file systems, and configure mounting options.

2. **Listing File Systems with fdisk**
   - Command: `fdisk -l`
   - Usage: Lists all partitions and their file systems on all disks.
   - Example: `sudo fdisk -l` lists all filesystems.
   - Specific Disk: `sudo fdisk -l /dev/sdb` lists the file system on `/dev/sdb`.

3. **Creating a File System with mkfs**
   - Command: `sudo mkfs -t [type] [device]`
   - Usage: Formats a partition with a specified file system type.
   - Example: `sudo mkfs -t ext4 /dev/sdb1` formats the `/dev/sdb1` partition with the ext4 file system.

4. **Creating a Mount Point**
   - Command: `sudo mkdir /path/to/mount-point`
   - Usage: Creates a directory to serve as a mount point.
   - Example: `sudo mkdir /data1` creates a directory named "data1".

5. **Mounting a File System**
   - Command: `sudo mount [device] [mount-point]`
   - Usage: Attaches the specified file system to the file system hierarchy at the mount point.
   - Example: `sudo mount /dev/sdb1 /data1` mounts the file system on `/dev/sdb1` to the directory `/data1`.

6. **Verifying Mount**
   - Command: `mount | grep [device]`
   - Usage: Checks if the device is mounted and displays its mount details.
   - Example: `sudo mount | grep sdb1` checks if `/dev/sdb1` is mounted and displays its mount information.

<br/>

### Additional Considerations

- **File System Check (fsck)**
  - Used to check and repair inconsistencies in file systems.
  - Run `sudo fsck [device]`, e.g., `sudo fsck /dev/sdb1`.

- **Unmounting File Systems**
  - Use `sudo umount [mount-point]` to safely unmount a file system.

- **Automounting File Systems**
  - Edit `/etc/fstab` to configure file systems to be mounted automatically at boot.

- **Choosing a File System Type**
  - Consider the specific needs (performance, reliability, compatibility) when choosing a file system type (ext4, XFS, Btrfs, etc.).
