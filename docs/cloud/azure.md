---
layout: default
title: Microsoft Azure
parent: Cloud
nav_order: 3
---

# Microsoft Azure

Connect your Microsoft Azure subscription to Axio and securely provision Azure infrastructure using standardized Infrastructure-as-Code workflows.

<div class="hero-image">

![Azure Integration](/assets/images/cloud/azure/azure-hero.png)

</div>

{: .highlight }

> ## Azure Integration
>
> Axio integrates with Microsoft Azure using **Service Principals**. Once connected, Azure subscriptions can be reused across Projects, Service Catalogs, Automation Pipelines, and Infrastructure Templates.

---

## Azure Integration Workflow

```mermaid
flowchart LR

A[Create Service Principal]
-->
B[Assign Required Roles]

B
-->
C[Add Credentials in Axio]

C
-->
D[Validate Connection]

D
-->
E[Save Provider]

E
-->
F[Provision Azure Resources]
```

---

# Before You Begin

Ensure you have the following:

- Azure Subscription
- Azure Tenant ID
- Client ID
- Client Secret
- Subscription ID
- Contributor or Custom RBAC Role

{: .note }

> Create a dedicated Service Principal for Axio instead of using a personal Azure account.

---

### Step 1 — Create a Service Principal

Create a Service Principal using the Azure Portal or Azure CLI.

<div class="doc-image">

![Create Service Principal](/assets/images/cloud/azure/create-service-principal.png)

</div>

The Service Principal acts as the identity that Axio uses to provision and manage Azure resources.

---

### Step 2 — Assign Required Permissions

Grant the Service Principal the required role on your Azure Subscription.

Recommended roles include:

- Contributor
- Reader (Monitoring)
- Network Contributor (if required)

<div class="doc-image">

![Azure RBAC](/assets/images/cloud/azure/azure-rbac.png)

</div>

{: .tip }

> Follow the Principle of Least Privilege by assigning only the permissions required for infrastructure provisioning.

---

### Step 3 — Add Azure Provider

Navigate to:

**Cloud → Add Provider**

Choose **Microsoft Azure**.

<div class="doc-image">

![Select Azure Provider](/assets/images/cloud/azure/select-azure-provider.png)

</div>

---

### Step 4 — Configure Azure Credentials

Provide the following details:

- Tenant ID
- Subscription ID
- Client ID
- Client Secret

<div class="doc-image">

![Azure Credentials](/assets/images/cloud/azure/azure-credentials.png)

</div>

---

### Step 5 — Validate Connection

Axio validates:

- Azure Authentication
- Subscription Access
- Service Principal Permissions
- Azure API Connectivity

<div class="doc-image">

![Azure Validation](/assets/images/cloud/azure/azure-validation.png)

</div>

---

### Step 6 — Save the Provider

After validation completes successfully, save the provider.

The Azure subscription is now available for:

- Projects
- Service Catalog
- Infrastructure Templates
- Automation Workflows

<div class="doc-image">

![Azure Connected](/assets/images/cloud/azure/azure-connected.png)

</div>

---

## Best Practices

<div class="feature-grid">

<div class="feature-card">

<h3>Dedicated Service Principal</h3>

<p>Use a separate identity for infrastructure automation</p>

</div>

<div class="feature-card">

<h3>Role-Based Access</h3>

<p>Grant only the permissions required</p>

</div>

<div class="feature-card">

<h3>Rotate Secrets</h3>

<p>Update Client Secrets regularly</p>

</div>

<div class="feature-card">

<h3>Separate Environments</h3>

<p>Use different subscriptions for Development, Staging, and Production</p>

</div>

</div>

---

{: .warning }

> Never store Azure Client Secrets inside Git repositories or Infrastructure-as-Code templates.

---

## Troubleshooting

| Issue | Resolution |
|--------|------------|
| Authentication Failed | Verify Tenant ID, Client ID, and Client Secret |
| Authorization Error | Ensure the Service Principal has the required RBAC role |
| Subscription Not Found | Verify the Subscription ID and associated permissions |
| Validation Failed | Check network connectivity and Azure API availability |
