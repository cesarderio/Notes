![Linux](../assets/Tux.png)

# **Linux Commands Cheat Sheet**

This cheat sheet provides a comprehensive guide for Linux commands, tailored for DevOps professionals and enthusiasts. It includes quick references, practical examples, and best practices for efficient Linux system management.

### **Table of Contents**

- [Basic Commands](#basic-commands)
- [Managing Packages](#managing-packages)
- [File Manipulation](#file-manipulation)
- [Process Management](#process-management)
- [Network and Connectivity](#network-and-connectivity)
- [System Information](#system-information)
- [Automation with Scripts](#automation-with-scripts)
- [Essential Tips and Tricks](#essential-tips-and-tricks)
- [Additional Commands](#additional-commands)
  - [File System and Disk Usage](#file-system-and-disk-usage)
  - [Advanced File Manipulation](#advanced-file-manipulation)
  - [System Monitoring](#system-monitoring)
  - [Network Diagnostics](#network-diagnostics)
- [Additional Tips and Tricks](#additional-tips-and-tricks)
  - [Command Line Efficiency](#command-line-efficiency)
  - [Keyboard Shortcuts](#keyboard-shortcuts)
  - [Customizing the Shell](#customizing-the-shell)
  - [File Editing](#file-editing)
- [Security Commands](#security-commands)
- [Scripting Examples](#scripting-examples)
  - [Example 1: Directory Cleanup Script](#example-1-directory-cleanup-script)
  - [Example 2: System Health Check Script](#example-2-system-health-check-script)
- [Troubleshooting Common Issues](#troubleshooting-common-issues)
  - [System Recovery](#system-recovery)
  - [Networking Issues](#networking-issues)
- [Version Control](#version-control)
  - [Basic Git Commands](#basic-git-commands)
- [Containerization and Virtualization](#containerization-and-virtualization)
  - [Docker Commands](#docker-commands)
  - [Kubernetes Commands](#kubernetes-commands)

## **Basic Commands**

- **`ls`**: List files and directories. E.g., `ls -l` for a detailed list, `ls -a` for all files.
- **`cd [directory]`**: Change the current directory. E.g., `cd /home/user`.
- **`pwd`**: Print the current working directory path.
- **`mkdir [directory]`**: Create a new directory. E.g., `mkdir new_folder`.
- **`touch [file]`**: Create an empty file. E.g., `touch new_file.txt`.
- **`rm [file/directory]`**: Remove files or directories. E.g., `rm file.txt`.
- **`cp [source] [destination]`**: Copy files and directories. E.g., `cp file.txt /home/user/`.
- **`mv [source] [destination]`**: Move or rename files and directories. E.g., `mv file.txt new_file.txt`.

## Managing Packages**

- **`apt`** or **`yum`**: Package managers for Debian-based and Red Hat-based systems.
  - `apt-get install [package]` or `yum install [package]`: Install packages.
  - `apt-get update` or `yum update`: Update package lists.
  - `apt-get upgrade` or `yum upgrade`: Upgrade installed packages.
  - `apt-get remove` or `yum remove`: Uninstall packages.

## **File Manipulation**

- **`cat [file]`**: Display file content. E.g., `cat file.txt`.
- **`more`** or **`less [file]`**: View long files one screen at a time.
- **`head [file]`** and **`tail [file]`**: Display the beginning or end of a file.
- **`grep [pattern] [file]`**: Search for text patterns in files.
- **`find [path] [expression]`**: Search for files and directories.
- **`wc [file]`**: Count lines, words, and characters in a file.
- **`chmod [permissions] [file]`**: Change file permissions.
- **`chown [owner] [file]`**: Change file ownership.

## **Process Management**

- **`ps`**: List running processes.
- **`top`** or **`htop`**: Monitor system activity and processes.
- **`kill [process_id]`** or **`pkill [process_name]`**: Terminate processes.

## **Network and Connectivity**

- **`ifconfig`** or **`ip`**: Configure network interfaces.
- **`ping [destination]`** or **`traceroute [destination]`**: Test network connectivity.
- **`netstat`** or **`ss`**: Display network statistics.
- **`ssh [user@host]`** or **`scp [source] [destination]`**: Securely connect and transfer files.
- **`wget [url]`** or **`curl [url]`**: Download files from the web.

## **System Information**

- **`uname`**: Display system information.
- **`df`** or **`du`**: Check disk usage.
- **`free`** or **`vmstat`**: Monitor system memory.
- **`uptime`** or **`who`**: View system uptime and logged-in users.
- **`dmesg`** or **`journalctl`**: Check system logs.

## **Automation with Scripts**

- **`#!/bin/bash`**: Start a shell script.
- **`for`** and **`while`** loops: Create repetitive tasks.
- **`if-then-else`** statements: Implement conditional logic.
- **`cron`** or **`systemd timers`**: Schedule tasks.

## **Essential Tips and Tricks**

- **Tab completion**: Press the Tab key to auto-complete commands and file paths.
- **Ctrl+C and Ctrl+Z**: Terminate or pause running processes.
- **Ctrl+D**: Log out of a terminal.
- **`history`**: Review command history.
- **`!` followed by a number or text**: Execute a previously run command.
- **`alias`**: Create shortcuts for long or complex commands.
- **`man`** or **`info`**: Access manual pages for command documentation.

## **Additional Commands**

### **File System and Disk Usage**

- **`df -h`**: Display disk space usage in human-readable format.
- **`du -sh [directory]`**: Show the size of a directory in a human-readable format.

### **Advanced File Manipulation**

- **`sed`**: Stream editor for filtering and transforming text.
- **`awk`**: Powerful text processing language.
- **`rsync`**: Fast and versatile tool for copying files remotely and locally.

### **System Monitoring**

- **`iotop`**: Monitor I/O usage by processes.
- **`nmon`**: Performance monitoring tool for Linux.

### **Network Diagnostics**

- **`dig [domain]`**: Query DNS name servers for information about host addresses, mail exchanges, etc.
- **`tcpdump`**: Dump traffic on a network.
- **`nmap`**: Network exploration tool and security/port scanner.

## **Additional Tips and Tricks**

### **Command Line Efficiency**

- **Globbing**: Use wildcard characters like `*` and `?` for file matching. E.g., `rm *.txt` to remove all text files.
- **Redirection and Piping**: Use `>` for redirecting output and `|` for piping output from one command to another. E.g., `grep 'text' file.txt | less`.
- **Command Substitution**: Use `$(command)` to use the output of a command as an argument to another command. E.g., `cd $(dirname $(find / -name filename.txt))`.

### **Keyboard Shortcuts**

- **Ctrl+R**: Search through command history.
- **Ctrl+L**: Clear the terminal screen.

### **Customizing the Shell**

- **Shell Aliases**: Add more examples of useful aliases.
- **Shell Prompt Customization**: Guide on customizing the prompt (PS1) for better usability.

### **File Editing**

- **`nano`**, **`vi`**, or **`emacs`**: Introduce basic usage of these text editors for editing configuration files and scripts.

## **Security Commands**

- **`chmod`** and **`chown`** Examples: Provide more examples for setting file permissions and ownership.
- **`ufw`** or **`firewalld`**: Basics of firewall setup and management.

## **Scripting Examples**

### **Example 1: Directory Cleanup Script**

```bash
#!/bin/bash

# Function to delete files older than a specified number of days
cleanup_old_files() {
    local dir=$1
    local days=$2
    echo "Cleaning up files older than $days days in $dir..."
    find "$dir" -type f -mtime +$days -exec rm -f {} \;
}

# Main script logic
if [ $# -ne 2 ]; then
    echo "Usage: $0 <directory> <days>"
    exit 1
fi

if [ ! -d "$1" ]; then
    echo "Error: Directory $1 not found."
    exit 1
fi

cleanup_old_files "$1" "$

2"
```

### **Example 2: System Health Check Script**

```bash
#!/bin/bash

# Check disk usage
df -h

# Check memory usage
free -h

# Check system load
uptime
```

## **Troubleshooting Common Issues**

### **System Recovery**

- **`fsck`**: File system consistency check.
- **`grub`**: Troubleshooting GRUB bootloader issues.

### **Networking Issues**

- **`ip link`**: Display network interfaces status.
- **`systemctl restart networking`**: Restart the networking service.

## **Version Control**

### **Basic Git Commands**

- **`git init`**: Initialize a new Git repository.
- **`git clone [repo]`**: Clone an existing repository.
- **`git commit -m "[message]"`**: Commit changes with a message.

## **Containerization and Virtualization**

### **Docker Commands**

- **`docker build`**: Build Docker images from a Dockerfile.
- **`docker run`**: Run a Docker container.
- **`docker ps`**: List running containers.

### **Kubernetes Commands**

- **`kubectl get pods`**: List Kubernetes pods.
- **`kubectl apply -f [file]`**: Apply configurations from a file.
- **`kubectl logs [pod]`**: View logs from a pod.

## **Conclusion**

This cheat sheet offers a wide range of essential Linux commands that DevOps professionals and enthusiasts can leverage for daily tasks. From basic file manipulation to advanced network diagnostics and system monitoring, it provides valuable references for quick solutions and common practices in system administration.

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
