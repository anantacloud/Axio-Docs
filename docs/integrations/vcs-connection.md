---
layout: default
title: VCS Connection
parent: Integrations
nav_order: 2
---

# VCS Connection

Version Control System (VCS) Connections allow Axio to access Infrastructure-as-Code repositories that define cloud resources, application infrastructure, and deployment configurations.

<div class="hero-image">

![VCS Connection](/assets/images/integrations/vcs/vcs-hero.png)

</div>

{: .highlight }

> ## Centralized Repository Management
>
> VCS Connections provide a single location to register and manage repositories used across multiple Axio projects.

---

## VCS Connection Workflow

```mermaid
flowchart LR

A[Select Repository]
-->
B[Authenticate]

B
-->
C[Validate Access]

C
-->
D[Register Repository]

D
-->
E[Assign to Project]

E
-->
F[Deploy Infrastructure]
```

---

# Before You Begin

Ensure that:

- A supported repository is available.
- Repository access has been granted.
- Authentication is configured.
- Projects have been created.

---

### Step 1 — Open VCS Connections

Navigate to:

**Settings → Integrations → VCS Connections**

<div class="doc-image">

![VCS Dashboard](/assets/images/integrations/vcs/vcs-dashboard.png)

</div>

---

### Step 2 — Create a Connection

Click **Add Connection**.

Provide:

- Connection Name
- Repository
- Branch
- Authentication Method

<div class="doc-image">

![Create Connection](/assets/images/integrations/vcs/create-vcs.png)

</div>

---

### Step 3 — Validate Repository Access

Axio verifies repository accessibility before registration.

<div class="doc-image">

![Repository Validation](/assets/images/integrations/vcs/vcs-validation.png)

</div>

Validation checks include:

- Authentication
- Repository permissions
- Branch availability

---

### Step 4 — Assign Projects

Select one or more projects that will use this repository.

<div class="doc-image">

![Assign Project](/assets/images/integrations/vcs/project-assignment.png)

</div>

---

### Step 5 — Repository Ready

The repository is now available for infrastructure deployments.

<div class="doc-image">

![Connection Complete](/assets/images/integrations/vcs/vcs-connected.png)

</div>

---

## Common Repository Usage

<div class="feature-grid">

<div class="feature-card">

<h3>Infrastructure Code</h3>

<p>Manage Terraform and IaC repositories</p>

</div>

<div class="feature-card">

<h3>Shared Modules</h3>

<p>Reuse infrastructure modules across projects</p>

</div>

<div class="feature-card">

<h3>Team Collaboration</h3>

<p>Maintain version-controlled infrastructure changes</p>

</div>

<div class="feature-card">

<h3>Standardization</h3>

<p>Use consistent repositories across environments</p>

</div>

</div>

---

## Best Practices

- Use dedicated repositories for infrastructure.
- Protect default branches.
- Follow consistent repository structures.
- Review repository permissions periodically.

{: .warning }

> Avoid making infrastructure changes outside the registered repository to maintain consistency and traceability.
