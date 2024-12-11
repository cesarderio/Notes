<!-- ![CasaOS](../assets/) -->

# CasaOS Setup Tutorial

A guide to setting up CasaOS, a lightweight, Docker-based home cloud system that provides an intuitive interface for managing Docker applications and personal data at home.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Initial Setup](#initial-setup)
  - [Configuring CasaOS](#configuring-casaos)
  - [Adding Applications](#adding-applications)
  - [File Management](#file-management)
- [Conclusion](#conclusion)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

CasaOS is a lightweight, Docker-based platform designed for home cloud management. It provides an intuitive web interface for managing Docker applications, personal data, and home services. CasaOS is ideal for users who want a simple, yet powerful system to manage their home cloud.

<br>

## **Prerequisites**

Before you begin, ensure you have the following:

- A computer or Raspberry Pi where you want to run CasaOS.
- Docker installed on your system. If you haven't installed Docker yet, refer to the [Docker installation guide](https://docs.docker.com/get-docker/).

<br>

## **Installation**

### **Step 1: Install CasaOS**

CasaOS provides an easy installation method using a one-line script. To install, run the following command in your terminal:

  ```bash
  curl -fsSL https://get.casaos.io -o get-casaos.sh && sh get-casaos.sh
  ```

This script will automatically download and install CasaOS along with all necessary dependencies.

<br>

### **Step 2: Access CasaOS**

Once the installation is complete, you can access the CasaOS interface through your web browser:

  ```yaml
  http://<YOUR-SERVER-IP>:80
  ```

Replace `<YOUR-SERVER-IP>` with the IP address of the system where CasaOS is installed. This will open the CasaOS dashboard.

<br>

## **Initial Setup**

Upon accessing CasaOS in your browser, you'll be greeted with the dashboard. From here, you can configure and manage your home cloud.

### **Configuring CasaOS**

- **Dashboard**: View system status and quick information about your setup.
- **App Store**: Easily browse and install Docker-based applications.
- **File Management**: Organize and manage the files stored in CasaOS.
- **Settings**: Adjust system settings, network configurations, and other preferences.

<br>

### **Adding Applications**

To install applications via the CasaOS App Store:

1. Open the **App Store** from the left sidebar.
2. Browse or search for applications you'd like to install.
3. Click on the application and follow the prompts to install it.

<br>

### **File Management**

CasaOS simplifies the management of your files:

1. Go to the **Files** section from the dashboard.
2. You can upload, download, and organize files in this section.

<br>

## **Conclusion**

CasaOS is a user-friendly solution for setting up a personal home cloud, utilizing Docker for efficient application management. It’s a great choice for users seeking a simple way to manage personal data and home services.

For more detailed information and advanced configurations, refer to the [official CasaOS documentation](https://docs.casaos.io/).

<br>

## **Resources**

- [Official CasaOS Documentation](https://docs.casaos.io/)
- [CasaOS GitHub Repository](https://github.com/casaos)

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

- 12/10/2024

## **License**

- This script is provided as-is without any warranties. Users are advised to review and understand the script before executing it.

- This project is licensed under the MIT License. See the LICENSE file for details.
