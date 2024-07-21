<h1 align="center">
Terraform with AWS
</h1>

### Install Terraform
###### You can install Terraform from the official HashiCorp website: 
- https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli or
- https://developer.hashicorp.com/terraform/install?product_intent=terraform#windows

### Setup Environment Variable
###### After installing Terraform, set up your environment variable.

### Install AWS CLI
###### Install AWS CLI from the official AWS website: 
- https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html

### Confirm Installation
###### Verify your installation by running the following commands:
- terraform --version
- aws --version

### Setup AWS IAM User
###### After installing AWS CLI, set up an AWS IAM user with the required permissions. Copy your AWS access key ID and AWS secret access key.

### Configure AWS
###### Run the following command to configure AWS:
- aws configure :-  This command will ask for your AWS access key ID, AWS secret access key, and AWS region.

### Create Terraform File
###### Create a directory for your Terraform file using the following command:
- mkdir terraform_setup

###### Create a file called main.tf using the following command:
- touch main.tf

###### Open main.tf in your text editor and paste the following configuration:

terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 4.16"
    }
  }

  required_version = ">= 1.2.0"
}

provider "aws" {
  region  = "us-west-2"
}

resource "aws_instance" "app_server" {
  ami           = "ami-830c94e3"
  instance_type = "t2.micro"

  tags = {
    Name = "ExampleAppServerInstance"
  }
}

<h1 align="center">
Terraform Commands
</h1>

<p1 align="center">
Here are the Terraform commands to run your Terraform file:
</p1>

### Build
- terraform init: Initialize the Terraform directory.
- terraform fmt: Format your configuration.
- terraform validate: Validate your configuration.
### Create Infrastructure
- terraform plan: Show your infrastructure in detail.
- terraform apply: Apply your Terraform file to create your infrastructure.
### Inspect Infrastructure State
- terraform show: Show your infrastructure state.
- terraform state list: List the resources in your project's state.




