<!-- ![Portainer](../assets/Portainer.png# Portainer Tutorial -->
<img src="../assets/Portainer.png" alt="Alt Text" width="400">

# Portainer

This tutorial covers the installation and basic usage of Portainer, an open-source tool designed to help manage Docker environments. Portainer provides a user-friendly web interface to manage Docker containers, images, networks, and volumes.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
  - [Step 1: Pull the Portainer Image](#step-1-pull-the-portainer-image)
  - [Step 2: Run Portainer](#step-2-run-portainer)
- [Accessing Portainer](#accessing-portainer)
- [Initial Setup](#initial-setup)
- [Using Portainer](#using-portainer)
  - [Managing Containers](#managing-containers)
  - [Managing Images](#managing-images)
- [Conclusion](#conclusion)
- [Contribution](#contribution)

<br>

## **Overview**

Portainer simplifies Docker management, making it easier to handle containers, images, networks, and volumes through a user-friendly interface.

<br>

## **Prerequisites**

To follow this tutorial, you should:

- Have Docker installed on your system. If Docker is not installed, refer to the [Docker installation guide](https://docs.docker.com/get-docker/).

<br>

## **Installation**

### **Step 1: Pull the Portainer Image**

Pull the Portainer Docker image from the Docker Hub:

```bash
docker pull portainer/portainer-ce
```

<br>

### **Step 2: Run Portainer**

Run the Portainer container with the following command:

```bash
docker run -d -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce
```

This command does the following:

- `-d` runs the container in detached mode.
- `-p 9000:9000` maps the container's port 9000 to the host's port 9000.
- `--name=portainer` names the container as 'portainer'.
- `--restart=always` ensures the container restarts automatically if it stops.
- `-v /var/run/docker.sock:/var/run/docker.sock` mounts the Docker socket.
- `-v portainer_data:/data` creates a volume for Portainer data persistence.

<br>

## **Accessing Portainer**

Once Portainer is running, access it by opening your web browser and navigating to:

```
http://<YOUR-DOCKER-HOST-IP>:9000
```

Replace `<YOUR-DOCKER-HOST-IP>` with the IP address of your Docker host.

<br>

## **Initial Setup**

1. **Create an Admin User**:
   - Upon first accessing Portainer, you'll be prompted to create an admin user.
   - Enter a username and password, then click "Create user".

2. **Connect to Docker**:
   - Select "Docker" as the environment to manage.
   - Click "Connect".

<br>

## **Using Portainer**

With Portainer, you can manage various aspects of your Docker environment:

### **Managing Containers**

1. Click on "Containers" in the left sidebar.
2. View running containers, start/stop existing containers, or create new ones.

### **Managing Images**

1. Click on "Images" in the left sidebar.
2. Pull new images from Docker Hub, remove existing images, or deploy containers from images.

<br>

## **Conclusion**

Portainer simplifies Docker management, making it easier to handle containers, images, networks, and volumes through a user-friendly interface. It's a valuable tool for anyone working with Docker, from beginners to experienced users.

For more advanced features and detailed usage, refer to the [official Portainer documentation](https://documentation.portainer.io/).

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
