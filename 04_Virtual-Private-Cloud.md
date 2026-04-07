## What is a Virtual Private Cloud (VPC)?

- A virtual private cloud (VPC) is a virtual network dedicated to your AWS account. It allows you to launch AWS resources, such as EC2 instances, in a logically isolated section of the AWS cloud.

- A real life example of a VPC is like having your own private network in the cloud. You can define your own IP address range, create subnets,and configure route tables and network gateways. This gives you complete control over your virtual networking environment.


- An analogy of VPC is like having your own private data center in the cloud. Just like you would have your own physical servers, switches, and routers in a traditional data center, you can create and manage your own virtual resources in a VPC.

🏠 Real-Life Analogy

Think of AWS like a big city 🏙️
The city = AWS cloud
Your VPC = your private house 🏠

Inside your house

Rooms = Subnets
Doors/windows locks = Security Groups
Address = IP range
Roads = Routing tables

👉 Only people you allow can enter your house
👉 You control everything inside


### Without VPC (old EC2-Classic)

- “You live in a hostel where the rooms already exist in a fixed design made by the owner. You can use a room, but you cannot change the building structure, layout, or network design rules.”

- Without VPC (old EC2-Classic)
“You live in a hostel where the rooms already exist in a fixed design made by the owner. You can use a room, but you cannot change the building structure, layout, or network design rules.”

A VPC has an range of IP addresses that you can define, and you can create subnets within that range to organize your resources.
So, the flow of the VPC is like this:
1. A request is made from a user laptops.
2. The request goes through the internet gateway and reaches the AWS cloud.
3. Then the request is routed to public subnet through the internet gateway.
4. Then is reaches to load balancer, which distributes the traffic to the EC2 instances in the private subnet.
5. From load balancer to private subnet, there must a proper route to go to the private subnet.
6. It uses the route table to find the correct path to the private subnet.
7. Then at private subnet, there is a security group that accepts or rejects traffic based on rules defined in security group.
   

## What are the main components of a VPC?
- Subnets: A subnet is a range of IP addresses in your VPC. You can create public subnets, which are accessible from the internet, and private subnets, which are not accessible from the internet.
- Route Tables: A route table contains a set of rules, called routes, that are used to determine where network traffic is directed. Each subnet must be associated with a route table, which controls the routing for that subnet.
- Internet Gateway: An internet gateway is a horizontally scaled, redundant, and highly available VPC component that allows communication between instances in your VPC and the internet. It serves two purposes: to provide a target in your VPC route tables for internet-routable traffic, and to perform network address translation (NAT) for instances that have been assigned public IPv4 addresses.
- Security Groups: A security group acts as a virtual firewall for your EC2 instances to control inbound and outbound traffic. You can specify rules that allow or deny traffic based on protocols, ports, and source/destination IP addresses. Security groups are stateful, meaning that if you allow an incoming request from a specific IP address and port, the response traffic is automatically allowed, regardless of outbound  rules. This makes it easier to manage and secure your instances in the VPC.


## VPC Flow Logs
- VPC Flow Logs is a feature that allows you to capture information about the IP traffic going to and from network interfaces in your VPC. It provides detailed visibility into the traffic patterns and can be used for troubleshooting, monitoring, and security analysis.
- VPC Flow Logs can capture information such as the source and destination IP addresses, ports, protocol, and the action taken (accept or reject) for each traffic flow. This information can be used to identify potential security threats, troubleshoot connectivity issues, and analyze traffic patterns for optimization.
- VPC Flow Logs can be published to Amazon CloudWatch Logs or Amazon S3 for storage and analysis.


![VPC Flow Diagram](./ss//vpc-flow.png)