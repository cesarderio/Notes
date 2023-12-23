# Disk Management

## Managing and Repairing Linux File Systems

<br/>

### Using `fsck` (File System Check)

- **Purpose**:
  - To check and repair Linux file systems.
  - Essential for ensuring file systems are not corrupt, which can prevent mounting.

- **Using `fsck`**:
  - Run as `sudo fsck /dev/sdX`, where `/dev/sdX` is the partition.
  - The command should point to a specific partition (e.g., `/dev/sdb1`), not just a device.
  - Error messages may occur if run on a device instead of a partition.

- **Behavior on Mounted File Systems**:
  - `fsck` cannot run on mounted file systems as it could lead to data corruption.
  - If a file system is mounted, `fsck` will abort with an error.

- **Exit Status**:
  - The exit status returned by `fsck` is crucial, especially for scripting.
  - Status includes information like file system errors corrected, the need for a reboot, etc.

- **Automatic Checks at Boot Time**:
  - Configured in `/etc/fstab`.
  - The sixth column in `fstab` indicates if `fsck` should check the file system at boot (0 = no, 1 = yes for root file system, 2 = yes for others).
  - `man 5 fstab` provides more details on `fstab` configuration.

<br/>

### Using `tune2fs`

- **Purpose**:
  - To adjust various parameters of ext2, ext3, and ext4 file systems.

- **Viewing File System Information**:
  - `sudo tune2fs -l /dev/sdX` lists detailed information about the file system.
  - Useful for checking the file system state, among other attributes.

- **Setting Volume Labels**:
  - Volume labels can be assigned for easier identification of file systems.
  - Example: `sudo tune2fs -L MyLabel /dev/sdb1` sets the label 'MyLabel' to `/dev/sdb1`.

- **Scheduling File System Checks**:
  - `tune2fs` can be used to schedule regular file system checks.
  - Example: `sudo tune2fs -i 1w /dev/sdb1` sets the file system on `/dev/sdb1` to be checked once a week.

<br/>

### Summary

- **`fsck`**:
  - Used for checking and repairing file systems.
  - Cannot operate on mounted partitions.
  - Automated checks can be configured via `/etc/fstab`.

- **`tune2fs`**:
  - Alters settings of ext file systems.
  - Can assign volume labels and schedule automated checks.
  - Provides detailed information about the file system.

<br/>

## RAID Disk Levels

<br/>

### Understanding RAID

- **Definition**: RAID stands for Redundant Array of Independent (or Inexpensive) Disks.
- **Purpose**: Combines multiple physical or virtual disks for improved performance and/or fault tolerance.
- **Application**: Used in enterprise environments with physical high-speed disks and a hardware RAID controller, as well as in software RAID configurations within operating systems.

<br/>

### Common RAID Levels

1. **RAID 0 (Disk Striping)**
   - **Mechanism**: Data is broken into stripes and distributed across all disks in the array.
   - **Performance**: High, due to multiple disks working simultaneously.
   - **Fault Tolerance**: None. Loss of one disk leads to total data loss.
   - **Minimum Disks Required**: 2

2. **RAID 1 (Disk Mirroring)**
   - **Mechanism**: Each disk in the array is a complete copy (mirror) of the others.
   - **Performance**: Improved read performance; write performance is the same as a single disk.
   - **Fault Tolerance**: High. Can tolerate the failure of all but one disk.
   - **Minimum Disks Required**: 2

3. **RAID 5 (Disk Striping with Distributed Parity)**
   - **Mechanism**: Data and parity information are striped across all disks.
   - **Performance**: Good, with slightly reduced write speeds due to parity calculation.
   - **Fault Tolerance**: Can tolerate the failure of one disk.
   - **Minimum Disks Required**: 3

4. **RAID 6 (Double-Parity RAID)**
   - **Mechanism**: Similar to RAID 5 but with double parity, allowing for two disks to fail without data loss.
   - **Performance**: Similar to RAID 5 but with additional overhead for double parity.
   - **Fault Tolerance**: Can tolerate the failure of two disks.
   - **Minimum Disks Required**: 4

5. **RAID 10 (Mirroring and Striping)**
   - **Mechanism**: Combines mirroring (RAID 1) and striping (RAID 0).
   - **Performance**: High, due to striping across mirrored pairs.
   - **Fault Tolerance**: High. Can tolerate multiple disk failures as long as they are not in the same mirrored pair.
   - **Minimum Disks Required**: 4

<br/>

### Summary

- **RAID 0**: High performance, no fault tolerance.
- **RAID 1**: Good fault tolerance, improved read performance.
- **RAID 5**: Balance of performance and fault tolerance with single-disk failure resilience.
- **RAID 6**: Enhanced fault tolerance with two-disk failure resilience.
- **RAID 10**: High performance and fault tolerance, suitable for environments with heavy read/write operations.

<br/>

### Additional Considerations

- **Hardware vs. Software RAID**: Hardware RAID generally offers better reliability and performance but can be more expensive. Software RAID is more flexible and cost-effective.
- **Usage**: The choice of RAID level depends on the specific needs for performance, data availability, and cost.

<br/>

## Configuring Software RAID in Linux (RAID Level 1)

<br/>

### Introduction to Software RAID

- **Purpose**: Combining multiple disks for improved performance or increased availability.
- **RAID Level 1**: Disk mirroring, which requires two disks. Anything written to the mirrored disks is written to both for availability purposes.

<br/>

### Steps to Configure RAID 1

1. **Identify Available Disks**:
   - Use `sudo lsblk --scsi` to list SCSI block storage devices.
   - In this demo, the disks of interest are `/dev/sdc` and `/dev/sdd`.

2. **Prepare Disks for RAID**:
   - Check current partitioning: `sudo fdisk -l /dev/sdc /dev/sdd`.
   - Create a partition on each disk and set it to 'Linux RAID autodetect':
     - Run `sudo fdisk /dev/sdc` and `sudo fdisk /dev/sdd`.
     - Create a new primary partition (`n`), select the default values for partition size, and set the type to `Linux RAID autodetect` (`t`, then `fd`).

3. **Install RAID Management Software**:
   - Install `mdadm` (mirror device administration): `sudo apt install mdadm`.

4. **Create the RAID Array**:
   - Use `mdadm` to create the RAID array:
     - `sudo mdadm --create /dev/md1 --level=1 --raid-devices=2 /dev/sdc1 /dev/sdd1`.
   - Confirm the creation of the array when prompted.

5. **Monitor RAID Synchronization**:
   - Check the progress of RAID array synchronization:
     - `sudo mdadm --detail /dev/md1`.
   - Initially, the synchronization process will start, even if the disks are empty.

6. **Create File System and Mount Point**:
   - Create a mount point directory: `sudo mkdir /mirror`.
   - Format the RAID array with a file system (e.g., ext4): `sudo mkfs -t ext4 /dev/md1`.
   - Mount the RAID array: `sudo mount /dev/md1 /mirror`.

<br/>

### Post-Configuration

- **Accessing the RAID Array**:
  - The RAID array is now accessible via the `/mirror` mount point.
  - Any data written to `/mirror` is mirrored across both disks.

<br/>

### Summary

- **RAID Level 1 (Mirroring)**:
  - Provides redundancy by mirroring data across two disks.
  - Ideal for scenarios where data availability is crucial.
  - Configured in Linux using `mdadm`.

- **Benefits**:
  - Increases data reliability and availability.
  - Transparent to the operating system; appears as a single logical disk.
