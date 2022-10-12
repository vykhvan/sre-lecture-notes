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
