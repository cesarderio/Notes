# Installation

<br>

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

<br>

### Kernel:

- **Heart of the Linux OS**: The kernel manages and mediates interactions between hardware and software.
- **View kernel version details with `uname -a`**: This command displays detailed information about the kernel.
- **The kernel starts the "/sbin/init" process first**: This is the initial process started by the kernel, crucial for the boot process.

<br>

### Library Files:

- **Found under "/var/lib"**: This directory commonly contains library files.
- **In Linux, the color blue usually means it is a directory/subdirectory**: A visual cue in many command-line interfaces to distinguish directories.

<br>

### Configuration Files:

- **Found in /etc/**: This is a standard directory for system configuration files.
- **Normally text files editable with tools such as vi/vim or nano**: These are common text editors used in the Linux environment.
- **Most end in ".conf"**: A conventional extension for configuration files.
- **Changes to .conf files usually mean restarting the related daemon**: This is necessary for the daemon to read and apply the new configurations.
- **Some daemons allow you to "reload" them**: This can apply changes without needing a full restart.
- **Installed packages may have more than one config file**: Indicating multiple configuration aspects.

<br>

### Daemons:

- **Background running processes not tied to a user terminal**: They perform various tasks silently in the background.
- **Usually started by the system or service manager**: Similar to how Windows services operate.
- **Can be controlled with the "service" command**: For example, `service sshd status; service sshd start/stop` manages the SSH daemon.

<br>

### Command Line Shells:

- **Include Bash, Korn, C, zsh**: Different shells for user preference in scripting and command-line interaction.

<br>

### GUI:

- **Based on X-Windows**: A windowing system for bitmap displays.
- **Started with `startx` command**: This command initiates the graphical interface.
- **Remote X forwarding**: Allows GUI applications to be run on a remote server but displayed locally.

<br>

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

<br>

## BIOS, UEFI, and the Linux Startup Process:

<br>

### BIOS - Basic Input/Output System:
- BIOS is firmware on a chip on the motherboard, providing the first layer of interaction between the hardware and the OS.
- It initializes hardware components during the boot process.

<br>

### UEFI - Unified Extensible Firmware Interface:
- UEFI is the modern successor to BIOS.
- Offers features like secure boot, Trusted Platform Module (TPM) support, GUI-based configuration options, and support for larger disk sizes.

<br>

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

<br>

### DRACUT Utility:
- A tool that can be used to customize the Linux startup process, especially the initial ramdisk (initrd).

<br>

### Linux Startup Process:
- **Initializes BIOS or UEFI**: Checks system integrity and loads the Master Boot Record (MBR).
- **MBR loads GRUB**: The bootloader (GRUB, located at `/boot/grub/grub.cfg` on Ubuntu) presents the boot menu.
- **Kernel Loading**: After a menu entry is selected, GRUB loads the compressed Linux kernel (`vmlinuz`) and executes `mkinitrd` to prepare for mounting the root filesystem.
    - **vmlinuz**: The compressed Linux kernel.
    - **mkinitrd** (make initial RAM disk): Creates an initrd to mount the root filesystem.
- **Run `/sbin/init`**: The first process that the kernel starts, leading to the establishment of a temporary RAM disk (initrd) until the kernel is fully booted.
- **initrd**: Initializes a RAM disk used during the boot process.
- **Launch runlevel-configured programs**: Based on the target run level.

<br>

### TPM - Trusted Platform Module:
- A dedicated microcontroller designed for secure hardware cryptographic processing.
- Commonly built into server motherboards or available as an add-on.
- The Linux kernel can detect the presence of a TPM chip.
- Encryption tied to the TPM chip ensures that encrypted data is bound to the specific hardware.
- Removing an encrypted storage device prevents decryption or access when used on different hardware.
- The OS disk must be decrypted with the TPM before the OS boot continues.

<br>

### UEFI and Secure Boot:
- Secure Boot is a feature of UEFI firmware.
- Ensures that only trusted software with a valid digital signature is loaded during the boot process.
- Can be disabled for older OS versions or dual-boot configurations.

<br>

## Linux Installation Sources:

<br>

### Manual Installations:
- **ISO DVD Image**: Installing Linux from an ISO image burned to a DVD.
- **Installation Files from Local or Network Storage**: Using local or networked media to install Linux.
- **Preboot Execution Environment (PXE) Boot**: Network-based installation method that loads installation files from a server.

<br>

### Automated Installations:
- **Pre-installed Virtual Machine**: Linux pre-installed on a virtual machine image.
- **Scripted Installation**: Automated installation process using scripts.
- **PXE Boot**: Automated network boot and installation.
- **Apply OS Image**: Deployment of a pre-configured Linux OS image.
- **Cloud Template (Infrastructure as Code)**: Using cloud templates for automated deployment, often part of an Infrastructure as Code strategy.

Specific Installation Methods for Distros:
- **Ubuntu**: Utilizing an *autoinstall config file* for automated installations.
- **Red Hat Enterprise Linux (RHEL)**: Employing a *Kickstart automation file* for streamlined installation processes.

<br>

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

<br>

### Local Linux Installation:
- **With or Without Scripted Files, Additional Software Packages, and Device Drivers**: Options for a customized installation.
- **Installation from Hard Disk, USB-Attached Storage**: Using local storage media for installation, which can include automated installation files.

<br>

### PXE - Preboot Execution Environment Boot Installation:
- **Enable PXE in BIOS**: Necessary step to allow network boot.
- **PXE and DHCP Integration**: PXE uses DHCP to obtain network configuration details.
- **Network Boot Process**: The device boots from its network card firmware and performs a DHCP broadcast to acquire IP configuration, even before the OS is installed.
- **Communication with PXE Server**: After network configuration, the device communicates with the PXE server.
- **Completing Linux Installation via PXE**: The installation can be manual or scripted, with the option to apply a specific Linux OS image.

<br>

## Installing a Linux Server

- **Choosing Installation Media**: Various distributions of Linux are available, each tailored for server use. The choice depends on the server's intended role and the user's preference.
    - Examples of server-focused distributions include Ubuntu Server, CentOS (now succeeded by Rocky Linux and AlmaLinux), and Debian Server.
- **Installation Process**: The installation process typically involves setting up network configurations, disk partitioning, and selecting packages relevant to the server's intended role.
- **Post-Installation Configuration**: After installation, server-specific configurations like setting up network services, firewalls, and user accounts are crucial.

<br>

## Installing a Linux Desktop

- **Selecting a Distribution**: Desktop distributions are designed for ease of use and typically come with a graphical user interface. Popular choices include Ubuntu, Fedora, and Linux Mint.
- **Installation Steps**: The process usually includes creating a bootable USB drive, partitioning the hard drive, and going through a guided setup.
- **Post-Installation**: Users can customize their desktop environment, install additional software, and configure system settings for personal use.

<br>

## Deploying a Cloud-Based Linux Server

- **Choosing a Cloud Provider**: Options include AWS, Azure, Google Cloud Platform, and other cloud services offering Linux server instances.
- **Instance Setup**: Involves selecting the server size (CPU, memory, storage), choosing the Linux distribution, and configuring network settings such as IP addresses and security groups.
- **Access and Management**: Once deployed, cloud-based Linux servers are typically managed remotely via SSH. Additional tools like Ansible, Puppet, or Chef can be used for configuration management.
- **Scalability and Maintenance**: One of the advantages of cloud-based servers is the ease of scaling resources as per demand. Regular updates and security patches are essential for maintaining server health and security.
