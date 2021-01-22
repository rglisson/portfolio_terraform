# Terraform Demo

![](img/terraform.PNG)

# Introduction & Goals
- The goal of the project was to use infrastructure-as-Code to create an ec2 instance, deploy on custom VPC on custom subnet, use a public IP address to ssh into the server, and setup a webserver to handle web traffic.

# Application
- "Terraform is an open-source infrastructure as code software tool created by HashiCorp. Users define and provision data center infrastructure using a declarative configuration language known as HashiCorp Configuration Language, or optionally JSON"
- I used Visual Studio Code to run the HCL script. To initialize the connection from Visual Studio to AWS, run 'terraform init'

![](img/plugin.PNG)

# Script
- Connect to AWS using by selecting your region and access keys

![](img/access.PNG)

- You can find the terraform templates from their website: https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/instance
- The first script assigns our VPC name with a CIDR block.

![](img/1_vpc.PNG)


- The second script sets up our internet gateway, named 'gw'.

![](img/2_ig.PNG)


- The third script is for our custom route table for IPv4 & IPv6 traffic

![](img/3_route.PNG)

- The fourth script creates the subnet. Make sure you match the correct availability zone

![](img/4_subnet.PNG)


- The fifth script associates the subnet with the route table

![](img/5_rt.PNG)


- The sixth script creates our security group. We allow traffic for HTTPS/HTTP  and SSH

![](img/6_sg_1.PNG)

- The seventh script creates a network interface with an IP address

![](img/7_ni.PNG)


- The eighth script creates an elastic IP for our network interface

![](img/8_elastic.PNG)

- The ninth script creates our ubuntu server and automatically runs a bash script to install updates and run apache

![](img/9_server.PNG)


# Run Script
- To run script: terraform apply --auto-approve
- To undo deployment: terraform destroy
- If the deployment is successfull, you will see that the EC2 is running on AWS

![](img/ec2.PNG)

- You can now ssh into the ubuntu server

![](img/ssh.PNG)


# Conclusion
- Terraform allows you to deploy a fully configured server within minutes of running the script. Since Terraform is open-source, it can be used universally on any cloud platform. 
