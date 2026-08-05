---
layout: default
title: Overview
parent: Organization
nav_order: 1
description: Learn how Organization resources are structured in Axio.
---

# Organization

<div class="announcement-box">

<div class="announcement-icon">
   <img src="{{ '/assets/images/icons/building-2.svg' | relative_url }}"
         alt="Organization"
         width="34"
         height="34">
</div>

<div>

## Manage all your organizational resources in one place.

Create and manage **Projects**, **Workspaces**, and **Environments** using either the **Axio UI** or **Platform as Code (Git-based)**.

</div>

</div>

---

## Organization Resources

An organization consists of the following core resources.

<div class="resource-grid">

<div class="resource-card project">

# Projects

Logical grouping of Workspaces and Environments.

### Features

- Group related workloads
- Manage project-level access
- Configure project settings

<div class="card-footer">

[Explore Projects →](projects/)

</div>

</div>

<div class="resource-card workspace">

# Workspaces

Isolated areas for applications, services, and infrastructure.

### Features

- Contains environments
- Team isolation
- Independent configuration

<div class="card-footer">

[Explore Workspaces →](workspaces/)

</div>

</div>

<div class="resource-card environment">

# Environments

Deployment targets like Development, Staging, and Production.

### Features

- Multiple environment types
- Deployment configuration
- Environment-specific settings

<div class="card-footer">

[Explore Environments →](environments/)

</div>

</div>

</div>

---

# Ways to Create Resources

Choose the workflow that best matches your team's development process.

<div class="method-grid">

<div class="method-card ui">

# From the UI

Create resources directly from the Axio web interface.

### Best for

- Quick setup
- Manual administration
- Learning the platform

<div class="card-footer">

[Create Resources from UI →](projects/create-from-ui/)

</div>

</div>

<div class="method-card git">

# Platform as Code (Git-Based)

Define Projects, Workspaces, and Environments using YAML or JSON files stored in Git.

### Best for

- GitOps
- Version Control
- Automation
- Audit & Compliance

<div class="card-footer">

[Platform as Code Guide →](../platform-as-code/repository-setup/)

</div>

</div>

</div>

---

# Resource Hierarchy

```text
Organization
│
├── Project
│      │
│      ├── Workspace
│      │        │
│      │        ├── Development
│      │        ├── Staging
│      │        └── Production
│      │
│      └── Workspace
│
└── Project
```

---

# Recommended Workflow

<div class="tip-box">

For Production workloads, it is recommended to manage resources using **Platform as Code**.

Benefits include:

- Version Control
- GitOps
- Pull Request Reviews
- Audit Trail
- Easy Rollback

</div>

---

## Next Steps

Continue exploring Organization resources.

| Resource | Description |
|-----------|-------------|
| **Projects** | Create and manage projects. |
| **Workspaces** | Organize services and teams. |
| **Environments** | Configure deployment targets. |
| **Platform as Code** | Manage resources using Git. |
