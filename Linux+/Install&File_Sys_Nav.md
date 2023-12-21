# Installation & File System Navigation

## Linux Overview:

- **Linux based on Unix**: Linux is a Unix-like operating system, sharing similar concepts and design philosophy.
- **Developed by Linus Torvalds in the early 1990s**: Created as an open-source alternative to Unix.
- **Many different flavors (distros)**: Varieties of Linux, each with unique features and designs, are available.
- **Used in servers, workstations, desktops, and GUI environments**: Linux is versatile, suitable for various applications from server environments to graphical user interfaces.

- **Consists of key components**:
    - ***Kernel***: Referred to as the "Heart" of Linux, it's the core part of the OS, managing system resources and hardware.
    - ***Libraries***: These are "Shared Libraries" or "Library Files" that provide common code that can be used by multiple programs.
    - ***Configuration Files***: These files store system and application settings.
    - ***Daemons***: These are "Background running programs", similar to services in Windows, performing tasks in the background.
    - ***Command line shells and GUI***: Interfaces for interacting with the system, including both command line interfaces like Bash and graphical interfaces.

### Kernel:

- **Heart of the Linux OS**: The kernel manages and mediates interactions between hardware and software.
- **View kernel version details with `uname -a`**: This command displays detailed information about the kernel.
- **The kernel starts the "/sbin/init" process first**: This is the initial process started by the kernel, crucial for the boot process.

### Library Files:

- **Found under "/var/lib"**: This directory commonly contains library files.
- **In Linux, the color blue usually means it is a directory/subdirectory**: A visual cue in many command-line interfaces to distinguish directories.

### Configuration Files:

