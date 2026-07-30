---
layout: default
title: Compliance
parent: Security & Governance
nav_order: 3
---

# Compliance

Compliance ensures that your infrastructure continuously adheres to organizational policies, security standards, and governance requirements throughout its lifecycle.

With Axio, compliance validation is integrated into every deployment, helping platform teams detect violations before infrastructure reaches production.

<div class="hero-image">

![Compliance Overview](/assets/images/security-governance/compliance/compliance-hero.png)

</div>

{: .highlight }

> ## Continuous Compliance
>
> Compliance is not a one-time activity. Axio continuously validates infrastructure against approved organizational policies during provisioning and operational lifecycle management.

---

## Compliance Workflow

```mermaid
flowchart LR

A[Infrastructure Request]
-->
B[Policy Validation]

B
-->
C[Compliance Evaluation]

C
-->
D{Compliant?}

D
-- Yes -->
E[Deploy Infrastructure]

D
-- No -->
F[Block Deployment]

F
-->
G[Remediation]

G
-->
B
```

---

# Before You Begin

Before enabling compliance validation, ensure:

- Governance policies are configured
- Cloud providers are connected
- Projects are onboarded
- Approval workflows are available (optional)

{: .note }

> Compliance validation automatically runs before infrastructure provisioning and can also be executed periodically to ensure ongoing compliance.

---

### Step 1 — Open Compliance Dashboard

Navigate to:

**Security & Governance → Compliance**

<div class="doc-image">

![Compliance Dashboard](/assets/images/security-governance/compliance/compliance-dashboard.png)

</div>

The dashboard provides:

- Compliance Status
- Active Policy Evaluations
- Failed Resources
- Recent Compliance Reports
- Historical Trends

---

### Step 2 — Select a Project

Choose the project or environment you want to evaluate.

<div class="doc-image">

![Select Project](/assets/images/security-governance/compliance/select-project.png)

</div>

Compliance checks can be performed for:

- Development
- Testing
- Staging
- Production

---

### Step 3 — Execute Compliance Validation

Run a compliance evaluation against the selected infrastructure.

Axio evaluates:

- Infrastructure Templates
- Cloud Configurations
- Security Policies
- Governance Rules
- Deployment Standards

<div class="doc-image">

![Compliance Validation](/assets/images/security-governance/compliance/compliance-validation.png)

</div>

{: .tip }

> Schedule recurring compliance scans to detect configuration changes introduced after deployment.

---

### Step 4 — Review Compliance Report

After validation completes, Axio generates a detailed compliance report.

<div class="doc-image">

![Compliance Report](/assets/images/security-governance/compliance/compliance-report.png)

</div>

The report includes:

- Passed Checks
- Failed Checks
- Severity Levels
- Resource Details
- Recommended Actions

---

### Step 5 — Review Violations

Every failed validation includes detailed remediation guidance.

<div class="doc-image">

![Compliance Violations](/assets/images/security-governance/compliance/compliance-violations.png)

</div>

Typical violations include:

- Missing resource tags
- Publicly exposed resources
- Unencrypted storage
- Unsupported regions
- Naming convention failures

---

### Step 6 — Remediate and Revalidate

After resolving identified issues, rerun compliance validation to confirm that all violations have been addressed.

<div class="doc-image">

![Compliance Success](/assets/images/security-governance/compliance/compliance-success.png)

</div>

---

## Compliance Categories

<div class="feature-grid">

<div class="feature-card">

<h3>Security</h3>

<p>Validate encryption, networking, and identity configurations</p>

</div>

<div class="feature-card">

<h3>Governance</h3>

<p>Ensure infrastructure follows organizational standards</p>

</div>

<div class="feature-card">

<h3>Operational</h3>

<p>Verify deployment consistency and lifecycle controls</p>

</div>

<div class="feature-card">

<h3>Cost</h3>

<p>Detect oversized resources and inefficient infrastructure</p>

</div>

</div>

---

## Compliance Reports

Compliance reports provide visibility into infrastructure health across projects.

Each report includes:

- Evaluation Summary
- Total Checks
- Passed Checks
- Failed Checks
- Severity Distribution
- Evaluation Timestamp
- Auditor Information

<div class="doc-image">

![Compliance Reports](/assets/images/security-governance/compliance/compliance-history.png)

</div>

---

{: .warning }

> Compliance validation should complement organizational security processes. Regular policy reviews and remediation workflows help maintain a secure and compliant infrastructure.
