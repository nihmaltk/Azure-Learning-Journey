## Azure DevOps Overview

Azure DevOps is a set of development tools and services provided by Microsoft to support the entire software development lifecycle.
It brings planning, development, testing, delivery, and monitoring into one integrated platform.

## Azure DevOps Cycle

Azure DevOps follows a continuous integration and continuous delivery (CI/CD) approach:

- **Plan** – Define work items, track progress using Boards.
- **Develop** – Write code, store it in Repos (Git).
- **Build** – Use Pipelines to compile, test, and package the application.
- **Test** – Run automated/manual tests to ensure quality.
- **Release** – Deploy to environments (staging, production) using Release Pipelines.
- **Monitor** – Use dashboards and integrated monitoring tools.

This cycle repeats continuously to improve software rapidly.

## How to Use Azure DevOps

- Create an Azure DevOps organization.
- Create a project (contains code, pipelines, boards, etc.).
- Use Repos for code version control.
- Define work items in Boards.
- Create Pipelines to automate build/test/deploy.
- Use Artifacts for storing packages.

## Benefits of Azure DevOps

- All-in-one toolset for DevOps practices.
- Cloud-based (no heavy setup).
- Supports multiple languages & platforms (Java, .NET, Python, Node.js, etc.).
- Integration-friendly (GitHub, Jenkins, Docker, Kubernetes, etc)
- Scalable for small teams to enterprise-level projects.

## How Azure DevOps Works

- Azure DevOps is service-based — you pick what you need:
- Code in Repos → tracked in Boards → built in Pipelines → deployed via Releases → tested in Test Plans.

All connected via Azure DevOps Portal or Azure CLI.

## Main Sections of Azure DevOps

Service	   |  Purpose                                                       |
---------- | -------------------------------------------------------------  |
Boards	   | Agile planning, work tracking, Kanban boards, backlogs.        |
Repos	   | Git-based version control for source code.                     |
Pipelines  | CI/CD automation for builds, tests, and deployments.           |
Test Plans | Manual and automated testing management.                       |
Artifacts  | Package management for dependencies (NuGet, npm, Maven, etc.). |