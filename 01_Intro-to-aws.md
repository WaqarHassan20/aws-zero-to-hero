# AWS ZERO TO HERO SERIES

## Intro To AWS

AWS (Amazon Web Services) is a cloud platform that gives you on-demand IT resources such as servers, storage, databases, networking, and analytics.

### Main Key Points
- Pay-as-you-go: You only pay for what you use.
- Global infrastructure: AWS has multiple Regions and Availability Zones for reliability.
- Scalability: Increase or decrease resources based on demand.
- Managed services: AWS handles much of the setup and maintenance.

### Common Service Examples
- `EC2`: Virtual servers for running applications.
- `S3`: Object storage for files, backups, and static websites.
- `RDS`: Managed relational databases (MySQL, PostgreSQL, etc.).
- `Lambda`: Run code without managing servers.

### Quick Example
If you are launching a simple web app:
- Host app on `EC2`.
- Store images in `S3`.
- Use `RDS` for user and product data.

## Private and Public Cloud

Cloud models explain where infrastructure is hosted and who manages it.

### Public Cloud
Infrastructure is owned and managed by a third-party provider (like AWS), and shared securely among customers.

Key points:
- Fast to start and highly scalable.
- Lower upfront cost.
- Ideal for startups, dev/test, and variable workloads.

Example:
- A startup deploys its app to AWS and scales during traffic spikes without buying physical servers.

### Private Cloud
Infrastructure is dedicated to a single organization, either on-premises or hosted by a provider.

Key points:
- More control and customization.
- Can help meet strict compliance requirements.
- Higher cost and management overhead.

Example:
- A bank keeps sensitive core systems in a private cloud to satisfy strict regulatory and security policies.

### Hybrid Approach (Common in Real Projects)
Many companies combine both:
- Private cloud for sensitive workloads.
- Public cloud for scalable web apps and analytics.

