# set up your Raspberry Pi as a network server to create and store full backups

<br>

## Overview

You can set up your Raspberry Pi as a network server to create and store full backups of different Linux machines on your network. This can be achieved using a variety of tools and protocols. Below are the steps to set up a simple backup server using `rsync`, a popular file copying tool that is ideal for creating backups:

### Step 1: Set Up the Raspberry Pi

1. **Install Raspbian**: Make sure your Raspberry Pi is set up with the latest version of Raspbian or Raspberry Pi OS.

2. **Connect to Network**: Ensure that the Raspberry Pi is connected to the same network as the Linux machines you want to back up.

3. **Install Necessary Packages**: You might need to install `rsync` and `ssh` if they are not already installed:

   ```bash
   sudo apt update
   sudo apt install rsync ssh
   ```

4. **Configure Storage**: Connect an external storage device to the Raspberry Pi (such as a USB hard drive or SSD) that will store the backups. Make sure it is formatted correctly and mounted.

### Step 2: Set Up SSH Keys (Optional but Recommended)

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

### Step 3: Create Backup Scripts on Linux Machines

1. On each Linux machine, create a script to back up files to the Raspberry Pi using `rsync`. For example:

   ```bash
   #!/bin/bash
   rsync -avz --delete /path/to/backup/ pi@raspberrypi.local:/path/to/destination/
   ```

   - `/path/to/backup/` is the directory you want to back up.
   - `pi@raspberrypi.local:/path/to/destination/` is the destination directory on your Raspberry Pi.

2. Make the script executable:

   ```bash
   chmod +x /path/to/script.sh
   ```

### Step 4: Automate the Backups

Set up a cron job on each Linux machine to run the backup script at regular intervals:

1. Edit the crontab:

   ```bash
   crontab -e
   ```

2. Add a line to schedule your backup script. For example, to run the backup daily at 2 AM:

   ```bash
   0 2 * * * /path/to/script.sh
   ```

### Considerations

- **Network Bandwidth**: Backups can consume significant network bandwidth. Consider scheduling them during off-peak hours.

- **Storage Capacity**: Ensure your Raspberry Pi has enough storage capacity to hold the backups from all machines.

- **Backup Integrity**: Regularly check the integrity of your backups.

- **Security**: Ensure that your network is secure, especially if you are using SSH key-based authentication.

- **Backup Strategy**: Decide on a backup strategy (full, incremental, differential) based on your needs.
