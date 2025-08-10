## Azure Resources

**Azure Resources** are the basic parts you use in Azure.

They can be:
- Virtual Machines (VMs)
- Storage accounts
- Databases
- Web apps
- Virtual networks

Each resource is something you can **create and manage** in Azure.

**Example:** If you create a virtual machine, that’s one Azure resource.

## Resource Groups in Azure

A **Resource Group** is like a folder that holds related Azure resources. It helps keep things organized and easy to manage.

**Why use Resource Groups?**
- Manage multiple resources together
- Group resources by project or team
- Control access using permissions

**Example:** You can create a resource group for your web app project that contains the app, database, and storage.

## Azure Resource Manager (ARM)

**Azure Resource Manager (ARM)** is the tool Azure uses to create and manage everything.

## What ARM Does:
- Deploys your resources
- Organizes them
- Helps track and control everything

## Easy-to-Understand Features:

- **Templates**
   - ARM uses files (called templates) to describe what you want to build
   - You write it once and use it again and again
   - Great for repeatable setups

- **Handles Order Automatically**
   - If one resource depends on another, ARM sets them up in the correct order

- **Error Handling**
   - If something goes wrong, ARM can stop or undo the changes

- **Tags**
   - Add labels to resources to organize them better
   - Example: Tag your resource with "Project: HR-App"

## Summary
| Concept           | What It Is                                   | Example                          |
|-------------------|----------------------------------------------|----------------------------------|
| **Resource**      | A single thing like a VM or storage          | Virtual Machine                  |
| **Resource Group**| A folder for related resources               | App + DB + Storage for a project |
| **ARM**           | Tool that builds and manages everything      | Uses template to set up web app  |

These basics help you manage your Azure projects more easily and efficiently.



