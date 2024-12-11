![Docker](../assets/docker.png)

# **How to Install Docker on Ubuntu**

This tutorial will go through the steps to install Docker on Ubuntu OS. This tutorial can be used for most Linux distributions. Please see links and resources for more information.

<br>

### **Table of Contents**

- [Prerequisites](#prerequisites)
- [Installation Steps](#installation-steps)
  - [Step 1: Update Package Index](#step-1-update-package-index)
  - [Step 2: Add Docker's GPG Key](#step-2-add-dockers-gpg-key)
  - [Step 3: Add Docker Repository](#step-3-add-docker-repository)
  - [Step 4: Update Package Index Again](#step-4-update-package-index-again)
  - [Step 5: Check Docker Version](#step-5-check-docker-version)
  - [Step 6: Install Docker](#step-6-install-docker)
  - [Step 7: Check Docker Service Status](#step-7-check-docker-service-status)
  - [Step 8: Add User to Docker Group (Optional)](#step-8-add-user-to-docker-group-optional)
  - [Step 9: Verify Docker Installation](#step-9-verify-docker-installation)
- [Conclusion](#conclusion)
- [Contribution](#contribution)

<br>

## **Overview**

Docker is a platform for developing, shipping, and running applications inside containers. This guide will walk you through the steps to install Docker on Ubuntu.

<br>

## **Prerequisites**

Before you begin, ensure you have the following:

- An Ubuntu machine with sudo privileges.
- Basic familiarity with the command line.

<br>

## **Installation Steps**

### **Step 1: Update Package Index**

First, update the apt package index and ensure that you have the necessary packages to allow apt to use a repository over HTTPS:

  ```bash
  sudo apt update
  sudo apt install apt-transport-https ca-certificates curl software-properties-common
  ```

<br>

### **Step 2: Add Docker's GPG Key**

Add Docker’s official GPG key to ensure the integrity of the software packages downloaded from the Docker repository:

  ```bash
  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
  ```

<br>

### **Step 3: Add Docker Repository**

Add the Docker repository to your system's software repository list:

  ```bash
  sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
  ```

<br>

### **Step 4: Update Package Index Again**

Update the apt package index again:

  ```bash
  sudo apt update
  ```

<br>

### **Step 5: Check Docker Version**

Ensure you are about to install Docker from the Docker repository instead of the default Ubuntu repository:

  ```bash
  apt-cache policy docker-ce
  ```

<br>

### **Step 6: Install Docker**

Install Docker:

  ```bash
  sudo apt install docker-ce
  ```

<br>

### **Step 7: Check Docker Service Status**

Check the status of the Docker service:

  ```bash
  sudo systemctl status docker
  ```

<br>

### **Step 8: Add User to Docker Group (Optional)**

Optionally, you can add your user to the `docker` group to run Docker commands without sudo:

  ```bash
  sudo usermod -aG docker ${USER}
  ```

To apply the new group membership, log out of your server and back in, or type the following:

  ```bash
  su - ${USER}
  ```

<br>

### **Step 9: Verify Docker Installation**

Verify that Docker is installed correctly by running the `hello-world` image:

  ```bash
  docker run hello-world
  ```

<br>

## **Conclusion**

Docker should now be successfully installed on your Ubuntu machine. You can now start using Docker to containerize your applications and deploy them with ease.

<br>

## **Contribution**

Your contributions can make this guide even better:

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

- Create a new Pull Request targeting the `Notes` directory.

Contributions are welcome! Feel free to open issues, suggest enhancements, or submit pull requests to improve the script.

<br>

## **Author**

- **Raphael Chookagian** | [GitHub Profile](https://github.com/cesar-group)

## **Date of Latest Revision**

- 12/10/2024

## **License**

- This guide is provided as-is without any warranties. Users are advised to review and understand the guide before executing any commands.

- This project is licensed under the MIT License. See the LICENSE file for details.
