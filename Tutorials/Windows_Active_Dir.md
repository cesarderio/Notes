<!-- <img src="../assets/active_directory.png" alt="Windows Active Directory" width="400"> -->

# Exploring Windows Active Directory: Centralized Management and Enhanced Security

Discover the core structure and benefits of Windows Active Directory (AD) for network management and security in modern organizations.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Objectives](#objectives)
- [Prerequisites](#prerequisites)
- [Steps](#steps)
  - [What is Active Directory?](#what-is-active-directory)
    - [Key Services of Active Directory](#key-services-of-active-directory)
  - [Understanding Domains, Forests, and Trees](#understanding-domains-forests-and-trees)
  - [Grouping Objects in a Domain](#grouping-objects-in-a-domain)
  - [The Benefits of Active Directory](#the-benefits-of-active-directory)
  - [Learning from Videos](#learning-from-videos)
- [Examples](#examples)
- [Notes](#notes)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

Windows Active Directory (AD) is a centralized system for managing network resources, security, and user access in enterprise environments. This tutorial explores AD's structure, components, and advantages.

<br>

## **Objectives**

By the end of this tutorial, you will:

- Understand the fundamental components of Active Directory.
- Learn how AD structures domains, forests, and trees.
- Explore the benefits of centralized management and enhanced security with AD.

<br>

## **Prerequisites**

To follow this tutorial, you should:

- Have a basic understanding of networking concepts.
- Access to a Windows Server environment or virtual lab with Active Directory setup capabilities (optional).
- Familiarity with administrative tools like the Active Directory Users and Computers console.

<br>

## **Steps**

### **What is Active Directory?**

Active Directory is like a central directory for an organization’s network, providing services for authentication, authorization, and management of resources.

---

#### **Key Services of Active Directory**

| Service                        | Description                                                                                  | Example                                    |
|--------------------------------|----------------------------------------------------------------------------------------------|--------------------------------------------|
| **Authentication**             | Verifies user identity when logging into the network.                                        | Logging into a domain-joined PC.           |
| **Domain Services**            | Manages network objects like users, computers, and groups.                                   | Setting user permissions for shared folders.|
| **Group Policy**               | Enforces security and configuration settings across the network.                             | Mandating password complexity policies.     |
| **LDAP Services**              | Provides a protocol for querying and modifying directory services.                          | Accessing directory data for applications. |

---

### **Understanding Domains, Forests, and Trees**

| Component                      | Description                                                                                  | Example                                    |
|--------------------------------|----------------------------------------------------------------------------------------------|--------------------------------------------|
| **Domain**                     | A group of objects (users, computers, etc.) sharing common policies and authentication.       | `example.local`.                           |
| **Tree**                       | A hierarchical structure of domains under a single namespace.                                | `sales.example.local`, `hr.example.local`. |
| **Forest**                     | A collection of multiple trees sharing common configurations.                                | Company-wide network spanning multiple branches.|

---

### **Grouping Objects in a Domain**

| Type                           | Description                                                                                  | Example Use Case                             |
|--------------------------------|----------------------------------------------------------------------------------------------|----------------------------------------------|
| **Security Groups**            | Define access permissions for resources.                                                     | Granting access to a shared folder.          |
| **Distribution Groups**        | Used for email distribution lists.                                                           | Sending emails to all HR employees.          |
| **Organizational Units (OUs)** | Logical containers for organizing objects within a domain.                                    | Creating OUs for departments like Sales or IT.|
| **Built-in Groups**            | Predefined groups with specific roles.                                                       | Administrators, Backup Operators.            |

---

### **The Benefits of Active Directory**

Active Directory offers:

| Feature                        | Description                                                                                  | Example Use Case                             |
|--------------------------------|----------------------------------------------------------------------------------------------|----------------------------------------------|
| **Centralized Management**     | Manage users, devices, and policies from a single interface.                                | Adding new employees to the domain.          |
| **File Sharing**               | Facilitates secure and efficient file sharing within the network.                           | Sharing project files among teams.           |
| **Integration**                | Seamlessly integrates with other Microsoft services.                                        | Syncing with Office 365 or Azure AD.         |
| **Enhanced Security**          | Enforces strict access controls and policies.                                               | Applying MFA for sensitive accounts.         |

---

### **Learning from Videos**

| Topic                          | Description                                                                                  | Link                                      |
|--------------------------------|----------------------------------------------------------------------------------------------|-------------------------------------------|
| **DHCP Overview**              | Explains how IP addresses are dynamically assigned in networks.                              | [Professor Messer - DHCP Basics](https://www.professormesser.com) |
| **Configuring DHCP**           | Practical guide to setting up DHCP in a Windows environment.                                | [DHCP Configuration](https://www.youtube.com) |

---

## **Examples**

### **Example 1: Creating a New Organizational Unit (OU)**

1. Open **Active Directory Users and Computers**.
2. Navigate to your domain and right-click it.
3. Select **New > Organizational Unit**.
4. Enter a name for the OU (e.g., "IT Department") and click **OK**.

---

### **Example 2: Configuring a Group Policy**

1. Open the **Group Policy Management Console (GPMC)**.
2. Right-click your domain or OU and select **Create a GPO in this domain**.
3. Name the GPO (e.g., "Password Policy") and click **OK**.
4. Edit the GPO to configure settings like password length and expiration.

---

## **Notes**

- Regularly monitor and update Active Directory to ensure security and optimal performance.
- Use Group Policy Objects (GPOs) for enforcing consistent policies across the network.
- Document your AD structure and configurations for troubleshooting and auditing.

<br>

## **Resources**

- [Active Directory Documentation](https://docs.microsoft.com/en-us/windows-server/identity/active-directory-domain-services)
- [Group Policy Best Practices](https://learn.microsoft.com/en-us/windows-server/identity/guidelines-for-best-practices-group-policy)
- [Networking Fundamentals](https://www.cisco.com/)

<br>

## **Contribution**

Your contributions can make this tutorial even better:

- Fork the repository.
- Create a new branch:

  ```bash
  git checkout -b add-active-directory-tutorial
  ```

- Make your changes.
- Commit your changes:

  ```bash
  git commit -m "Added Active Directory tutorial"
  ```

- Push to the branch:

  ```bash
  git push origin add-active-directory-tutorial
  ```

- Create a Pull Request targeting the Notes repository.

Contributions are welcome! Let’s refine this guide together.

<br>

## **Author**

- **Raphael Chookagian** | [GitHub Profile](https://github.com/cesar-group)

## **Date of Latest Revision**

- 12/11/2024

## **License**

- This script is provided as-is without any warranties. Users are advised to review and understand the script before executing it.

- This project is licensed under the MIT License. See the LICENSE file for details.
