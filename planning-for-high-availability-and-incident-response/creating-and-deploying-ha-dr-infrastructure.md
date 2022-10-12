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