- **Found in /etc/**: This is a standard directory for system configuration files.
- **Normally text files editable with tools such as vi/vim or nano**: These are common text editors used in the Linux environment.
- **Most end in ".conf"**: A conventional extension for configuration files.
- **Changes to .conf files usually mean restarting the related daemon**: This is necessary for the daemon to read and apply the new configurations.
- **Some daemons allow you to "reload" them**: This can apply changes without needing a full restart.
- **Installed packages may have more than one config file**: Indicating multiple configuration aspects.

### Daemons:

- **Background running processes not tied to a user terminal**: They perform various tasks silently in the background.
- **Usually started by the system or service manager**: Similar to how Windows services operate.
- **Can be controlled with the "service" command**: For example, `service sshd status; service sshd start/stop` manages the SSH daemon.

### Command Line Shells:

- **Include Bash, Korn, C, zsh**: Different shells for user preference in scripting and command-line interaction.

### GUI:

- **Based on X-Windows**: A windowing system for bitmap displays.
- **Started with `startx` command**: This command initiates the graphical interface.
- **Remote X forwarding**: Allows GUI applications to be run on a remote server but displayed locally.

## Linux Distributions:

- **Distros are variants of the Linux OS**: These are different versions of Linux, each with unique characteristics and designed for various purposes.
- **Based on Debian, Red Hat, and SUSE**: These are the foundational families from which many distros derive. Each family offers a different approach and package management system.
- **Specialized for different sectors**: Some distros are tailored for specific uses, such as industrial applications, multimedia production, or security and penetration testing.
- **Why So Many different distros?**: The Linux Kernel is open-source and free, allowing for the development of an entire OS without licensing costs. This freedom encourages innovation and customization.
- **Many new distributions are based on existing ones**: It's common to build new distros by modifying and adapting existing ones.
- **Variations in GUI and software packages**: Distros can differ significantly in their user interface (e.g., GNOME vs. KDE) and the software packages they include by default.

Examples of Distros:
- **Debian**: Known for its stability and large software repository.
- **Ubuntu**: Popular for its ease of use and strong community support.
- **Fedora**: Known for featuring cutting-edge technology.
- **Arch Linux**: Appeals to experienced users who prefer a do-it-yourself approach.
- **Peppermint**: Lightweight and user-friendly, suitable for older hardware.
- **Kali Linux**: Specialized for penetration testing and security auditing.
- **CentOS**: Favored for servers due to its stability and long-term support.
- **Pop!_OS**: Developed by System76, optimized for their hardware but usable on others.

Specialized Distros:
- **Kali Linux**: Focused on Penetration Testing and security.
- **64Studio**: Tailored for Video & Media Production.
- **AsteroidOS**: Designed for smartwatches.
- **Audiophile**: Optimized for high-quality music playback.
- **Apertis**: Developed for vehicle infotainment systems.
- **Raspbian**: Customized for Raspberry Pi devices.

----------------------------------------------------------------------------------

## BIOS, UEFI, and the Linux Startup Process:

### BIOS - Basic Input/Output System:
- BIOS is firmware on a chip on the motherboard, providing the first layer of interaction between the hardware and the OS.
- It initializes hardware components during the boot process.

### UEFI - Unified Extensible Firmware Interface:
- UEFI is the modern successor to BIOS.
- Offers features like secure boot, Trusted Platform Module (TPM) support, GUI-based configuration options, and support for larger disk sizes.

### Linux Run Levels:
- **0**: Power off
- **1**: Rescue/emergency single-user mode, typically for root/administrative access
- **3**: Multi-user mode without a graphical user interface, commonly used for servers
- **5**: Multi-user mode with a graphical user interface
- **6**: Reboot

Commands:
- View current run level: `runlevel`
- Reboot the system: `sudo init 6`
- Shutdown the system: `sudo init 0`

Scripts:
- **S** (Start script): Scripts that start services.
- **K** (Kill script): Scripts that stop services.

### DRACUT Utility:
- A tool that can be used to customize the Linux startup process, especially the initial ramdisk (initrd).

### Linux Startup Process:
- **Initializes BIOS or UEFI**: Checks system integrity and loads the Master Boot Record (MBR).
- **MBR loads GRUB**: The bootloader (GRUB, located at `/boot/grub/grub.cfg` on Ubuntu) presents the boot menu.
- **Kernel Loading**: After a menu entry is selected, GRUB loads the compressed Linux kernel (`vmlinuz`) and executes `mkinitrd` to prepare for mounting the root filesystem.
    - **vmlinuz**: The compressed Linux kernel.
    - **mkinitrd** (make initial RAM disk): Creates an initrd to mount the root filesystem.
- **Run `/sbin/init`**: The first process that the kernel starts, leading to the establishment of a temporary RAM disk (initrd) until the kernel is fully booted.
- **initrd**: Initializes a RAM disk used during the boot process.
- **Launch runlevel-configured programs**: Based on the target run level.

### TPM - Trusted Platform Module:
- A dedicated microcontroller designed for secure hardware cryptographic processing.
- Commonly built into server motherboards or available as an add-on.
- The Linux kernel can detect the presence of a TPM chip.
- Encryption tied to the TPM chip ensures that encrypted data is bound to the specific hardware.
- Removing an encrypted storage device prevents decryption or access when used on different hardware.
- The OS disk must be decrypted with the TPM before the OS boot continues.

### UEFI and Secure Boot:
- Secure Boot is a feature of UEFI firmware.
- Ensures that only trusted software with a valid digital signature is loaded during the boot process.
- Can be disabled for older OS versions or dual-boot configurations.


## Linux Installation Sources:

### Manual Installations:
- **ISO DVD Image**: Installing Linux from an ISO image burned to a DVD.
- **Installation Files from Local or Network Storage**: Using local or networked media to install Linux.
- **Preboot Execution Environment (PXE) Boot**: Network-based installation method that loads installation files from a server.

### Automated Installations:
- **Pre-installed Virtual Machine**: Linux pre-installed on a virtual machine image.
- **Scripted Installation**: Automated installation process using scripts.
- **PXE Boot**: Automated network boot and installation.
- **Apply OS Image**: Deployment of a pre-configured Linux OS image.
- **Cloud Template (Infrastructure as Code)**: Using cloud templates for automated deployment, often part of an Infrastructure as Code strategy.

Specific Installation Methods for Distros:
- **Ubuntu**: Utilizing an *autoinstall config file* for automated installations.
- **Red Hat Enterprise Linux (RHEL)**: Employing a *Kickstart automation file* for streamlined installation processes.

### Linux Installation Details:
- **Language and Keyboard Layout**: Setting up preferred language and keyboard configurations.
- **Installation Type (Full/Minimal)**: Choosing between a full installation or a minimal setup.
- **Third-Party Device Drivers**: Installing drivers for non-standard or specialized hardware.
- **Network Connectivity**: Configuring network settings during installation.
- **Mass Storage Configuration**: Setting up storage devices and partitions.
- **User Credentials**: Creating usernames and passwords.
- **Additional Software Packages**: Selecting extra software to install.
- **Updates**: Configuring settings for receiving system updates.
- **HWE Kernel**: Installing the Hardware Enablement (HWE) kernel for improved hardware support, especially important for third-party drivers and software.

### Local Linux Installation:
- **With or Without Scripted Files, Additional Software Packages, and Device Drivers**: Options for a customized installation.
- **Installation from Hard Disk, USB-Attached Storage**: Using local storage media for installation, which can include automated installation files.

### PXE - Preboot Execution Environment Boot Installation:
- **Enable PXE in BIOS**: Necessary step to allow network boot.
- **PXE and DHCP Integration**: PXE uses DHCP to obtain network configuration details.
- **Network Boot Process**: The device boots from its network card firmware and performs a DHCP broadcast to acquire IP configuration, even before the OS is installed.
- **Communication with PXE Server**: After network configuration, the device communicates with the PXE server.
- **Completing Linux Installation via PXE**: The installation can be manual or scripted, with the option to apply a specific Linux OS image.

Your notes on "Installing a Linux Server," "Installing a Linux Desktop," and "Deploying a Cloud-Based Linux Server" are brief and appear to be outlines or placeholders for more detailed information. I'll expand on these sections while preserving the structure of your notes, providing more detail and context:

---

## Installing a Linux Server

- **Choosing Installation Media**: Various distributions of Linux are available, each tailored for server use. The choice depends on the server's intended role and the user's preference.
    - Examples of server-focused distributions include Ubuntu Server, CentOS (now succeeded by Rocky Linux and AlmaLinux), and Debian Server.
- **Installation Process**: The installation process typically involves setting up network configurations, disk partitioning, and selecting packages relevant to the server's intended role.
- **Post-Installation Configuration**: After installation, server-specific configurations like setting up network services, firewalls, and user accounts are crucial.

## Installing a Linux Desktop

- **Selecting a Distribution**: Desktop distributions are designed for ease of use and typically come with a graphical user interface. Popular choices include Ubuntu, Fedora, and Linux Mint.
- **Installation Steps**: The process usually includes creating a bootable USB drive, partitioning the hard drive, and going through a guided setup.
- **Post-Installation**: Users can customize their desktop environment, install additional software, and configure system settings for personal use.

## Deploying a Cloud-Based Linux Server

- **Choosing a Cloud Provider**: Options include AWS, Azure, Google Cloud Platform, and other cloud services offering Linux server instances.
- **Instance Setup**: Involves selecting the server size (CPU, memory, storage), choosing the Linux distribution, and configuring network settings such as IP addresses and security groups.
- **Access and Management**: Once deployed, cloud-based Linux servers are typically managed remotely via SSH. Additional tools like Ansible, Puppet, or Chef can be used for configuration management.
- **Scalability and Maintenance**: One of the advantages of cloud-based servers is the ease of scaling resources as per demand. Regular updates and security patches are essential for maintaining server health and security.


## Managing Linux Hardware

- **ls /dev**: 
   - This command lists the contents of the `/dev` directory, which is a standard part of the Linux Filesystem hierarchy. 
   - This directory is present in all Linux distributions and contains device files representing hardware components.
   - Common device files include `cdrom` for optical drives, `usb` for USB devices, and `sda`, `sdb`, etc., for storage devices.

- **ls /dev/sd?**:
   - This command displays all the mass storage devices recognized by the system, such as hard drives and SSDs.

- **Installing Specialized Drivers**:
   - To install specific hardware drivers, use package management commands. For example, `sudo apt install nvidia-kernel-***` installs Nvidia drivers on Debian-based distributions.

- **ls /proc**:
   - The `/proc` directory contains a pseudo-filesystem that provides an interface to kernel data structures. It is dynamic, reflecting the current state of the kernel.
   - It includes information about processes and system information.

- **cat /proc/cpuinfo**:
   - This command displays detailed information about the CPU, such as its type, make, model, and performance metrics.

- **ls /proc/bus/pci**:
   - Lists PCI bus information, showing what PCI devices are currently recognized by the system.

- **cat /proc/bus/pci/devices**:
   - Displays detailed information about the devices connected to the PCI bus.

- **lspci**:
   - The command `lspci` lists all PCI devices. 
   - Using `lspci -v` provides verbose output, showing more detailed information.
   - Piping it to `more`, as in `lspci -v | more`, allows you to view the information one screenful at a time for easier reading.

- **lsusb -v**:
   - Lists USB devices in verbose mode, showing detailed information about each connected USB device.

- **DMI (Desktop Management Interface)**:
   - Provides BIOS or UEFI information.
   - The command `sudo dmidecode` accesses this information and displays it in a readable format.


## Using Linux File System Navigation Commands

- **pwd**: 
   - Stands for "print working directory." 
   - This command displays the current directory you are in.

- **cd /etc**: 
   - Changes the current directory to the `/etc` directory.
   - `/etc` typically contains configuration files and directories.

- **cd**:
   - Typing `cd` alone will change the directory to your home directory.

- **ls**: 
   - Lists the contents of a directory.
   - Similar to the `dir` command in Windows.

- **Directory and File Color Coding in Ubuntu**:
   - Blue highlighted words usually represent subdirectories.
   - Green indicates executable files.
   - Plain text typically denotes regular files.

- **ls -l** and **ll**: 
   - Both commands provide a long listing format of directory contents, showing detailed information like permissions, ownership, size, and modification date.

- **Understanding Permissions and Ownership**:
   - "d" indicates a directory.
   - A blank space indicates a regular file.
   - The third column shows the user who owns the file.
   - The fourth column shows the group that owns the file.
   - Permissions are indicated numerically (Read = 4, Write = 2, Execute = 1).

- **ls -a**: 
   - Lists all files in the directory, including hidden files (those starting with a dot).

- **mkdir**:
   - Creates a new directory.
   - `mkdir scripts/notes -p` creates the specified path, including any necessary parent directories.

- **..** (Double Dot):
   - Represents the parent directory.
   - Used to navigate up one level in the directory hierarchy.

- **cp**: 
   - Copies files and directories.

- **touch**: 
   - Creates new, empty files.

- **Terminal Editors**:
   - Includes `nano`, `vi`, and `vim`, which are common text editors in Linux.

- **mv**: 
   - Moves or renames files and directories.
   - `mv ../dataset1 .` moves `dataset1` from one level up to the current directory.

- **rmdir**: 
   - Removes directories, but only if they are empty.

- **rm -r**:
   - Removes directories and their contents recursively.
   - `rm -r ./directorydataset` removes the specified directory and all its subdirectories and files.

- **rm -f**:
   - Forces the removal of files or directories without prompting for confirmation.


## Navigating the Linux File System

- **pwd**: 
   - Displays the current working directory.

- **cd**: 
   - Changes the current directory to another directory.

- **ls -l or ll**: 
   - Lists the contents of a directory in long format, showing detailed information.

- **ls b***: 
   - Lists all files and directories starting with the letter 'b'.

- **ls -d b***: 
   - Lists directories starting with 'b' without showing their contents.

- **lsblk**: 
   - Lists all block devices (like hard drives and USB drives) connected to the system.

- **lsblk --scsi**: 
   - Specifically lists SCSI block devices.

- **fdisk**: 
   - A utility to view and manage disk partitions.
   - `sudo fdisk /dev/sda1 -l`: Lists the partitions on the `/dev/sda1` drive.

- **mount**: 
   - Manages mounted filesystems.
   - Filesystems are attached to a directory tree at the mount point.
   - `mount | grep boot`: Searches for the mount point of the boot partition.

- **Disk Space Utilization Commands**:
   - **df**: Displays information about the disk space usage of mounted filesystems.
      - `df -h`: Shows the disk space usage in human-readable format (e.g., MB, GB).
   - **du**: Provides disk usage of files and directories.
      - `du -h`: Shows the disk usage in a human-readable format.
      - `du -sh * | sort -hr`: Summarizes disk usage of each item in the current directory and sorts them in human-readable format, largest first.

## Searching the Linux File System

- **find**: 
   - A powerful command used to search for files and directories within the file system based on various criteria.
   - `sudo find / -name "[Bb]udget*"`: Searches the entire file system for files or directories whose names start with 'Budget' or 'budget'.
   - `sudo find / -name "[Bb]udget*" -user user1`: Narrows the search to files or directories named 'Budget' or 'budget' and owned by 'user1'.

- **Redirection Operators**:
   - `>`: Redirects output to a file or another command.
   - `2>`: Redirects standard error to a file or another command.
   - `2>/dev/null`: Redirects standard error to `/dev/null`, effectively discarding any error messages.

- **Specific Searches with find**:
   - `sudo find / -type d -name apache2`: Searches for directories named 'apache2'.
   - `sudo find / -type f -perm 0740`: Finds files with specific permissions (in this case, files where the user has read, write, and execute permissions; the group has read permissions; and others have no permissions).

- **locate**:
   - A command that uses a database of indexed files to quickly locate files.
   - Typically faster than `find` as it searches through a pre-built database rather than the file system.
   - May require installation: `sudo apt install plocate`.
   - `ls /var/lib/plocate`: Lists the contents of the directory where the `locate` database files are stored.
   - `sudo updatedb`: Updates the `locate` database to reflect the current state of the file system.
   - `locate mysql`: Searches for all files related to 'mysql'.

## Filtering Data with Linux Commands

### grep:
- **grep**: A powerful tool used for searching text data sets for lines that match a given pattern.
- **Examples**:
  - `cat cities.txt | grep -i london`: Searches for 'london' in `cities.txt`, ignoring case.
  - `grep -i london < cities.txt`: Directs the content of `cities.txt` into `grep` to search for 'london', ignoring case.
  - `grep -i london *`: Searches for 'london' in all files in the current directory, ignoring case.

### sed:
- **sed**: A stream editor used for performing basic text transformations on an input stream (a file or input from a pipeline).
- **Examples**:
  - `sed 's/London/Liverpool/' customers.txt`: Replaces the first instance of 'London' with 'Liverpool' in each line of `customers.txt`, but only in the command line output.
  - `sed 's/London/Liverpool/' customers.txt > new_customers.txt`: Performs the same substitution and writes the output to `new_customers.txt`.

### awk:
- **awk**: A powerful programming language designed for text processing and typically used for data extraction and reporting.
- **Examples**:
  - `awk '{print $2, $3}' customers.txt`: Prints the 2nd and 3rd fields (columns) from each line in `customers.txt`.
  - `awk '{print NR, $0}' customers.txt`: Prints each line in `customers.txt` with its line number.
  - `awk -F: '{print $1}' /etc/passwd`: Splits lines in `/etc/passwd` by colon (`:`) and prints the first field, typically the username.
