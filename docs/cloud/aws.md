---
layout: default
title: Amazon Web Services
parent: Cloud
nav_order: 2
---

# Amazon Web Services (AWS)

Connect your AWS account to Axio to provision, manage, and monitor cloud infrastructure using Infrastructure-as-Code.

<div class="hero-image">

![AWS Integration](/assets/images/cloud/aws/aws-hero.png)

</div>

{: .highlight }

> ## AWS Integration
>
> Axio securely connects to your AWS account using IAM credentials, allowing projects and service catalogs to provision AWS resources while maintaining centralized governance and security.

---

## Architecture

```mermaid
flowchart LR

A[Axio]
-->
B[AWS Provider]

B
-->
C[IAM Authentication]

C
-->
D[AWS Account]

D
-->
E[Provision Resources]
```

---

# Prerequisites

Before connecting AWS, ensure that you have:

- An active AWS Account
- IAM User or IAM Role
- Access Key ID
- Secret Access Key
- Required IAM Permissions

{: .note }

> Use a dedicated IAM identity for Axio instead of personal AWS credentials.

---

# Step 1 — Create AWS Credentials

Create an IAM User or IAM Role with permissions required for infrastructure provisioning.

<div class="doc-image">

![IAM User](/assets/images/cloud/aws/aws-iam-user.png)

</div>

Typical permissions include:

- EC2
- VPC
- IAM
- S3
- EKS
- CloudWatch

---

# Step 2 — Navigate to Cloud Providers

Open **Cloud → Add Provider** inside Axio.

<div class="doc-image">

![Cloud Providers](/assets/images/cloud/aws/aws-provider-page.png)

</div>

---

# Step 3 — Select Amazon Web Services

Choose **Amazon Web Services** from the provider list.

<div class="doc-image">

![Select AWS](/assets/images/cloud/aws/aws-select-provider.png)

</div>

---

# Step 4 — Enter Credentials

Provide:

- Access Key ID
- Secret Access Key
- Default Region

<div class="doc-image">

![AWS Credentials](/assets/images/cloud/aws/aws-credentials.png)

</div>

{: .tip }

> Restrict IAM permissions using the principle of least privilege.

---

# Step 5 — Validate Connection

Axio verifies:

- Authentication
- Account Access
- IAM Permissions
- Region Availability

<div class="doc-image">

![Validation](/assets/images/cloud/aws/aws-validation.png)

</div>

---

# Step 6 — Save Provider

Once validation succeeds, save the provider.

The AWS account becomes available for:

- Projects
- Service Catalog
- Infrastructure Templates
- Automation

<div class="doc-image">

![AWS Connected](/assets/images/cloud/aws/aws-connected.png)

</div>

---

## Best Practices

- Use IAM Roles whenever possible
- Rotate access keys regularly
- Restrict permissions
- Enable CloudTrail auditing
- Separate Production and Development accounts

{: .warning }

> Never expose AWS credentials in repositories or Terraform code.

---

## Next Steps

<div class="cta-box">

<div class="cta-content">

### Configure Microsoft Azure

Learn how to integrate Azure subscriptions with Axio.

</div>

<div class="cta-action">

[Microsoft Azure →](./azure/){: .btn .btn-primary }

</div>

</div>
