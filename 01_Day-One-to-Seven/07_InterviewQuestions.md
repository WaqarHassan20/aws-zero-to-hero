## Interview Questions of Production Project Previously Worked On

### Q1. You are about to design a VPC architecture for 2-Tier application. The application needs to be highly available and scalable. What would be your design and why? OR How would you design a VPC architecture ?

- I would create 2 subnets: Private and Public.
- The public subnet would host the load balancer and be accessible from the internet.
- The private subnet would host the application servers.
- I would distribute the subnets across multiple availability zones to ensure high availability.
- Additionally, I would implement auto-scaling for the application servers to ensure scalability.

---

### Q2. Your organization has a VPC with multiple subnets. You want to restrict outbound internet access for resources in one subnet but allow outbound internet access for resources in another subnet. How would you achieve this?

- Route Table Configuration (Recommended) :
- This is the most standard architectural approach.
Allow Access: Associate the subnet with a Public Route Table that has a route (0.0.0.0/0) pointing to an Internet Gateway (IGW).
Restrict Access: Associate the other subnet with a Private Route Table that lacks a route to 0.0.0.0/0. Without this route, resources cannot reach the internet even if they have public IPs.

- Network Access Control Lists (NACLs) :
- This acts as a firewall at the subnet boundary.
Method: Create a custom NACL for the restricted subnet.
Action: Add an Outbound Rule (e.g., Rule #100) that sets the Destination to 0.0.0.0/0 and the Action to DENY.
Note: NACLs are stateless, meaning you must specifically manage both inbound and outbound rules for traffic to flow.

- Security Groups :
- This acts as a firewall at the instance level.
Method: Assign different Security Groups to the resources in each subnet.
Allow Access: Keep the default outbound rule (0.0.0.0/0 ALLOW).
Restrict Access: Remove the default "Allow All" outbound rule and only add specific rules for internal VPC CIDR ranges or specific required endpoints.

- Note: Security Groups are stateful; if you allow an industry-standard request in, the response is automatically allowed out.

---

### Q3. You have a VPC with a public subnet and a private subnet. Instances in the private subnet need to access the internet for software updates. How would you allow internet access for instances in the private subnet?

- I would set up a NAT Gateway in the public subnet. (Network Address Translation - NAT)
- To allow internet access for instances in the private subnet, we can use a NAT Gateway or a NAT instance. We would place the NAT Gateway/instance in the public subnet and configure the private subnet route table to send outbound traffic to the NAT Gateway/instance. This way, instances in the private subnet can access the internet through the NAT Gateway/instance.

---

### Q4. You have launched EC2 instances in your VPC, and you want them to communicate with each other using private IP addresses. What steps would you take to enable this communication?

- Security groups are at instance level.
- NACLs are at subnet level.
- Configure the security groups associated with the EC2 instances to allow inbound and outbound traffic on the necessary ports (e.g., TCP port 80 for HTTP, TCP port 22 for SSH).
- By default, instances within the same VPC can communicate with each other using private IP addresses. 
  To ensure this communication, we need to make sure that the instances are launched in the same VPC and are placed in the same subnet or subnets that are connected through a peering connection or a VPC peering link. 
  Additionally, we should check the security groups associated with the instances to ensure that the necessary inbound and outbound rules are configured to allow communication between them.

---

### Q5. You want to implement strict network access control for your VPC resources. How would you achieve this?

- To implement granular network access control for VPC resources, we can use Network Access Control Lists (ACLs).
- NACLs are stateless and operate at the subnet level. We can define inbound and outbound rules in the NACLs to allow or deny traffic based on source and destination IP addresses, ports, and protocols.
- By carefully configuring NACL rules, we can enforce fine-grained access control for traffic entering and leaving the subnets.

---

### Q6. Your organization requires an isolated environment within the VPC for running sensitive workloads. How would you set up this isolated environment?

- To set up an isolated environment within the VPC, we can create a subnet with no internet gateway attached.
- This subnet, known as an "isolated subnet," will not have direct internet connectivity. We can place the sensitive workloads in this subnet, ensuring that they are protected from inbound and outbound internet traffic. 
   However, if these workloads require outbound internet access, we can set up a NAT Gateway or NAT instance in a different subnet and configure the isolated subnet's route table to send outbound traffic through the NAT Gateway/instance.

---

### Q7. Your application needs to access AWS services, such as S3 securely within your VPC. How would you achieve this?

- To securely access AWS services within the VPC, we can use VPC endpoints.
- VPC endpoints allow instances in the VPC to communicate with AWS services privately, without requiring internet gateways or NAT gateways. 
- We can create VPC endpoints for specific AWS services, such as S3 and DynamoDB, and associate them with the VPC. 
  This enables secure and efficient communication between the instances in the VPC and the AWS services.

---

### Q8. What is the difference between NACL and Security groups ? Explain with a use case ?

- Subnets works at instance level, while NACLs works at subnet level.
- If you have any configuration with instance level, go with the security groups.
- If you have any configuration with subnet level, go with the NACLs.e.g to block the entire subnet from accessing the internet, you would use a NACL. If you want to allow only specific instances to access the internet, you would use security groups.
- NACLs are stateless while security groups are stateful. This means that with NACLs, you need to explicitly allow both inbound and outbound traffic for a connection to work, while with security groups, if you allow inbound traffic, the response is automatically allowed outbound.

- For example, I want to design a security architecture, I would use a combination of NACLs and security groups. At the subnet level, I would configure NACLs to enforce inbound and outbound traffic restrictions based on source and destination IP addresses, ports, and protocols. NACLs are stateless and can provide an additional layer of defense by filtering traffic at the subnet boundary.
  At the instance level, I would leverage security groups to control inbound and outbound traffic. Security groups are stateful and operate at the instance level. By carefully defining security group rules, I can allow or deny specific traffic to and from the instances based on the application's security requirements.
  By combining NACLs and security groups, I can achieve granular security controls at both the network and instance level, providing defense-in-depth for the sensitive application.

---

### Q9. What is the difference between IAM users, groups, roles and policies ?

- IAM User: An IAM user is an identity within AWS that represents an individual or application needing access to AWS resources. IAM users have permanent long-term credentials, such as a username and password, or access keys (Access Key ID and Secret Access Key). IAM users can be assigned directly to IAM policies or added to IAM groups for easier management of permissions.
- IAM Role: An IAM role is similar to an IAM user but is not associated with a specific individual. Instead, it is assumed by entities such as IAM users, applications, or services to obtain temporary security credentials. IAM roles are useful when you want to grant permissions to entities that are external to your AWS account or when you want to delegate access to AWS resources across accounts. IAM roles have policies attached to them that define the permissions granted when the role is assumed.
- IAM Group: An IAM group is a collection of IAM users. By organizing IAM users into groups, you can manage permissions collectively. IAM groups make it easier to assign permissions to multiple users simultaneously. Users within an IAM group inherit the permissions assigned to that group. For example, you can create a "Developers" group and assign appropriate policies to grant permissions required for developers across your organization.
- IAM Policy: An IAM policy is a document that defines permissions and access controls in AWS. IAM policies can be attached to IAM users, IAM roles, and IAM groups to define what actions can be performed on which AWS resources. IAM policies use JSON (JavaScript Object Notation) syntax to specify the permissions and can be created and managed independently of the users, roles, or groups. IAM policies consist of statements that include the actions allowed or denied, the resources on which the actions can be performed, and any additional conditions.

- #### One line definition of all terms :
  - IAM User: An identity representing an individual or application with permanent credentials.
  - IAM Role: An identity that can be assumed by entities to obtain temporary credentials.
  - IAM Group: A collection of IAM users for easier permission management.
  - IAM Policy: A document defining permissions and access controls in AWS.

---

### Q10. You have a private subnet in your VPC that contains a number of instances that should not have direct internet access. However, you still need to be able to securely access these instances for administrative purposes. How would you set up a bastion host to facilitate this access?

- To securely access the instances in the private subnet, you can set up a bastion host (also known as a jump host or jump box). The bastion host acts as a secure entry point to your private subnet. Here's how you can set up a bastion host:
- Create a new EC2 instance in a public subnet, which will serve as the bastion host. Ensure that this instance has a public IP address or is associated with an Elastic IP address for persistent access.
- Configure the security group for the bastion host to allow inbound SSH (or RDP for Windows) traffic from your IP address or a restricted range of trusted IP addresses. This limits access to the bastion host to authorized administrators only.
- Place the instances in the private subnet and configure their security groups to allow inbound SSH (or RDP) traffic from the bastion host security group.
SSH (or RDP) into the bastion host using your private key or password. From the bastion host, you can then SSH (or RDP) into the instances in the private subnet using their private IP addresses.