---
layout: default
title: Create Environment using Platform as Code
parent: Environments
grand_parent: Organization
nav_order: 2
permalink: /axio/organization/create-environment-platform-as-code/
---

<h1>
  <img src="{{ '/assets/icons/layout-dashboard.svg' | relative_url }}"
       class="page-icon"
       alt="Environment">
  Create an Environment using Platform as Code
</h1>

<p class="page-description">
Define an Environment in a YAML or JSON file and synchronize it from your Git repository.
</p>

<div class="important-box">
  <div class="important-header">
    <img src="{{ '/assets/icons/triangle-alert.svg' | relative_url }}" alt="Warning">
    <h3>Important</h3>
  </div>

  <p>
    <strong>Platform as Code is not Infrastructure as Code.</strong> PaC manages the Axio platform itself (projects, workspaces, environments, policies, runners, and more). It is <strong>not</strong> the same as <code>axio.yaml</code> stack blueprint files in IaC repositories, which describe stack provisioning.
  </p>

  <p>
    An Environment manifest requires a parent <strong>Workspace</strong> (and typically a <strong>Project</strong>). Define and synchronize Project and Workspace manifests first, then add the Environment referencing <code>spec.workspace</code> and <code>spec.project</code>.
  </p>

  <p>
    Connect repositories under <strong>Administration → Integrations → Source Control</strong>, then synchronize from <strong>Platform as Code → Synchronizations</strong>.
  </p>
</div>

<div class="prerequisite-box">

<div class="prerequisite-header">

<img src="{{ '/assets/icons/info.svg' | relative_url }}" alt="Info">

<h3>Prerequisites</h3>

</div>

<ul>
<li>A Git provider connection configured in <strong>Administration → Integrations → Source Control</strong>.</li>
<li>A repository registered for Platform as Code synchronization (created automatically on first <strong>Sync now</strong>, or configured explicitly).</li>
<li>The target <strong>Project</strong> and <strong>Workspace</strong> already defined in Git and synchronized into Axio.</li>
<li>Permission to synchronize:
  <ul>
    <li><strong>Administrators</strong> — full PaC management (<code>pac:manage</code>): connect repos, configure schedules, sync, and approve plans.</li>
    <li><strong>Members (scoped)</strong> — can run <strong>Sync now</strong> on Admin-configured repositories for in-scope product resources.</li>
    <li><strong>Viewers</strong> — read-only access to catalog, resources, and sync history.</li>
  </ul>
</li>
</ul>

</div>

<hr>

<h2>Step-by-Step Guide</h2>

<div class="step-layout">

<div class="step-left">

<div class="step-item">
<div class="step-circle-pac">1</div>
<div class="step-content">
<h3>Ensure parent Project and Workspace exist</h3>
<p>
Confirm the Project and Workspace manifests are in Git and synchronized. Use workspace and project <strong>slugs</strong> from their <code>metadata.name</code> values (e.g. <code>ecommerce</code>, <code>development</code>) in the Environment spec.
</p>
</div>
</div>

<div class="step-item">
<div class="step-circle-pac">2</div>
<div class="step-content">
<h3>Define the Environment</h3>
<p>Create a YAML or JSON file containing the Environment definition.</p>
<ul>
<li><strong><code>metadata.name</code></strong> — Stable identifier; becomes the environment slug (unique within the workspace).</li>
<li><strong><code>spec.displayName</code></strong> — Human-readable name shown in the UI (falls back to <code>metadata.name</code> if omitted).</li>
<li><strong><code>spec.workspace</code></strong> — <strong>Required.</strong> References the parent Workspace by slug or ID.</li>
<li><strong><code>spec.project</code></strong> — Recommended. References the parent Project by slug or ID. Helps resolve the workspace unambiguously.</li>
<li><strong><code>spec.description</code></strong> — Optional summary.</li>
<li><strong><code>spec.type</code></strong> — Optional: <code>DEVELOPMENT</code>, <code>STAGING</code>, <code>PRODUCTION</code>, or <code>CUSTOM</code> (defaults to <code>DEVELOPMENT</code> on create).</li>
<li><strong><code>spec.deploymentGovernance</code></strong> — Optional. Configure deployment operators, approvers, and self-approval in Git (alternative to UI <strong>Assign owner</strong>).</li>
</ul>
<p>Do <strong>not</strong> author a <code>status</code> block — Axio generates and manages status automatically.</p>
</div>
</div>

