<!-- <img src="../assets/wclt.png" alt="Windows Command Line and SMB Ports" width="400"> -->

# Navigating Windows Command Line Tools and Understanding SMB Ports

Explore the essential concepts of SMB ports and master critical Windows command line tools for effective system management and troubleshooting.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Objectives](#objectives)
- [Prerequisites](#prerequisites)
- [Steps](#steps)
  - [Understanding SMB Ports](#understanding-smb-ports)
    - [Port 445: SMB over TCP/IP](#port-445-smb-over-tcpip)
    - [Port 139: SMB over NetBIOS](#port-139-smb-over-netbios)
  - [Windows Command Line Tools](#windows-command-line-tools)
    - [Using `chkdsk.exe`](#using-chkdskexe)
    - [Using `regedit.exe`](#using-regeditexe)
    - [Using `sfc.exe` (System File Checker)](#using-sfcexe-system-file-checker)
  - [Multimedia Learning Resource](#multimedia-learning-resource)
- [Examples](#examples)
- [Notes](#notes)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

Understanding the Server Message Block (SMB) protocol and its associated ports, as well as key Windows command line tools, is essential for IT professionals. These skills enable effective network communication, troubleshooting, and system management.

<br>

## **Objectives**

By the end of this tutorial, you will:

- Understand the role and importance of SMB ports (445 and 139).
- Learn how to use essential Windows command line tools for system maintenance.
- Gain confidence in diagnosing and resolving system and network issues.

<br>

## **Prerequisites**

To follow this tutorial, you should:

- Have a Windows-based computer with administrator privileges.
- Basic knowledge of networking and command line interfaces.
- Internet access to watch the recommended video for deeper insights.

<br>

## **Steps**

### **Understanding SMB Ports**

#### **Port 445: SMB over TCP/IP**

- **Purpose**: Facilitates SMB communication directly over TCP/IP without NetBIOS.
- **Significance**: Used in modern networks for file and printer sharing.
- **Security Tip**: Always secure Port 445 with a firewall to prevent unauthorized access over the internet.

#### **Port 139: SMB over NetBIOS**

- **Purpose**: Supports older SMB implementations that rely on NetBIOS.
- **Significance**: Common in legacy systems but largely phased out in favor of Port 445.
- **Security Tip**: Disable NetBIOS over TCP/IP on modern systems to minimize attack vectors.

---

### **Windows Command Line Tools**

#### **Using `chkdsk.exe`**

| Command                   | Description                                              | Example                                |
|---------------------------|----------------------------------------------------------|----------------------------------------|
| `chkdsk C:`               | Checks the C: drive for file system errors.              | `chkdsk C:`                            |
| `chkdsk /f`               | Fixes detected errors on the specified drive.            | `chkdsk /f C:`                         |
| `chkdsk /r`               | Locates bad sectors and recovers readable information.   | `chkdsk /r D:`                         |

#### **Using `regedit.exe`**

| Task                      | Description                                              | Example                                |
|---------------------------|----------------------------------------------------------|----------------------------------------|
| Open Registry Editor      | Launch the Registry Editor to make system configuration changes. | Press `Win + R` and type `regedit`.   |
| Export Registry Keys      | Create a backup of specific Registry keys.               | `File > Export` in the Registry Editor.|
| Edit Keys                 | Modify configuration values within specific keys.        | Right-click a key and select `Modify`. |

#### **Using `sfc.exe` (System File Checker)**

| Command                   | Description                                              | Example                                |
|---------------------------|----------------------------------------------------------|----------------------------------------|
| `sfc /scannow`            | Scans and repairs integrity violations in system files.  | Run from an elevated Command Prompt.   |
| `sfc /verifyonly`         | Checks system files but does not repair them.            | `sfc /verifyonly`                      |

---

### **Multimedia Learning Resource**

For a comprehensive, hands-on demonstration of these tools, watch [Professor Messer’s video on Microsoft Command Line Tools](https://www.professormesser.com/free-a-plus-training/220-1002/microsoft-command-line-tools/). It provides practical guidance and examples, perfect for visual learners.

---

## **Examples**

Here’s a practical example of using `sfc.exe` to repair system files:

1. Open the Command Prompt as an administrator.
2. Run the following command:

   ```cmd
   sfc /scannow
   ```

3. Wait for the tool to complete the scan and repair process.
4. Review the output for details on any repaired or unrepaired files.

---

## **Notes**

- **SMB Ports**: Block or secure Port 445 and Port 139 when not in use to mitigate potential security risks.
- **Command Line Tools**: Always run administrative tools like `regedit` or `sfc` with caution, as improper use can affect system stability.
- For modern systems, prioritize tools like `sfc` and `chkdsk` for maintenance tasks.

---

## **Resources**

- [Microsoft Docs on SMB](https://learn.microsoft.com/en-us/windows-server/storage/file-server/troubleshoot/smb-overview)
- [Professor Messer’s Video on Command Line Tools](https://www.professormesser.com/free-a-plus-training/220-1002/microsoft-command-line-tools/)
- [Official Windows Command Line Documentation](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/windows-commands)

---

## **Contribution**

Your contributions can make this tutorial even better:

- Fork the repository.
- Create a new branch:

  ```bash
  git checkout -b add-smb-cmdline-tutorial
  ```

- Make your changes.
- Commit your changes:

  ```bash
  git commit -m "Added SMB and Windows Command Line Tools tutorial"
  ```

- Push to the branch:

  ```bash
  git push origin add-smb-cmdline-tutorial
  ```

- Create a Pull Request targeting the Notes repository.

Contributions are welcome! Let’s keep building valuable resources for IT professionals.

<br>

## **Author**

- **Raphael Chookagian** | [GitHub Profile](https://github.com/cesar-group)

## **Date of Latest Revision**

- 12/11/2024

## **License**

- This script is provided as-is without any warranties. Users are advised to review and understand the script before executing it.

- This project is licensed under the MIT License. See the LICENSE file for details.
