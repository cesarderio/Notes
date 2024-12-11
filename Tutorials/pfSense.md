![Pfsense](../assets/PfSense_logo.png)

# Setting Up pfSense Router in VirtualBox

Learn how to set up a pfSense router in a VirtualBox virtual machine step by step.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Objectives](#objectives)
- [Prerequisites](#prerequisites)
- [Steps](#steps)
  - [Download pfSense](#download-pfsense)
  - [Prepare VirtualBox](#prepare-virtualbox)
  - [Configure Network Adapters](#configure-network-adapters)
  - [Mount pfSense ISO](#mount-pfsense-iso)
  - [Install pfSense](#install-pfsense)
  - [Initial Setup of pfSense](#initial-setup-of-pfsense)
  - [Access pfSense Web Interface](#access-pfsense-web-interface)
- [Additional Tips](#additional-tips)
- [Notes](#notes)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

This tutorial provides a comprehensive guide to setting up a pfSense router in a VirtualBox virtual machine, configuring it, and accessing its web interface for advanced network management.

<br>

## **Objectives**

By the end of this tutorial, you will:

- Learn how to download and prepare the pfSense ISO.
- Be able to set up a VirtualBox virtual machine for pfSense.
- Understand how to configure and access pfSense's features.

<br>

## **Prerequisites**

To follow this tutorial, you should:

- Have VirtualBox installed on your system.
- Be familiar with basic command-line operations.
- Have sufficient system resources to create and run a virtual machine.

<br>

## **Steps**

### **Download pfSense**

| Step                          | Description                                                                 | Example                                  |
|-------------------------------|-----------------------------------------------------------------------------|------------------------------------------|
| Download pfSense ISO          | Visit the [pfSense download page](https://www.pfsense.org/download/) and download the latest stable release ISO. | `pfSense-CE-2.5.2-RELEASE-amd64.iso` |

<br>

### **Prepare VirtualBox**

| Step                          | Description                                                                 | Example                                  |
|-------------------------------|-----------------------------------------------------------------------------|------------------------------------------|
| Launch VirtualBox             | Open Oracle VM VirtualBox.                                                 | N/A                                      |
| Create a new VM               | Fill in the details: name, type, version, and memory size.                 | `Name: pfSense Router, Type: BSD, Version: FreeBSD (64-bit)` |
| Allocate memory               | Allocate RAM for the VM.                                                   | `512 MB`                                 |
| Create a virtual hard disk    | Select VDI as the disk type and allocate 8 GB of space.                    | Use VirtualBox UI                        |

<br>

### **Configure Network Adapters**

| Step                          | Description                                                                 | Example                                  |
|-------------------------------|-----------------------------------------------------------------------------|------------------------------------------|
| Configure Adapter 1           | Attach to NAT network.                                                     | Adapter 1: NAT                          |
| Configure Adapter 2           | Attach to Internal Network or Host-Only.                                   | Adapter 2: Internal Network (e.g., intnet) |

<br>

### **Mount pfSense ISO**

| Step                          | Description                                                                 | Example                                  |
|-------------------------------|-----------------------------------------------------------------------------|------------------------------------------|
| Attach pfSense ISO            | Add the pfSense ISO file to the VM's storage settings.                     | Use VirtualBox UI                        |

<br>

### **Install pfSense**

| Step                          | Description                                                                 | Example                                  |
|-------------------------------|-----------------------------------------------------------------------------|------------------------------------------|
| Start the VM                  | Boot the VM and launch the pfSense installer.                              | Use VirtualBox UI                        |
| Follow installation steps     | Use the defaults or customize as needed during installation.               | Follow on-screen instructions            |
| Reboot the VM                 | Reboot after installation completes.                                       | Use VirtualBox UI                        |

<br>

### **Initial Setup of pfSense**

| Step                          | Description                                                                 | Example                                  |
|-------------------------------|-----------------------------------------------------------------------------|------------------------------------------|
| Assign interfaces             | Configure WAN (`em0`, NAT) and LAN (`em1`, Internal).                       | Follow on-screen instructions            |
| Note LAN IP address           | Record the LAN interface's IP address displayed by pfSense.                | `192.168.1.1`                            |

<br>

### **Access pfSense Web Interface**

| Step                          | Description                                                                 | Example                                  |
|-------------------------------|-----------------------------------------------------------------------------|------------------------------------------|
| Open a browser                | Navigate to the LAN IP address displayed by pfSense.                       | `http://192.168.1.1`                     |
| Log in                        | Use the default credentials to log in.                                     | Username: `admin`, Password: `pfsense`   |
| Complete setup wizard         | Configure firewall rules, NAT, and other settings as needed.               | Use pfSense Web Interface                |

<br>

## **Additional Tips**

- **Backup**: Regularly backup your VM to prevent data loss.
- **Documentation**: Refer to pfSense and VirtualBox documentation for detailed configurations.

<br>

## **Notes**

- **Pro Tip**: Allocate sufficient memory and storage to ensure smooth operation.
- **Warning**: Misconfigured network settings can lead to connectivity issues.

<br>

## **Resources**

- [pfSense Downloads Page](https://www.pfsense.org/download/)
- [VirtualBox Documentation](https://www.virtualbox.org/manual/)
- [pfSense Official Documentation](https://docs.netgate.com/pfsense/en/latest/)

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
