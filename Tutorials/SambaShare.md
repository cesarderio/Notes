<img src="../assets/Samba_Logo.png" alt="Alt Text" width="400">

# Setting up SambaShare Files and Directories

Learn how to configure file sharing using Samba for Linux, Windows, and macOS systems. Samba allows seamless file sharing across different operating systems.

<br>

### **Table of Contents**

- [Overview](#overview)
- [For Linux (Ubuntu/Raspberry Pi)](#for-linux-ubunturaspberry-pi)
- [For Windows](#for-windows)
- [For macOS](#for-macos)
- [Cross-Platform Access](#cross-platform-access)
- [Security Tips](#security-tips)
- [Contribution](#contribution)

<br>

## **Overview**

Samba is a software suite that allows file and print sharing between computers running Linux, Windows, and macOS. This tutorial guides you through setting up Samba shares for each operating system.

<br>

## **For Linux (Ubuntu/Raspberry Pi)**

1. **Install File Sharing Software (Samba)**:
   - Open a terminal and update your package lists:

     ```bash
     sudo apt update
     ```

   - Install Samba:

     ```bash
     sudo apt install samba samba-common-bin
     ```

2. **Configure Samba**:
   - Edit the Samba configuration file:

     ```bash
     sudo nano /etc/samba/smb.conf
     ```

   - Add your shared folder details at the end of the file:

     ```
     [SharedFolder]
     path = /path/to/shared/folder
     read only = no
     browsable = yes
     ```

3. **Set Up Samba User**:
   - Create a Samba user:

     ```bash
     sudo smbpasswd -a your_username
     ```

   - Enter a password when prompted.

4. **Restart Samba**:
   - Restart the Samba service:

     ```bash
     sudo systemctl restart smbd
     ```

5. **Access the Shared Folder**:
   - Access it from other devices using the network path (e.g., `\raspberrypi\SharedFolder`).

6. **Security**:
   - Keep your system updated and use strong passwords.

<br>

## **For Windows**

1. **Select Folder to Share**:
   - Right-click the folder you want to share.
   - Choose "Properties" and then the "Sharing" tab.

2. **Advanced Sharing**:
   - Click on "Advanced Sharing".
   - Check "Share this folder" and set permissions as needed.

3. **Network Discovery**:
   - Ensure network discovery is turned on in your network settings.

4. **Access the Shared Folder**:
   - Access it from other devices using `\\ComputerName\SharedFolderName`.

<br>

## **For macOS**

1. **Choose Folder to Share**:
   - Open System Preferences and go to "Sharing".
   - Select "File Sharing" and add the folder you want to share.

2. **Set Permissions**:
   - Set the desired access permissions for the shared folder.

3. **Connect from Other Devices**:
   - On a Mac, connect via Finder > Go > Connect to Server (`smb://MacName/SharedFolder`).
   - On Windows, use `\\MacName\SharedFolder`.

<br>

## **Cross-Platform Access**

- Accessing from Linux to Windows/Mac and vice versa involves using SMB/CIFS protocols.
- Ensure that the network paths are correctly entered based on the host's OS and shared folder name.
- Compatibility might vary, and additional software (like Samba for Linux) might be needed for seamless integration.

<br>

## **Security Tips**

- Always ensure that the network you are using is secure.
- Regularly update your systems and software.
- Use strong, unique passwords for user accounts and shared folders.
- Consider network security measures like firewalls and VPNs, especially in a business environment.

<br>

> *This tutorial provides a broad overview. The exact steps might vary slightly based on the specific version of the OS and the network setup. Always check for the latest best practices and updates for your specific OS.*

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
