# Unpacking Intrusion Detection and Prevention Systems (IDS/IPS)

Understanding the nuances of Intrusion Detection and Prevention Systems (IDS/IPS) is essential in the field of cybersecurity. This tutorial explores the differences between IDS/IPS and firewalls, scenarios for choosing network-based IDS over host-based IDS, and the major drawbacks of network intrusion detection systems (NIDS).

<br>

### **Table of Contents**

- [Overview](#overview)
- [Objectives](#objectives)
- [Prerequisites](#prerequisites)
- [Steps](#steps)
  - [Key Differences Between Firewalls and IDS](#key-differences-between-firewalls-and-ids)
  - [Deciding Between Network-Based and Host-Based IDS](#deciding-between-network-based-and-host-based-ids)
  - [Major Drawbacks of Network Intrusion Detection Systems (NIDS)](#major-drawbacks-of-network-intrusion-detection-systems-nids)
- [Notes](#notes)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

Intrusion Detection and Prevention Systems (IDS/IPS) are vital tools in identifying and preventing cyber threats. Understanding their functions and limitations helps organizations strengthen their security posture.

<br>

## **Objectives**

By the end of this tutorial, you will:

- Understand the differences between IDS/IPS and firewalls.
- Learn when to choose network-based IDS over host-based IDS.
- Recognize the limitations of network intrusion detection systems (NIDS).

<br>

## **Prerequisites**

To follow this tutorial, you should:

- Have a basic understanding of cybersecurity concepts and network traffic.
- Be familiar with network monitoring tools.
- Have access to IDS/IPS solutions for practical exploration (optional).

<br>

## **Steps**

### **Key Differences Between Firewalls and IDS**

| Aspect                     | Firewall                                   | IDS                                                                 |
|----------------------------|-------------------------------------------|--------------------------------------------------------------------|
| **Function**               | Controls and regulates network traffic.  | Monitors and observes network traffic for potential threats.       |
| **Action**                 | Actively blocks or allows traffic.       | Passively alerts IT or SOC teams about detected threats.           |

<br>

### **Deciding Between Network-Based and Host-Based IDS**

Choose the appropriate type of IDS based on your security needs:

| Scenario                         | Best Option                                                                                     |
|----------------------------------|-------------------------------------------------------------------------------------------------|
| **Monitoring all network traffic** | Network-Based IDS: Provides visibility into all traffic across the network.                    |
| **Overseeing multiple devices**   | Network-Based IDS: Efficiently manages devices connected to the network.                       |
| **Device-specific monitoring**    | Host-Based IDS: Focuses on specific devices for deeper inspection.                             |

<br>

### **Major Drawbacks of Network Intrusion Detection Systems (NIDS)**

| Challenge                      | Explanation                                                                                     |
|--------------------------------|-------------------------------------------------------------------------------------------------|
| **Passive Nature**             | NIDS cannot actively intervene to prevent threats, limiting its role to detection and alerting.|
| **Expertise Requirement**      | Requires specialized knowledge for proper operation and maintenance.                           |
| **High Rate of False Positives**| Frequent false positives can obscure real threats and cause inefficiencies in analysis.         |

<br>

## **Notes**

- IDS and firewalls complement each other but serve distinct roles in network security.
- NIDS are ideal for large-scale network monitoring but require skilled personnel for effective use.
- Host-based IDS is a better choice for device-specific security needs.

<br>

## **Resources**

- [Network Intrusion Detection and Prevention - CompTIA Security+ SY0-501](https://www.youtube.com/watch?v=hEgWPWIuq_s&ab_channel=ProfessorMesser): A comprehensive overview of IDS/IPS tailored for the Security+ exam.

<br>

## **Contribution**

Your contributions can enhance this tutorial:

- Fork the repository.
- Create a new branch:

  ```bash
  git checkout -b my-awesome-feature
  ```

- Make your changes.
- Commit your changes:

  ```bash
  git commit -am 'Added insights on IDS/IPS functionality'
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

- 12/12/2024

## **License**

- This script is provided as-is without any warranties. Users are advised to review and understand the script before executing it.

- This project is licensed under the MIT License. See the LICENSE file for details.
