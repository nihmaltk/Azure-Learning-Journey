## Authentication Services in Azure

- Authentication is the process of verifying who you are. It's about proving your identity.
- When you sign in to the Azure portal with a username and password, Azure is authenticating you.

## Main Azure Authentication Services:
- **Azure Active Directory (Azure AD)** – The main identity service for Azure, Office 365, and other Microsoft cloud services.
- **Microsoft Entra ID** – Azure AD is now part of Microsoft Entra, providing identity and access management.
- **Multi-Factor Authentication (MFA)** – Adds an extra layer of verification (e.g., SMS code, authenticator app).

## Identity Access Management (IAM)
IAM combines authentication with authorization, which is the process of determining what you are allowed to do after you've been authenticated

## Key IAM Components:

- **Users** – Real people in your organization.
- **Groups** – Collection of users with shared permissions.
- **Service Principals** – Identities for apps/services to access Azure resources.
- **Managed Identities** – Automatically managed service principals for Azure services.

## Role-Based Access Control

- Role-Based Access Control (RBAC) is the system Azure uses for IAM. It lets you manage access by assigning permissions to a security principal (like a user or a group), at a specific scope (like a subscription, resource group, or individual resource), using a role definition.

## Implementing RBAC (Role-Based Access Control)

RBAC assigns roles to users, groups, or service principals to control access.

Basic RBAC Steps:

1. **Identify the scope**:
- Management group → affects multiple subscriptions.
- Subscription → affects all resources in that subscription.
- Resource group → affects all resources in the group.
- Individual resource → affects only that resource.

2. **Assign a role**:
- Owner → Full control, including role assignments.
- Contributor → Create/manage resources but no access control.
- Reader → View resources only.
- Custom roles → User-defined permissions.

3. **Apply the assignment**.

## Best Practices for RBAC

- Principle of Least Privilege – Give only the permissions needed.
- Use Groups, Not Individuals – Easier to manage.
- Regularly Review Role Assignments – Remove unused access.
- Use Built-in Roles First – Create custom roles only if needed.
- Use Management Groups – For consistent permissions across multiple subscriptions.
- Avoid Owner Role unless absolutely needed.
- Use Privileged Identity Management (PIM) → Give just-in-time admin access instead of permanent rights.