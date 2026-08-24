# TKH-Final-Capstone

# Secure Automated Web Architecture

## Description

This project demonstrates the deployment of secure cloud infrastructure using Infrastructure as Code (IaC) principles. Terraform is used to provision AWS networking resources and deploy an EC2 web server running Apache. GitHub Actions and tfsec are integrated to provide automated security scanning and validation of the Terraform code before deployment.

## Problem Statement

Organizations need a repeatable and secure way to deploy cloud infrastructure while reducing manual configuration errors. This project addresses that challenge by automating infrastructure deployment and incorporating security validation into the development workflow.

## Technologies Used

- AWS
- Terraform
- Amazon EC2
- Amazon VPC
- GitHub
- GitHub Actions
- tfsec
- Apache HTTP Server

## Architecture

The infrastructure is deployed inside a custom AWS VPC with a CIDR block of `10.0.0.0/16`.

Components include:

- Custom VPC
- Public Subnet (`10.0.1.0/24`)
- Internet Gateway
- Route Table and Route Table Association
- Security Group
- EC2 Web Server

Security is enforced through a Security Group that:

- Allows HTTP traffic (Port 80) from the internet
- Restricts SSH traffic (Port 22) to a trusted IP address
- Allows outbound traffic as required for system updates

## Methodology

1. Terraform was used to define the AWS infrastructure.
2. A custom VPC and public subnet were created.
3. An Internet Gateway and Route Table were configured to provide internet access.
4. A Security Group was configured to control inbound and outbound traffic.
5. An EC2 instance was deployed using Amazon Linux.
6. A user data script automatically installed and started Apache.
7. GitHub Actions was configured to execute tfsec security scans on every push to the main branch.
8. The infrastructure was deployed using Terraform.

## Results

- Successfully provisioned AWS infrastructure using Terraform.
- Created a functioning EC2 web server accessible through a public IP address.
- Automated Apache installation using a Terraform user data script.
- Implemented a GitHub Actions pipeline for automated security scanning.
- Successfully passed tfsec security validation and generated a green GitHub Actions pipeline run.

## Future Improvements

Potential enhancements include:

- Configure HTTPS using AWS Certificate Manager.
- Deploy behind an Application Load Balancer.
- Implement Auto Scaling Groups.
- Store Terraform state remotely using Amazon S3.
- Add CloudWatch monitoring and alerts.
- Expand the CI/CD pipeline with automated deployment stages.

## Author

Franklin

TKH Final Capstone Project
