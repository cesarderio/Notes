<img src="../assets/rsynclogo.png" alt="Alt Text" width="400">

# Set Up Your Raspberry Pi as a Network Server to Create and Store Full Backups

Learn how to configure your Raspberry Pi as a network server to create and store full backups of Linux machines on your network.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Step-by-Step Guide](#step-by-step-guide)
  - [Set Up the Raspberry Pi](#set-up-the-raspberry-pi)
  - [Set Up SSH Keys (Optional)](#set-up-ssh-keys-optional)
  - [Create Backup Scripts on Linux Machines](#create-backup-scripts-on-linux-machines)
  - [Automate the Backups](#automate-the-backups)
- [Considerations](#considerations)
- [Conclusion](#conclusion)

<br>

## **Overview**

You can set up your Raspberry Pi as a network server to create and store full backups of different Linux machines on your network. This can be achieved using a variety of tools and protocols. Below are the steps to set up a simple backup server using `rsync`, a popular file copying tool that is ideal for creating backups.

<br>

## **Prerequisites**

1. **Raspberry Pi**: A Raspberry Pi running Raspberry Pi OS.
2. **External Storage**: An external hard drive or SSD connected to the Raspberry Pi for storing backups.
3. **Linux Machines**: Other Linux machines on the same network to be backed up.
4. **Basic Terminal Knowledge**: Familiarity with terminal commands.

<br>

## **Step-by-Step Guide**

### **Set Up the Raspberry Pi**

1. **Install Raspbian**:
   - Make sure your Raspberry Pi is set up with the latest version of Raspberry Pi OS.

2. **Connect to Network**:
   - Ensure that the Raspberry Pi is connected to the same network as the Linux machines you want to back up.

3. **Install Necessary Packages**:
   - Install `rsync` and `ssh` if they are not already installed:

     ```bash
     sudo apt update
     sudo apt install rsync ssh
     ```

4. **Configure Storage**:
   - Connect an external storage device to the Raspberry Pi (such as a USB hard drive or SSD) that will store the backups. Ensure it is formatted correctly and mounted.

     ```bash
     sudo mkdir /media/pi/BackupDrive
     sudo mount /dev/sda1 /media/pi/BackupDrive
     ```

<br>

### **Set Up SSH Keys (Optional)**

To securely and conveniently automate backups, set up SSH key-based authentication from each Linux machine to your Raspberry Pi:

1. On each Linux machine, generate an SSH key pair (if not already done):

   ```bash
   ssh-keygen
   ```

2. Copy the public key to your Raspberry Pi:

   ```bash
   ssh-copy-id pi@raspberrypi.local
   ```

   Replace `pi@raspberrypi.local` with the username and hostname/IP of your Raspberry Pi.

<br>

### **Create Backup Scripts on Linux Machines**

1. On each Linux machine, create a script to back up files to the Raspberry Pi using `rsync`. For example:

   ```bash
   #!/bin/bash
   rsync -avz --delete /path/to/backup/ pi@raspberrypi.local:/media/pi/BackupDrive/machine_name_backup/
   ```

   - `/path/to/backup/` is the directory you want to back up.
   - `pi@raspberrypi.local:/media/pi/BackupDrive/machine_name_backup/` is the destination directory on your Raspberry Pi.

2. Make the script executable:

   ```bash
   chmod +x /path/to/script.sh
   ```

<br>

### **Automate the Backups**

1. Set up a cron job on each Linux machine to run the backup script at regular intervals:

   ```bash
   crontab -e
   ```

2. Add a line to schedule your backup script. For example, to run the backup daily at 2 AM:

   ```bash
   0 2 * * * /path/to/script.sh
   ```

<br>

## **Considerations**

- **Network Bandwidth**: Backups can consume significant network bandwidth. Consider scheduling them during off-peak hours.
- **Storage Capacity**: Ensure your Raspberry Pi has enough storage capacity to hold the backups from all machines.
- **Backup Integrity**: Regularly check the integrity of your backups.
- **Security**: Ensure that your network is secure, especially if you are using SSH key-based authentication.
- **Backup Strategy**: Decide on a backup strategy (full, incremental, differential) based on your needs.

<br>

## **Conclusion**

By following this tutorial, you have set up your Raspberry Pi as a network server for creating and storing backups of Linux machines. This setup ensures your data is securely stored and easily accessible for recovery. Remember to monitor storage usage and regularly verify the integrity of your backups.

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
