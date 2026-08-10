---
layout: default
title: Synchronizations
parent: Platform as Code
nav_order: 3
---

<div class="announcement-box">
    <div class="announcement-content">

        <div>
            <h2>Synchronizations</h2>

            <p>
                Reconcile Git-managed manifests with Axio resources and track
                the progress of GitOps changes.
            </p>

        </div>

    </div>
</div>

<div class="prerequisite-header">

    <img src="{{ '/assets/icons/info.svg' | relative_url }}"
         alt="Info">

    <h3>What are Synchronizations?</h3>

</div>

<p>
    Synchronizations connect the desired state stored in Git with the resources
    managed by Axio. They provide the workflow used to discover changes,
    validate manifests, and reconcile resources.
</p>

<div class="step-left">

    <div class="step-item">

        <div class="step-circle-ui">1</div>

        <div class="step-content">

            <h3>Configure the Git Source</h3>

            <p>
                Configure the source repository containing your Platform as
                Code manifests.
            </p>

            <ul>
                <li><strong>Repository</strong></li>
                <li><strong>Branch</strong></li>
                <li><strong>Manifest path</strong></li>
            </ul>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">2</div>

        <div class="step-content">

            <h3>Discover Manifests</h3>

            <p>
                Axio reads the configured Git source and discovers the
                Platform as Code manifests that represent desired resources.
            </p>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">3</div>

        <div class="step-content">

            <h3>Validate Changes</h3>

            <p>
                The discovered manifests are validated against the available
                resource definitions and configuration requirements.
            </p>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">4</div>

        <div class="step-content">

            <h3>Reconcile Resources</h3>

            <p>
                Valid changes are synchronized so that Axio resources reflect
                the desired state represented in Git.
            </p>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">5</div>

        <div class="step-content">

            <h3>Review the Result</h3>

            <p>
                Check synchronization status and review any errors, approval
                requirements, or drift reported for the resources.
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
    Keep manifests small, valid, and version controlled. When a synchronization
    fails, review the manifest, resource dependencies, and synchronization
    history before retrying.
</p>

<a class="nav-button previous"
   href="{{ '/docs/platform-as-code/resources/' | relative_url }}">
    ← Resources
</a>

<a class="nav-button next"
   href="{{ '/docs/platform-as-code/history/' | relative_url }}">
    History →
</a>
