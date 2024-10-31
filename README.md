# Deploy-A-2-tier-Application-On-AWS-Using-Terraform
Project Summary: Deploying a 2-Tier Application on AWS Using Terraform
In this project, you'll deploy a scalable, secure, and highly available two-tier application on AWS infrastructure using Terraform. The architecture consists of two main layers:

Web/Application Layer - Front-end user access via an Application Load Balancer (ALB), handling traffic across multiple EC2 instances managed by an Auto Scaling Group (ASG).
Database Layer - A back-end relational database managed by Amazon RDS.
The project structure separates configurations into modular files for easier maintenance, scaling, and reusability. You’ll also implement network design best practices using Virtual Private Clouds (VPCs), subnets, NAT gateways, and security groups to ensure secure communication between resources and the internet. Additionally, CloudFront will be set up to handle content distribution, improving access latency for users, and Route 53 for managing DNS and routing.

Project File Structure
Root Directory:

backend.tf: Configures Terraform’s backend, where Terraform state files are stored, typically on a remote backend like S3.
main.tf: Main infrastructure configuration, typically where module calls are placed to organize the deployment workflow.
provider.tf: Specifies AWS as the provider, configuring the credentials and region settings.
terraform.tfvars: Contains variable values for deployment, such as instance types, VPC configuration, and other adjustable settings.
variables.tf: Defines variables used in the infrastructure code for flexibility and reusability.
Modules:

ALB (Application Load Balancer): Defines the ALB for distributing incoming application traffic across EC2 instances. Also includes relevant outputs.
ASG (Auto Scaling Group): Configures the EC2 Auto Scaling Group and includes a config.sh script for launching instances with the necessary environment and application configurations.
CloudFront: Configures Amazon CloudFront for content distribution, reducing latency by caching resources at edge locations.
Key: Manages key pairs for secure SSH access to EC2 instances.
NAT: Configures NAT Gateways to allow instances in private subnets to access the internet without being exposed directly.
RDS (Relational Database Service): Configures Amazon RDS for relational database setup, hosting the backend database for the application.
Route 53: Manages DNS and routing configurations, directing user traffic to the ALB.
Security Group: Manages firewall settings, defining rules for both inbound and outbound traffic for various components.
VPC (Virtual Private Cloud): Configures the networking environment with subnets, routing, and internet gateways.
What You’ll Learn
Terraform Basics and Modularization:

Understanding Terraform basics, syntax, and structure.
Leveraging Terraform modules to create reusable, manageable code.
Infrastructure as Code (IaC) Practices:

Automating infrastructure provisioning on AWS with Terraform.
Version-controlling infrastructure configurations for collaborative development.
AWS Networking and Security Design:

Creating a VPC with both public and private subnets.
Configuring security groups, NAT gateways, and routing to secure application layers.
Managing DNS with Route 53 and implementing security best practices for public and private subnets.
Implementing a Scalable and High-Availability Application Architecture:

Setting up an Application Load Balancer (ALB) to distribute traffic across EC2 instances.
Configuring an Auto Scaling Group to ensure the application scales automatically with demand.
CloudFront and Content Delivery:

Configuring Amazon CloudFront for content caching, minimizing latency for end-users.
Managing Stateful Applications:

Deploying Amazon RDS to handle data storage and retrieval for application backends.
Real-world Deployment Workflow:

Using remote state backends, such as S3, for state management.
Configuring environment variables and secrets for deployment flexibility across development, staging, and production.
