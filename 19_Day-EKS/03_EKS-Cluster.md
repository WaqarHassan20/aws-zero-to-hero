### EKS Cluster
- EKS Cluster is a Kubernetes cluster that is managed by Amazon Web Services (AWS).
- It is a fully managed service that is available in all AWS regions.
- It is a multi-node cluster that is available in all AWS regions.
- It is a multi-zone cluster that is available in all AWS regions.
- It is a multi-region cluster that is available in all AWS regions.
- It is a multi-account cluster that is available in all AWS regions.
- It is a multi-tenant cluster that is available in all AWS regions.
- It is a multi-namespace cluster that is available in all AWS regions.

- I have created a cluster using the eksctl command line tool. It is a simple and easy to use tool that allows you to create and manage EKS clusters from the command line. It is a great tool for developers who want to quickly create and manage EKS clusters without having to use the AWS Management Console.
- Now the cluster have created on UI and showing me the oidc which is open id connect and it is a service that allows you to authenticate users and applications using the OpenID Connect protocol. It is a great way to secure your EKS cluster and it is easy to set up and use. It allows you to authenticate users and applications using the OpenID Connect protocol, which is a widely used authentication protocol that is supported by many identity providers.
- It is a great way to secure your EKS cluster and it is easy to set up and use. It allows you to authenticate users and applications using the OpenID Connect protocol, which is a widely used authentication protocol that is supported by many identity providers.
- This oidc will help to find and filter that specific cluster whenever you will mess up with the IAM service.
  

#### Working of Ingress and ALB

- In Kubernetes, without Ingress, each service is usually exposed using its own Load Balancer. This Load Balancer receives incoming traffic from the internet and simply forwards it to a node in the cluster, and then Kubernetes Service sends it to the correct pods. The problem with this approach is that every service needs a separate Load Balancer, which increases cost and does not provide smart routing like based on URL paths or domains.
- With Ingress, this approach becomes more efficient. Instead of creating multiple Load Balancers, we use a single Application Load Balancer (ALB) in most cloud setups like AWS. We define routing rules such as /api or /app inside an Ingress resource. These rules are not directly used by the ALB; instead, an Ingress Controller (like AWS Load Balancer Controller or NGINX Ingress Controller) reads these rules and configures the ALB accordingly.
- After this setup, the ALB stores these routing rules internally. When a request comes, the ALB does not contact the Ingress Controller again. It simply checks its existing configuration and forwards the request to the correct Kubernetes Service based on the path or domain. The Service then distributes the request to the appropriate pods. So, Ingress Controller acts like a configurator that defines routing rules, while the ALB acts as the actual traffic handler that executes those rules at runtime.