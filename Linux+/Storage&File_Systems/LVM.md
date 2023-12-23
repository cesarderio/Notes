# LVM - Logical Volume Management

## Understanding Logical Volume Management (LVM) in Linux

<br/>

### What is LVM?

- **Definition**: LVM stands for Logical Volume Management.
- **Functionality**: Allows grouping together storage media (physical or virtual) into a single logical unit.
- **Purpose**: Provides a flexible way of managing storage space across multiple disks.

<br/>

### Key Concepts in LVM

1. **Physical Volume (PV)**:
   - Represents a physical or logical storage device.
   - Can be a physical disk or a logical disk in a virtual machine.

2. **Volume Group (VG)**:
   - A collection of physical volumes pooled together.
   - Allows the combination of multiple physical volumes into a larger virtual storage unit.

3. **Logical Volume (LV)**:
   - A portion of a volume group that is presented to the operating system as a logical volume.
   - Acts similarly to a disk partition from the OS perspective.

<br/>

### LVM vs RAID

- **Differences from RAID**:
  - LVM does not inherently provide data redundancy or parity like some RAID levels (e.g., RAID 5).
  - LVM is primarily focused on flexible disk space management across multiple devices.

<br/>

### Configuring LVM in Linux

1. **Identifying Disks for LVM**:
   - Use `lvmdiskscan` to scan for available disks.
   - Mark the desired disks for LVM use.

2. **Creating Physical Volumes (PVs)**:
   - Use `pvcreate` to initialize physical volumes for LVM.
   - Example: `sudo pvcreate /dev/sdb /dev/sdc /dev/sdd`.

3. **Creating a Volume Group (VG)**:
   - Combine PVs into a VG using `vgcreate`.
   - Example: `sudo vgcreate VolGroup1 /dev/sdb /dev/sdc /dev/sdd`.

4. **Creating Logical Volumes (LVs)**:
   - Use `lvcreate` to create logical volumes within a VG.
   - Example: `sudo lvcreate -L 50G -n projects VolGroup1`.

5. **Formatting and Mounting the LV**:
   - Format the LV with a filesystem (e.g., ext4).
   - Mount the LV to a directory for use.
   - Example: `sudo mkfs -t ext4 /dev/VolGroup1/projects` and `sudo mount /dev/VolGroup1/projects /projects`.

6. **Making Persistent Mounts**:
   - Edit `/etc/fstab` to ensure the LV mounts automatically on boot.

<br/>

### Advantages of LVM

- **Flexibility**: Easily resize and manage storage without being constrained by physical disk sizes.
- **Efficiency**: Optimize storage utilization by allocating space based on actual usage and demand.
- **Convenience**: Manage storage with logical names and resize volumes without unmounting or affecting uptime.


<br/>

## Configuring Logical Volume Management (LVM) in Linux

<br/>

### Introduction to LVM

- **Purpose**: LVM allows for flexible management of physical storage space in Linux by grouping multiple storage devices into a single logical unit.
- **Components**:
  - **Physical Volumes (PVs)**: Individual storage devices.
  - **Volume Group (VG)**: A pool of physical volumes.
  - **Logical Volumes (LVs)**: Segments of a volume group that are presented to the OS as logical units.

<br/>

### Step-by-Step Configuration Process

1. **Identifying Suitable Storage Devices**:
   - Run `sudo lvmdiskscan` to list available storage devices.
   - Focus on specific devices (e.g., `/dev/sdb`, `/dev/sdc`, `/dev/sdd`) for LVM use.

2. **Creating Physical Volumes**:
   - Use `sudo pvcreate` to initialize physical volumes for LVM.
   - Example: `sudo pvcreate /dev/sdb /dev/sdc /dev/sdd`.

3. **Verifying Physical Volume Creation**:
   - Run `sudo pvs` to list and verify the created physical volumes.

4. **Creating a Volume Group**:
   - Combine physical volumes into a volume group with `sudo vgcreate`.
   - Example: `sudo vgcreate VolGroup1 /dev/sdb /dev/sdc /dev/sdd`.

5. **Verifying Volume Group Creation**:
   - Use `sudo vgs` to confirm the creation and size of the volume group.

6. **Creating a Logical Volume**:
   - Use `sudo lvcreate` to create a logical volume within a volume group.
   - Specify size and name for the logical volume.
   - Example: `sudo lvcreate -L 50G -n projects VolGroup1`.

7. **Formatting the Logical Volume**:
   - Format the new logical volume with a filesystem (e.g., ext4).
   - Example: `sudo mkfs -t ext4 /dev/mapper/VolGroup1-projects`.

8. **Mounting the Logical Volume**:
   - Create a mount point and mount the logical volume.
   - Example: `sudo mkdir /projects && sudo mount /dev/VolGroup1/projects /projects`.

9. **Making the Mount Persistent**:
   - Edit `/etc/fstab` to ensure the logical volume is mounted automatically at boot.
   - Add an entry for the logical volume specifying the mount point, filesystem type, and other mount options.

<br/>

### Key Takeaways

- **Flexibility**: LVM allows for dynamic resizing and management of storage.
- **Efficiency**: Multiple physical disks can be managed as a single unit, simplifying storage administration.
- **Practical Use**: Ideal for situations where storage needs may change over time, allowing for easy expansion or reduction of storage space.

<br/>

### Additional Tips

