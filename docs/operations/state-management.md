---
layout: default
title: State Management
parent: Operations
nav_order: 1
---

# State Management

Manage your infrastructure state securely from a centralized control plane. Axio stores, tracks, and protects infrastructure state throughout the complete deployment lifecycle, enabling reliable Infrastructure-as-Code operations across teams.

<div class="hero-image">

![State Management Overview](/assets/images/state-management/state-management-hero.png)

</div>

{: .highlight }
> ## Platform Overview
>
> State Management acts as the **single source of truth** for your infrastructure.
> Every deployment updates the infrastructure state, allowing Axio to safely coordinate provisioning, detect configuration drift, and maintain deployment history.

---

## State Management Workflow

```mermaid
flowchart LR

A[Connect Repository]
-->
B[Read Infrastructure]

B
-->
C[Lock State]

C
-->
D[Provision Resources]

D
-->
E[Update State]

E
-->
F[Detect Drift]

F
-->
G[Observability]
```

---

# Before You Begin

Ensure you have completed the following:

- Git repository connected
- Cloud provider configured
- Terraform modules available
- Required credentials added
- Appropriate project permissions

{: .note }

> Infrastructure state should always be stored remotely.
> Shared state enables collaboration, versioning, and safe deployments.

---

### Step 1 — Connect Your Repository

Connect the Git repository that contains your Infrastructure-as-Code project.

<div class="doc-image">

![Repository Connection](/assets/images/state-management/repository.png)

</div>

During repository discovery Axio will:

- Detect Terraform projects
- Read module structure
- Validate repository configuration
- Prepare infrastructure metadata

---

### Step 2 — Configure Remote State

Choose where your infrastructure state will be stored.

<div class="doc-image">

![Remote Backend](/assets/images/state-management/backend.png)

</div>

Supported remote backends include:

- AWS S3
- Azure Storage
- Google Cloud Storage
- Terraform Cloud
- Axio Managed Backend

{: .important }

> Never store production Terraform state locally.
> Remote state enables secure collaboration and automatic locking.

---

### Step 3 — Lock Infrastructure State

Before provisioning begins, Axio automatically acquires a state lock.

<div class="doc-image">

![State Lock](/assets/images/state-management/lock.png)

</div>

State locking prevents:

- Concurrent deployments
- State corruption
- Race conditions
- Manual conflicts

---

### Step 4 — Provision Infrastructure

After validation completes, infrastructure changes are executed.

<div class="doc-image">

![Deployment Progress](/assets/images/state-management/provision.png)

</div>

Axio continuously tracks:

- Current execution
- Provisioning logs
- Resource creation
- Failed operations

---

### Step 5 — Update Infrastructure State

When deployment succeeds, Axio updates the latest infrastructure state.

<div class="doc-image">

![State Versions](/assets/images/state-management/state-version.png)

</div>

Each deployment automatically records:

- State version
- Deployment ID
- Timestamp
- Triggered by
- Infrastructure changes

{: .tip }

> Every state update is versioned, making rollback and auditing significantly easier.

---

### Step 6 — Detect Configuration Drift

Axio continuously compares the desired infrastructure with the actual cloud environment.

<div class="doc-image">

![Drift Detection](/assets/images/state-management/drift.png)

</div>

Drift detection helps identify:

- Manual cloud changes
- Missing resources
- Unexpected modifications
- Infrastructure inconsistencies
