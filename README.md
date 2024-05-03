MY first Terraform script:

Created EC2 instances in AWS using Terraform scripts developed in Codespaces github .Utilized Terraform, an infrastructure as code tool, to automate the provisioning of EC2 instances on the AWS cloud platform.Defined the specifications for EC2 instances, including the AMI (Amazon Machine Image), instance type,VPC,Subnets and KEY_Pairs within the Terraform scripts.before running the code,Running terraform init initializes a Terraform working directory by downloading the provider plugins and modules defined in your configuration, after initializes i have Run "terraform plan" in my Terminal this generates an execution plan that previews the changes Terraform will make to your infrastructure,Overall, terraform plan allows you to preview the changes Terraform will make to your infrastructure before actually applying them, helping you validate your configuration and avoid unintended consequences.and then terraform apply automates the process of provisioning and managing infrastructure resources based on my Terraform configuration, ensuring consistency, reproducibility, and predictability in my infrastructure deployments.

$ aws configure:

AWS Access Key ID [None]: your-access-key-id
AWS Secret Access Key [None]: your-secret-access-key
Default region name [None]: ap-south-1
Default output format [None]: json

terraform ec2 instance code:

provider "aws" {
    region = "ap-south-1"  # Region 
}

resource "aws_instance" "example" {
    ami           = "ami-0f58b397bc5c1f2e8"  # AMI ID
    instance_type = "t2.micro"
    subnet_id     = "subnet-0d0dc8151746986db"  # Specify the subnet ID of your desired subnet
  vpc_security_group_ids = ["sg-0dac8253c44d2dc80"]
  key_name = "SAIPANDU01"
}

              
