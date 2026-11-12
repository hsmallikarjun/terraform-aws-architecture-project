# terraform-aws-architecture-project
End-to-End Infrastructure Automation on AWS using Terraform (Custom VPC, Subnets, Internet Gateway, Route Tables, Security Groups, EC2 Instances, and Application Load Balancer).


# AWS Infrastructure Automation with Terraform (Zero-to-Hero Project)

A production-ready infrastructure-as-code (IaC) setup built using Terraform to automate provisioning and deployment on AWS. This project sets up a robust, highly available multi-AZ network architecture complete with an Application Load Balancer (ALB) and automated web server bootstrap configurations.

## 🚀 Architecture Overview
* **Networking:** Custom VPC with defined IPv4 CIDR blocks (`10.0.0.0/16`).
* **Subnets:** Public subnets deployed across multiple Availability Zones (`us-east-1a` & `us-east-1b`) with auto-assigned public IPs.
* **Routing:** Internet Gateway (IGW) attached and custom Route Tables configured for public traffic routing.
* **Security:** Security Groups configured with restricted inbound rules (Port 80 for HTTP, Port 22 for SSH) and full outbound access.
* **Compute:** Ubuntu EC2 instances bootstrapped via custom shell scripts (`user_data`) running Apache web servers displaying dynamic instance metadata.
* **Load Balancing:** Application Load Balancer (ALB) distributing traffic evenly across EC2 instances through healthy Target Groups and Listener Rules.

## 🛠️ Prerequisites & Tech Stack
* **Cloud Provider:** AWS
* **IaC Tool:** Terraform
* **Scripting:** Bash (User Data / Apache Web Server)

## ⚙️ Quick Start Guide
1. **Configure AWS Credentials:**
   ```bash
   aws configure

   Initialize Terraform:  terraform init

   Validate & Plan:terraform validate
                   terraform plan

   Deploy Infrastructure:terraform apply -auto-approve

   At last Clean Up (Destroy Infrastructure to avoid costs):terraform destroy -auto-approve
