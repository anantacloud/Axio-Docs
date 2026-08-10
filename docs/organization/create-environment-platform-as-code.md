---
layout: default
nav_order: 2
grand_parent: Organization
parent: Environments
title: Create Environment using Platform as Code
---

::: announcement-box
::: announcement-content
    <img src="{{ '/assets/icons/environment.svg' | relative_url }}"
         alt="Environment"
         class="page-icon">

    <div>
      <h2>Create Environment using Platform as Code</h2>
      <p>
        Define and manage Axio environments declaratively using a YAML manifest.
      </p>
    </div>
:::
:::

## Overview

Platform as Code allows you to create and manage Axio resources using
version-controlled YAML manifests.

Instead of creating an environment manually from the Axio UI, you can
define the desired configuration in a YAML file and apply it through the
Axio CLI.

This approach makes environment configuration:

-   **Repeatable** --- recreate environments using the same manifest.
-   **Version controlled** --- keep configuration in Git.
-   **Consistent** --- use the same configuration across environments.
-   **Automation friendly** --- integrate environment creation into
    CI/CD pipelines.

------------------------------------------------------------------------

## Prerequisites

::: prerequisite-header
`<img src="{{ '/assets/icons/info.svg' | relative_url }}"
       alt="Info">`{=html}

```{=html}
<h3>
```
Prerequisite
```{=html}
</h3>
```
:::

```{=html}
<p>
```
Ensure that you have permission to create Environments and that a
Workspace already exists.
```{=html}
</p>
```
Before creating an environment, make sure you have:

-   An Axio organization.
-   A Workspace where the environment will be created.
-   Permission to create and manage environments.
-   The Axio CLI configured and authenticated.
-   Platform as Code support enabled for your Axio installation.

------------------------------------------------------------------------

## Step 1: Create the Environment Manifest

Create a file named `environment.yaml`.

The manifest defines the desired state of your Axio environment.

``` yaml
apiVersion: platform.axio.io/v1
kind: Environment

metadata:
  name: my-environment
  sensitive: true

spec:
  displayName: Environment-testing
  workspace: production
```

### Manifest Fields

  -----------------------------------------------------------------------
  Field                               Description
  ----------------------------------- -----------------------------------
  `apiVersion`                        API version used to define the Axio
                                      resource.

  `kind`                              Specifies that the resource is an
                                      `Environment`.

  `metadata.name`                     Unique name of the environment.

  `metadata.sensitive`                Indicates whether the environment
                                      contains sensitive configuration.

  `spec.displayName`                  Human-readable display name of the
                                      environment.

  `spec.workspace`                    Workspace in which the environment
                                      is created.
  -----------------------------------------------------------------------

> **Note:** The value of `spec.workspace` must reference an existing
> Workspace that you have permission to use.

------------------------------------------------------------------------

## Step 2: Apply the Manifest

Use the Axio CLI to create the environment from the YAML manifest.

``` bash
axio apply -f environment.yaml
```

The CLI reads the manifest and creates the environment in the specified
Workspace.

A successful operation should confirm that the resource was created or
applied successfully.

------------------------------------------------------------------------

## Step 3: Verify the Environment

After applying the manifest, verify that the environment was created.

``` bash
axio get environments
```

You should see your newly created environment in the list.

For example:

``` text
NAME             DISPLAY NAME          WORKSPACE
my-environment   Environment-testing   production
```

------------------------------------------------------------------------

## Step 4: Update the Environment

Platform as Code also allows you to update an existing environment.

Update the values in `environment.yaml`.

For example:

``` yaml
apiVersion: platform.axio.io/v1
kind: Environment

metadata:
  name: my-environment
  sensitive: true

spec:
  displayName: Environment-production
  workspace: production
```

Apply the updated manifest:

``` bash
axio apply -f environment.yaml
```

Axio will reconcile the resource with the configuration defined in the
manifest.

------------------------------------------------------------------------

## Step 5: Delete the Environment

When an environment is no longer required, remove it using the Axio CLI.

``` bash
axio delete -f environment.yaml
```

Verify that the environment has been removed:

``` bash
axio get environments
```

------------------------------------------------------------------------

## Recommended Manifest Structure

For production usage, keep your Platform as Code manifests organized in
a version-controlled repository.

A simple structure can look like:

``` text
platform/
├── environments/
│   ├── development/
│   │   └── environment.yaml
│   ├── staging/
│   │   └── environment.yaml
│   └── production/
│       └── environment.yaml
└── README.md
```

This structure makes it easier to manage environment configuration
separately for development, staging, and production.

------------------------------------------------------------------------

::: tip-box
### Tip

Store your environment manifests in Git and review changes through pull
requests before applying them to shared or production Workspaces.
:::

------------------------------------------------------------------------

## Best Practices

### Use meaningful environment names

Choose names that clearly identify the purpose of the environment.

``` yaml
metadata:
  name: production-environment
```

### Keep manifests in version control

Store Platform as Code manifests in Git so that configuration changes
can be tracked and reviewed.

### Separate environments

Maintain separate manifests or directories for development, staging, and
production environments.

### Keep Workspace references valid

Make sure the Workspace referenced by `spec.workspace` already exists
and that the user or automation applying the manifest has the required
permissions.

### Review changes before applying

Use pull requests and CI/CD validation to review configuration changes
before they are applied to shared environments.

---

## Expected Result

After applying the manifest successfully, the environment is created and
managed as an Axio resource.

You can manage the same environment declaratively by updating the YAML
manifest and applying it again.

---

## Next Steps

Now that you know how to create an environment using Platform as Code,
you can:

-   Create and manage multiple environments.
-   Integrate environment manifests into CI/CD pipelines.
-   Store environment configuration in Git.
-   Manage Axio resources consistently across environments.


← [Create Environment from UI](create-environment-ui)