<div class="step-item">
<div class="step-circle-pac">3</div>
<div class="step-content">
<h3>Commit and push</h3>
<p>Commit the Environment definition and push it to the branch configured for synchronization (typically <code>main</code>).</p>
</div>
</div>

<div class="step-item">
<div class="step-circle-pac">4</div>
<div class="step-content">
<h3>Synchronize with Axio</h3>
<p>Go to <strong>Platform as Code → Synchronizations</strong> and synchronize the connected repository.</p>
<h4>Manual synchronization</h4>
<p>Click <strong>Sync now</strong> to fetch Git changes, validate manifests, resolve dependencies, build a sync plan, and apply the Environment.</p>
<h4>Scheduled synchronization</h4>
<p>Enable the <strong>Auto</strong> switch and choose an interval (or daily schedule) to periodically reconcile the repository.</p>
<h4>Review the sync run</h4>
<p>Check <strong>Recent runs</strong> for validation results, resources created/updated, and any approval required.</p>
</div>
</div>

<div class="step-item">
<div class="step-circle-pac">5</div>
<div class="step-content">
<h3>Environment created</h3>
<p>
After a successful synchronization, the Environment appears under the referenced Workspace on <strong>Organization → Environments</strong> with a <strong>Git-managed</strong> badge. Git-managed environments must be updated through Git synchronization — manual edits in the UI are restricted.
</p>
</div>
</div>

</div>

<div class="step-right">

<div class="code-card">

<div class="tabs">

<input type="radio" id="yaml-tab" name="environment-code" checked>
<label for="yaml-tab" class="tab-label">YAML</label>

<input type="radio" id="json-tab" name="environment-code">
<label for="json-tab" class="tab-label">JSON</label>

<div class="content-wrapper">

<div class="yaml-content">

<pre><code>apiVersion: platform.axio.io/v1
kind: Environment

metadata:
  name: production

spec:
  displayName: Production Environment
  project: ecommerce
  workspace: development
  description: Production deployment target
  type: PRODUCTION
</code></pre>

</div>

<div class="json-content">

<pre><code>{
  "apiVersion": "platform.axio.io/v1",
  "kind": "Environment",
  "metadata": {
    "name": "production"
  },
  "spec": {
    "displayName": "Production Environment",
    "project": "ecommerce",
    "workspace": "development",
    "description": "Production deployment target",
    "type": "PRODUCTION"
  }
}
</code></pre>

</div>

</div>

</div>

</div>

<div class="repo-card">

<h3>Repository structure</h3>

<p>Nested directories are supported. Axio recursively discovers YAML/JSON manifest files under the repository working directory.</p>

<pre><code>platform-config/
├── projects/
│   └── ecommerce.yaml
├── workspaces/
│   └── development.yaml
└── environments/
    ├── staging.yaml
    └── production.yaml
</code></pre>

<p>
<code>spec.workspace</code> must match the Workspace manifest's <code>metadata.name</code>. When both are new, synchronize Project → Workspace → Environment in dependency order (a single sync run handles this if all files are present).
</p>

</div>

</div>

</div>

<hr>

<h2>Field reference</h2>

