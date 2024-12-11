<img src="../assets/Virtualbox_logo.png" alt="Alt Text" width="400">

# VirtualBox Management & Commands

VBoxManage commands are used for managing VirtualBox VMs via the command line. These commands cover a wide range of functionalities, from creating and controlling VMs to adjusting network settings and managing disk images. This guide provides an overview of the most commonly used VBoxManage commands.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Commands](#commands)
  - [List Virtual Machines](#list-virtual-machines)
  - [Start a Virtual Machine](#start-a-virtual-machine)
  - [Power Off a Virtual Machine](#power-off-a-virtual-machine)
  - [Pause and Resume a Virtual Machine](#pause-and-resume-a-virtual-machine)
  - [Create a Virtual Machine](#create-a-virtual-machine)
  - [Modify VM Settings](#modify-vm-settings)
  - [Attach an ISO to VM](#attach-an-iso-to-vm)
  - [Create a Virtual Hard Disk](#create-a-virtual-hard-disk)
  - [Take and Restore Snapshots](#take-and-restore-snapshots)
  - [Delete a Virtual Machine](#delete-a-virtual-machine)
  - [Configure Network Settings](#configure-network-settings)
  - [Show VM Information](#show-vm-information)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

VBoxManage is a command-line interface for VirtualBox that provides powerful options for creating, managing, and configuring virtual machines. It is especially useful for automation and scripting purposes.

<br>

## **Commands**

### **List Virtual Machines**

- Command:

  ```bash
  VBoxManage list vms
  ```

  Lists all registered VMs.

<br>

### **Start a Virtual Machine**

- Start a VM in headless mode (without a GUI):

  ```bash
  VBoxManage startvm [vmname] --type headless
  ```

- Start a VM with a GUI:

  ```bash
  VBoxManage startvm [vmname] --type gui
  ```

<br>

### **Power Off a Virtual Machine**

- Command:

  ```bash
  VBoxManage controlvm [vmname] poweroff
  ```

  Powers off the specified VM.

<br>

### **Pause and Resume a Virtual Machine**

- Pause a VM:

  ```bash
  VBoxManage controlvm [vmname] pause
  ```

- Resume a paused VM:

  ```bash
  VBoxManage controlvm [vmname] resume
  ```

<br>

### **Create a Virtual Machine**

- Command:

  ```bash
  VBoxManage createvm --name [vmname] --register
  ```

  Creates a new VM with the specified name.

<br>

### **Modify VM Settings**

- Set the memory size:

  ```bash
  VBoxManage modifyvm [vmname] --memory [memorysize in MB]
  ```

- Set the number of CPUs:

  ```bash
  VBoxManage modifyvm [vmname] --cpus [number]
  ```

- Enable the VirtualBox Remote Desktop Extension:

  ```bash
  VBoxManage modifyvm [vmname] --vrde on
  ```

<br>

### **Attach an ISO to VM**

- Command:

  ```bash
  VBoxManage storageattach [vmname] --storagectl [controllername] --port 0 --device 0 --type dvddrive --medium [path/to/iso]
  ```

  Attaches an ISO file to the specified VM.

<br>

### **Create a Virtual Hard Disk**

- Command:

  ```bash
  VBoxManage createmedium disk --filename [path/to/vdi] --size [size in MB]
  ```

  Creates a new virtual hard disk file.

<br>

### **Take and Restore Snapshots**

- Take a snapshot:

  ```bash
  VBoxManage snapshot [vmname] take [snapshotname]
  ```

- Restore a snapshot:

  ```bash
  VBoxManage snapshot [vmname] restore [snapshotname]
  ```

<br>

### **Delete a Virtual Machine**

- Command:

  ```bash
  VBoxManage unregistervm [vmname] --delete
  ```

  Deletes the VM and all its associated files.

<br>

### **Configure Network Settings**

- Set the first network adapter to use NAT:

  ```bash
  VBoxManage modifyvm [vmname] --nic1 nat
  ```

<br>

### **Show VM Information**

- Command:

  ```bash
  VBoxManage showvminfo [vmname]
  ```

  Displays detailed information about the specified VM.

<br>

## **Resources**

- [VirtualBox Official Documentation](https://www.virtualbox.org/manual/UserManual.html)
- [VBoxManage Command Reference](https://www.virtualbox.org/manual/ch08.html)
- [VirtualBox Community Forums](https://forums.virtualbox.org/)



<br>

## **Contribution**

Your contributions can make these scripts even better:

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

- Create a new Pull Request targeting the Notes directory.

Contributions are welcome! Feel free to open issues, suggest enhancements, or submit pull requests to improve the script.

<br>

## **Author**

- **Raphael Chookagian** | [GitHub Profile](https://github.com/cesar-group)

## **Date of Latest Revision**

- 12/09/2024

## **License**

- This script is provided as-is without any warranties. Users are advised to review and understand the script before executing it.

- This project is licensed under the MIT License. See the LICENSE file for details.
