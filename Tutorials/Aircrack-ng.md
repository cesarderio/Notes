# Aircrack-ng Tutorial for Beginners

Learn how to use Aircrack-ng, a powerful suite for WiFi security analysis, to understand and test wireless network security protocols.

<br>

## **Table of Contents**

- [Overview](#overview)
- [Objectives](#objectives)
- [Prerequisites](#prerequisites)
- [Steps](#steps)
  - [Installation](#installation)
  - [Basic Concepts](#basic-concepts)
  - [Capturing Packets](#capturing-packets)
  - [Cracking WEP](#cracking-wep)
  - [Cracking WPA/WPA2](#cracking-wpawpa2)
- [Advanced Techniques](#advanced-techniques)
  - [Deauthenticating Clients](#deauthenticating-clients)
  - [Creating a Wordlist](#creating-a-wordlist)
- [Best Practices and Tips](#best-practices-and-tips)
- [Resources](#resources)
- [Author](#author)

<br>

## **Overview**

Aircrack-ng is a network software suite that includes tools for packet sniffing, WEP/WPA key cracking, and WiFi network analysis. It captures network packets and attempts to crack the network password, making it invaluable for WiFi security testing.

<br>

## **Objectives**

By the end of this tutorial, you will:

- Understand the purpose and capabilities of Aircrack-ng.
- Learn to capture network packets and perform basic WiFi security analysis.
- Practice ethical usage of Aircrack-ng tools.

<br>

## **Prerequisites**

- **Hardware**: A wireless network adapter capable of packet injection and monitor mode.
- **Software**:
  - **Linux**: Install Aircrack-ng via package manager (`sudo apt-get install aircrack-ng`).
  - **Windows**: Limited functionality available.
  - **macOS**: Install using tools like MacPorts or Brew.
- **Legal Considerations**: Only use Aircrack-ng on networks you own or have explicit permission to test.

<br>

## **Steps**

### **Installation**

Follow these steps to install Aircrack-ng:

- **Linux**:

  ```bash
  sudo apt-get install aircrack-ng
  ```

- **Windows**: Download the [Windows version](https://www.aircrack-ng.org/) and install it.
- **macOS**: Use Brew:

  ```bash
  brew install aircrack-ng
  ```

<br>

### **Basic Concepts**

#### Understanding WiFi Security

- WiFi networks use security protocols like WEP, WPA, and WPA2.
- Aircrack-ng tests the robustness of these protocols by analyzing captured packets.

#### Required Hardware

- Ensure your network adapter supports **packet injection** and **monitor mode**.

<br>

### **Capturing Packets**

1. Start capturing packets using `airodump-ng`:

   ```bash
   airodump-ng wlan0
   ```

2. Identify the target network’s:
   - **BSSID**
   - **Channel**
   - **ESSID**


3. Focus on a specific network:

   ```bash
   airodump-ng --bssid [target BSSID] -c [channel] --write [output file] wlan0
   ```

<br>

### **Cracking WEP**

1. Capture enough data packets from the target network.
2. Use Aircrack-ng to crack the WEP key:

   ```bash
   aircrack-ng [output file]-01.cap
   ```



### **Cracking WPA/WPA2**

1. Capture a WPA handshake:
   - Deauthenticate a client if needed (see [Deauthenticating Clients](#deauthenticating-clients)).
2. Use a wordlist to attempt cracking the key:

   ```bash
   aircrack-ng -w [wordlist file] [output file]-01.cap
   ```


<br>

## **Advanced Techniques**

### **Deauthenticating Clients**

To capture a handshake for WPA/WPA2 cracking, force a client to reconnect:

```bash
aireplay-ng --deauth 0 -a [target BSSID] -c [client BSSID] wlan0
```



### **Creating a Wordlist**

Generate a custom wordlist using tools like `crunch`:

```bash
crunch [min-length] [max-length] [charset] -o [output file]
```

Example:

```bash
crunch 8 12 abcdef123 > wordlist.txt
```


<br>

## **Best Practices and Tips**

- **Stay Legal**: Only use Aircrack-ng on authorized networks.
- **Hardware Compatibility**: Confirm your adapter supports necessary features.
- **Ethical Usage**: Use Aircrack-ng to improve the security of your own networks.
- **Password Strength**: Promote strong, complex passwords for improved network security.


<br>

## **Resources**

- [Aircrack-ng Official Documentation](https://www.aircrack-ng.org/doku.php)
- [WiFi Security Basics](https://en.wikipedia.org/wiki/Wireless_security)
- [Installing Drivers for Wireless Adapters](https://www.aircrack-ng.org/doku.php?id=compatibility_drivers)

<br>

## **Contribution**

Your contributions can make these scripts even better:

- Fork the repository.

- Create a new branch:

  ```bash
  git checkout -b my-awesome-feature
  ```

- Make your invaluable changes.

- Commit your changes:

  ```bash
  git commit -am 'Added some amazing features'
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

- 12/09/2024



## **License**

- This script is provided as-is without any warranties. Users are advised to review and understand the script before executing it.

- This project is licensed under the MIT License. See the LICENSE file for details.


<!-- # Aircrack-ng Tutorial for Beginners

<br>

## Overview

Aircrack-ng is a network software suite consisting of a detector, packet sniffer, WEP and WPA/WPA2-PSK cracker, and analysis tool. It works by capturing network packets and then attempting to crack the network password. This tutorial will guide beginners through the basics of using Aircrack-ng for WiFi security analysis.

<br>

## Installation

- **Linux**: Most distributions provide Aircrack-ng in their repositories. Install it using the package manager, e.g., `sudo apt-get install aircrack-ng`.
- **Windows**: Windows versions are available, but functionality is limited compared to Linux.
- **macOS**: Can be installed using tools like MacPorts or Brew.

<br>

## Basic Concepts

<br>

### Understanding WiFi Security

- WiFi networks typically use WEP, WPA, or WPA2 for security.
- Aircrack-ng can test the strength of these security protocols.

<br>

### Required Hardware

- A wireless network adapter capable of packet injection is required.

<br>

## Using Aircrack-ng

<br>

### Capturing Packets

- Use `airodump-ng` to capture packets from a network.

  ```bash
  airodump-ng wlan0
  ```

- Identify your target network's BSSID, channel, and ESSID.

<br>

### Targeting a Specific Network

- Capture packets from a specific network:

  ```bash
  airodump-ng --bssid [target BSSID] -c [channel] --write [output file] wlan0
  ```

<br>

### Cracking WEP

- After capturing enough data packets, use Aircrack-ng to crack the WEP key:

  ```bash
  aircrack-ng [output file]-01.cap
  ```

<br>

### Cracking WPA/WPA2

- WPA/WPA2 cracking requires a handshake packet.
- Use `airodump-ng` to capture the handshake.
- Use `aircrack-ng` with a wordlist to crack the key:

  ```bash
  aircrack-ng -w [wordlist file] [output file]-01.cap
  ```

<br>

## Advanced Aircrack-ng Techniques

<br>

### Deauthenticating Clients (For Capturing Handshakes)

- Use `aireplay-ng` to deauthenticate a client, forcing a handshake capture:

  ```bash
  aireplay-ng --deauth 0 -a [target BSSID] -c [client BSSID] wlan0
  ```

<br>

### Creating a Wordlist

- Custom wordlists can be more effective. Tools like `crunch` can help create them.

<br>

## Best Practices and Tips

- **Legal Considerations**: It's illegal to access or attack a network without permission.
- **Hardware Compatibility**: Ensure your network adapter supports packet injection and monitor mode.
- **Strong Passwords**: Use Aircrack-ng to assess the strength of your network's password, promoting the use of strong, complex passwords.

<br>

## Conclusion

Aircrack-ng is a powerful suite for assessing WiFi network security. It's crucial for network administrators and security professionals to understand these tools to safeguard against vulnerabilities.

<br>

## Further Learning

- **Official Documentation**: For comprehensive learning, refer to the [official Aircrack-ng documentation](https://www.aircrack-ng.org/doku.php).
- **Practice Networks**: Create or use practice networks for legal and ethical hacking experience. -->
