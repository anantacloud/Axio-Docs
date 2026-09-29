---
layout: default
title: Platform as Code
nav_order: 4
has_toc: false
permalink: /axio/platform-as-code/
---

# Platform as Code

Manage your Axio **platform** resources using Git. Define, version, and collaborate on organization configuration — projects, workspaces, environments, policies, runners, workflows, and more — then synchronize Git with Axio to discover, validate, and reconcile the desired state.

<div class="important-box">
  <div class="important-header">
    <img src="{{ '/assets/icons/triangle-alert.svg' | relative_url }}" alt="Warning">
    <h3>Important</h3>
  </div>

  <p>
    <strong>Platform as Code is not Infrastructure as Code.</strong> PaC manages the Axio platform itself.
    It is <strong>not</strong> the same as <code>axio.yaml</code> stack blueprints in IaC repositories, which describe stack provisioning (variables, runtime, workflow).
    See <a href="{{ '/axio/stack/from-axio/' | relative_url }}">Create Stack from axio.yaml</a> and
    <a href="{{ '/axio/organization/overview/' | relative_url }}">Organization overview</a>.
  </p>

  <p>
    Connect Git under <strong>Administration → Integrations → Source Control</strong>, then register repositories and run synchronization from
    <strong>Platform as Code → Synchronizations</strong> in the left sidebar.
  </p>
</div>

<div class="prerequisite-box">

<div class="prerequisite-header">

<img src="{{ '/assets/icons/info.svg' | relative_url }}" alt="Info">

<h3>Prerequisites</h3>

</div>

<ul>
<li>A Git provider connection (GitHub, GitLab, Bitbucket, or Azure DevOps) under <strong>Administration → Integrations → Source Control</strong>.</li>
<li>YAML or JSON manifests using <code>apiVersion: platform.axio.io/v1</code> and a supported <code>kind</code> (see the <strong>Catalog</strong> tab).</li>
<li>Permissions:
  <ul>
    <li><strong>Administrators</strong> — full PaC management (<code>pac:manage</code>): connect repos, configure schedules, sync, approve plans.</li>
    <li><strong>Members (scoped)</strong> — run <strong>Sync now</strong> on Admin-configured repositories for in-scope resources.</li>
    <li><strong>Viewers</strong> — read-only access to catalog, resources, and sync history (<code>pac:read</code>).</li>
  </ul>
</li>
</ul>

</div>

