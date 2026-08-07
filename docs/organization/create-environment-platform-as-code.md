---
layout: default
title: Create Environment using Platform as Code
parent: Environments
grand_parent: Organization
nav_order: 2
---

<div class="announcement-box">
    <div class="announcement-content">

# Create Environment using Platform as Code

Create and manage environments declaratively using Platform as Code. This approach enables version-controlled, repeatable, and automated environment provisioning across your organization.

</div>
</div>

## Overview

Platform as Code allows you to define environments as YAML resources. These definitions can be stored in a Git repository and applied through your CI/CD pipeline, enabling consistent and auditable environment management.

---

## Prerequisites

Before creating an environment, ensure that:

- An organization already exists.
- A workspace has been created.
- You have permission to create resources in the selected workspace.
- The Platform as Code controller is configured.

---

## Environment Manifest

Create an `environment.yaml` file.

```yaml
apiVersion: platform.axio.io/v1
kind: Environment

metadata:
  name: production
  sensitive: true

spec:
  displayName: Production Environment
  workspace: platform-team
```

---

## Manifest Fields

| Field | Description |
|--------|-------------|
| apiVersion | API version of the Environment resource. |
| kind | Resource type. Always `Environment`. |
| metadata.name | Unique identifier of the environment. |
| metadata.sensitive | Marks the environment as sensitive. |
| spec.displayName | Friendly name shown in the UI. |
| spec.workspace | Workspace where the environment will be created. |

---

## Apply the Manifest

Apply the resource using the Platform CLI.

```bash
axio apply -f environment.yaml
```

---

## Verify the Environment

Verify that the environment has been created successfully.

```bash
axio get environments
```

Example output:

```text
NAME          WORKSPACE       STATUS
production    platform-team   Ready
```

---

## Update an Environment

Modify the YAML file and apply it again.

Example:

```yaml
spec:
  displayName: Production Environment
  workspace: platform-team
```

```bash
axio apply -f environment.yaml
```

The platform updates the existing environment instead of creating a duplicate resource.

---

## Delete an Environment

Delete the environment using the manifest.

```bash
axio delete -f environment.yaml
```

Or delete it by name.

```bash
axio delete environment production
```

---

<div class="tip-box">

### 💡 Tip

Store environment manifests in Git and manage them through pull requests to maintain a complete audit trail and enable collaboration.

</div>

---

## Best Practices

- Keep environment manifests in source control.
- Use meaningful names such as **development**, **staging**, and **production**.
- Review all changes through pull requests.
- Maintain separate manifests for different deployment stages.
- Avoid modifying production resources manually.
- Automate deployments using CI/CD pipelines.

---

## Expected Result

After applying the manifest:

- The environment is created automatically.
- It appears under the specified workspace.
- The configuration becomes version-controlled.
- Infrastructure provisioning remains consistent across deployments.

---

## Next Steps

Once your environment is created, you can:

- Configure infrastructure resources.
- Deploy applications into the environment.
- Manage secrets and credentials.
- Apply governance and security policies.
- Integrate the environment into your CI/CD workflows.

---

<div class="cta-box">

## What's Next?

Learn how to deploy applications and manage infrastructure resources within your environment.

<a href="environment.html" class="btn btn-primary">
Explore Environment Documentation →
</a>

</div>
