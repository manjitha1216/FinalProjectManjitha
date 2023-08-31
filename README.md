# FinalProjectManjitha
Project Tasks

01. Create a Terraform code for Security Group and EC2 Instance  
02. Use Ansible for configuring EC2 (Install Nginx or Apache)  
03. Create a GitHub Repository   
04. Prepare an index.html file  
05. Create a CI/CD Pipeline (Using GitHub Actions or Jenkins), that will take your index.html file from the repository and upload it on EC2 instance.
  
Task 1: Create a Terraform code for Security Group and EC2 Instance

Prepare the terraform   
As part of this, we should setup

Terraform  
VS Code  
AWSCLI  

To create an ec2 instance, We should connect to aws account first  
In terraform file main.tf we can connect to AWS cloud using 'provider block' to create an ec2 instance, should use 'resource block'
In the provider block, mention the cloud name, and region name

provider "aws" {
project = "acme-app"
region  = "us-central1"
}
In the resource block, We should mention information to create an instance.

To create an EC2 instance (object), we should have the below information  
Instance name
Operating system (AMI)
instance Type
Keypair
VPC
Storage


