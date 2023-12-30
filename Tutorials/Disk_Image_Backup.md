# Full Disk Image Backup and Restore for Ubuntu Linux

This tutorial provides a step-by-step guide on how to create a full disk image backup of your Ubuntu Linux system and how to restore it. This is particularly useful for creating a snapshot of your entire system for backup or migration purposes.

<br>

## Prerequisites

- A Lenovo/Asus/etc laptop (or similar) running Ubuntu Linux.
- An external hard drive with enough storage space for the disk image.
- A live Ubuntu USB stick for booting the laptop.

<br>

## Creating the Backup

<br>

### Boot from a Live USB

1. Insert the live Ubuntu USB stick into your laptop.
2. Reboot the laptop and enter the boot menu (usually by pressing F12 or another key during startup).
3. Select the USB stick from the boot menu to boot into the live Ubuntu environment.

<br>

### Connect the External Hard Drive

1. Connect your external hard drive to the laptop.
2. Open a terminal in the live session.

<br>

### Identify and Prepare the Drives

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

<br>

### Backup the Disk

1. **Use `dd` to Create the Image**:

   ```bash
   sudo dd if=/dev/sda of=/media/backup/laptop_backup.img bs=4M status=progress
   ```

   - Replace `/dev/sda` with your laptop's disk identifier.
   - Replace `/media/backup/laptop_backup.img` with your desired backup file path and name.

2. **Wait for the Process to Complete**: This might take a while depending on the size of your disk and the speed of your external drive.

<br>

### Safely Unmount and Reboot

1. **Unmount the External Drive**:

   ```bash
   sync
   sudo umount /media/backup
   ```

2. **Reboot the Laptop**:
   - Remove the live USB stick.
   - Reboot into your normal Ubuntu system.

<br>

## Restoring from the Backup

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

## Conclusion

You now have a complete disk image of your Ubuntu system, which can be used for backup or restoration. Remember to handle the `dd` command with care, as it can lead to data loss if used improperly.
