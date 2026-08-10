---
layout: default
title: Platform as Code
nav_order: 1
has_children: true
---

<div class="announcement-box">
    <div class="announcement-content">

        <div>
            <h2>Platform as Code</h2>

            <p>
                Manage Axio resources declaratively through Git-managed manifests,
                resource schemas, synchronization, and change history.
            </p>

        </div>

    </div>
</div>

<div class="prerequisite-header">

    <img src="{{ '/assets/icons/info.svg' | relative_url }}"
         alt="Info">

    <h3>Overview</h3>

</div>

<p>
    Axio Platform as Code provides a GitOps-based workflow for managing platform
    resources. Instead of making configuration changes directly in the platform,
    define the desired state in YAML manifests, store those manifests in Git,
    and synchronize them with Axio.
</p>

## Platform as Code workflow

<div class="step-left">

    <div class="step-item">

        <div class="step-circle-ui">1</div>

        <div class="step-content">

            <h3>Explore the Catalog</h3>

            <p>
                Browse the available resource kinds, schemas, required fields,
                dependencies, and YAML examples before creating a manifest.
            </p>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">2</div>

        <div class="step-content">

            <h3>Define resources in Git</h3>

            <p>
                Create YAML manifests that describe the desired state of your
                Axio resources and commit them to the configured repository.
            </p>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">3</div>

        <div class="step-content">

            <h3>Synchronize changes</h3>

            <p>
                Use Synchronizations to reconcile Git-managed manifests with
                resources in Axio.
            </p>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">4</div>

        <div class="step-content">

            <h3>Review resources and history</h3>

            <p>
                Use Resources to inspect the current Git-managed resource
                inventory and History to review synchronization and change
                activity.
            </p>

        </div>

    </div>

</div>

<div class="tip-header">

    <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
         alt="Tip">

    <h3>Tip</h3>

</div>

<p>
    Treat Git as the source of truth for Git-managed Platform as Code resources.
    Make changes in the manifest repository and synchronize them through Axio.
</p>

<div class="nav-buttons">

<a class="nav-button next"
   href="{{ '/docs/platform-as-code/catalog/' | relative_url }}">
    Catalog →
</a>

</div>
