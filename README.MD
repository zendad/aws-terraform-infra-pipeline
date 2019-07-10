# AWS Infra Deployment Using Terraform
Note that this is intended to be a demonstration and it **does not** set up a production-quality, well-tuned and highly available environment. It is intended to be a demonstration and provide a quick-start
for anyone who wants to try the functionality of such a setup.

This demonstrates the deployment of infrastructure on AWS.

# Requirements
AWS access keys and secret or If you're running Terraform from an EC2 instance with IAM Instance Profile using IAM Role, Terraform will just ask the metadata API endpoint for credentials.


# Tools
## 1. Terraform
Best practice are followed by separating the resources into different terraform files
1. main.tf - VMs to be deployed
2. variables.tf - variables used in creating the enviroment
3. security.tf - security rules and groups being applied
4. storage.tf - storaged being used (EBS Volumes)
5. network.tf - network components(VPC,subnets and gateways)
7. database.tf - databases(RDS)
8. loadbalancer.tf - ELBs either classic,network or ALB
6. output.tf - example output

# Run the terraform

```
    terraform validate
    terraform init -input=false 
    terraform plan -out=tfplanefs 
    terraform apply -input=false tfplanefs 
    terraform destroy 
```

# Missing tests
This is missing tests not built into terraform code
