### My account has facing some issues with CodeDeploy, and I am unable to even open a see the Dashboard of CodeDeploy.
### It is showing me the an error of incomplete signup process and some unauthorized access. I have contacted AWS support and they are looking into the issue. I will update this section once the issue is resolved and I am able to access CodeDeploy.

### Good luck!


### What are tags in AWS?

- Tags are metadata that you can add to AWS resources to help organize and manage resources.
- Tags consist of a key and a value, and you can use them to categorize resources based on various criteria such as environment, department, project, or cost center.
- Tags can be used for cost allocation, access control, automation, and resource management.
- For example, you can tag your EC2 instances with the key "Environment" and the value "Production" to easily identify which instances are part of your production environment. You can also use tags to filter and search for resources in the AWS Management Console or to create custom reports for cost allocation.


### Steps from Tutorial for CodeDeploy

- Create an application in CodeDeploy.
- While creating application , choose the compute platform as EC2/On-Premises.
- Now create an EC2 instance as hosting server for our application.
- Once the EC2 instance is up and running, we need to install CodeDeploy agent on it.
- We can do this by connecting to the instance via SSH and running the following commands:

```ssh -i <key_pair> <instance_ip>
```

```sudo apt update, sudo apt install ruby-full -y, sudo apt install wget, cd /home/ubuntu
```

Here we are finding the current region and s3 bucket name . so fix this command from the documentation of AWS CodeDeploy for the correct region and bucket name.

```wget https://aws-codedeploy-us-east-1.s3.amazonaws.com/latest/install
```

```chmod +x install
```

```sudo ./install auto
```

Now you have to start this agent service using the command:

```sudo service codedeploy-agent status
```
OR

```sudo service codedeploy-agent start
```

- Now you have to give the permission to the EC2 instance to talk to CodeDeploy service.
- For that you have to create an IAM role with the name "CodeDeployDemo-EC2-Role". 
- Now attach policy "AWSCodeDeployRole" to it. After creating role, attach it to your EC2 instance.
- Now go to CodeDeploy console then you application and create a deployment group which are actually the target for our deployment.(Target Groups)
- While creating deployment group, choose the service role as "CodeDeployDemo-EC2-Role" and select the EC2 instance which we have created earlier.
- Now go back to IAM Role and allow the ec2FullAccess to the role "CodeDeployDemo-EC2-Role" which we have created earlier.
- Now create an file named as "appspec.yml" always at the root of your github repo. If you are using S3 bucket, you can give custom stored paths.
- Now create a deployment in CodeDeploy and select the application, deployment group and the revision which is your github repo.
- 