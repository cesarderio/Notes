# Mounting File Systems

## Mounting Local Linux File Systems

<br/>

### Initial Steps and Disk Partitioning

1. **Viewing System Partitions**
   - Command: `sudo fdisk -l`
   - Usage: Displays how the system storage is partitioned.

2. **Creating a New Partition**
   - Use `sudo fdisk /dev/sdc` to start the fdisk utility for the `/dev/sdc` device.
   - When prompted "Device does not exist, create new partition?", respond with `y` for a new partition.
   - Choose `p` for a primary partition.
   - Select the default partition number `1`.
   - Accept the default starting and ending sectors by pressing Enter.
   - Finally, press `w` to write the changes to disk.

3. **Verifying the New Partition**
   - Command: `sudo fdisk -l /dev/sdc`
   - Confirm that the new partition (`/dev/sdc1`) is correctly created with the expected size.

<br/>

### Formatting and Mounting the Partition

1. **Formatting the Partition**
   - Command: `sudo mkfs -t ext4 /dev/sdc1`
   - Formats `/dev/sdc1` with the ext4 file system.

2. **Creating a Mount Point**
   - Command: `sudo mkdir /data2`
   - Creates a directory named "data2" for mounting.

3. **Mounting the File System**
   - Command: `sudo mount /dev/sdc1 /data2`
   - Mounts the `/dev/sdc1` partition to the `/data2` directory.

4. **Verifying the Mount**
   - Command: `sudo mount | grep sdc`
   - Checks if `/dev/sdc` is correctly mounted.

<br/>

### Setting Up Persistence

1. **Editing fstab for Automatic Mounting**
   - File: `/etc/fstab`
   - Add the line: `/dev/sdc1 /data2 ext4 rw 0 2`
   - This configuration ensures that `/dev/sdc1` is automatically mounted to `/data2` at startup.

2. **Saving the fstab File**
   - Use `Ctrl+X` to exit and save the changes in the `fstab` file.

3. **Rebooting the System**
   - Command: `sudo init 6`
   - Reboots the system to apply the changes.

4. **Verifying Automatic Mounting**
   - After reboot, use `sudo mount | grep sdc` to confirm that `/dev/sdc1` is automatically mounted to `/data2`.

5. **Unmounting a File System**
   - Command: `sudo umount /data2`
   - Unmounts the file system from `/data2`.

6. **Manually Mounting a File System**
   - Command: `sudo mount /dev/sdc1 /data2`
   - Mounts `/dev/sdc1` to `/data2` manually.

<br/>

### Additional Notes

- Ensure that all commands are executed with the appropriate permissions, especially when modifying disk partitions and file system configurations.
- Be cautious while editing `/etc/fstab`, as incorrect entries can cause boot issues.
- Always back up important data before partitioning or formatting drives.


<br/>

## Mounting Remote Cloud-based File Systems

<br/>

### Managing Remote Linux Mount Points: Mounting Azure Cloud File Systems

<br/>

#### Setting Up a Shared Folder in Microsoft Azure

1. **Creating a New Storage Account in Azure**
   - Sign into the Azure GUI portal.
   - Click "Create a resource" and select "Storage account".
   - Specify details like the Resource group and account name (e.g., `storacceastyhz765`).
   - Choose the appropriate region (e.g., East US) for proximity to users.
   - Review and create the storage account.

2. **Creating a File Share in the Storage Account**
   - Navigate to the created storage account (e.g., `storacceastyhz765`).
   - Go to "File shares" and click "Add file share".
   - Name the file share (e.g., `projects`).
   - Create the file share without changing other default settings.

3. **Uploading Files and Creating Directories**
   - Within the `projects` file share, add a directory (e.g., `current_year`).
   - Upload files to the directory (e.g., `Project_A.txt`, `Project_B.txt`, `Project_C.txt`).

<br/>

#### Connecting to the Shared Folder from Linux

1. **Generating Mount Script in Azure**
   - In the Azure portal, navigate to the created file share (`projects`).
   - Click the "Connect" button and select the Linux tab.
   - Use the "Show script" option to generate a script for creating a mount point in Linux.
   - The script will use an SMB (Server Message Block) connection with a CIFS (Common Internet File System) file system type.
   - Copy the generated script.

2. **Executing the Script on Linux Host**
   - SSH into the Linux host where you want to mount the shared folder (use tools like PuTTY).
   - Run the copied script to create the mount point and configure the connection.
   - This will include a `sudo mount -t cifs` command that refers to the Azure DNS name and specifies the local mount point (e.g., `/mnt/projects`).
   - The script also sets up credentials for authentication.

