
# AWS CLI Commands

A cheat sheet for some of the most popular and useful AWS CLI commands.

## General Commands

| Command | Description |
| --- | --- |
| `aws configure` | Configure AWS CLI with your credentials and region. |
| `aws help` | Get help for a specific command. |
| `aws --version` | Show the version of the AWS CLI. |

## S3 Commands

| Command | Description |
| --- | --- |
| `aws s3 ls` | List all S3 buckets. |
| `aws s3 ls s3://<bucketa_name>` | List all objects in a bucket. |
| `aws s3 cp <local-path> s3://<bucketa_name>` | Copy a file from your local machine to an S3 bucket. |
| `aws s3 cp s3://<bucketa_name>/<key> <local-path>` | Copy a file from an S3 bucket to your local machine. |
| `aws s3 sync <local-path> s3://<bucketa_name>` | Sync a directory with an S3 bucket. |
| `aws s3 mv <source> <destination>` | Move a file or object. |
| `aws s3 rm s3://<bucketa_name>/<key>` | Delete an object from an S3 bucket. |

## EC2 Commands

| Command | Description |
| --- | --- |
| `aws ec2 describea_instances` | Describe all EC2 instances. |
| `aws ec2 starta_instances -a_instancea_ids <instancea_id>` | Start an EC2 instance. |
| `aws ec2 stopa_instances -a_instancea_ids <instancea_id>` | Stop an EC2 instance. |
| `aws ec2 reboota_instances -a_instancea_ids <instancea_id>` | Reboot an EC2 instance. |
| `aws ec2 terminatea_instances -a_instancea_ids <instancea_id>` | Terminate an EC2 instance. |
| `aws ec2 create-security-group --groupa_name <groupa_name> --description <description>` | Create a new security group. |
| `aws ec2 authorize-security-groupa_ingress --groupa_name <groupa_name> --protocol <protocol> --port <port> --cidr <cidr>` | Add a new inbound rule to a security group. |

## IAM Commands

| Command | Description |
| --- | --- |
| `aws iam list-users` | List all IAM users. |
| `aws iam create-user --usera_name <usera_name>` | Create a new IAM user. |
| `aws iam list-roles` | List all IAM roles. |
| `aws iam create-role --rolea_name <rolea_name> --assume-role-policy-document <policy-document>` | Create a new IAM role. |
| `aws iam list-policies` | List all IAM policies. |
| `aws iam create-policy --policya_name <policya_name> --policy-document <policy-document>` | Create a new IAM policy. |

## CloudWatch Commands

| Command | Description |
| --- | --- |
| `aws logs describe-log-groups` | List all CloudWatch log groups. |
| `aws logs describe-log-streams --log-groupa_name <log-groupa_name>` | List all log streams in a log group. |
| `aws logs get-log-events --log-groupa_name <log-groupa_name> --log-streama_name <log-streama_name>` | Get log events from a log stream. |
| `aws cloudwatch list-metrics` | List all CloudWatch metrics. |
| `aws cloudwatch get-metric-statistics -a_namespace <namespace> --metrica_name <metrica_name> --start-time <start-time> --end-time <end-time> --period <period> --statistics <statistics>` | Get statistics for a metric. |

## Lambda Commands

| Command | Description |
| --- | --- |
| `aws lambda list-functions` | List all Lambda functions. |
| `aws lambda create-function --function-name <function-name> --runtime <runtime> --role <role> --handler <handler> --zip-file <zip-file>` | Create a new Lambda function. |
| `aws lambda invoke --function-name <function-name> <output-file>` | Invoke a Lambda function. |
| `aws lambda update-function-code --function-name <function-name> --zip-file <zip-file>` | Update a Lambda function's code. |

## RDS Commands

| Command | Description |
| --- | --- |
| `aws rds describe-db-instances` | List all RDS instances. |
| `aws rds create-db-instance --db-instance-identifier <db-instance-identifier> --db-instance-class <db-instance-class> --engine <engine>` | Create a new RDS instance. |
| `aws rds reboot-db-instance --db-instance-identifier <db-instance-identifier>` | Reboot an RDS instance. |
| `aws rds delete-db-instance --db-instance-identifier <db-instance-identifier>` | Delete an RDS instance. |

## ECS Commands

| Command | Description |
| --- | --- |
| `aws ecs list-clusters` | List all ECS clusters. |
| `aws ecs create-cluster --cluster-name <cluster-name>` | Create a new ECS cluster. |
| `aws ecs list-services --cluster <cluster-name>` | List all services in a cluster. |
| `aws ecs create-service --cluster <cluster-name> --service-name <service-name> --task-definition <task-definition> --desired-count <desired-count>` | Create a new service. |

## ECR Commands

| Command | Description |
| --- | --- |
| `aws ecr describe-repositories` | List all ECR repositories. |
| `aws ecr create-repository --repository-name <repository-name>` | Create a new ECR repository. |
| `aws ecr get-login-password --region <region>` | Get a login password for Docker. |
| `docker push <aws_account_id>.dkr.ecr.<region>.amazonaws.com/<repository-name>:<tag>` | Push a Docker image to ECR. |

## CloudFormation Commands

| Command | Description |
| --- | --- |
| `aws cloudformation list-stacks` | List all CloudFormation stacks. |
| `aws cloudformation create-stack --stack-name <stack-name> --template-body <template-body>` | Create a new CloudFormation stack. |
| `aws cloudformation update-stack --stack-name <stack-name> --template-body <template-body>` | Update a CloudFormation stack. |
| `aws cloudformation delete-stack --stack-name <stack-name>` | Delete a CloudFormation stack. |

## DynamoDB Commands

| Command | Description |
| --- | --- |
| `aws dynamodb list-tables` | List all DynamoDB tables. |
| `aws dynamodb create-table --table-name <table-name> --attribute-definitions <attribute-definitions> --key-schema <key-schema> --provisioned-throughput <provisioned-throughput>` | Create a new DynamoDB table. |
| `aws dynamodb put-item --table-name <table-name> --item <item>` | Put an item into a DynamoDB table. |
| `aws dynamodb get-item --table-name <table-name> --key <key>` | Get an item from a DynamoDB table. |