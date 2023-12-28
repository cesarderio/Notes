# Docker Tutorial

<br>

## Introduction to Docker

Docker is a platform for developers and sysadmins to develop, deploy, and run applications with containers. The use of Linux containers to deploy applications is called containerization. Containers are not new, but their use for easily deploying applications is.

<br>

## How Docker Works

- **Containers vs. Virtual Machines**: Unlike virtual machines, containers do not bundle a full operating system - only the necessary components needed to run the application. This makes containers lighter and more efficient.
- **Docker Engine**: The core of Docker is the Docker Engine, a lightweight runtime and toolkit that manages containers, images, builds, and more.
- **Docker Hub**: Docker also provides a cloud-based registry service called Docker Hub where you can share your containers with others.

<br>

## Managing Docker

- **Images**: Create Docker images that package up applications and preconfigured server environments.
- **Containers**: Run instances of Docker images; you can start, stop, move, and delete containers.
- **Dockerfiles**: Use Dockerfiles to automate the creation of container images.
- **Volumes**: Persist data in Docker containers using volumes.
- **Networking**: Connect your Docker containers to each other and to non-Dockerized services using Docker's networking capabilities.

<br>

## Docker Ecosystem

- **Docker Compose**: Tool for defining and running multi-container Docker applications.
- **Docker Swarm**: For managing a cluster of Docker Engines, known as a swarm.

<br>

## Key Docker Commands

- **`docker run [options] [image]`**: This command runs a Docker container from an image. Example: `docker run -d -p 80:80 nginx` starts an Nginx server in detached mode and maps port 80.

- **`docker build -t [tag] .`**: Builds a Docker image from a Dockerfile in the current directory. The `-t` flag tags the image with a name.

- **`docker images`**: Lists all Docker images on the local system.

- **`docker ps`**: Lists running containers. Use `docker ps -a` to list all containers.

- **`docker stop [container_id]`**: Stops a running container.

- **`docker rm [container_id]`**: Removes a container.

- **`docker rmi [image_id]`**: Removes a Docker image.

- **`docker pull [image]`**: Pulls a Docker image from Docker Hub or other registries.

- **`docker exec -it [container_id] [command]`**: Executes a command inside a running container, like accessing the shell.

<br>

## Best Practices for Using Docker

- **Security**: Use trusted base images and scan your images for vulnerabilities.
- **Efficiency**: Optimize your Docker images for size and speed.
- **Storage**: Use Docker volumes for persistent storage.
