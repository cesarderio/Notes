<!-- <img src="../assets/disk_backup.png" alt="Alt Text" width="400"> -->

# **Full Disk Image Backup and Restore for Ubuntu Linux**

This tutorial provides a step-by-step guide on how to create a full disk image backup of your Ubuntu Linux system and how to restore it. This is particularly useful for creating a snapshot of your entire system for backup or migration purposes.

<br>

### **Table of Contents**

- [Prerequisites](#prerequisites)
- [Creating the Backup](#creating-the-backup)
  - [Boot from a Live USB](#boot-from-a-live-usb)
  - [Connect the External Hard Drive](#connect-the-external-hard-drive)
  - [Identify and Prepare the Drives](#identify-and-prepare-the-drives)
  - [Backup the Disk](#backup-the-disk)
  - [Safely Unmount and Reboot](#safely-unmount-and-reboot)
- [Restoring from the Backup](#restoring-from-the-backup)
- [Conclusion](#conclusion)
- [Contribution](#contribution)

<br>

## **Prerequisites**

- A laptop (e.g., Lenovo, Asus) or similar running Ubuntu Linux.
- An external hard drive with enough storage space for the disk image.
- A live Ubuntu USB stick for booting the laptop.

<br>

## **Creating the Backup**

### **Boot from a Live USB**

1. Insert the live Ubuntu USB stick into your laptop.
2. Reboot the laptop and enter the boot menu (usually by pressing F12 or another key during startup).
3. Select the USB stick from the boot menu to boot into the live Ubuntu environment.

### **Connect the External Hard Drive**

1. Connect your external hard drive to the laptop.
2. Open a terminal in the live session.

### **Identify and Prepare the Drives**

1. **Identify the Laptop's Hard Drive**:

   ```bash
   lsblk
   # or
   sudo fdisk -l
   ```

   - Locate your laptop's hard drive (usually `/dev/sda`).

2. **Mount the External Hard Drive**:
   - Identify the external drive in `lsblk`.
   - Create a mount point and mount the drive:

     ```bash
     sudo mkdir /media/backup
     sudo mount /dev/sdx1 /media/backup
     ```

     Replace `/dev/sdx1` with your external drive's identifier.

### **Backup the Disk**

1. **Use `dd` to Create the Image**:

   ```bash
   sudo dd if=/dev/sda of=/media/backup/laptop_backup.img bs=4M status=progress
   ```

   - Replace `/dev/sda` with your laptop's disk identifier.
   - Replace `/media/backup/laptop_backup.img` with your desired backup file path and name.

2. **Wait for the Process to Complete**: This might take a while depending on the size of your disk and the speed of your external drive.

### **Safely Unmount and Reboot**

1. **Unmount the External Drive**:

   ```bash
   sync
   sudo umount /media/backup
   ```

2. **Reboot the Laptop**:
   - Remove the live USB stick.
   - Reboot into your normal Ubuntu system.

<br>

## **Restoring from the Backup**

To restore your system from the backup:

1. Boot from the live Ubuntu USB stick as before.
2. Connect the external hard drive with the backup image.
3. Open a terminal and mount the external drive as described above.
4. Restore the image to the laptop's disk:

   ```bash
   sudo dd if=/media/backup/laptop_backup.img of=/dev/sda bs=4M status=progress
   ```

   - Ensure `/dev/sda` is the correct disk device for your laptop.
   - This process will overwrite the laptop's disk, so proceed with caution.

5. After completion, unmount the external drive and reboot.

<br>

## **Conclusion**

You now have a complete disk image of your Ubuntu system, which can be used for backup or restoration. Remember to handle the `dd` command with care, as it can lead to data loss if used improperly.

<br>

## **Contribution**

Your contributions can make this guide even better:

- Fork the repository.
- Create a new branch:

  ```bash
  git checkout -b my-awesome-feature
  ```

- Make your invaluable changes.
- Commit your changes:

  ```bash
  git commit -am 'Added some amazing features'
  ```

- Push to the branch:

  ```bash
  git push origin my-awesome-feature
  ```

- Create a new Pull Request targeting the `Notes` directory.

Contributions are welcome! Feel free to open issues, suggest enhancements, or submit pull requests to improve the script.

<br>

## **Author**

- **Raphael Chookagian** | [GitHub Profile](https://github.com/cesar-group)

## **Date of Latest Revision**

- 12/10/2024

## **License**

- This guide is provided as-is without any warranties. Users are advised to review and understand the guide before executing any commands.

- This project is licensed under the MIT License. See the LICENSE file for details.
