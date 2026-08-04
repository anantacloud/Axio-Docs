---
layout: default
title: Environment
parent: Organization
nav_order: 3
---

# Service Catalog

The Service Catalog enables engineering teams to provision standardized infrastructure and platform services through reusable templates.

Rather than creating cloud resources manually, users simply select an approved service, provide required inputs, and allow Axio to automate the provisioning workflow.

---

## Why Service Catalog?

Without standardization, teams often provision infrastructure differently.

This results in:

- Inconsistent environments
- Manual provisioning
- Configuration errors
- Governance challenges
- Increased operational overhead

Axio addresses these challenges with a centralized Service Catalog.

---

## Typical Services

- Kubernetes Cluster
- Virtual Machine
- Database
- Object Storage
- Network
- IAM Configuration
- Monitoring Stack

---

## Service Provisioning Workflow

```mermaid
flowchart LR

A[User]

A --> B[Browse Catalog]

B --> C[Select Service]

C --> D[Provide Inputs]

D --> E[Approval]

E --> F[Provision Infrastructure]

F --> G[Ready to Use]
```

---

## Benefits

- Faster provisioning
- Improved consistency
- Reduced manual effort
- Enhanced governance
- Better developer experience

---

## Example Catalog

| Service | Category |
|----------|----------|
| Amazon EKS | Kubernetes |
| Azure AKS | Kubernetes |
| Google GKE | Kubernetes |
| PostgreSQL | Database |
| Virtual Machine | Compute |
| VPC Network | Networking |

---

## Best Practices

- Publish reusable templates
- Keep service documentation updated
- Review catalog versions regularly
- Apply governance policies to every service

---

## Related Topics

- Module Registry
- Provider Registry
- Policy & Compliance
- Automation

---

> The Service Catalog empowers engineering teams to provision secure, compliant, and reusable infrastructure with confidence.
