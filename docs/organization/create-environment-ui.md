---
layout: default
title: Create Environment from UI
parent: Environments
grand_parent: Organization
nav_order: 1
---

<div class="announcement-box">
    <div class="announcement-content">
        <img src="{{ '/assets/icons/layers.svg' | relative_url }}"
             class="page-icon"
             alt="Environment">

# Create Environment from UI

Create an environment through the Axio web interface to organize and manage application deployments. Environments help isolate configurations, credentials, and infrastructure for different stages such as development, staging, and production.

</div>
</div>

## Prerequisites

Before creating an environment, ensure that:

- You have access to the Axio platform.
- A **Workspace** already exists.
- You have permission to create environments within the selected workspace.

---

## Step-by-Step Guide

<div class="step-container">

<div class="step">

### **1. Login to Axio**

Sign in to the Axio platform using your credentials.

</div>

<div class="step">

### **2. Navigate to Environments**

Go to:

**Organization → Environments**

</div>

<div class="step">

### **3. Click Create Environment**

Click the **Create Environment** button.

</div>

<div class="step">

### **4. Enter Environment Details**

Provide the required information:

- **Name** – Unique identifier for the environment.
- **Display Name** – Friendly name displayed in the UI.
- **Workspace** – Select the workspace where the environment will be created.
- **Description** *(Optional)* – Brief description of the environment.

</div>

<div class="step">

### **5. Review Configuration**

Verify all the entered information before creating the environment.

</div>

<div class="step">

### **6. Create the Environment**

Click **Create** to provision the environment.

</div>

</div>

---

## Example

| Field | Example |
|--------|---------|
| Name | production |
| Display Name | Production Environment |
| Workspace | platform-team |
| Description | Production deployment environment |

---

<div class="tip-box">

### 💡 Tip

Use meaningful names such as **development**, **staging**, or **production** so that environments are easy to identify across projects.

</div>

---

## Best Practices

- Follow a consistent naming convention.
- Create separate environments for each deployment stage.
- Add clear descriptions for easier maintenance.
- Organize environments under the appropriate workspace.
- Grant access only to authorized users.

---

## Expected Result

After successful creation:

- The environment appears under the selected workspace.
- It becomes available for deployments and resource management.
- Team members with the required permissions can access and manage it.

---

## Next Steps

After creating an environment, you can:

- Configure infrastructure resources.
- Deploy applications into the environment.
- Assign credentials and secrets.
- Configure policies and access permissions.
- Monitor deployments and environment health.

---

<div class="cta-box">

## What's Next?

Continue with **Create Environment using Platform as Code** to automate environment creation through declarative configuration.

<a href="create-environment-platform-as-code.html" class="btn btn-primary">
Create Environment using Platform as Code →
</a>

</div>
