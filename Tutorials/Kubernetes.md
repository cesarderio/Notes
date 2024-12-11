<!-- ![Kubernetes](../assets/kubernetes.png) -->
<img src="../assets/kubernetes.png" alt="Alt Text" width="400">


# **Introduction to Kubernetes**

Kubernetes, often abbreviated as K8s, is a powerful open-source platform that automates the deployment, scaling, and management of containerized applications. Originally developed by Google and now maintained by the Cloud Native Computing Foundation (CNCF), Kubernetes is widely used for orchestrating containerized applications in large-scale environments.

With Kubernetes, applications are deployed in containers, which are managed by clusters of machines. Kubernetes abstracts the complexity of managing these clusters and ensures the proper scheduling, scaling, and operational tasks for applications.

<br>

### **Table of Contents**

- [How Kubernetes Works](#how-kubernetes-works)
- [Managing Kubernetes](#managing-kubernetes)
- [Kubernetes Ecosystem](#kubernetes-ecosystem)
- [Key Kubernetes Commands](#key-kubernetes-commands)
- [Best Practices for Using Kubernetes](#best-practices-for-using-kubernetes)
- [Contribution](#contribution)

<br>

## **How Kubernetes Works**

- **Pods**: The smallest deployable units in Kubernetes, representing a single instance of a running process in a cluster.
- **Nodes**: The machines (physical or virtual) that run the containerized applications managed by Kubernetes.
- **Cluster**: A group of nodes running containerized applications managed by Kubernetes.
- **Control Plane**: The component that manages the Kubernetes cluster, including the API server, scheduler, and controller manager.

<br>

## **Managing Kubernetes**

- **YAML Files**: Kubernetes configurations are usually defined using YAML files, specifying the desired state for applications and the resources they require.
- **kubectl**: The command-line tool used to interact with the Kubernetes API and manage the cluster.
- **Deployments**: A controller that ensures the desired number of pod replicas are running.
- **Services**: Abstracts a set of pods and provides a stable IP address or DNS name for accessing the pods.

<br>

## **Kubernetes Ecosystem**

- **Minikube**: A tool for running Kubernetes clusters locally, useful for development and testing.
- **Helm**: A package manager for Kubernetes, helping to define, install, and upgrade complex Kubernetes applications.
- **Kubernetes Dashboard**: A web-based user interface for managing Kubernetes clusters.

<br>

## **Key Kubernetes Commands**

- **`kubectl get pods`**: Lists all pods in the current namespace.
- **`kubectl create -f [file.yml]`**: Creates a resource defined in a YAML file.
- **`kubectl apply -f [file.yml]`**: Applies changes to a resource defined in a YAML file.
- **`kubectl delete -f [file.yml]`**: Deletes a resource defined in a YAML file.
- **`kubectl describe [resource] [name]`**: Shows detailed information about a specific resource.
- **`kubectl logs [pod_name]`**: Fetches logs from a specific pod.
- **`kubectl port-forward [pod_name] [local_port]:[pod_port]`**: Forwards a local port to a port on the pod.
- **`kubectl scale --replicas=[n] [resource_type] [resource_name]`**: Scales a resource to the specified number of replicas.
- **`kubectl exec -it [pod_name] -- [command]`**: Executes a command inside a pod.

<br>

## **Best Practices for Using Kubernetes**

- **Security**: Use role-based access control (RBAC), network policies, and secrets management to secure the cluster.
- **Monitoring and Logging**: Implement comprehensive monitoring and logging tools to ensure the health and stability of your cluster.
- **Resource Limits**: Define resource limits and requests to prevent resource contention and ensure fair allocation.
- **Updates**: Keep the Kubernetes version and container images up to date to avoid security vulnerabilities.

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
