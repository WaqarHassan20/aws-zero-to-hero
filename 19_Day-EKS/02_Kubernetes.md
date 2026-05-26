### What is Kubernetes

- Kubernetes is an open-source container orchestration platform that automates the deployment, scaling, and management of containerized applications. It was originally developed by Google and is now maintained by the Cloud Native Computing Foundation (CNCF). Kubernetes provides a framework for running distributed systems resiliently, allowing you to manage your applications efficiently across a cluster of machines.

- We install the things in MasterNode like:
- **API Server** : It is the central component of the Kubernetes control plane that exposes the Kubernetes API. It serves as the entry point for all administrative tasks and communication between components in the cluster. The API server validates and processes API requests, and updates the cluster state accordingly.
- **ETCD** :  It is a distributed key-value store that Kubernetes uses to store all cluster data, including configuration, state, and metadata. It ensures consistency and reliability across the cluster.
- **Scheduler** : It is responsible for scheduling pods (the smallest deployable units in Kubernetes) onto worker nodes based on resource requirements and constraints.
- **Controller Manager** : It runs various controllers that manage the state of the cluster, such as node controller, replication controller, and endpoint controller. These controllers ensure that the desired state of the cluster is maintained by monitoring and responding to changes in the cluster.
- **Cloud Controller Manager** : It is responsible for managing cloud-specific resources and interactions with the underlying cloud provider. It allows Kubernetes to integrate with various cloud platforms and manage resources like load balancers, storage, and networking.
- **Kubelet** : It is the agent that runs on each worker node and is responsible for managing the containers that run on that node. It communicates with the API server to receive instructions and reports back the status of the node.

#### ETCD information
- In kubernetes, etcd is a combo of two different terms. One is etc/ and the other is d.
- The etc/ is a directory in Linux where configuration files are stored and d stands for distributed key-value store. So etcd is a distributed key-value store that Kubernetes uses to store all cluster data, including configuration, state, and metadata. It ensures consistency and reliability across the cluster.
- ETCD is a distributed key-value store that is used to store the cluster state and configuration data. It is a highly available and fault-tolerant system that is used to store the cluster state and configuration data.

#### Flow of Kubernetes
- When i deploy my any of the app inside the pod which will be inside any worker node, then all the nodes can access it inside the kubernetes cluster but the external world cannot access it.
- So if i want to access it from outside the cluster, then i need to expose it by using the service. So when i create a service.
- There are three ways for exposing the service.
- **ClusterIP** : It is the default type of service. It is only accessible from the cluster. This is the most common type of service.
- **NodePort** : It exposes the service on a static port on each node's IP address. This port is then forwarded to the pod's container port.
- **LoadBalancer** : It creates an external load balancer that routes traffic to the service. This is typically used in cloud environments where a load balancer can be provisioned automatically.
- The best approach is to use the LoadBalancer type of service because it is more scalable and it can handle more traffic. It also provides better performance and it is more secure than the other two types of services.
- If i have a cluster of 100 nodes, then i can use the LoadBalancer type of service to expose my app to the external world.
- I will use an Ingress controller to manage external access to services in the cluster. This avoids creating multiple LoadBalancer services for each application. Instead, a single external entry point (usually one LoadBalancer) is used, and the Ingress controller routes traffic to the appropriate service based on host names or URL paths.
- User → LoadBalancer → Ingress Controller → Service → Pod → Container

#### What if setup the Kubernetes cluster on AWS manually by spinning up 6 instances 3 for MasterNode and 3 for WorkerNode ?

- We need to install the things in each instance.
- So if something is asked from MasterNode to WorkerNode, it will take time to respond.
- This process will call the API call and it will take time to respond.
- Plus it is a very tedious and error prune process too.
- Though we can use the service **Kops** to automate the setup process.
- For one cluster, if etcd creates issues or server crashes or certificate expires or any other issues, then the whole cluster will be down and it will take time to recover the cluster.
- And this is the effort for one cluster , imagine if you have 100 clusters, then it will be a nightmare to manage all the clusters. 

#### Architecture

- It has two main parts.
- One is Control Plane or Master Node.
- The Other is Data Plane or Worker node.
- 