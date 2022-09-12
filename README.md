# What's inside this repo

This repo contains a simple example demonstrating the usage of a module in Terraform. 

The module of this repo is called [vpc](/modules/vpc) and its functionality can be summed up as below:

- It creates a VPC on AWS with cidr 10.0.0.0/16
- It creates a subnet within the VPC with cidr 10.0.1.0/24 
- It returns the ```subnet_id``` of the subnet described above
- It returns the ```ami_id``` of the latest available amazon linux image 
- The AWS region can be passed as an input to the module (if it is not passed, the module will use the default value of the region variable which is "us-east-1")

The [main.tf ](/main.tf) file calls the vpc module defining the ```region``` parameter and it creates an AWS instance in the subnet which was initially created by the vpc module. Finally the Private IP of the instance is returned to the shell after running ```terraform apply```
