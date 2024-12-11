<!-- ![Kali](../assets/Kali.png) -->
<img src="../assets/Kali.png" alt="Alt Text" width="400">


# **Basic Navigation and Commands in Kali Linux**

Kali Linux is a powerful Linux distribution used for penetration testing, ethical hacking, and network security assessments. This tutorial provides a foundational understanding of how to navigate Kali Linux and use its most common applications.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Getting Started with Kali Linux](#getting-started-with-kali-linux)
  - [Installation](#installation)
  - [Initial Setup](#initial-setup)
- [Basic Navigation in Kali Linux](#basic-navigation-in-kali-linux)
  - [Kali Interface](#kali-interface)
  - [Essential Commands](#essential-commands)
  - [File Management](#file-management)
- [Network Configuration in Kali](#network-configuration-in-kali)
- [Package Management](#package-management)
  - [Using `apt`](#using-apt)
- [System Monitoring and Management](#system-monitoring-and-management)
  - [Monitoring Resources](#monitoring-resources)
  - [Managing Services](#managing-services)
- [User and Group Management](#user-and-group-management)
- [Popular Tools and Applications in Kali Linux](#popular-tools-and-applications-in-kali-linux)
  - [Nmap](#nmap)
  - [Metasploit Framework](#metasploit-framework)
  - [Wireshark](#wireshark)
  - [Burp Suite](#burp-suite)
  - [Aircrack-ng](#aircrack-ng)
- [Advanced Tips and Tricks](#advanced-tips-and-tricks)
- [Conclusion](#conclusion)
- [References](#references)
- [Contribution](#contribution)

<br>

## **Overview**

- **Overview of Kali Linux**: Kali Linux is a Debian-based distribution designed for penetration testing and digital forensics, equipped with numerous tools for security testing.
- **Key Features**: Advanced tools for penetration testing, security assessments, wireless network analysis, and more.
- **Guide Purpose**: This guide will help users navigate Kali Linux, use essential commands, and familiarize themselves with common tools for network security.

<br>

## **Getting Started with Kali Linux**

### **Installation**

- Download Kali Linux from the official website.
- Burn the image to a USB drive or DVD.
- Boot from the USB/DVD and follow the installation instructions.

### **Initial Setup**

- Set your timezone, language, and keyboard preferences.
- Create a user account and password.

<br>

## **Basic Navigation in Kali Linux**

### **Kali Interface**

- Kali uses the GNOME desktop environment by default.
- The desktop consists of a top bar, a bottom panel, and desktop icons.

### **Essential Commands**

- **`cd`**: Change directory.
- **`ls`**: List files and directories.
- **`pwd`**: Print the working directory.
- **`mkdir`**: Create a new directory.

### **File Management**

- **`cp`**: Copy files and directories.
- **`mv`**: Move or rename files and directories.
- **`rm`**: Remove files and directories.

<br>

## **Network Configuration in Kali**

- Use **`ifconfig`** to configure network interfaces.
- Test connectivity using **`ping`**.
- View network connections with **`netstat`**.

<br>

## **Package Management**

### **Using `apt`**

- **Update package lists**:

  ```bash
  sudo apt update
  ```

- **Upgrade packages**:

  ```bash
  sudo apt upgrade
  ```

- **Install a package**:

  ```bash
  sudo apt install [package_name]
  ```

<br>

## **System Monitoring and Management**

### **Monitoring Resources**

- **`top`** or **`htop`**: Monitor real-time system performance.
- **`free`**: View memory usage.

### **Managing Services**

- **Start a service**:

  ```bash
  sudo systemctl start [service_name]
  ```

- **Stop a service**:

  ```bash
  sudo systemctl stop [service_name]
  ```

- **Enable a service to start at boot**:

  ```bash
  sudo systemctl enable [service_name]
  ```

<br>

## **User and Group Management**

- **Create a new user**:

  ```bash
  sudo useradd [username]
  ```

- **Set or change a user's password**:

  ```bash
  sudo passwd [username]
  ```

- **Create a new group**:

  ```bash
  sudo groupadd [group_name]
  ```

- **Add a user to a group**:

  ```bash
  sudo usermod -aG [group_name] [username]
  ```

- **Change file permissions**:

  ```bash
  chmod [permissions] [file]
  ```

- **Change file ownership**:

  ```bash
  chown [user]:[group] [file]
  ```

<br>

## **Popular Tools and Applications in Kali Linux**

### **Nmap**

- **Basic scan**:

  ```bash
  nmap [target_IP]
  ```

- **Scan specific ports**:

  ```bash
  nmap -p [port_range] [target_IP]
  ```

### **Metasploit Framework**

- **Start Metasploit**:

  ```bash
  msfconsole
  ```

- **Basic commands**: `search`, `use`, `set`, `exploit`

### **Wireshark**

- **Launch Wireshark**:

  ```bash
  wireshark
  ```

- Select a network interface to capture packets.
- Apply filters to analyze specific traffic.

### **Burp Suite**

- **Start Burp Suite**:

  ```bash
  burpsuite
  ```

- Configure your browser to use Burp as a proxy.
- Intercept and modify HTTP requests and responses.

### **Aircrack-ng**

- **Monitor Wi-Fi networks**:

   ```bash
    airmon-ng start [interface_name]
   ```

- **Capture traffic**:

  ```bash
  airodump-ng [monitor_interface]
  ```

- **Crack Wi-Fi password**:

  ```bash
  aircrack-ng [capture_file]
  ```

<br>

## **Advanced Tips and Tricks**

- Customize the look and feel of Kali through **GNOME Tweaks**.
- Use keyboard shortcuts like **`Ctrl+Alt+T`** for terminal access.

<br>

## **Conclusion**

By understanding basic navigation and common commands in Kali Linux, you can begin working effectively with this powerful penetration testing and network security distribution.

<br>

## **References**

- [Kali Linux Official Website](https://www.kali.org)
- [Kali Linux Documentation](https://www.kali.org/docs/)

<br>

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