- **Space Allocation**: Leave some free space in the volume group for LVM to function correctly and for future expansion.
- **Persistent Mounts**: Properly configuring `/etc/fstab` is crucial for ensuring that the logical volume remains accessible after system reboots.

<br/>

## Storage Area Networks and Network Attached Storage

<br/>

### Storage Area Networks (SAN)

- **Definition**: A SAN is a dedicated network specifically for storage communications.
- **Purpose**: Allows storage consumers, such as Linux servers, to access shared storage over a network.
- **Types of SANs**:
  - **iSCSI SAN**: Uses standard network equipment. SCSI commands are embedded within IP packets and sent over the network. iSCSI initiators (consumers) connect to iSCSI targets (storage providers) typically listening on TCP port 3260.
  - **Fibre Channel (FC) SAN**: A high-speed SAN designed for enterprise use with specialized equipment like host bus adapters (HBAs) and Fibre Channel switches. More expensive than iSCSI, it offers redundancy and high performance.

<br/>

### iSCSI SAN Configuration

- **Components**:
  - **iSCSI Initiators**: Can be software agents in the OS or specialized controller cards in the server.
  - **iSCSI Targets**: Network storage units that provide storage.
- **Network Setup**: Typically set up with a dedicated VLAN for isolated data transfer.
- **Storage Management**: To the Linux server, iSCSI storage appears like local storage, which can be partitioned and managed accordingly.

<br/>

### Fibre Channel (FC) SAN

- **Characteristics**: Uses specialized equipment for high-speed, secure, and reliable storage networking.
- **Redundancy**: Multiple paths to storage for redundancy, mitigating the risk of a single point of failure.
- **Storage Arrays**: Often include backup units for data protection.
- **Security Considerations**: Include data encryption at rest, file access auditing, and physical security.

<br/>

### Network Attached Storage (NAS)

- **Functionality**: A NAS device is a specialized storage appliance for sharing files over a network.
- **Protocols**: Accessible using file sharing protocols like SMB and NFS.
- **Disk Management**: Supports JBOD (Just a Bunch of Disks) and various RAID configurations.
- **Use Cases**: Ideal for centralized file sharing and storage in a network environment.

<br/>

### Summary

- SANs and NAS provide flexible, centralized storage solutions for Linux environments.
- SANs, especially iSCSI and FC, offer dedicated, high-performance storage networking.
- NAS devices facilitate easy file sharing and storage expansion.

<br/>

### Key Points for Linux Configuration

- **iSCSI Initiators**: Linux servers can be configured as iSCSI initiators to connect to iSCSI SANs.
- **FC SAN Connection**: Requires specialized hardware (HBAs) and configuration for connectivity.
- **NAS Integration**: Linux can easily connect to NAS devices via standard network protocols.

<br/>

## Configuring a Linux-based iSCSI Initiator

<br/>

### Introduction to iSCSI in Linux

- **Objective**: Connect a Linux host to network storage using iSCSI (Internet Small Computer Systems Interface).
- **Setup**: Utilize a Windows Server as the iSCSI target and a Linux machine as the iSCSI initiator.

<br/>

### Setting Up the iSCSI Target on Windows Server

1. **Install iSCSI Support**:
   - Access Server Manager and add the iSCSI Target Server role under File and Storage Services.

2. **Create an iSCSI Virtual Disk**:
   - Use the Server Manager to create a new iSCSI virtual disk on an available drive.
   - Example: Name the disk `iSCSI_Vdisk1` and set its size to 9.91 GB.

3. **Configure iSCSI Target**:
   - Create a new target (e.g., `LinuxHosts`) and specify which initiators (IP addresses) are allowed to connect.
   - Note the IQN (iSCSI Qualified Name) of the target for later use.

<br/>

### Configuring the Linux iSCSI Initiator

1. **Discover iSCSI Target**:
   - Run `sudo iscsiadm --mode discovery --type sendtargets --portal [Windows Host IP]` to discover the iSCSI target on the Linux host.

2. **Connect to iSCSI Target**:
   - Use `sudo iscsiadm --mode node --targetname [IQN] --portal [Windows Host IP] --login` to initiate a connection to the iSCSI target.

3. **Verify Connection**:
   - Confirm the connection using `lsblk --scsi | grep iscsi` and `sudo fdisk -l`.
   - The iSCSI disk should appear as a local device (e.g., `/dev/sde`).

<br/>

### Setting Up the iSCSI Disk on Linux

1. **Partition the iSCSI Disk**:
   - Use `sudo fdisk /dev/sde` to create a new partition on the iSCSI disk.

2. **Format the Partition**:
   - Format the new partition with a filesystem (e.g., ext4) using `sudo mkfs -t ext4 /dev/sde1`.

3. **Create Mount Point and Mount the Disk**:
   - Create a directory for mounting (e.g., `sudo mkdir /iscsi`).
   - Mount the iSCSI disk to the created directory: `sudo mount /dev/sde1 /iscsi`.

4. **Verify Mount**:
   - Use `sudo mount | grep iscsi` to ensure the disk is successfully mounted.

<br/>

### Summary

- **iSCSI in Linux**: Enables a Linux host to use network storage as if it were local, enhancing storage flexibility and capacity.
- **Configuration Process**: Involves setting up an iSCSI target on a Windows Server, discovering and connecting to it from a Linux host, and then partitioning, formatting, and mounting the iSCSI disk on Linux.





