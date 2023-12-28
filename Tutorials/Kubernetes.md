<!-- # Kubernetes Tutorial

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
- **Security**: Implement robust security measures including network policies, role-based access control, and secrets management. -->




# Kubernetes Tutorial

<br>

## Introduction to Kubernetes

Kubernetes, often abbreviated as K8s, is a powerful open-source container orchestration platform that automates containerized applications' deployment, scaling, and management. Originally developed by Google and now maintained by the Cloud Native Computing Foundation (CNCF), Kubernetes provides a robust architecture that enables users to efficiently deploy and manage applications at scale.

At its core, Kubernetes utilizes a master-worker node model, where a central control plane, consisting of components like the API server, controller manager, scheduler, and etcd, manages the overall state and configuration of the cluster. Worker nodes, on the other hand, host the actual containerized applications and run the necessary components like kubelet and kube-proxy to communicate with the control plane. This distributed architecture, coupled with declarative configuration and a rich set of features for service discovery, load balancing, and automatic scaling, makes Kubernetes an essential tool for modern containerized application deployment and orchestration.

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

<bra>

### Components of Kubernetes Architecture

- **Kube-apiserver**: The API server is the central component that exposes the Kubernetes API. It processes REST operations, validates and configures data, and acts as the front end for the Kubernetes control plane.
- **etcd**: A distributed key-value store that stores the cluster’s configuration data, providing a consistent and highly available way to manage and store this information.
- **Kube-scheduler**: Watches for newly created Pods with no assigned node and selects a node for them to run on. The scheduler considers factors like resource constraints, affinity/anti-affinity specifications, and more.
- **Kube-controller-manager**: Manages various controllers that regulate the state of the system. Examples include the Node Controller (manages nodes), Replication Controller (ensures the desired number of replicas are running), and more.
- **Cloud-controller-manager**: A set of controllers that interact with the underlying cloud provider’s API to manage resources like virtual machines, load balancers, and storage volumes.

<br>

### Worker Node Components

- **Kubelet**: The primary “node agent” that runs on each node. It ensures that containers are running in a Pod, and it communicates with the master node to receive and execute commands.
- **Kube-proxy**: Maintains network rules on nodes, implementing the Kubernetes Service concept. It enables communication to the correct Pod from within or outside the cluster.
- **Container Runtime**: The software responsible for running containers, such as Docker or containerd. It pulls the container image from a registry, unpacks the container, and runs it.

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

<br>

### Conclusion

The master node consists of essential components such as the kube-apiserver, etcd, kube-scheduler, kube-controller-manager, and cloud-controller-manager, which collectively manage the cluster’s state, configuration, scheduling, and various controllers. On the worker nodes, the kubelet, kube-proxy, and a container runtime collaborate to execute and maintain containerized applications, ensuring their proper deployment and communication. Kubernetes streamlines the deployment, scaling, and management of containerized applications, offering a comprehensive solution for modern, scalable, and resilient infrastructure.
