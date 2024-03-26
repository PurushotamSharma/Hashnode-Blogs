---
title: "Day 01 of 7 Days of Terraform: Getting Started with Azure"
seoTitle: "Terraform"
datePublished: Tue Mar 26 2024 11:28:27 GMT+0000 (Coordinated Universal Time)
cuid: clu8amuqh000208jo5zekc1na
slug: day-01-of-7-days-of-terraform-getting-started-with-azure
tags: cloud, blogging, azure, automation, devops, terraform, trainwithshubham

---

## 🚀 **Introduction:**

Welcome to Day 1 of the Terraform 7 Days Challenge! Today, we'll embark on our journey into the world of infrastructure as code (IaC) by setting up our environment and creating a basic Terraform project to deploy resources on Azure.

## 🚀 **Prerequisites:**

Before we begin, ensure you have the following prerequisites:

1. **Azure Account:** Sign up for a free Azure account if you don't have one already.
    
2. **Azure CLI:** Install Azure CLI to interact with Azure services from your command line.
    
3. **Terraform:** Install Terraform to define and provision infrastructure resources.
    

**Step 1: Installing Azure CLI:** Follow these steps to install Azure CLI:

1. Visit the [Azure CLI installation page](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli) for instructions tailored to your operating system.
    
2. Once installed, open your terminal and run `az login` to log in to your Azure account.
    

**Step 2: Installing Terraform:** Here's how to install Terraform:

1. Visit the [Terraform download page](https://www.terraform.io/downloads.html) and download the appropriate version for your OS.
    
2. Extract the downloaded archive and move the Terraform binary to a directory included in your system's PATH.
    
3. Verify the installation by running `terraform --version` it in your terminal.
    

**Step 3: Configuring Azure Credentials:** To authenticate Terraform with your Azure account, follow these steps:

1. Run `az login` in your terminal and follow the instructions to authenticate with your Azure account.
    
2. Once logged in, run `az account show` to view information about the currently selected Azure subscription.
    

**Step 4: Creating Terraform Configuration:** Now, let's create a Terraform configuration file to define our Azure VM.

1. Create a new directory for your Terraform project and navigate into it.
    
2. Create a file named [`main.tf`](http://main.tf) and open it in a text editor.
    
3. Copy and paste the following Terraform configuration into [`main.tf`](http://main.tf):
    

```plaintext
terraform {
  required_providers {
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "=3.0.0"
    }
  }
}

provider "azurerm" {
  features {}
}

resource "azurerm_resource_group" "example" {
  name     = "example-resources"
  location = "East US"
}

resource "azurerm_virtual_network" "example" {
  name                = "example-network"
  address_space       = ["10.0.0.0/16"]
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
}

resource "azurerm_subnet" "example" {
  name                 = "internal"
  resource_group_name  = azurerm_resource_group.example.name
  virtual_network_name = azurerm_virtual_network.example.name
  address_prefixes     = ["10.0.2.0/24"]
}

resource "azurerm_linux_virtual_machine" "example" {
  name                = "example-machine"
  resource_group_name = azurerm_resource_group.example.name
  location            = azurerm_resource_group.example.location
  size                = "Standard_DS1_v2"
  admin_username      = "adminuser"
  network_interface_ids = [
    azurerm_network_interface.example.id,
  ]

  admin_ssh_key {
    username   = "adminuser"
    public_key = file("~/.ssh/id_rsa.pub")
  }

  os_disk {
    caching              = "ReadWrite"
    storage_account_type = "Standard_LRS"
  }

  source_image_reference {
    publisher = "Canonical"
    offer     = "UbuntuServer"
    sku       = "18.04-LTS"
    version   = "latest"
  }
}
```

**Let's understand this code step by step:**

```plaintext
terraform {
  required_providers {
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "=3.0.0"
    }
  }
}
```

This section specifies the required providers for the Terraform configuration. Here, we're requiring the `azurerm` provider from HashiCorp, which allows Terraform to interact with Azure resources. We specify the source (location of the provider) as `"hashicorp/azurerm"` and the required version as `"=3.0.0"`.

```plaintext
provider "azurerm" {
  features {}
}
```

In this section, we define the provider configuration for Azure. We specify `"azurerm"` the provider type, which corresponds to the Azure provider. The `features {}` block is empty here, but it allows you to enable optional features provided by the Azure provider if needed.

```plaintext
resource "azurerm_resource_group" "example" {
  name     = "example-resources"
  location = "East US"
}
```

This section defines an Azure resource group named `"example-resources"` in the East US region. Resource groups are logical containers that hold related Azure resources for easier management, billing, and access control.

```plaintext
resource "azurerm_virtual_network" "example" {
  name                = "example-network"
  address_space       = ["10.0.0.0/16"]
  location            = azurerm_resource_group.example.location
  resource_group_name = azurerm_resource_group.example.name
}
```

Here, we define an Azure virtual network named `"example-network"`. Virtual networks in Azure allow you to logically isolate and segment your resources. We specify the address space (`"10.0.0.0/16"`) for the virtual network and associate it with the previously created resource group.

```plaintext
resource "azurerm_subnet" "example" {
  name                 = "internal"
  resource_group_name  = azurerm_resource_group.example.name
  virtual_network_name = azurerm_virtual_network.example.name
  address_prefixes     = ["10.0.2.0/24"]
}
```

This section creates a subnet named `"internal"` within the virtual network `"example-network"`. Subnets allow you to divide your virtual network into smaller, manageable sections. We assign the subnet the address prefix `"10.0.2.0/24"`.

```plaintext
resource "azurerm_linux_virtual_machine" "example" {
  name                = "example-machine"
  resource_group_name = azurerm_resource_group.example.name
  location            = azurerm_resource_group.example.location
  size                = "Standard_DS1_v2"
  admin_username      = "adminuser"
  network_interface_ids = [
    azurerm_network_interface.example.id,
  ]

  admin_ssh_key {
    username   = "adminuser"
    public_key = file("~/.ssh/id_rsa.pub")
  }

  os_disk {
    caching              = "ReadWrite"
    storage_account_type = "Standard_LRS"
  }

  source_image_reference {
    publisher = "Canonical"
    offer     = "UbuntuServer"
    sku       = "18.04-LTS"
    version   = "latest"
  }
}
```

Finally, this section defines an Azure Linux Virtual Machine named `"example-machine"`. We specify the resource group, location, VM size, and administrative username. The `network_interface_ids` attribute links the VM to the previously created network interface. We also specify an SSH public key for authentication and define the VM's OS disk and source image.

Overall, this Terraform configuration sets up a basic infrastructure environment in Azure, including a resource group, virtual network, subnet, and a Linux virtual machine. Each resource is defined using Terraform's declarative syntax, making it easy to understand and manage infrastructure as code.

**Step 5: Provisioning Azure VM with Terraform:** Now that we've defined our Terraform configuration, let's provision the Azure VM:

1. In your terminal, navigate to the directory containing your [`main.tf`](http://main.tf) file.
    
2. Run `terraform init` to initialize your Terraform project and download the Azure provider plugin.
    
3. Run `terraform plan` to preview the execution plan and verify what Terraform will create.
    
4. Finally, run `terraform apply` to apply the configuration and create the Azure VM.
    

## 🚀 **Conclusion:**

Congratulations! You've successfully created an Azure Virtual Machine using Terraform. In this article, we covered the installation of Azure CLI and Terraform, configuring Azure credentials, creating Terraform configuration, and provisioning Azure resources. Stay tuned for Day 02, where we'll explore more advanced Terraform features.

🎉 Happy Learning! 🌍✨