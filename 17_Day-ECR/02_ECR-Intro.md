## What are EC2, EBS, and EKS?

- Elastic means that a service is highly scalable and available on demand.
- EC2, EBS, and EKS are all part of AWS's Elastic services.

### Amazon EC2 (Elastic Compute Cloud)

- It is a virtual machine (server) in the cloud.
- You can install OS (Linux/Windows)
- Run apps, websites, backend servers
- Full control like your own computer
- Example: Hosting your Node.js app or database server

### Amazon EBS (Elastic Block Store)
- It is storage (hard disk) for EC2
- Works like a hard drive (SSD)
- Attached to EC2 instances
- Stores OS, files, databases
- Example: Your EC2 server needs space → EBS provides it

### Amazon EKS (Elastic Kubernetes Service)

- It is a managed Kubernetes service

- Used to run containers (Docker apps) at scale
- Handles deployment, scaling, orchestration
- AWS manages the Kubernetes control plane
- Example: Running multiple microservices in containers

#### Simple analogy 🔥
- EC2 → Computer (CPU + RAM)
- EBS → Hard Drive
- EKS → System that manages many containerized apps automatically
#### When to use what
- Use EC2 → when you want full control (manual server)
- Use EBS → when your EC2 needs persistent storage
- Use EKS → when you are working with Docker + Kubernetes + microservices

---

