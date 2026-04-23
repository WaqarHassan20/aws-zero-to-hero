
### What are the CFT and how do they work?
CloudFormation templates (CFT) are JSON or YAML formatted text files that describe the infrastructure and configuration of the resources in AWS.
CFTs are used to automate the deployment and management of AWS resources. They allow you to define your infrastructure as code, which can be versioned, tested, and deployed in a consistent manner.
CFTs consist of several sections, including:
- Template Version
- Description
- Resources
- Parameters
- Outputs
- Mappings
- Conditions
- DependsOn
- Metadata
- Transformations
- Description

### Benefits of using CFT
- **Automation**: CFTs allow you to automate the deployment and management of AWS resources.
- **Versioning**: CFTs can be versioned, which allows you to track changes to your infrastructure over time.
- **Testing**: CFTs can be tested before deployment, which allows you to catch errors and ensure that your infrastructure is deployed as expected.
- **Reproducibility**: CFTs can be used to reproduce your infrastructure in a consistent manner.


### When CFT & When aws-cli
- **aws-cli** : use this when you want some short and quick actions on AWS resources
- **CFT** : use this when you want to define your infrastructure as code


## CFT does:
- **creates infrastructure**: helps to creates infrastructure in AWS
- **Drift Detection**: helps to detect any changes in the infrastructure that are not made through CFT

## What are stacks:
- Stacks are collections of resources that are deployed as a unit.
- Stacks are used to deploy and manage your infrastructure in AWS.
- Stacks are defined by CFTs.
- Stacks can be created, updated, and deleted.
- Stacks can be nested, which allows you to create complex infrastructure.
- Stacks can be tagged, which allows you to organize your infrastructure.

