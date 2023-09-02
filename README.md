

This Terraform Git repo contains a module that create azure container registry in Azure.

## Prerequisites

Before you can use this Terraform module, you will need to have the following installed:

- [Terraform](https://www.terraform.io/downloads.html) - v1.0.5 or later
- [Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli) - v2.26.0 or later

## Usage

To use this Terraform module, follow these steps:

From your local, generate and Set up SSH key pair for Github.

Clone this Git repo to your local machine.

```bash
git@github.com:duck-creek/tf.acr.git
```

Change into the directory containing the module.

```bash
cd tf.acr
cd module

```

Create a new file named `azure.tfvars` in the same directory as your `.tf` files.

```bash
touch azure.tfvars
```

Open the file in your preferred text editor.

```bash
nano azure.tfvars
```

Add your desired inputs to the file in the following format:

```ruby
acr_name                                 = ""
azure_resource_group                     = ""
location                                 = ""
acr_sku                                  = ""

```
Review the changes that Terraform will make to your Azure resources.


Initialize Terraform in the directory.

```bash
terraform init
```
```bash
terraform plan -var-file="azure.tfvars"
```
```bash
terraform apply -var-file="azure.tfvars"

```
## for publishing this terraform module to the azure artifact you need to follow these steps
1. Go to the Azure DevOps
2. create the new pipeline where you need to choose the existing pipeline and specify the path of your yaml file
3. Run the pipeline with the desired version of your module(you need to change your version in the metadata.yaml)


