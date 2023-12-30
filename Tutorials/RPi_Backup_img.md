# Full Featured Tutorial: Creating a Complete Backup Image of Your Raspberry Pi SD Card

<br>

## Introduction

Creating a full backup image of your Raspberry Pi's SD card is essential for easy recovery or cloning of your setup. This tutorial guides you through the process of creating an image file of your Raspberry Pi's SD card and storing it on an external hard drive. This image can be used to restore your setup on another SD card or keep as a backup.

<br>

## Prerequisites

- A Raspberry Pi running Ubuntu or a similar OS.
- An external hard drive with sufficient storage space.
- Basic knowledge of terminal commands.

<br>

## Step-by-Step Guide

<br>

### Preparing the External Hard Drive

1. **Mount the External Hard Drive**:
   - Connect your external hard drive to the Raspberry Pi.
   - Open the terminal and run `lsblk` or `df -h` to see if the drive is mounted.
   - If not mounted, create a mount point and mount the drive:

     ```bash
     sudo mkdir /media/pi/MyExternalDrive
     sudo mount /dev/sda1 /media/pi/MyExternalDrive
     ```

     Replace `/dev/sda1` with your drive's identifier as shown in `lsblk`.

2. **Navigate to the Mounted Drive**:
   - Change directory to the mount point:

     ```bash
     cd /media/pi/MyExternalDrive
     ```

<br>

### Creating the Image

3. **Identify the SD Card Device**:
   - In the terminal, run `lsblk` to identify your SD card device. It's usually labeled as `/dev/mmcblk0`.

4. **Create the Image with `dd` Command**:

   - Execute the following command to create an image of your SD card:

     ```bash
     sudo dd if=/dev/mmcblk0 of=./raspberry_pi_backup.img bs=4M status=progress
     ```

   - `if=/dev/mmcblk0` specifies the SD card as the input.
   - `of=./raspberry_pi_backup.img` specifies the output image file.
   - `bs=4M` sets the block size to 4MB for efficient copying.
   - `status=progress` displays the progress.

<br>

### Post-Creation

5. **Safely Eject the Hard Drive**:

   - After the backup is complete, ensure to safely unmount the drive:

     ```bash
     sync
     sudo umount /media/pi/MyExternalDrive
     ```

6. **Restoring or Cloning**:

   - To restore the image to another SD card, use:

     ```bash
     sudo dd if=./raspberry_pi_backup.img of=/dev/sdX bs=4M status=progress
     ```

   - Replace `/dev/sdX` with your new SD card's device name.
   - Alternatively, use software like BalenaEtcher for a GUI approach.

<br>

## Safety and Notes

- Double-check the device names (`/dev/mmcblk0`, `/dev/sdX`) to avoid data loss.
- The `dd` command requires caution. Incorrect usage can result in data loss.
- The backup file size will be equal to your SD card’s total capacity.
- Ensure enough space on your external hard drive.
- Consider using graphical tools for a more user-friendly experience.

<br>

## Conclusion

By following this tutorial, you have created a complete image of your Raspberry Pi's SD card. This image is crucial for backup purposes and can be used to quickly restore or clone your Raspberry Pi setup onto another SD card. Remember to handle the `dd` command with care and always verify device names before proceeding.
