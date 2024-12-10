# **Containerization and Virtualization**

A beginner-friendly guide to understanding Docker and Kubernetes, two powerful tools for containerization and orchestration.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Objectives](#objectives)
- [Prerequisites](#prerequisites)
- [Steps](#steps)
  - [Docker Commands](#docker-commands)
  - [Kubernetes Commands](#kubernetes-commands)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

Containerization and virtualization are technologies that allow you to run software applications in isolated environments. This tutorial focuses on Docker for containerization and Kubernetes for orchestration.

<br>

## **Objectives**

By the end of this tutorial, you will:

- Understand the basics of Docker and Kubernetes.
- Learn how to use Docker commands to manage containers.
- Learn how to use Kubernetes commands for orchestrating containerized applications.

<br>

## **Prerequisites**

- Basic understanding of IT operations and command-line interfaces.
- A Linux-based system for practice (e.g., Ubuntu, CentOS).
- Administrative access to install software and configure systems.

<br>

## **Steps**

### **Docker Commands**

Docker is a platform for developing, shipping, and running applications inside containers. Containers package the application along with its dependencies, providing a consistent environment across different platforms.

- **`docker run [options] [image]`**
  Runs a Docker container from an image.
  Example:

    ```bash
    docker run -d -p 80:80 nginx
    ```

  This command starts an Nginx server in detached mode and maps port 80.

- **`docker build -t [tag] .`**
  Builds a Docker image from a Dockerfile in the current directory. The `-t` flag tags the image with a name.

- **`docker images`**
  Lists all Docker images on the local system.

- **`docker ps`**
  Lists running containers. Use `docker ps -a` to list all containers.

- **`docker stop [container_id]`**
  Stops a running container.

- **`docker rm [container_id]`**
  Removes a container.

- **`docker rmi [image_id]`**
  Removes a Docker image.

- **`docker pull [image]`**
  Pulls a Docker image from Docker Hub or other registries.

- **`docker exec -it [container_id] [command]`**
  Executes a command inside a running container, such as accessing the shell.
  Example:

  ```bash
  docker exec -it [container_id] /bin/bash
  ```

<br>

### **Kubernetes Commands**

Kubernetes is an orchestration tool used to manage containerized applications at scale. It automates the deployment, scaling, and operation of applications in containers.

- **`kubectl get pods`**
  Lists all pods in the current namespace.

- **`kubectl create -f [file.yml]`**
  Creates a resource (like a pod, service, etc.) defined in a YAML file.

- **`kubectl apply -f [file.yml]`**
  Applies changes to a resource defined in a YAML file.

- **`kubectl delete -f [file.yml]`**
  Deletes a resource defined in a YAML file.

- **`kubectl describe [resource] [name]`**
  Shows detailed information about a specific resource, such as a pod.
  Example:

  ```bash
  kubectl describe pod my-pod
  ```

- **`kubectl logs [pod_name]`**
  Fetches logs from a specific pod. This is useful for debugging.

- **`kubectl port-forward [pod_name] [local_port]:[pod_port]`**
  Forwards a local port to a port on the pod, useful for testing purposes.

- **`kubectl scale --replicas=[n] [resource_type] [resource_name]`**
  Scales a resource, such as a deployment, to the specified number of replicas.

- **`kubectl exec -it [pod_name] -- [command]`**
  Executes a command inside a pod, often used to get an interactive shell.

<br>

## **Resources**

- [Docker Documentation](https://docs.docker.com)
- [Kubernetes Documentation](https://kubernetes.io/docs)

<br>

## **Contribution**

Your contributions can make this guide even better:

- Fork the repository.
- Create a new branch:

  ```bash
  git checkout -b my-awesome-feature
  ```

- Make your changes.
- Commit your changes:

  ```bash
  git commit -am 'Added some amazing features'
  ```

- Push to the branch:

  ```bash
  git push origin my-awesome-feature
  ```

- Create a new Pull Request.

Contributions are welcome! Feel free to open issues, suggest improvements, or submit pull requests to improve the content.

<br>

## **Author**

- **Raphael Chookagian** | [GitHub Profile](https://github.com/cesar-group)

## **Date of Latest Revision**

- 12/10/2024

## **License**

- This guide is provided as-is without any warranties. Users are advised to review and understand the content before following the steps.
- This project is licensed under the MIT License. See the LICENSE file for details.
