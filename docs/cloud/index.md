---
layout: default
title: Cloud
nav_order: 3
has_children: true
---

# Cloud

Connect and manage your cloud infrastructure from a unified control plane.

Axio enables organizations to securely integrate cloud providers, manage credentials, provision infrastructure, and standardize deployments across multiple cloud environments.

<div class="hero-image">

![Cloud Overview](/assets/images/cloud/cloud-overview.png)

</div>

{: .highlight }

> ## Multi-Cloud Platform
>
> Axio provides a consistent deployment experience across multiple cloud providers. Configure cloud accounts once and reuse them across projects, service catalogs, and infrastructure deployments.

---

## Supported Cloud Providers

<div class="feature-grid">

<div class="feature-card">

### Amazon Web Services

Provision AWS infrastructure securely using IAM-based authentication.

</div>

<div class="feature-card">

### Microsoft Azure

Connect Azure subscriptions using Service Principals.

</div>

<div class="feature-card">

### Google Cloud Platform

Manage GCP projects using Service Accounts.

</div>

</div>

---

## Cloud Onboarding Workflow

```mermaid
flowchart LR

A[Select Cloud Provider]
-->
B[Configure Credentials]

B
-->
C[Validate Connection]

C
-->
D[Register Provider]

D
-->
E[Provision Infrastructure]

E
-->
F[Monitor Resources]
```

---

## Before You Begin

Ensure that you have:

- Administrative access to your cloud account
- Required IAM permissions
- Valid credentials or service accounts
- A configured Axio Project

{: .note }

> Every connected cloud account can be reused across multiple projects and infrastructure templates.

---

## Documentation

Continue with the following guides:

- Configure Cloud
- Amazon Web Services
- Microsoft Azure
- Google Cloud Platform
