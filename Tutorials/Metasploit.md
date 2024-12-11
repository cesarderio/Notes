<img src="../assets/metsploit.png" alt="Alt Text" width="400">

# Metasploit Tutorial for Beginners

Learn the basics of Metasploit, one of the most widely used tools for penetration testing, offering a large collection of exploit modules, payload options, and other powerful features for security professionals.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Objectives](#objectives)
- [Prerequisites](#prerequisites)
- [Steps](#steps)
  - [Installation](#installation)
  - [Basic Commands](#basic-commands)
    - [Starting Metasploit](#starting-metasploit)
    - [Searching for Exploits](#searching-for-exploits)
    - [Configuring and Launching Exploits](#configuring-and-launching-exploits)
- [Fundamental Concepts](#fundamental-concepts)
  - [Exploits and Payloads](#exploits-and-payloads)
  - [Auxiliary Modules](#auxiliary-modules)
  - [Meterpreter](#meterpreter)
- [Advanced Techniques](#advanced-techniques)
  - [Using Meterpreter](#using-meterpreter)
  - [Post-Exploitation](#post-exploitation)
- [Best Practices and Tips](#best-practices-and-tips)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

Metasploit Framework is an open-source tool used by penetration testers and security professionals for vulnerability research, exploit development, and security assessments. It provides an extensive library of exploits, payloads, and modules to test system security.

<br>

## **Objectives**

By the end of this guide, you will:

- Understand the purpose and capabilities of Metasploit.
- Learn how to install and launch Metasploit.
- Explore fundamental and advanced features like exploits, payloads, and Meterpreter.

<br>

## **Prerequisites**

- Basic knowledge of Linux commands and networking concepts.
- A machine with Metasploit installed (Kali Linux recommended).

<br>

## **Steps**

### **Installation**

#### **Kali Linux**

Metasploit Framework comes pre-installed on Kali Linux.

#### **Windows and macOS**

You can install Metasploit Framework using the installer available on the [official Metasploit website](https://www.metasploit.com/download).

<br>

### **Basic Commands**

#### **Starting Metasploit**

Launch Metasploit by opening a terminal and typing:

```bash
msfconsole
```

#### **Searching for Exploits**

Search for exploits using the `search` command:

```bash
search [exploit name]
```

#### **Configuring and Launching Exploits**

1. **Select an Exploit**:

   ```bash
   use exploit/[path]
   ```

2. **Set Options**:

   ```bash
   set [option] [value]
   ```

   Example:

   ```bash
   set RHOSTS 192.168.1.105
   ```

3. **Launch the Exploit**:

   ```bash
   exploit
   ```

   or:

   ```bash
   run
   ```

<br>

## **Fundamental Concepts**

### **Exploits and Payloads**

- **Exploits**: Code that takes advantage of vulnerabilities in software.
- **Payloads**: Code that executes after a successful exploit, such as reverse or bind shells.

### **Auxiliary Modules**

These modules provide functionality beyond exploitation, such as scanners, fuzzers, and data enumeration tools.

### **Meterpreter**

Meterpreter is an advanced payload providing an interactive shell for controlling compromised systems.

<br>

## **Advanced Techniques**

### **Using Meterpreter**

After establishing a Meterpreter session, you can run various commands:

- **System Info**:

  ```bash
  sysinfo
  ```

- **Take a Screenshot**:

  ```bash
  screenshot
  ```

- **Access Webcam**:

  ```bash
  webcam_snap
  ```

### **Post-Exploitation**

Metasploit includes modules for:

- Privilege escalation.
- System reconnaissance.
- Credential harvesting.

<br>

## **Best Practices and Tips**

- **Ethical Use**: Always obtain explicit permission before testing networks and systems.
- **Update Regularly**: Ensure Metasploit is up-to-date for the latest exploits and modules.
- **Practice Safely**: Use vulnerable environments like Metasploitable for practice.

<br>

## **Resources**

- [Official Metasploit Documentation](https://docs.rapid7.com/metasploit/)
- [Metasploitable VM](https://sourceforge.net/projects/metasploitable/) for practice.
- [Online Courses and Tutorials](https://www.cybrary.it/) for hands-on training.

<br>

## **Contribution**

Your contributions can improve this guide:

- Fork the repository.

- Create a new branch:

  ```bash
  git checkout -b improve-metasploit-guide
  ```

- Make your updates.

- Commit your changes:

  ```bash
  git commit -am 'Enhanced Metasploit tutorial'
  ```

- Push to the branch:

  ```bash
  git push origin improve-metasploit-guide
  ```

- Create a Pull Request targeting the Notes directory.

<br>

## **Date of Latest Revision**

- 12/10/2024

<br>

## **License**

- This guide is provided as-is without warranties. Use it responsibly and ensure you comply with legal and ethical guidelines.

- This project is licensed under the MIT License. See the LICENSE file for details.
