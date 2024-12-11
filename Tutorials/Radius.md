<!-- <img src="../assets/radius_authentication.png" alt="RADIUS Authentication" width="400"> -->

# Navigating RADIUS Authentication: Centralized Security in Networking

Learn the fundamentals of RADIUS authentication and the AAA framework to centralize and enhance network security.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Objectives](#objectives)
- [Prerequisites](#prerequisites)
- [Steps](#steps)
  - [Understanding the AAA Framework](#understanding-the-aaa-framework)
  - [The Role of NAS in AAA](#the-role-of-nas-in-aaa)
  - [Implementing RADIUS Authentication](#implementing-radius-authentication)
    - [RADIUS Encryption Algorithms](#radius-encryption-algorithms)
  - [Benefits of RADIUS](#benefits-of-radius)
  - [Learning from Videos](#learning-from-videos)
- [Examples](#examples)
- [Notes](#notes)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

RADIUS (Remote Authentication Dial-In User Service) is a protocol used to centralize the Authentication, Authorization, and Accounting (AAA) of network users. It plays a pivotal role in managing network security and ensuring efficient resource access.

<br>

## **Objectives**

By the end of this tutorial, you will:

- Understand the AAA framework and its role in network security.
- Learn how RADIUS authentication centralizes and simplifies user management.
- Explore practical examples of RADIUS implementation.

<br>

## **Prerequisites**

To follow this tutorial, you should:

- Have basic knowledge of networking concepts.
- Access to a network environment or server capable of RADIUS implementation (e.g., FreeRADIUS).
- Familiarity with authentication and security protocols.

<br>

## **Steps**

### **Understanding the AAA Framework**

The AAA framework underpins RADIUS functionality:

| Component                      | Description                                                                                  | Example                                    |
|--------------------------------|----------------------------------------------------------------------------------------------|--------------------------------------------|
| **Authentication**             | Verifies user identity before granting access.                                               | Logging in to a secure network.            |
| **Authorization**              | Determines user permissions based on their role.                                             | Accessing specific VLANs or file servers.  |
| **Accounting**                 | Tracks user activities and resource usage.                                                   | Logging connection durations and bandwidth. |

---

### **The Role of NAS in AAA**

The **Network Access Server (NAS)** acts as the middleman between the user and the authentication server. It collects user credentials and forwards them to the RADIUS server for processing.

| Function                       | Description                                                                                  | Example                                    |
|--------------------------------|----------------------------------------------------------------------------------------------|--------------------------------------------|
| **Authentication Relay**       | Passes user credentials to the RADIUS server.                                                | NAS authenticates Wi-Fi clients.           |
| **Authorization Enforcer**     | Enforces permissions granted by the RADIUS server.                                           | Restricts guest access to internet-only VLAN.|

---

### **Implementing RADIUS Authentication**

RADIUS centralizes authentication, authorization, and accounting for efficient management.

#### **Steps to Implement RADIUS**

1. **Set Up a RADIUS Server**:
   - Install FreeRADIUS or a similar server.
   - Configure the server with user credentials and policies.

2. **Configure Network Devices**:
   - Point switches, access points, or firewalls to the RADIUS server for authentication.

3. **Test Authentication**:
   - Verify user login via the configured devices and ensure permissions are correctly applied.

---

#### **RADIUS Encryption Algorithms**

RADIUS uses robust encryption protocols to secure data transmission:

| Algorithm                      | Description                                                                                  | Use Case                                   |
|--------------------------------|----------------------------------------------------------------------------------------------|--------------------------------------------|
| **CHAP**                       | Challenge-response authentication for secure password exchange.                              | Authenticating VPN connections.            |
| **TLS**                        | Encrypts entire sessions for enhanced security.                                              | Secure wireless communication.             |
| **PEAP**                       | Encapsulates EAP within an encrypted TLS tunnel.                                             | Wi-Fi authentication in enterprise setups. |

---

### **Benefits of RADIUS**

| Benefit                        | Description                                                                                  | Example                                    |
|--------------------------------|----------------------------------------------------------------------------------------------|--------------------------------------------|
| **Centralized Control**        | Manages authentication from a single server.                                                 | Configuring a central RADIUS for all office Wi-Fi. |
| **Integration with AAA**       | Combines authentication, authorization, and accounting.                                       | Logs user access and bandwidth usage.      |
| **Scalability**                | Adapts to network growth and increasing user demand.                                          | Expanding authentication to multiple branch offices.|

---

### **Learning from Videos**

| Topic                          | Description                                                                                  | Link                                      |
|--------------------------------|----------------------------------------------------------------------------------------------|-------------------------------------------|
| **Authentication Methods**     | Explores user identity verification techniques.                                              | [Authentication Basics](https://www.youtube.com) |
| **Defense in Depth**           | Discusses multi-layered security strategies.                                                 | [Defense in Depth](https://www.professormesser.com) |
| **RADIUS and TACACS**          | Compares RADIUS with other authentication protocols.                                          | [RADIUS and TACACS](https://www.professormesser.com) |
| **Kerberos Authentication**    | Explains Kerberos in-depth and its use in secure environments.                               | [Kerberos Overview](https://www.youtube.com) |

---

## **Examples**

### **Example 1: Setting Up FreeRADIUS**

1. Install FreeRADIUS on a Linux server:
   ```bash
   sudo apt install freeradius
   ```
2. Configure the `clients.conf` file to define NAS devices:
   ```conf
   client 192.168.1.1 {
       secret = testing123
       shortname = switch1
   }
   ```
3. Restart the RADIUS service:
   ```bash
   sudo systemctl restart freeradius
   ```

---

### **Example 2: Testing RADIUS Authentication**

1. Use the `radtest` tool to verify user authentication:
   ```bash
   radtest username password 127.0.0.1 0 testing123
   ```
2. Check the RADIUS logs for authentication success or failure.

---

## **Notes**

- Use strong shared secrets for RADIUS clients to prevent unauthorized access.
- Combine RADIUS with certificates for enhanced security in Wi-Fi networks.
- Regularly review RADIUS logs to monitor access and detect anomalies.

<br>

## **Resources**

- [FreeRADIUS Documentation](https://freeradius.org/documentation/)
- [Understanding AAA and RADIUS](https://www.cisco.com/)
- [Professor Messer Networking Videos](https://www.professormesser.com/)

<br>

## **Contribution**

Your contributions can make this tutorial even better:

- Fork the repository.
- Create a new branch:

  ```bash
  git checkout -b add-radius-tutorial
  ```

- Make your changes.
- Commit your changes:

  ```bash
  git commit -m "Added RADIUS authentication tutorial"
  ```

- Push to the branch:

  ```bash
  git push origin add-radius-tutorial
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