<div class="platform-code-layout">

    <!-- LEFT -->

    <div class="platform-workflow">

        <div class="step-item">

            <div class="step-circle-ui">1</div>

            <div class="step-content">

                <h3>Connect Git Repository</h3>

                <p>
                    Connect your Git provider under <strong>Administration → Integrations → Source Control</strong>.
                    Register the repository for Platform as Code and set the <strong>working directory</strong> to the folder that contains manifests (default: <code>platform-config</code>).
                </p>

            </div>

        </div>

        <div class="step-item">

            <div class="step-circle-ui">2</div>

            <div class="step-content">

                <h3>Define Manifests in Git</h3>

                <p>
                    Author desired-state YAML using Kubernetes-style envelopes (<code>apiVersion</code>, <code>kind</code>, <code>metadata</code>, <code>spec</code>).
                    Browse supported kinds in <strong>Platform as Code → Catalog</strong>. Do not author <code>status</code> — Axio generates it.
                </p>

            </div>

        </div>

        <div class="step-item">

            <div class="step-circle-ui">3</div>

            <div class="step-content">

                <h3>Synchronize</h3>

                <p>
                    Open <strong>Platform as Code → Synchronizations</strong> and click <strong>Sync now</strong>, or enable <strong>Auto</strong> on a schedule.
                    Axio discovers manifests, validates them, previews a plan, and reconciles resources. Some changes require approval before apply.
                </p>

            </div>

        </div>

        <div class="step-item">

            <div class="step-circle-ui">4</div>

            <div class="step-content">

                <h3>Monitor &amp; Review</h3>

                <p>
                    Use <strong>Dashboard</strong>, <strong>Resources</strong>, and <strong>History</strong> to track sync status, Git-managed resources, drift, validation outcomes, and approval history.
                </p>

            </div>

        </div>

    </div>

    <!-- RIGHT -->

    <div class="platform-right">

        <div class="platform-description">
            Axio Platform as Code brings GitOps principles to platform resource management. Git is the source of truth for Git-managed resources — define manifests in version control, synchronize them with Axio, and let the platform discover, validate, and reconcile the desired state.
        </div>

        <h3 class="platform-workflow-heading">
            Platform as Code Workflow
        </h3>

        <div class="workflow-diagram">

            <div class="workflow-node">
                <div class="workflow-icon-define">
                    <img src="{{ '/assets/icons/file-code-corner (1).svg' | relative_url }}" alt="Define">
                </div>
                <strong>Define</strong>
                <span>Write resource manifests in Git</span>
            </div>

            <div class="workflow-arrow">→</div>

            <div class="workflow-node">
                <div class="workflow-icon-commit">
                    <img src="{{ '/assets/icons/git-branch (1).svg' | relative_url }}" alt="Commit">
                </div>
                <strong>Commit</strong>
                <span>Commit and push changes to the repository</span>
            </div>

            <div class="workflow-arrow">→</div>

            <div class="workflow-node">
                <div class="workflow-icon-sync">
                    <img src="{{ '/assets/icons/refresh-cw (1).svg' | relative_url }}" alt="Synchronize">
                </div>
                <strong>Synchronize</strong>
                <span>Sync now, scheduled Auto sync, or webhook</span>
            </div>

            <div class="workflow-arrow">→</div>

            <div class="workflow-node">
                <div class="workflow-icon-discover">
                    <img src="{{ '/assets/icons/search.svg' | relative_url }}" alt="Discover">
                </div>
                <strong>Discover</strong>
                <span>Axio scans the working directory for manifests</span>
            </div>

            <div class="workflow-arrow">→</div>

            <div class="workflow-node">
                <div class="workflow-icon-validate">
                    <img src="{{ '/assets/icons/shield-check (2).svg' | relative_url }}" alt="Validate">
                </div>
                <strong>Validate</strong>
                <span>Schema, business rules, and policy checks</span>
            </div>

            <div class="workflow-arrow">→</div>

            <div class="workflow-node">
                <div class="workflow-icon-reconcile">
                    <img src="{{ '/assets/icons/git-merge.svg' | relative_url }}" alt="Reconcile">
                </div>
                <strong>Reconcile</strong>
                <span>Resources are created or updated in Axio</span>
            </div>

            <div class="workflow-arrow">→</div>

            <div class="workflow-node">
                <div class="workflow-icon-observe">
                    <img src="{{ '/assets/icons/clipboard-list.svg' | relative_url }}" alt="Observe">
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

                    <li>Version control and auditability via Git history</li>

                    <li>Consistent, repeatable management across environments</li>

                    <li>Validation, policy enforcement, and drift detection</li>

                    <li>Collaborative workflows with pull requests and reviews</li>

                    <li>Full visibility — dashboard, resource explorer, and sync history</li>

                </ul>

            </div>

            <div class="platform-card platform-tip">

                <div class="tip-header">

                    <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
                         alt="Tip">

                    <h3>Tip</h3>

                </div>

                <p>
                    Treat Git as the source of truth for Git-managed Platform as Code resources.
                    Make changes in the manifest repository and use <strong>Sync now</strong> or a configured <strong>Auto</strong> schedule to synchronize them with Axio.
                    Resources synced from Git show a <strong>Git-managed</strong> indicator in the UI.
                </p>

                <hr>

                <strong>Example manifest:</strong>

                <pre><code>apiVersion: platform.axio.io/v1
kind: Project
metadata:
  name: ecommerce
spec:
  displayName: E-Commerce Platform
  description: Customer-facing workloads</code></pre>

                <strong>Example repository structure:</strong>

                <pre><code>platform-config/
├── projects/
├── workspaces/
├── environments/
├── policies/
├── runner-pools/
└── workflow-templates/</code></pre>

            </div>

        </div>

        <div class="platform-card" style="margin-top: 1.5rem;">

            <h3>In the Axio UI</h3>

            <p>Open <strong>Platform as Code</strong> in the left sidebar:</p>

            <ul>
                <li><strong>Dashboard</strong> — GitOps overview, connected repositories, recent sync activity</li>
                <li><strong>Catalog</strong> — Browse 145+ resource kinds and view schema documentation</li>
                <li><strong>Resources</strong> — Explorer for Git-managed and UI-created platform resources</li>
                <li><strong>Synchronizations</strong> — Register repos, <strong>Sync now</strong>, configure <strong>Auto</strong> schedules</li>
                <li><strong>History</strong> — Read-only audit of sync, validation, approval, and reconciliation outcomes</li>
            </ul>

            <p>
                To create organization resources with PaC, see
                <a href="{{ '/axio/organization/project/create-project-platform-as-code/' | relative_url }}">Create Project using Platform as Code</a>,
                <a href="{{ '/axio/organization/workspace/create-workspace-platform-as-code/' | relative_url }}">Create Workspace using Platform as Code</a>, and
                <a href="{{ '/axio/organization/environment/create-environment-platform-as-code/' | relative_url }}">Create Environment using Platform as Code</a>.
            </p>

        </div>

    </div>

</div>


<div class="page-navigation">

<a
class="nav-button previous"
href="{{ '/axio/stack/built-in/' | relative_url }}">

← Built-In Templates

</a>

<a
class="nav-button next"
href="{{ '/axio/organization/overview/' | relative_url }}">

Organization Overview →

</a>

</div>
