## What is EC2 in AWS

EC2 (Elastic Compute Cloud) is a web service that provides resizable compute capacity in the cloud. It allows you to run virtual servers, called instances, on demand.
- EC2 is like renting a virtual machine in the cloud. You can choose the operating system, CPU, memory, and storage that you need.
- You can launch and manage EC2 instances using the AWS Management Console, CLI, or SDK
- EC2 is a fundamental service in AWS and is used for a wide range of applications, from hosting websites to running big data analytics.
- EC2 provides a variety of instance types optimized for different use cases, such as compute-optimized, memory-optimized, and storage-optimized instances.
- EC2 also offers features like auto-scaling, which allows you to automatically adjust the number of instances based on demand, and Elastic Load Balancing, which distributes incoming traffic across multiple instances for better performance and reliability.

### Main Key Points

- There are several types of ec2 machines, such as:
  - General Purpose (T3, M5)
  - Compute Optimized (C5)
  - Memory Optimized (R5)
  - Storage Optimized (I3)
  - Accelerated Computing (P3, G4)
- You can choose the instance type based on your workload requirements, such as CPU, memory, storage, and network performance. 

- EC2 instances can be accessed using Public IPv4 address from the outside world.

- use the command `ssh -i filename.pem ubuntu@public-ipv4-address` to connect to the EC2 instance using SSH. Make sure to replace `filename.pem` with the path to your private key file and `public-ipv4-address` with the actual public IPv4 address of your EC2 instance.

- also run the command `chmod 400 filename.pem` to set the correct permissions for your private key file before connecting to the EC2 instance. This command ensures that only the owner can read the file, which is necessary for security reasons when using SSH.

- on in some cases you can use the command `chmod 600 filename.pem` instead of chmod 400, but it is generally recommended to use chmod 400 for private key files to ensure that they are not accessible by other users on the system.
  
