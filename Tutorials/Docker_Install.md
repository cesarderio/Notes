# How to Install Docker on Ubuntu

Docker is a platform for developing, shipping, and running applications inside containers. This guide will walk you through the steps to install Docker on Ubuntu.

## Prerequisites

Before you begin, ensure you have the following:

- An Ubuntu machine with sudo privileges.
- Basic familiarity with the command line.

## Step 1: Update Package Index

First, update the apt package index and ensure that you have the necessary packages to allow apt to use a repository over HTTPS:

```bash
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```

## Step 2: Add Docker's GPG Key

Add Docker’s official GPG key to ensure the integrity of the software packages downloaded from the Docker repository:

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

## Step 3: Add Docker Repository

Add the Docker repository to your system's software repository list:

```bash
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

## Step 4: Update Package Index Again

Update the apt package index again:

```bash
sudo apt update
```

## Step 5: Check Docker Version

Ensure you are about to install Docker from the Docker repository instead of the default Ubuntu repository:

```bash
apt-cache policy docker-ce
```

## Step 6: Install Docker

Install Docker:

```bash
sudo apt install docker-ce
```

## Step 7: Check Docker Service Status

Check the status of the Docker service:

```bash
sudo systemctl status docker
```

## Step 8: Add User to Docker Group (Optional)

Optionally, you can add your user to the `docker` group to run Docker commands without sudo:

```bash
sudo usermod -aG docker ${USER}
```

To apply the new group membership, log out of your server and back in, or type the following:

```bash
su - ${USER}
```

## Step 9: Verify Docker Installation

Verify that Docker is installed correctly by running the `hello-world` image:

```bash
docker run hello-world
```

## Conclusion

Docker should now be successfully installed on your Ubuntu machine. You can now start using Docker to containerize your applications and deploy them with ease.

