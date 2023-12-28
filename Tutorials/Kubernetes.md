# Kubernetes Tutorial

<br>

## Introduction to Kubernetes

Kubernetes, also known as K8s, is an open-source platform designed to automate deploying, scaling, and operating application containers. It eliminates many of the manual processes involved in deploying and scaling containerized applications. It groups containers that make up an application into logical units for easy management and discovery.

<br>

### How Kubernetes Works

- **Pods**: The smallest deployable units created and managed by Kubernetes.
- **Nodes**: Worker machines in Kubernetes, which can be either a physical or virtual machine.
- **Cluster**: A set of Nodes that run containerized applications managed by Kubernetes.
- **Control Plane**: Coordinates all activities in your cluster, including scheduling applications, maintaining application state, scaling, and rolling out new updates.

<br>

### Managing Kubernetes

- **YAML Files**: Define your applications and their environment using YAML files.
- **kubectl**: Command-line tool for interacting with the Kubernetes cluster.
- **Deployments**: Manage a set of identical pods. Deployments will replace any instances that fail.
- **Services**: An abstraction which defines a logical set of Pods and a policy by which to access them.

<br>

### Kubernetes Ecosystem
- **Minikube**: Run Kubernetes locally for development and testing.
- **Helm**: Used for managing Kubernetes packages called charts.
- **Kubernetes Dashboard**: A web-based user interface for Kubernetes clusters.

<br>

## Key Kubernetes Commands

- **`kubectl get pods`**: Lists all pods in the current namespace.

- **`kubectl create -f [file.yml]`**: Creates a resource (like a pod, service, etc.) defined in a YAML file.

- **`kubectl apply -f [file.yml]`**: Applies changes to a resource defined in a YAML file.

- **`kubectl delete -f [file.yml]`**: Deletes a resource defined in a YAML file.

- **`kubectl describe [resource] [name]`**: Shows detailed information about a specific resource, like `kubectl describe pod my-pod`.

- **`kubectl logs [pod_name]`**: Fetches logs from a specific pod. Useful for debugging.

- **`kubectl port-forward [pod_name] [local_port]:[pod_port]`**: Forwards a local port to a port on the pod, useful for testing.

- **`kubectl scale --replicas=[n] [resource_type] [resource_name]`**: Scales a resource, like a deployment, to the specified number of replicas.

- **`kubectl exec -it [pod_name] -- [command]`**: Executes a command inside a pod, often used to get an interactive shell.

<br>

### Best Practices for Using Kubernetes

- **Regular Updates**: Keep your Kubernetes cluster and applications up to date.
- **Monitoring and Logging**: Implement comprehensive monitoring and logging to understand the state of your cluster and applications.
- **Resource Limits**: Set resource limits and requests to ensure fair allocation of resources among all applications.
- **Security**: Implement robust security measures including network policies, role-based access control, and secrets management.
