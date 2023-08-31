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

In the terraform file (refer main.tf file) we can connect to AWS cloud using 'provider block'     
In the provider block, mention the region name  
provider "aws" {
  region = "eu-central-1"
}
To create an ec2 instance, should use 'resource block'  
In the resource block, We should mention information to create an instance.    
To create an EC2 instance and security group, we should have the below information    
Instance name  
Operating system (AMI)  
instance Type  
Keypair  
VPC

Use the documentation

https://registry.terraform.io/providers/hashicorp/aws/latest  
https://registry.terraform.io/modules/terraform-aws-modules/security-group/aws/latest


Task 2: Use Ansible for configuring EC2 (Install Nginx or Apache)  

Set Up one EC2 Instance as the Master:
Configure the necessary security groups and SSH key pairs to ensure proper connectivity between the master and the host machine.   
Install Ansible on the Master  https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-ansible-on-ubuntu-22-04  
Verify that Ansible is installed with ansible --version

Create an Ansible Inventory File:  
This file lists the target host machines where you want to install Nginx.  
[web]
ubuntu@172.31.27.151 ansible_ssh_private_key_file="id_rsa"  

Create an Ansible playbook (refer nginx.yml) to install Nginx on the target host(s).  
Run Ansible Playbook  
sudo ansible-playbook -i hosts nginx.yml

Verify Nginx Installation with your public ip
http://3.120.149.155

Task 05: Create a CI/CD Pipeline (Using GitHub Actions or Jenkins)
install jenkins and docker using in the instance below links  
https://www.jenkins.io/doc/book/installing/docker/#setup-wizard
https://docs.docker.com/engine/install/ubuntu/#uninstall-docker-engine  

check the jenkins using your public ip (eg: http://35.159.17.214:8080/)
install all the necessary plugins and do the configurations.

dashboard-> Manage Jenkins->System -> make the changes under "Publish over SSH" -> update your key and SSH Servers settings
dashboard -> create a new job -> go to configurations -> add your github project url -> select Git under source code management and give git repository url -> check "GitHub hook trigger for GITScm polling" under build triggers -> check "Send files or execute commands over SSH after the build runs" under build environment -> give name for the server -> add the source file set (eg: **/*.html) -> give the remote directry (eg:/) -> apply and save

Make sure to give permission for the users in html directory   
Then Build the project and check if index.html file is there inside the instance and verify it using your public ip


