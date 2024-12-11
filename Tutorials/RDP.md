<!-- ![RDP](../assets/rdp.png) -->
<img src="../assets/rdp.png" alt="Alt Text" width="400">


# Remote Desktop Protocol (RDP) Installation and Setup Tutorial

This tutorial provides detailed instructions for installing and setting up Remote Desktop Protocol (RDP) on a Linux server. RDP allows you to access and control your Linux server remotely from a Windows or macOS computer using the Remote Desktop client.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Installation Steps](#installation-steps)
  - [Step 1: Install RDP Server (xrdp)](#step-1-install-rdp-server-xrdp)
  - [Step 2: Configure Firewall](#step-2-configure-firewall)
  - [Step 3: Start and Enable RDP Service](#step-3-start-and-enable-rdp-service)
  - [Step 4: Connect to RDP Server](#step-4-connect-to-rdp-server)
  - [Step 5: Log in to Desktop Environment](#step-5-log-in-to-desktop-environment)
  - [Step 6: Optional Configuration](#step-6-optional-configuration)
    - [Customize RDP Port (Optional)](#customize-rdp-port-optional)
    - [Secure RDP Connection (Optional)](#secure-rdp-connection-optional)
- [Conclusion](#conclusion)

<br>

## **Overview**

Remote Desktop Protocol (RDP) allows you to access and control your Linux server remotely from a Windows or macOS computer. This tutorial provides a step-by-step guide for installing and setting up RDP on a Linux server.

<br>

## **Prerequisites**

1. **Linux Server**: A Linux-based server (e.g., Ubuntu) with root access.
2. **Network Access**: Ensure that your server has network access and is reachable from the client computer.
3. **Desktop Environment**: A desktop environment installed on your Linux server (e.g., GNOME, XFCE).
4. **SSH Access**: SSH access enabled on your server to facilitate remote administration.

<br>

## **Installation Steps**

Follow these steps to install and set up Remote Desktop Protocol (RDP) on your Linux server:

### **Step 1: Install RDP Server (xrdp)**

Install the `xrdp` package, which provides an open-source RDP server for Linux:

```bash
sudo apt update
sudo apt install xrdp
```

<br>

### **Step 2: Configure Firewall**

If you have a firewall enabled on your server (e.g., UFW), allow traffic on port 3389, which is used by RDP:

```bash
sudo ufw allow 3389/tcp
```

<br>

### **Step 3: Start and Enable RDP Service**

Start the `xrdp` service and enable it to start automatically on system boot:

```bash
sudo systemctl start xrdp
sudo systemctl enable xrdp
```

<br>

### **Step 4: Connect to RDP Server**

On your Windows or macOS computer, use a Remote Desktop client to connect to your Linux server. Open the Remote Desktop client and enter the IP address or hostname of your server.

<br>

### **Step 5: Log in to Desktop Environment**

Once connected, you will be prompted to enter your username and password. Use the credentials of a user account on your Linux server. After authentication, you will have access to the desktop environment of your Linux server.

<br>

### **Step 6: Optional Configuration**

#### **Customize RDP Port (Optional)**

If you wish to use a custom port for RDP, you can configure `xrdp` to listen on a different port. Edit the configuration file:

```bash
sudo nano /etc/xrdp/xrdp.ini
```

Find the `[xrdp1]` section and modify the `port` parameter to your desired port number.

#### **Secure RDP Connection (Optional)**

To enhance security, you can tunnel RDP traffic through an SSH connection. This adds an extra layer of encryption to your RDP sessions and protects against unauthorized access. Refer to SSH tunneling documentation for more information.

<br>

## **Conclusion**

You have successfully installed and set up Remote Desktop Protocol (RDP) on your Linux server. You can now remotely access and manage your server's desktop environment from a Windows or macOS computer using the Remote Desktop client.

For advanced configurations and troubleshooting, refer to the `xrdp` documentation and community resources.

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
