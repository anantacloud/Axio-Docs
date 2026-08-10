---
layout: default
title: Platform as Code
nav_order: 3
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

<p class="platform-overview">
    Axio Platform as Code provides a GitOps-based workflow for managing platform
    resources. Instead of making configuration changes directly in the platform,
    define the desired state in YAML manifests, store those manifests in Git,
    and synchronize them with Axio.
</p>

<h2 class="workflow-title">Platform as Code workflow</h2>

<div class="platform-code-layout">

    <!-- LEFT -->

    <div class="platform-workflow">

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

    <!-- RIGHT -->

    <div class="platform-right">

        <div class="platform-description">
            Axio Platform as Code brings GitOps principles to platform resource
            management. Define resources as code, keep them version controlled,
            and let Axio discover, validate, and reconcile the desired state.
        </div>

        <h3 class="platform-workflow-heading">
            Platform as Code Workflow
        </h3>

        <div class="workflow-diagram">

            <div class="workflow-node">
                <div class="workflow-icon">1</div>
                <strong>Define</strong>
                <span>Write resource manifests in Git</span>
            </div>

            <div class="workflow-arrow">→</div>

            <div class="workflow-node">
                <div class="workflow-icon">2</div>
                <strong>Commit</strong>
                <span>Commit and push changes to the repository</span>
            </div>

            <div class="workflow-arrow">→</div>

            <div class="workflow-node">
                <div class="workflow-icon">3</div>
                <strong>Discover</strong>
                <span>Axio discovers changes from Git</span>
            </div>

            <div class="workflow-arrow">→</div>

            <div class="workflow-node">
                <div class="workflow-icon">4</div>
                <strong>Validate</strong>
                <span>Manifest and policy checks are performed</span>
            </div>

            <div class="workflow-arrow">→</div>

            <div class="workflow-node">
                <div class="workflow-icon">5</div>
                <strong>Reconcile</strong>
                <span>Resources are created or updated in Axio</span>
            </div>

            <div class="workflow-arrow">→</div>

            <div class="workflow-node">
                <div class="workflow-icon">6</div>
                <strong>Observe</strong>
                <span>Monitor status, drift, and history</span>
            </div>

        </div>

        <div class="platform-bottom-grid">

            <div class="platform-card benefits-card">

                <h3>Benefits</h3>

                <ul>

                    <li>Single source of truth for platform resources</li>

                    <li>Version control and auditability</li>

                    <li>Consistent and repeatable deployments</li>

                    <li>Policy enforcement and drift detection</li>

                    <li>Collaborative workflows with Git</li>

                    <li>Full visibility with history and status</li>

                </ul>

            </div>

            <div class="platform-card platform-tip">

                <div class="tip-header">

                    <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
                         alt="Tip">

                    <h3>Tip</h3>

                </div>

                <p>
                    Treat Git as the source of truth for Git-managed Platform as
                    Code resources. Make changes in the manifest repository and
                    synchronize them through Axio.
                </p>

                <hr>

                <strong>Example structure:</strong>

                <pre><code>platform-resources/
├── organizations/
├── projects/
├── workspaces/
├── environments/
└── stacks/</code></pre>

            </div>

        </div>

    </div>

</div>

<div class="platform-navigation">

    <a
        class="nav-button previous"
        href="{{ '/docs/organization/' | relative_url }}">

        ← Organization Overview

    </a>

    <a
        class="nav-button next"
        href="{{ '/docs/platform-as-code/catalog/' | relative_url }}">

        Catalog →

    </a>

</div>

