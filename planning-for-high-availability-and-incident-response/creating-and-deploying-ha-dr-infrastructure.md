# Creating and deploying HA and DR infrastructure using Terraform

## Terraform Introduction

* Idempotent
    * Result is the same unless you change the code
* Config Files
    * HashiCorp Configuration Language (HCL)
* Terraform State
    * State files: Terraform creates to keep track of deployments
    * Compares the state file against infrastructure that is deployed
    * Definition files: .tf files that define the infrastructure
    * Stored in a shared location

Terraform is made up of blocks. There are 4 types of blocks we will be using:

### Provider Blocks

* Cloud Providers
* Store in root project file called _config.tf
* The state file and deployment region MUST be the same

```
terraform {
    backend "s3" {
        bucket = "terraform"
        key = "terraform/terraform.tfstate"
        region = "us-east-2"
    }
}

provider "aws" {
    region = "us-east-2"
}
```

### Resource Blocks

* Resource block: defines a resource that Terraform will deploy
* Generally resource names should be lowercase and use _ instead of -

```
resource "aws_instance" "aws_linux" {
    ami = ami-074cce78125f09d61
    count = 1
    instance_type = t2.micro

    tags = {
        Name = "EC2 Instance"
    }
}
```

### Variable Block

* Define variables for re-use
* Variables can be stored in separate files

```
variable "instance_count" {
    description = "The desired number of EC2 instances."
    default = 2
}

resource "aws_instance" "aws_linux" {
    ami = ami-074cce78125f09d61
    count = var.instance_count
    instance_type = t2.micro

    tags = {
        Name = "EC2 Instance"
    }
}
```

### Module Blocks

* Groups of reusable code

## Deploying Assets via Terraform

### Module Folder Structure

* File names don't matter to Terraform

```
modules
|__ec2
   |__ec2.tf   -> defines the resource
   |__ _var.tf -> contains variables
   |__ _out.tf -> contains outputs
```

### Module Example - Resource Definition

**ec2.tf**

```
resource "aws_instance" "aws_linux" {
    ami           = var.aws_ami
    count         = var.instance_count
    instance_type = "t3.micro"
    subnet_id     = var.public_subnet_ids[0]

    tags = {
        Name = "Web"
    }
}
```

### Module Example - Variables File

**_var.tf**

```
variable "instance_count" {}
variable "aws_ami" {}
variable "public_subnet_ids" {}
```

* Setting the variables is required
* Do NOT need to use all the variables defined in a module
* A variable MUST be defined if you want to use it in a module

### Module Example - Output File

**_out.tf**

```
output "aws_instance" {
    value = aws_instance.aws_linux
}
```

### Module Usage

* Call a module in a .tf file
* A module can be called many times

```
module "project_ec2" {
    source            = "./modules/ec2"
    instance_count    = 2
    aws_ami           = "ami-0b9064170e32bde34"
    public_subnet_ids = module.vpc.public_subnet_ids
}
```

### Example Project Structure

```
Project
|__modules
   |__ec2
      |__ec2.tf
      |__ _var.tf
      |__ _out.tf
   |__vpc
|__main.tf        -> Defines shared deployment information
|__ _config.tf    -> Contains configurations such as Terraform state
|__ec2.tf
```