| Field | Required | Description |
|-------|:--------:|-------------|
| <code>apiVersion</code> | Yes | Must be <code>platform.axio.io/v1</code> |
| <code>kind</code> | Yes | Must be <code>Environment</code> |
| <code>metadata.name</code> | Yes | Unique environment slug within the workspace |
| <code>spec.displayName</code> | No | Display name in the Axio UI |
| <code>spec.workspace</code> | Yes | Parent Workspace slug or ID |
| <code>spec.project</code> | Recommended | Parent Project slug or ID; required when the workspace slug is ambiguous across projects |
| <code>spec.description</code> | No | Optional description |
| <code>spec.type</code> | No | <code>DEVELOPMENT</code>, <code>STAGING</code>, <code>PRODUCTION</code>, or <code>CUSTOM</code> (default <code>DEVELOPMENT</code>) |
| <code>spec.deploymentGovernance</code> | No | Owners, approvers, and self-approval policy (see below) |
| <code>status</code> | No | **Do not author** — system-managed |

<p><strong>Naming rules:</strong> Environment slugs must be unique within the parent workspace. Conflicting slugs fail validation during synchronization.</p>

<p><strong>System environments:</strong> The auto-provisioned <strong>Default Environment</strong> is a protected system resource and cannot be modified or deleted through Platform as Code.</p>

<p><strong>Workspace assignment:</strong> PaC update changes name, description, type, and governance — not workspace reassignment. Move environments between workspaces using the UI edit flow for non-Git-managed resources.</p>

<hr>

<h2>What happens next?</h2>

<ul>
<li>The Environment is created or updated in Axio after a successful synchronization.</li>
<li>The Environment appears under the referenced Project and Workspace on <strong>Organization → Environments</strong> with a <strong>Git-managed</strong> badge.</li>
<li>Future changes flow through Git — edit the manifest, commit, push, and synchronize again.</li>
<li>You can run <strong>Sync now</strong> at any time or enable <strong>Auto</strong> scheduled synchronization.</li>
<li>Review sync results under <strong>Recent runs</strong> and <strong>Platform as Code → History</strong>.</li>
<li>Deploy <strong>Stacks</strong> into the environment, or define stack manifests and synchronize them next.</li>
</ul>

<div class="resource-grid-info">

<div class="resource-card environment">

    <div class="card-title">

        <img class="environment-icon" src="{{ '/assets/icons/globe.svg' | relative_url }}"
             alt="Git-managed">

        <h3>Git-managed environments</h3>

    </div>

    <p>
        Environments created through Platform as Code are managed from Git. The UI shows a <strong>Git-managed</strong> badge.
    </p>

    <ul>
        <li>Update the environment by editing the manifest in Git and synchronizing</li>
        <li>Manual rename/delete in the UI is blocked for Git-managed environments</li>
        <li>Git-managed environments cannot be unassigned from their workspace via the UI</li>
        <li>Removing an environment from Git may stage a <strong>pending removal</strong> — review under Synchronizations</li>
    </ul>

</div>

<div class="resource-card workspace">

    <div class="card-title">

        <img class="workspace-icon" src="{{ '/assets/icons/boxes.svg' | relative_url }}"
             alt="Sensitive">

        <h3>Sensitive manifests and approval</h3>

    </div>

    <p>
        Optional <code>metadata.sensitive: true</code> marks a manifest so Git-driven <strong>updates or removals</strong> require sync plan approval before apply.
    </p>

    <p>
        This is separate from the UI <strong>Sensitive</strong> checkbox (delete/archive/destroy protection), configured when editing an environment in the UI.
    </p>

</div>

</div>

<div class="tip-box">

<div class="tip-header">
<img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}" alt="Tip">
<h3>Tip</h3>
</div>

<p>
  Keep Environment definitions in Git alongside Projects and Workspaces in the same repository. Use <code>type: PRODUCTION</code> for production targets and set <code>allowSelfApproval: false</code> in governance for separation of duties. Browse templates under <strong>Platform as Code → Catalog</strong>.
</p>

</div>


<div class="page-navigation">

<a class="nav-button previous"
href="{{ '/axio/organization/environment/create-environment-ui/' | relative_url }}">
← Create Environment from UI
</a>

<a class="nav-button next"
href="{{ '/axio/stack/from-axio/' | relative_url }}">
Create Stack from axio.yaml →
</a>

</div>
