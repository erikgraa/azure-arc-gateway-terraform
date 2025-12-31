# Azure Arc gateway with Terraform

This repository provides an example of deploying an Azure Arc gateway with Terraform!

![Release](/assets/portal.png)

## 🚀 Features

- Azure Arc gateway deployed with a Terraform module
- "Do not delete" lock on deployed resource

## 📄 Usage

### 1️⃣  Deploy with Terrraform locally

1. Clone this repository.
2. Copy or rename the `terraform.auto.tfvars.example` file to `terraform.auto.tfvars`. 
3. Fill out the Azure Arc gateway name and Azure resource group name for use locally.
4. Log in to Azure and run Terraform. The subscription ID can be sourced from the `ARM_SUBSCRIPTION_ID` environment variable.

```powershell
az login
$env:ARM_SUBSCRIPTION_ID = (az account list | ConvertFrom-Json).id
terraform init
terraform plan
terraform apply
```

### 2️⃣ Deploy with HCP Terraform

Read the related blog post at https://blog.graa.dev/AzureArc-GatewayTerraform for more information about this scenario.

### 📂 Outputs

Use the following outputs when onboarding Azure Connected Machine agents:

```terraform
terraform output

azure_arc_gateway_resource_id = "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/resourceGroup/providers/Microsoft.HybridCompute/gateways/arc-gateway"
azure_arc_gateway_url = "gatewayId.gw.arc.azure.com"
```

## 🌳 Repository

The repository structure is as follows.

```plaintext
│   .gitignore
│   LICENSE
│   main.tf
│   provider.tf
│   README.md
│   terraform.auto.tfvars.example
│   variables.tf
│
├───assets
│       portal.png
│
└───modules
    └───azure-arc-gateway
            main.tf
            outputs.tf
            README
            variables.tf
            versions.tf
```

## ✍ Blog post

See the related blog post at https://blog.graa.dev/AzureArc-GatewayTerraform.

## 👏 Contributions

Any contributions are welcome and appreciated!
