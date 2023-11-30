# module-12
Infrastructure as Code with Terraform


Providers in Terraform
1. created main.tf
2. terraform init on terminal. .terraform.lock.hcl and awsprovider file got created
3. added providers.tf

--------------------------------------------------

Resources & Data Sources
1. copied main.tf of gitalb
2. added vpc config to main.tf and performed terraform plan
3. added data "aws_vpc" and new resource to main.tf to create a subnet in an existing VPC
4. apllied it

--------------------------------------------------

Change & Destroy Terraform Resources
1. added tags to main.tf
2. terraform apply shows changes 
3. deleted some resources and applied

--------------------------------------------------

Output values
1. added output values to main.tf, after apply they got printed on the screen

--------------------------------------------------

Variables in Terraform
1. added variable cidr_blcok
2. value can be added after using apply if no value is set in main.tf
3. terraform apply -var "varname=value" skips the input if value is not set or to override a value
4. added terraform.tfvars with a cidr_block value
5. if terraform.tfvars renamed use apply -var-file filename 
6. "default" is used, if no other value is specified
7. "type" specifies if value is a string, boolean or else
8. If its a list of strings, use [0] for first value, [1] second value and so on
9. added values in terraform.tfvars as a list with diffrent attributes

--------------------------------------------------

Create Git Repository for local Terraform Project
1. created gitignore file

--------------------------------------------------

Automate Provisioning EC2 with Terraform
1. recreated main.tf and added variables in .tfvars file, applied afterwards
2. created custom route table and added subnet
3. added security group resource with port 22, 8080, added my public IP to .tfvars. 
4. added egress to allow outgoing traffic
5. added data to get always latest AWS Linux image and resource for creating EC2 and ssh key (of my local pubkey)
6. ssh into EC2
7. added "user_data" to update server, install docker and run container
99. copied main.tf of https://gitlab.com/nanuchi/terraform-learn/-/blob/feature/deploy-to-ec2/main.tf and changed variablenames in tfvars

--------------------------------------------------

Provisioners in Terraform
1. copied main.tf of https://gitlab.com/nanuchi/terraform-learn/-/tree/feature/provisioners
2. changed vars in tfvars file
3. undertood term of provisioners and why it should not be used in terraform

--------------------------------------------------

Modules in Terraform
1. renamed main.tf to main_before_module.tf and created new one
2. copied main, variables and output.tf of https://gitlab.com/nanuchi/terraform-learn/-/tree/feature/modules?ref_type=heads
3. created folders for modules webserver and subnet and created main.tf, outputs.tf and variables.tf
4. performed terraform init and apply
5. destroyed afterwards

--------------------------------------------------

Automate Provisioning EKS cluster with Terraform
1. copied files of https://gitlab.com/nanuchi/terraform-learn/-/tree/feature/eks
2. created terraform.tfvars file
3. updated kubeconfig file to be able to communicate with eks cluster
4. applied nginx-config.yaml

--------------------------------------------------

CI/CD with Terraform

1. copied files of https://gitlab.com/nanuchi/java-maven-app/-/tree/feature/sshagent-terraform
2. created new SSH keypair in AWS for Jenkins
3. installed terraform in jenkins container as root user
4. changed values in variables.tf to my own needs (e.g jenkins running locally on my proxmox host)
5. built pipeline

--------------------------------------------------

Remote State in Terraform

1. added S3 bucket in AWS and added config for bucket in main.tf
2. built pipeline

--------------------------------------------------


Reference: DevOps Bootcamp and TWN