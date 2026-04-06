# NACLs in VPC

- NACLs (Network Access Control Lists) are another layer of security in a VPC

- NACLs are stateless, meaning that they evaluate each request independently, without considering the state of the connection. This means that if you allow an incoming request from a specific IP address and port, the response traffic will not be automatically allowed, and you will need to create a separate rule to allow the response traffic.

- NACLs operate at the subnet level, while security groups operate at the instance level. This means that NACLs apply to all instances within a subnet, while security groups can be applied to individual instances. NACLs are evaluated before security groups, so if a request is denied by a NACL, it will not reach the security group for evaluation. This allows you to create a layered security approach, where you can use NACLs to provide a broad level of security for your subnets, and then use security groups to provide more granular control for your instances.


# NAT Gateway in VPC

- A NAT (Network Address Translation) gateway is a managed service that allows instances in a private subnet to connect to the internet or other AWS services, while preventing inbound traffic from the internet from reaching those instances. It acts as a bridge between the private subnet and the internet, allowing outbound traffic to flow from the private subnet to the internet, while blocking any inbound traffic from the internet to the private subnet.

- Inbound traffic is simply traffic that originates from outside the VPC and is destined for resources within the VPC.

- Outbound traffic is traffic that originates from resources within the VPC and is destined for destinations outside the VPC, such as the internet or other AWS services.

- A NAT gateway allows instances in a private subnet to initiate outbound traffic to the internet while preventing any inbound traffic from the internet from reaching those instances, providing a secure way for instances in a private subnet to access external resources without exposing them to potential threats from the internet.


