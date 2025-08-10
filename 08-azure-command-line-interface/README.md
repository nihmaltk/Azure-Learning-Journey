## What is Azure CLI?

Azure CLI (Command-Line Interface) is a tool to manage Azure resources directly from your terminal. You can create, configure, and control services like VMs, storage accounts, and more — all using simple commands.

You can use it from:
- Your local machine (Windows, macOS, Linux)
- Azure Cloud Shell (built into the Azure Portal — no installation needed)

## Why Use Azure CLI?

- **Speed and Efficiency**: Perform quick tasks without navigating the Azure Portal.
- **Automation**: Ideal for scripting and automating deployment/configuration.
- **Portability**: Scripts can be reused by teams or shared across environments.
- **Consistency**: Perform same task across environments with same command

## Installation

- Visit the official page: [Install Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli)

Verify installation:

```bash
az version
```

After installing, open terminal and run:

  ```bash
  az login
  ```
  This opens a browser to sign in to your Azure account.

## Create VM with Virtual Network using Azure CLI

### Step 1: Create a Resource Group

```bash
az group create --name MyResourceGroup --location eastus
```

**Explanation:**

* `az group create` → Command to create a new resource group
* `--name MyResourceGroup` → Name for your group 
* `--location eastus` → Azure region for the group

You can use **an existing resource group** instead of creating a new one. Just skip this step and use the existing group's name in the next steps.

# Step 2: Create a Virtual Machine

```bash 
az vm create \
  --resource-group azureCLIResourceGroup \
  --name azureCLIVM \
  --image <OS_IMAGE_NAME> \
  --vnet-name <VNET_NAME> \
  --subnet <SUBNET_NAME> \
  --admin-username <ADMIN_USERNAME> \
  --generate-ssh-keys
  --output json \             
  --verbose      
  ```

**Explantion**

`az vm create` - Create a new Virtual Machine in Azure.

`--resource-group azureCLIResourceGroup` - Specifies the resource group where the VM should be created.

`--name azureCLIVM` - Gives the name to your virtual machine.

`--image <OS_IMAGE_NAME>` - Defines the operating system image for the VM.

`--vnet-name <VNET_NAME>` - Specifies the Virtual Network (VNet) in which the VM will be placed.

`--subnet <SUBNET_NAME>` - Specifies the subnet within the VNet to attach the VM's network interface to.

`--admin-username <ADMIN_USERNAME>` - VM's username.

`--generate-ssh-keys` - If you don’t have SSH keys, Azure will generate and store them in your local PC . If keys already exist, it uses them.

`--ouput json` -  Outputs the result in JSON format (structured and machine-readable)

`--verbose` - Displays detailed progress messages (step-by-step execution)

## Summary

- Azure CLI is fast, scriptable, and ideal for automation.
- Perfect for devs, testers, and DevOps engineers.
- With `az` commands, you can control Azure without using the Portal.

**Azure CLI Documentation**
[https://learn.microsoft.com/en-us/cli/azure/](https://learn.microsoft.com/en-us/cli/azure/)

