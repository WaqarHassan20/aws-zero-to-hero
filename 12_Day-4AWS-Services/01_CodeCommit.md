# AWS CodeCommit

AWS CodeCommit is a fully managed source control service that hosts secure private Git repositories. It removes the need to run and maintain your own Git server while still giving you the normal Git workflow.

## Key Features

* **Fully managed:** No servers, backups, or software maintenance.
* **Secure:** Repositories are encrypted with AWS KMS and protected in transit with HTTPS or SSH.
* **Highly available:** Data is stored redundantly across AWS infrastructure.
* **Scalable:** Works for small projects and large repositories without you managing capacity.
* **Collaborative:** Supports branches, pull requests, and merges for team development.
* **Integrated:** Connects easily with IAM, CodeBuild, and CodePipeline.

## Core Concepts

* **Repository:** A private Git repository where your source code is stored.
* **Branch:** A separate line of development for features, fixes, or experiments.
* **Commit:** A saved snapshot of your changes at a specific point in time.
* **Pull request:** A review step used before merging changes into another branch.

## How It Works

1. Create a repository in CodeCommit.
2. Clone it locally using Git.
3. Work on a branch and push commits back to AWS.
4. Open a pull request for review and merge when approved.
5. Trigger CodeBuild or CodePipeline when new code is pushed.

## Benefits

* **Less administration:** AWS handles the source control service for you.
* **Better security:** IAM controls who can read, write, or manage repositories.
* **Team workflow:** Pull requests and branching make collaboration easier.
* **CI/CD friendly:** Fits naturally into automated build and deployment pipelines.

## Common Access Methods

* **HTTPS:** Simple Git access using HTTPS credentials.
* **SSH:** Secure Git access using SSH keys.
* **IAM:** Permissions are controlled through AWS Identity and Access Management.

## Use Cases

* **Private code hosting:** Store application source code in a private repository.
* **Team collaboration:** Let multiple developers work on the same project safely.
* **CI/CD pipelines:** Use CodeCommit with CodeBuild and CodePipeline.
* **Infrastructure as code:** Store CloudFormation or Terraform templates in Git.