3. **Verifying and Persisting the Mount**
   - Check the `/etc/fstab` file to ensure the mount entry is added for persistence.
   - Use commands like `ls /mnt/projects` to verify the mounted files and directories.

<br/>

#### Summary

- This process demonstrates how to create a cloud-based shared folder in Microsoft Azure and mount it on a Linux system using SMB/CIFS.
- The Azure portal provides a convenient way to generate the necessary scripts for mounting.
- Ensuring the mount is persistent across reboots is achieved by adding the mount details to the `/etc/fstab` file.


<br/>

## Linux File System Hard and Soft (Symbolic) Links

<br/>

### Understanding Inodes

- **What is an Inode?**
  - It's a 128-byte entry in the filesystem table that describes a file or directory.
  - Contains metadata, including pointers to actual disk data blocks, owning user and group, permissions, and timestamps.

- **Checking Inode Numbers**
  - Use `ls -i` to display filesystem entries with their inode numbers.

<br/>

### Hard Links

- **Concept**
  - A hard link creates a new filename that points to an existing inode.
  - Allows multiple filenames to share a single inode, referencing the same file data on disk.

- **Characteristics**
  - File data is shared; modifying one link reflects in all.
  - Deleting a file only affects the data when the last hard link is removed.
  - Limited to a single disk partition.

- **Creating a Hard Link**
  - Use the `ln` command.
  - Example: `ln /budgets/file1.xls /home/cblackwell/file1.xls`
  - Creates a new entry in a different directory, but both point to the same inode.

- **Identifying Hard Links**
  - `ls -li` shows files with their inode numbers.
  - `ls -l` shows the count of hard links to a file.

<br/>

### Symbolic (Soft) Links

- **Concept**
  - A symbolic link (symlink) creates a new filename with a new inode that points to an existing filename.
  - Acts as a pointer or shortcut to another file.

- **Characteristics**
  - Has its own inode and metadata but points to another file's data.
  - Can span across disk partitions.
  - Modifications to file data are reflected across all symlinks.

- **Creating a Symbolic Link**
  - Use the `ln -s` command.
  - Example: `ln -s /budgets/file1.xls /home/cblackwell/file1.xls`
  - This creates a symlink in the user's home directory pointing to the original file.

- **Symlink Metadata**
  - Can have different owners, permissions compared to the original file.

<br/>

### Summary

- **Hard Links**
  - Multiple entries, one inode, same disk partition.
  - Ideal for creating alternate paths to a file within the same filesystem.

- **Symbolic Links**
  - Separate inodes, can point across partitions.
  - Useful for creating shortcuts or links to files located in different filesystems.


<br/>

## Working With Hard and Soft (Symbolic) Links in Linux

<br/>

### Understanding and Creating Hard Links

- **Concept of Hard Links**
  - Hard links provide an alternative way to access the same file data.
  - They point to the same inode, sharing the same file data and metadata.

- **Creating a Hard Link**
  - Use the `ln` command without any flags.
  - Example: `ln customers.txt hardlink_customers.txt`
  - This creates a new file entry (`hardlink_customers.txt`) pointing to the same inode as `customers.txt`.

- **Observing Hard Link Behavior**
  - Both the original file and the hard link reflect the same content changes.
  - Use `ls -li` to view inode numbers. Hard links share the same inode number.

- **Limitation**
  - Hard links cannot span across different disk partitions.

<br/>

### Understanding and Creating Symbolic (Soft) Links

- **Concept of Symbolic Links**
  - Symbolic links, or symlinks, create a new file entry with a new inode that points to an existing filename.
  - They can have different permission sets, owners, and groups from the original file.

- **Creating a Symbolic Link**
  - Use the `ln -s` command.
  - Example: `ln -s customers.txt softlink_customers.txt`
  - Creates a symlink (`softlink_customers.txt`) pointing to `customers.txt`.

- **Observing Symbolic Link Behavior**
  - Symlinks have different inode numbers from the original file.
  - Modifications to file data are reflected in both the symlink and the original file.
  - Use `ls -li` to observe the different inode numbers.

- **Advantages**
  - Symlinks can span different file systems and disk partitions.

<br/>

### Practical Demonstration

- **Modifying File Content via Links**
  - Changes made to the file content through either the hard link or the symlink are reflected in all linked files.
  - Example: Modifying `customers.txt` through `softlink_customers.txt` updates the content in both files.

- **Visual Indicators**
  - In many Linux distributions, symlinks are visually differentiated (e.g., different text color, arrow symbol).

<br/>

### Summary

- **Hard Links**
  - Multiple file entries with the same inode.
  - Ideal for alternative file access within the same filesystem.

- **Symbolic Links**
  - Separate inode, points to an original file.
  - Flexible, can point to files across different filesystems and partitions.

<br/>

