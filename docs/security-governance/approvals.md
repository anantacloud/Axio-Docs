---
layout: default
title: Approvals
parent: Security & Governance
nav_order: 2
---

# Approvals

Approval Workflows help organizations enforce governance before infrastructure changes are applied. By introducing approval gates, Axio ensures that sensitive deployments are reviewed by the appropriate stakeholders before execution.

<div class="hero-image">

![Approval Workflow](/assets/images/security-governance/approvals/approvals-hero.png)

</div>

{: .highlight }

> ## Why Approval Workflows?
>
> Production infrastructure often requires additional oversight. Approval workflows ensure deployments follow organizational policies while reducing operational risks.

---

## Approval Workflow

```mermaid
flowchart LR

A[Developer Creates Deployment]
-->
B[Policy Validation]

B
-->
C[Approval Request]

C
-->
D{Approved?}

D
-- Yes -->
E[Deploy Infrastructure]

D
-- No -->
F[Reject Deployment]

F
-->
G[Review & Modify]
```

---

# Before You Begin

Before creating approval workflows:

- Projects should be configured
- Roles and permissions should be assigned
- Cloud providers should be connected
- Policies should already exist

{: .note }

> Approval workflows are typically used for Production environments or high-impact infrastructure changes.

---

### Step 1 — Navigate to Approval Management

Open:

**Security & Governance → Approvals**

<div class="doc-image">

![Approval Dashboard](/assets/images/security-governance/approvals/approval-dashboard.png)

</div>

Here you can:

- View Approval Rules
- Create Approval Policies
- Review Pending Requests
- View Approval History

---

### Step 2 — Create an Approval Policy

Click **Create Approval Workflow**.

Configure:

- Workflow Name
- Description
- Target Environment
- Required Approvers

<div class="doc-image">

![Create Approval](/assets/images/security-governance/approvals/create-approval.png)

</div>

---

### Step 3 — Configure Approval Rules

Choose when approvals are required.

Examples include:

- Production deployments
- Infrastructure deletion
- IAM changes
- Network modifications
- Cost threshold exceeded

<div class="doc-image">

![Approval Rules](/assets/images/security-governance/approvals/approval-rules.png)

</div>

{: .tip }

> Keep approval rules simple and focused. Separate production approval policies from development workflows.

---

### Step 4 — Assign Approvers

Select one or more approvers.

Supported approver types:

- Platform Administrators
- Team Leads
- Security Teams
- Project Owners

<div class="doc-image">

![Assign Approvers](/assets/images/security-governance/approvals/assign-approvers.png)

</div>

---

### Step 5 — Review Approval Requests

Whenever a deployment matches an approval rule, Axio creates a pending approval request.

<div class="doc-image">

![Approval Request](/assets/images/security-governance/approvals/pending-request.png)

</div>

Approvers can:

- Review Infrastructure Changes
- Approve
- Reject
- Add Comments

---

### Step 6 — Deployment Execution

Once approved, the deployment continues automatically.

<div class="doc-image">

![Deployment Approved](/assets/images/security-governance/approvals/deployment-approved.png)

</div>

---

## Approval Levels

<div class="feature-grid">

<div class="feature-card">

<h3>Single Approval</h3>

<p>One authorized user approves the deployment</p>

</div>

<div class="feature-card">

<h3>Multi-Level Approval</h3>

<p>Multiple approvers review before deployment</p>

</div>

<div class="feature-card">

<h3>Environment-Based</h3>

<p>Require approvals only for selected environments</p>

</div>

<div class="feature-card">

<h3>Emergency Override</h3>

<p>Allow temporary administrative approval when required</p>

</div>

</div>

---

## Best Practices

- Use approvals only where necessary
- Separate Development and Production workflows
- Keep approval history for auditing
- Notify stakeholders automatically
- Review approval rules periodically

{: .warning }

> Avoid requiring approvals for every deployment. Excessive approval gates can slow delivery and reduce developer productivity.
