# Install OpenWRT in VirtualBox VM

Learn how to install OpenWRT in a VirtualBox virtual machine step by step.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Objectives](#objectives)
- [Prerequisites](#prerequisites)
- [Steps](#steps)
  - [Download and Prepare the OpenWRT Image](#download-and-prepare-the-openwrt-image)
  - [Create a New Virtual Machine in VirtualBox](#create-a-new-virtual-machine-in-virtualbox)
  - [Configure the VM](#configure-the-vm)
  - [Start the VM and Configure OpenWRT](#start-the-vm-and-configure-openwrt)
  - [Access the Web Interface](#access-the-web-interface)
- [Additional Tips](#additional-tips)
- [Notes](#notes)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

This tutorial provides a comprehensive guide to installing OpenWRT in a VirtualBox virtual machine, configuring it, and accessing its web interface.

<br>

## **Objectives**

By the end of this tutorial, you will:

- Learn how to download and prepare the OpenWRT image.
- Be able to set up a VirtualBox virtual machine for OpenWRT.
- Understand how to configure and access OpenWRT's features.

<br>

## **Prerequisites**

To follow this tutorial, you should:

- Have VirtualBox installed on your system.
- Be familiar with basic command-line operations.
- Have sufficient system resources to create and run a virtual machine.

<br>

## **Steps**

### **Download and Prepare the OpenWRT Image**

| Step                                | Description                                                                 | Command/Example                          |
|-------------------------------------|-----------------------------------------------------------------------------|------------------------------------------|
| Download OpenWRT image              | Visit the [OpenWRT downloads page](https://downloads.openwrt.org/releases/) and download the x86/64 image. | `openwrt-19.07.6-x86-64-combined-ext4.img` |
| Convert image to VDI format         | Use `vboxmanage` to convert the image to VDI format.                       | `vboxmanage.exe convertdd <input> <output>` |
| Resize the VDI file                 | Resize the VDI file for more storage space (e.g., 512 MB).                 | `vboxmanage.exe modifyhd --resize 512 <file>` |

<br>

### **Create a New Virtual Machine in VirtualBox**

| Step                                | Description                                                                 | Example                                  |
|-------------------------------------|-----------------------------------------------------------------------------|------------------------------------------|
| Launch VirtualBox                   | Open Oracle VM VirtualBox.                                                 | N/A                                      |
| Create a new VM                     | Fill in the details: name, type, version, and memory size.                 | `Name: OpenWRT, Memory: 128 MB`         |
| Move the VDI file                   | Move the `openwrt.vdi` file to the VM folder.                              | `C:\VMs\OpenWRT`                       |

<br>

### **Configure the VM**

| Step                                | Description                                                                 | Example                                  |
|-------------------------------------|-----------------------------------------------------------------------------|------------------------------------------|
| Add storage attachment              | Add the `openwrt.vdi` file to the VM's storage settings.                   | Use VirtualBox UI                        |
| Configure network adapters          | Set network adapters for bridged mode.                                     | Adapter 1: Bridged, Adapter 2: Bridged   |

<br>

### **Start the VM and Configure OpenWRT**

| Step                                | Description                                                                 | Command/Example                          |
|-------------------------------------|-----------------------------------------------------------------------------|------------------------------------------|
| Start the VM                        | Start the virtual machine in VirtualBox.                                   | Use VirtualBox UI                        |
| Set root password                   | Set a password for the root user.                                          | `passwd`                                 |
| Configure network and install Luci  | Set LAN IP, restart network, update packages, and install Luci.            | `uci set network.lan.ipaddr='192.168.0.251'` <br> `service network restart` <br> `opkg update` <br> `opkg install luci` |

<br>

### **Access the Web Interface**

| Step                                | Description                                                                 | Example                                  |
|-------------------------------------|-----------------------------------------------------------------------------|------------------------------------------|
| Open a browser                      | Access OpenWRT's web interface using its LAN IP address.                   | `http://192.168.0.251`                   |
| Log in                              | Use the root username and the password set earlier.                        | Username: `root`, Password: `<your_pass>`|

<br>

## **Additional Tips**

- **VirtualBox Version**: Ensure your VirtualBox is up to date for compatibility.
- **Backup**: Regularly backup your VM to prevent data loss.
- **Documentation**: Refer to OpenWRT and VirtualBox documentation for detailed configurations.

<br>

## **Notes**

- **Pro Tip**: Allocate sufficient memory and storage to ensure smooth operation.
- **Warning**: Misconfigured network settings can lead to connectivity issues.

<br>

## **Resources**

- [OpenWRT Downloads Page](https://downloads.openwrt.org/releases/)
- [VirtualBox Documentation](https://www.virtualbox.org/manual/)
- [OpenWRT Official Documentation](https://openwrt.org/docs/start)

<br>

## **Contribution**

Your contributions are highly encouraged to enhance this guide:

- Fork the repository.
- Create a new branch:

    ```bash
    git checkout -b my-awesome-feature
    ```

- Make your valuable changes.
- Commit your changes:

    ```bash
    git commit -am 'Added some amazing features'
    ```

- Push to the branch:

    ```bash
    git push origin my-awesome-feature
    ```

- Create a new Pull Request targeting the `Notes` directory.

Contributions are welcome! Feel free to open issues, suggest enhancements, or submit pull requests to improve this guide.

<br>

## **Author**

- **Raphael Chookagian** | [GitHub Profile](https://github.com/cesar-group)

## **Date of Latest Revision**

- 12/10/2024

## **License**

- This guide is provided as-is without any warranties. Users are advised to review and understand the guide before executing any commands.

- This project is licensed under the MIT License. See the LICENSE file for details.
