## What is Azure Resource Manager (ARM)?
- ARM is the deployment and management layer for Azure.
- It lets you create, update, and delete Azure resources in a consistent way.

## Key points:

- Everything in Azure goes through ARM.
- ARM manages resources using a declarative approach (you describe what you want, not how to do it).
- Works with templates to automate deployments.

## What are ARM Templates?
- JSON files that describe the resources you want to create in Azure.
- Automate deployments — no need to click through the portal.

## Benefits:
- Consistency — same template, same environment.
- Repeatability — deploy multiple environments easily (Dev, Test, Prod).
- Version control — store in GitHub/Azure DevOps.
- Automated — works with CI/CD.

## Comparisons

Tool / Method       | How it Works                                        |	Pros	                                                   |Cons                            |
--------------------| ----------------------------------------------------| ---------------------------------------------------------|--------------------------------|
ARM Templates (JSON)|	Native Azure JSON-based templates interpreted by ARM|	Official Microsoft tool, fully supported, integrates well| JSON syntax can be verbose     |
Bicep	              | A higher-level language that compiles to ARM JSON	  | Easier to write/read, modular, less verbose	             | Needs learning Bicep syntax    |
Azure CLI	          | Command-line commands to create resources	          | Quick for one-off tasks	                             |Not as reusable/automated as templates|
Terraform	          | Third-party IaC tool using HCL syntax	              | Multi-cloud support, large community	  | Needs plugin/provider management, not native Azure|

## Why ARM Templates if there are other tools?
- If you only work in Azure and want Microsoft-supported, portal-integrated templates - ARM Templates.
- If you want simpler syntax but still native - Bicep.
- If you work multi-cloud - Terraform.

## Basic ARM Template Structure
An ARM template is a JSON file with specific sections:

``` bash
{
  "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#",
  "contentVersion": "1.0.0.0",
  "parameters": {
    "vmName": {
      "type": "string",
      "defaultValue": "myVM",
      "metadata": {
        "description": "Name of the virtual machine"
      }
    }
  },
  "variables": {
    "location": "[resourceGroup().location]"
  },
  "functions": [],
  "resources": [
    {
      "type": "Microsoft.Compute/virtualMachines",
      "apiVersion": "2021-07-01",
      "name": "[parameters('vmName')]",
      "location": "[variables('location')]",
      "properties": {}
    }
  ],
  "outputs": {
    "vmResourceId": {
      "type": "string",
      "value": "[resourceId('Microsoft.Compute/virtualMachines', parameters('vmName'))]"
    }
  }
}
```
**$schema** 
- URL pointing to the JSON schema that defines the allowed structure for the template.

**contentVersion**
- Version of your template for tracking. No functional effect on deployment.

**parameters**
- Accepts values at deployment time so your template is reusable.

**variables**
- Stores values calculated inside the template to avoid repetition.

**functions**
- Custom functions you can define for complex logic. Often left empty in simple templates.

**resources**
- The actual Azure resources to be deployed (VMs, VNETs, Storage Accounts, etc.).

**outputs**
- Values returned after deployment (like resource IDs, IP addresses).

## Deploying ARM Template via Azure CLI

```bash
az deployment group create \
  --name MyDeployment \
  --resource-group MyResourceGroup \
  --template-file azuredeploy.json \
  --parameters vmName=myVM
```

* `az deployment group create` - Deploys resources at the resource group level.
* `--name` - Name of the deployment.
* `--resource-group` - Target resource group.
* `--template-file` - Path to ARM template file.* 
* `--parameters` - Values for template parameters.

## Summary

- ARM is Azure’s native Infrastructure as Code tool.
- ARM templates use JSON for declarative deployments.
- Compared to CLI (imperative) and Bicep/Terraform, ARM is Azure-specific but powerful.
- Structure includes schema, parameters, variables, functions, resources, outputs.
- CLI can deploy templates directly to Azure.