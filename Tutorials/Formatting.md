# **Formatting an SSD with EXT4 File System in Ubuntu Linux**

A step-by-step guide to formatting a 2.5" SSD with the EXT4 file system using the GNOME Disks utility in Ubuntu Linux.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Objectives](#objectives)
- [Prerequisites](#prerequisites)
- [Steps](#steps)
  - [Open GNOME Disks Utility](#open-gnome-disks-utility)
  - [Select Your SSD](#select-your-ssd)
  - [Choose the Partition Table](#choose-the-partition-table)
  - [Create a New Partition](#create-a-new-partition)
  - [Configure the Partition](#configure-the-partition)
  - [Format and Finalize](#format-and-finalize)
- [Conclusion](#conclusion)
- [Contribution](#contribution)

<br>

## **Overview**

This tutorial will guide you through the process of formatting a 2.5" SSD with the EXT4 file system using the GNOME Disks utility in Ubuntu Linux. The EXT4 file system is commonly used for Linux-based systems due to its stability and performance.

<br>

## **Objectives**

By the end of this tutorial, you will:

- Learn how to use the GNOME Disks utility to format an SSD.
- Understand how to choose the right partition table for your SSD.
- Successfully format an SSD with the EXT4 file system for use in Ubuntu Linux.

<br>

## **Prerequisites**

- Ubuntu Linux operating system.
- A 2.5" SSD to format.
- Backup any important data from the SSD, as this process will erase it.

<br>

## **Steps**

### **Open GNOME Disks Utility**

1. Press the Super key (Windows key) on your keyboard.
2. Type **"Disks"** in the search bar and open the GNOME Disks utility.

<br>

### **Select Your SSD**

1. In the GNOME Disks utility, you will see a list of connected drives.
2. Identify and select the 2.5" SSD that you want to format.

<br>

### **Choose the Partition Table**

1. In the GNOME Disks utility, you will be prompted to choose a partition table:
   - **MBR (Master Boot Record)**: Suitable for SSDs under 2TB and older systems.
   - **GPT (GUID Partition Table)**: Recommended for SSDs over 2TB and modern systems.

2. Choose the appropriate partition table based on your SSD size and system compatibility.

<br>

### **Create a New Partition**

1. If there are any existing partitions, you can delete them by selecting the partition and clicking the **minus (-)** button.
2. Click the **plus (+)** button to create a new partition.

<br>

### **Configure the Partition**

1. In the "Create Partition" dialog, set the desired size for the new partition (you can use the entire SSD).
2. In the **File System** section, select **EXT4**.
3. Optionally, you can name the partition for easier identification.

<br>

### **Format and Finalize**

1. Click **Create** to format the partition with the EXT4 file system.
2. Wait for the process to complete. Once done, your SSD will be ready for use with the EXT4 file system.

<br>

## **Conclusion**

Your 2.5" SSD is now formatted with the EXT4 file system and is ready for use on your Ubuntu Linux system. Remember that this process erases all data on the SSD, so ensure you have backed up any important files before proceeding.

<br>

## **Contribution**

Your contributions can make this guide even better:

- Fork the repository.
- Create a new branch:

  ```bash
  git checkout -b my-awesome-feature
  ```

- Make your changes.
- Commit your changes:

  ```bash
  git commit -am 'Added some amazing features'
  ```

- Push to the branch:

  ```bash
  git push origin my-awesome-feature
  ```

- Create a new Pull Request.

Contributions are welcome! Feel free to open issues, suggest improvements, or submit pull requests to improve the content.

<br>

## **Author**

- **Raphael Chookagian** | [GitHub Profile](https://github.com/cesar-group)

## **Date of Latest Revision**

- 12/10/2024

## **License**

- This guide is provided as-is without any warranties. Users are advised to review and understand the content before following the steps.

- This project is licensed under the MIT License. See the LICENSE file for details.
