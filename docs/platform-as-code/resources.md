---
layout: default
title: Resources
parent: Platform as Code
nav_order: 2
---

<div class="announcement-box">
    <div class="announcement-content">

        <div>
            <h2>Resources</h2>

            <p>
                View the read-only inventory of Platform as Code resources
                reconciled from Git-managed manifests.
            </p>

        </div>

    </div>
</div>

<div class="prerequisite-header">

    <img src="{{ '/assets/icons/info.svg' | relative_url }}"
         alt="Info">

    <h3>What are Resources?</h3>

</div>

<p>
    The Resources page provides visibility into platform resources that have
    been reconciled from Git manifests. It is intended for observing the
    current state of Git-managed resources rather than editing them directly.
</p>

<div class="step-left">

    <div class="step-item">

        <div class="step-circle-ui">1</div>

        <div class="step-content">

            <h3>Open Resources</h3>

            <p>
                Navigate to <strong>Platform as Code → Resources</strong> to
                view the Git-managed resource inventory.
            </p>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">2</div>

        <div class="step-content">

            <h3>Review Resource Information</h3>

            <p>
                Review information such as resource name, type, Git-managed
                status, repository, branch, manifest path, and commit.
            </p>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">3</div>

        <div class="step-content">

            <h3>Check Synchronization Status</h3>

            <p>
                Use the synchronization status to understand whether a
                resource is ready, awaiting approval, failed, drifted, or
                otherwise requires attention.
            </p>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">4</div>

        <div class="step-content">

            <h3>Check Drift</h3>

            <p>
                Review the Drift information to identify resources whose
                current state differs from the desired state represented by
                the Git-managed manifest.
            </p>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">5</div>

        <div class="step-content">

            <h3>Update the Git Manifest</h3>

            <p>
                To change a Git-managed resource, update its YAML manifest in
                the configured source repository and push a commit. Do not
                treat the Resources page as the authoring interface.
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
    Use Resources for visibility and troubleshooting. Make configuration
    changes in the source Git repository and let synchronization reconcile
    those changes.
</p>

<a class="nav-button previous"
   href="{{ '/docs/platform-as-code/catalog/' | relative_url }}">
    ← Catalog
</a>

<a class="nav-button next"
   href="{{ '/docs/platform-as-code/synchronizations/' | relative_url }}">
    Synchronizations →
</a>
