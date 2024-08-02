# Terrafpem-Notes
### AWS Terraform provider?
- Install Terrafrom windows
    - Set the environment variable
    - check cmd - terraform version
    - Install git
- Created EC2 instance without key

### Conncet terraform to EC2
- create 2folder folders
  - mkdir terraform
  - mkdir scriptcode
    - cd scriptcode - write here your code
      - vi script.tf
        - cmd use - terraform init  

- Creade IAM user give admin privilage
   - Download IAM access key secret key

### use this code to create instance 
```sh
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}

# Configure the AWS Provider
provider "aws" {
  region = "us-east-1"
}

resource "aws_instance" "S1" {
  ami           = data.aws_ami.ubuntu.id
  instance_type = "t3.micro"

  tags = {
    Name = "Server1"
  }


}
```
- CMD - Terraform plan
- CMD - Terraform apply
[AWS Terraform provider](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)
