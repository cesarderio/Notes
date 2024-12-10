# Formatting an SSD with EXT4 File System in Ubuntu Linux

This guide provides a step-by-step tutorial on how to format a 2.5" SSD with the EXT4 file system using the GNOME Disks utility in Ubuntu Linux.

## Prerequisites

- Ubuntu Linux operating system
- A 2.5" SSD that you wish to format
- Backup any important data from your SSD

## Steps

### 1. Open GNOME Disks Utility

- Press the Super key (also known as the Windows key).
- Type "Disks" and open the GNOME Disks utility.

### 2. Select Your SSD

- In the Disks utility, identify and select the SSD you want to format from the list of drives.

### 3. Choose the Partition Table

- **MBR (Master Boot Record)**: Also known as DOS, suitable for SSDs under 2TB and older systems.
- **GPT (GUID Partition Table)**: Modern and required for drives over 2TB, recommended for newer systems.

### 4. Create a New Partition

- Delete existing partitions if necessary by selecting the partition and clicking the minus (-) button.
- Click the plus (+) button to create a new partition.

### 5. Configure the Partition

- In the "Create Partition" dialog, set the size for the new partition (you can use the entire SSD).
- For the "Type" or "File System" option, select **EXT4**.
- Optionally, you can name the partition for easier identification.

### 6. Format and Finalize

- Click "Create" to format the partition with the EXT4 file system.
- Once the process completes, the SSD will be ready for use with the EXT4 file system.

## Conclusion

Your SSD is now formatted with the EXT4 file system and ready for use in your Ubuntu Linux system. Remember, this process erases all existing data on the SSD, so ensure you have backups of any important files before proceeding.
