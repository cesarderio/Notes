# **Restoring and Redeploying Docker Containers from Backups**

This tutorial will cover creating and restoring Docker containers.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Step-by-Step Guide](#step-by-step-guide)
  - [Step 1: Restore Docker Images](#step-1-restore-docker-images)
  - [Step 2: Restore Docker Volumes](#step-2-restore-docker-volumes)
  - [Step 3: Redeploy Containers](#step-3-redeploy-containers)
- [Conclusion](#conclusion)
- [Contribution](#contribution)

<br>

## **Overview**

Restoring Docker containers from backups is essential for quickly recovering from data loss or replicating your Docker environment on another system. This tutorial will guide you through restoring Docker images, volumes, and redeploying containers using `docker-compose`.

<br>

## **Prerequisites**

- Docker installed on the system where you want to restore the backups.
- Backup files of Docker images, volumes, and `docker-compose.yml` as created in [Docker_Backup](./Docker_Backup.md).

<br>

## **Step-by-Step Guide**

### **Step 1: Restore Docker Images**

To restore Docker images from `.tar` files:

1. **Load Images**:

   ```bash
   docker load -i /path/to/backup/folder/myimage.tar
   ```

   - Replace `/path/to/backup/folder/myimage.tar` with the path to your image backup.

<br>

### **Step 2: Restore Docker Volumes**

Restoring Docker volumes involves creating new volumes and populating them with data from your backups.

1. **Create Volume**:

   ```bash
   docker volume create volume_name
   ```

   - Replace `volume_name` with the name of the volume you're restoring.

2. **Restore Volume Data**:

   ```bash
   docker run --rm -v volume_name:/volume -v /path/to/backup/folder:/backup alpine sh -c "tar xvf /backup/volume_name.tar -C /volume"
   ```

   - Adjust `volume_name` and `/path/to/backup/folder/` accordingly.

<br>

### **Step 3: Redeploy Containers**

If you use `docker-compose`, you can easily redeploy your containers.

1. **Navigate to Backup Directory**:

   ```bash
   cd /path/to/backup/folder
   ```

2. **Redeploy Using Docker Compose**:

   ```bash
   docker-compose -f docker-compose.yml up -d
   ```

   - This command redeploys containers based on the configurations in your `docker-compose.yml`.

<br>

## **Conclusion**

You have now successfully restored your Docker images and volumes and redeployed your containers. This process allows for quick recovery and ensures minimal downtime in case of data loss or when moving to a new Docker environment.

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
