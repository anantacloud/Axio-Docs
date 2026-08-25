---
layout: default
title: Platform as Code
nav_order: 4
has_toc: false
---

# Platform as Code

Manage your platform resources using Git. Define, version, and collaborate on your infrastructure and platform configuration as code.
           
<div class="platform-code-layout">

    <!-- LEFT -->

    <div class="platform-workflow">

        <div class="step-item">

            <div class="step-circle-ui">1</div>

            <div class="step-content">

                <h3>Connect Git Repository</h3>

                <p>
                    Connect your Git repository that contains the resource manifests. Axio will use this repository as the source of truth.
                </p>

            </div>

        </div>


        <div class="step-item">

            <div class="step-circle-ui">2</div>

            <div class="step-content">

                <h3>Synchronize</h3>

                <p>
                    Trigger a synchronization to have Axio discover, validate, and reconcile the resources defined in Git. Synchronization can be started manually or configured on a schedule.
                </p>

            </div>

        </div>

        <div class="step-item">

            <div class="step-circle-ui">3</div>

            <div class="step-content">

                <h3>Monitor & Review</h3>

                <p>
                    Track synchronization status, resource drift, and synchronization history to review changes and their outcomes.
                </p>

            </div>

        </div>

    </div>

    <!-- RIGHT -->

    <div class="platform-right">

        <div class="platform-description">
            Axio Platform as Code brings GitOps principles to platform resource
            management. Define resources as code, keep them version controlled,
            and synchronize them with Axio to discover, validate, and reconcile             the desired state.
        </div>

        <h3 class="platform-workflow-heading">
            Platform as Code Workflow
        </h3>

        <div class="workflow-diagram">

            <div class="workflow-node">
                <div class="workflow-icon-define">
                    <img src="/assets/icons/file-code-corner (1).svg" alt="Define">
                </div>
                <strong>Define</strong>
                <span>Write resource manifests in Git</span>
            </div>

            <div class="workflow-arrow">→</div>

            <div class="workflow-node">
                <div class="workflow-icon-commit">
                    <img src="/assets/icons/git-branch (1).svg" alt="Commit">
                </div>
                <strong>Commit</strong>
                <span>Commit and push changes to the repository</span>
            </div>

            <div class="workflow-arrow">→</div>

            <div class="workflow-node">
                <div class="workflow-icon-sync">
                    <img src="/assets/icons/refresh-cw (1).svg" alt="Synchronize">
                </div>
                <strong>Synchronize</strong>
                <span>Trigger manually or on a configured schedule</span>
            </div>

            <div class="workflow-arrow">→</div>

            <div class="workflow-node">
                <div class="workflow-icon-discover">
                    <img src="/assets/icons/search.svg" alt="Discover">
                </div>
                <strong>Discover</strong>
                <span>Axio discovers changes from Git</span>
            </div>

            <div class="workflow-arrow">→</div>

            <div class="workflow-node">
                <div class="workflow-icon-validate">
                    <img src="/assets/icons/shield-check (2).svg" alt="Validate">
                </div>
                <strong>Validate</strong>
                <span>Manifest and policy checks are performed</span>
            </div>

            <div class="workflow-arrow">→</div>

            <div class="workflow-node">
                <div class="workflow-icon-reconcile">
                    <img src="/assets/icons/git-merge.svg" alt="Reconcile">
                </div>
                <strong>Reconcile</strong>
                <span>Resources are created or updated in Axio</span>
            </div>

            <div class="workflow-arrow">→</div>

            <div class="workflow-node">
                <div class="workflow-icon-observe">
                    <img src="/assets/icons/clipboard-list.svg" alt="Observe">
                </div>
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

                    <li>Consistent and repeatable management</li>

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
                    use <strong>Sync now</strong> or a configured schedule to synchronize them with Axio.
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
