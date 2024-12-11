<img src="../assets/medusa.png" alt="Alt Text" width="400">

# Medusa Password Cracker: A Comprehensive Guide

Learn how to install and use Medusa, a command-line tool for brute-force password cracking, on Kali Linux. Medusa supports numerous protocols and services, making it a versatile tool for security assessments.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Objectives](#objectives)
- [Prerequisites](#prerequisites)
- [Steps](#steps)
  - [Installation](#installation)
  - [Basic Usage](#basic-usage)
- [Modules](#modules)
- [Warning](#warning)
- [Conclusion](#conclusion)
- [Contribution](#contribution)

<br>

## **Overview**

Medusa is a fast, parallel, and modular brute-force password cracker. It is used by security professionals to test the strength of credentials on various network services.

<br>

## **Objectives**

By the end of this guide, you will:

- Understand what Medusa is and how it works.
- Learn how to install Medusa on Kali Linux.
- Use Medusa to perform basic brute-force password attacks.
- Explore its modular features for different protocols.

<br>

## **Prerequisites**

- Kali Linux operating system (Medusa is typically pre-installed, but this guide includes manual installation).
- Basic understanding of terminal commands and networking.
- Administrative/root privileges.

<br>

## **Steps**

### **Installation**

#### **Update System Repositories**

Before installing, ensure your package list is up to date:

```bash
sudo apt-get update
```

#### **Install Medusa**

Install Medusa using the package manager:

```bash
sudo apt-get install medusa
```

<br>

### **Basic Usage**

Medusa works by attempting to connect to a service using a predefined list of usernames and passwords to find valid credentials.

#### **Syntax**

The basic syntax for Medusa is:

```bash
medusa -h [hostname] -u [username] -p [password] -M [module]
```

Replace `[hostname]`, `[username]`, `[password]`, and `[module]` with the target's details and the service you are attacking.

#### **Example**

To attempt a brute-force SSH login:

```bash
medusa -h 192.168.1.101 -u root -p password123 -M ssh
```

This command attempts to log into the SSH server at `192.168.1.101` as the user `root` with the password `password123`.

<br>

## **Modules**

Medusa supports various modules for different protocols and services, such as:

- FTP
- HTTP
- SMB
- SQL
- SSH

To list all available modules:

```bash
medusa -d
```

<br>

## **Warning**

Use Medusa responsibly and legally. Unauthorized access to systems and networks is illegal. Medusa should be used solely for authorized penetration testing and security assessment activities.

<br>

## **Conclusion**

Medusa is a powerful tool in the arsenal of penetration testers and security professionals for performing brute-force attacks. Its effectiveness in finding weak credentials makes it valuable for security auditing and testing.

For more advanced features and detailed usage, refer to the Medusa documentation:

```bash
medusa -h
```

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
