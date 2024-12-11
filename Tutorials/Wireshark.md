<!-- ![Wireshark](../assets/wireshark.png) -->
<img src="../assets/wireshark.png" alt="Alt Text" width="400">


# Wireshark Tutorial for Beginners

Wireshark is a free and open-source packet analyzer. It's used for network troubleshooting, analysis, software and protocol development, and education. This tutorial will guide you through the basics of using Wireshark effectively.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Getting Started with Wireshark](#getting-started-with-wireshark)
  - [Installation](#installation)
  - [Basic Concepts](#basic-concepts)
    - [The Wireshark Interface](#the-wireshark-interface)
    - [Capturing Data](#capturing-data)
  - [Using Wireshark](#using-wireshark)
    - [Opening and Saving Captures](#opening-and-saving-captures)
    - [Applying Display Filters](#applying-display-filters)
    - [Analyzing Protocols](#analyzing-protocols)
    - [Following Streams](#following-streams)
- [Advanced Wireshark Features](#advanced-wireshark-features)
  - [Using Color Rules](#using-color-rules)
  - [Exporting Objects](#exporting-objects)
  - [Using Statistics](#using-statistics)
- [Best Practices and Tips](#best-practices-and-tips)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

Wireshark allows you to inspect the detailed information of network packets, understand network protocols, and analyze network issues. It is an invaluable tool for network administrators and developers.

<br>

## **Getting Started with Wireshark**

### **Installation**

- **Windows/macOS**: Download the installer from [Wireshark's official website](https://www.wireshark.org/download.html).
- **Linux**: Most Linux distributions include Wireshark in their repositories. Install using the package manager, e.g., `sudo apt-get install wireshark` for Debian/Ubuntu.

<br>

### **Basic Concepts**

#### **The Wireshark Interface**

- **Main Toolbar**: Provides quick access to common actions.
- **Packet List Pane**: Shows all the packets in the current capture.
- **Packet Details Pane**: Details of the selected packet.
- **Packet Bytes Pane**: Displays the data of the selected packet in hexadecimal and ASCII.

#### **Capturing Data**

- Select the appropriate network interface and start capturing packets.
- You can apply capture filters to limit the data you collect.

<br>

### **Using Wireshark**

#### **Opening and Saving Captures**

- To open a saved capture: `File > Open`.
- To save a capture: `File > Save As`.

#### **Applying Display Filters**

- Use display filters to isolate packets of interest from a packet capture.
- Example: `http.request.method == "GET"` to filter HTTP GET requests.

#### **Analyzing Protocols**

- Click on a packet to view its details.
- Expand the protocol details in the packet details pane to see protocol-specific information.

#### **Following Streams**

- Right-click on a packet and select `Follow > TCP Stream` to see the entire conversation between two endpoints.

<br>

## **Advanced Wireshark Features**

### **Using Color Rules**

- Wireshark uses colors to help you identify types of traffic at a glance.
- Customize color settings through `View > Coloring Rules`.

### **Exporting Objects**

- Extract files, such as images or executables, transferred over the network: `File > Export Objects`.

### **Using Statistics**

- Access various statistics like protocol hierarchy, conversations, and IO graphs under `Statistics` in the menu.

<br>

## **Best Practices and Tips**

- **Filtering Effectively**: Learn and use display filters to focus on relevant data.
- **Regular Updates**: Keep Wireshark updated to get the latest protocol dissectors and features.
- **Respect Privacy**: Be mindful of privacy and legal issues when capturing network traffic.

<br>

## **Resources**

- [Wireshark User's Guide](https://www.wireshark.org/docs/wsug_html/)
- [Wireshark Display Filter Reference](https://www.wireshark.org/docs/dfref/)
- [Wireshark Community](https://ask.wireshark.org/)

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
