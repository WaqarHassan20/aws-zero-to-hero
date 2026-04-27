## Flow of code deployment:

We are uisng the four different tools for code deployment if done manually which are as:

1. **Github**: Writes code and pushes it to a version control system (e.g., GitHub, Bitbucket).
2. **Jenkins:** Used for Orchestration and pipeline management. It automates the build, test, and deployment processes.
3. **Docker:** Used for containerization and to build the application into a container image.
4. **ArgoCD:** Used for continuous deployment and to manage the deployment of applications to Kubernetes clusters.


## Alternative tools:
- for Githbub: Gitlab, Bitbucket
- for Jenkins: Gitlab CI/CD, Bamboo, GitHub Actions 
- for Docker: Podman, Buildah
- for ArgoCD: FluxCD, Spinnaker, Jenkins X

## In terms of AWS services, we can use:
- **CodeCommit**: A fully-managed source control service that makes it easy for teams to host secure and scalable private Git repositories.
- **CodeBuild**: A fully managed continuous integration service that compiles source code, runs tests, and produces software packages that are ready to deploy.
- **CodeDeploy**: A fully managed deployment service that automates software deployments to a variety of compute services such as Amazon EC2, AWS Lambda, and on-premises servers.
- **CodePipeline**: A fully managed continuous delivery service that helps you automate your release pipelines for fast and reliable application and infrastructure updates. CodePipeline automates the build, test, and deploy phases of your release process every time there is a code change, based on the release model you define. This enables you to rapidly and reliably deliver features and updates. You can easily integrate AWS services such as CodeBuild, CodeDeploy, and third-party services such as GitHub or Jenkins into any stage of your release process.

## The flow is : 
1. **CodeCommit**: Writes code and pushes it to a version control system (e.g., GitHub, Bitbucket).
2. **CodeBuild**: Compiles source code, runs tests, and produces software packages that are ready to deploy.
3. **CodeDeploy**: Deploys the software packages to a variety of compute services such as Amazon EC2, AWS Lambda, and on-premises servers.
4. **CodePipeline**: Automates the build, test, and deploy phases of your release process every time there is a code change, based on the release model you define. This enables you to rapidly and reliably deliver features and updates. You can easily integrate AWS services such as CodeBuild, CodeDeploy, and third-party services such as GitHub or Jenkins into any stage of your release process.

### Aws CodeCommit service is a fully-managed source control service that makes it easy for teams to host secure and scalable private Git repositories. Here, private word is very important because it means that the code is not accessible to the public and can only be accessed by authorized users.