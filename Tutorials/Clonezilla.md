# Clonezilla

Clonezilla is a free, open-source disk imaging and cloning tool. It can be used to create a complete snapshot of your entire hard drive, including the operating system, installed programs, settings, and files.

<br>

## Requirements

- A USB drive with at least 4GB of space to create a bootable Clonezilla drive.
- An external hard drive or network location to save the image.
- A computer running Windows.

<br>

### Step 1: Create a Bootable Clonezilla USB

1. **Download Clonezilla**: Visit the Clonezilla website and download the ISO file for Clonezilla Live.
2. **Create Bootable USB**: Use a tool like Rufus or balenaEtcher to create a bootable USB drive with the Clonezilla ISO.
   - Launch the tool, select the Clonezilla ISO, and choose your USB drive as the destination.
   - Start the process and wait until it's completed.

<br>

### Step 2: Prepare Your Computer

1. **Backup Important Data**: Always backup important files separately as an extra precaution.
2. **Connect External Drive**: Connect the external hard drive or ensure network connectivity for storing the image.
3. **Restart Computer with USB**: Restart your computer and boot from the Clonezilla USB drive. This might require entering the BIOS or UEFI settings to change the boot order.

<br>

### Step 3: Using Clonezilla to Create the Image

1. **Boot into Clonezilla**: Choose “Clonezilla Live (Default settings)” from the boot menu.
2. **Language and Keyboard**: Select your preferred language and keyboard layout.
3. **Start Clonezilla**: Choose “Start Clonezilla” to enter the disk cloning process.
4. **Select Mode**: Choose “device-image” to create an image of your hard drive.
5. **Choose Image Repository**: Select where to save the image (local drive, SSH server, Samba server, etc.).
6. **Select Source Disk**: Choose the hard drive you want to image.
7. **Image Naming and Options**:
   - Name your image for easy identification.
   - Choose compression options (if needed).
   - Select any advanced parameters (expert users).

<br>

### Step 4: Start the Imaging Process

1. **Confirm and Begin**: Review your selections and confirm to start the imaging process.
2. **Monitor the Process**: Clonezilla will show progress. This can take time depending on the size of your hard drive and the speed of your computer and storage media.

<br>

### Step 5: Completing the Process

1. **Completion**: Once done, you will receive a message stating the process is complete.
2. **Shutdown or Reboot**: Safely shutdown or reboot your computer.
3. **Remove USB Drive**: Remove the Clonezilla USB drive after shutting down.

<br>

### Tips and Best Practices

- **Verify Image**: After creating the image, it's a good practice to verify its integrity.
- **Regular Imaging**: Regularly image your drive to keep the backup updated.
- **Safe Storage**: Store the external hard drive in a safe place to avoid physical damage.
- **Documentation**: Keep a record of when the image was created and its contents for easy reference.

<br>

### Troubleshooting

- **Boot Issues**: If you have trouble booting from the USB, check your BIOS/UEFI settings.
- **Storage Space**: Ensure your external drive has enough space for the image.
- **Compatibility**: Some newer hardware might have compatibility issues with Clonezilla. Check the Clonezilla website for the latest version and support information.
