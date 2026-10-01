---
layout: default
title: Create Workspace using Platform as Code
parent: Workspaces
grand_parent: Organization
nav_order: 2
permalink: /axio/organization/workspace/create-workspace-platform-as-code/
---

<h1>
  <img src="{{ '/assets/icons/layout-dashboard.svg' | relative_url }}"
       class="page-icon"
       alt="Workspace">
  Create a Workspace using Platform as Code
</h1>

<p class="page-description">
Define a Workspace in a YAML or JSON file and synchronize it with Axio from your Git repository.
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
    A Workspace manifest requires a parent <strong>Project</strong>. Define and synchronize the Project first, then add the Workspace manifest referencing <code>spec.project</code>.
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
<li>The target <strong>Project</strong> already defined in Git and synchronized into Axio (or present from a prior sync in the same repository).</li>
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
<h3>Ensure the parent Project exists</h3>
<p>
The Workspace depends on a Project. Confirm the Project manifest (for example <code>projects/ecommerce.yaml</code>) is in Git and has been synchronized successfully. Use the project <strong>slug</strong> from <code>metadata.name</code> (e.g. <code>ecommerce</code>) in <code>spec.project</code>.
</p>
</div>
</div>

<div class="step-item">
<div class="step-circle-pac">2</div>
<div class="step-content">
<h3>Define the Workspace</h3>
<p>Create a YAML or JSON file containing the Workspace definition.</p>
<ul>
<li><strong><code>metadata.name</code></strong> — Stable identifier; becomes the workspace slug (unique within the project).</li>
<li><strong><code>spec.displayName</code></strong> — Human-readable name shown in the UI (falls back to <code>metadata.name</code> if omitted).</li>
<li><strong><code>spec.project</code></strong> — <strong>Required.</strong> References the parent Project by slug or ID.</li>
<li><strong><code>spec.description</code></strong> — Optional summary.</li>
</ul>
<p>Do <strong>not</strong> author a <code>status</code> block — Axio generates and manages status automatically.</p>
</div>
</div>

<div class="step-item">
<div class="step-circle-pac">3</div>
<div class="step-content">
<h3>Commit and push</h3>
<p>Commit the Workspace definition and push it to the branch configured for synchronization (typically <code>main</code>).</p>
</div>
</div>

<div class="step-item">
<div class="step-circle-pac">4</div>
<div class="step-content">
<h3>Synchronize with Axio</h3>
<p>Go to <strong>Platform as Code → Synchronizations</strong> and synchronize the connected repository.</p>
<h4>Manual synchronization</h4>
<p>Click <strong>Sync now</strong> to fetch Git changes, validate manifests, resolve the Project dependency, build a sync plan, and apply the Workspace.</p>
<h4>Scheduled synchronization</h4>
<p>Enable the <strong>Auto</strong> switch and choose an interval (or daily schedule) to periodically reconcile the repository.</p>
<h4>Review the sync run</h4>
<p>Check <strong>Recent runs</strong> for validation results, resources created/updated, and any approval required. Changes to sensitive manifests may require approval before apply.</p>
</div>
</div>

<div class="step-item">
<div class="step-circle-pac">5</div>
<div class="step-content">
<h3>Workspace created</h3>
<p>
After a successful synchronization, the Workspace appears under the referenced Project on <strong>Organization → Workspaces</strong> with a <strong>Git-managed</strong> badge. Git-managed workspaces must be updated through Git synchronization — manual edits in the UI are restricted.
</p>
</div>
</div>

</div>

<div class="step-right">

<div class="code-card">

<div class="tabs">

<input type="radio" id="yaml-tab" name="workspace-code" checked>
<label for="yaml-tab" class="tab-label">YAML</label>

<input type="radio" id="json-tab" name="workspace-code">
<label for="json-tab" class="tab-label">JSON</label>

<div class="content-wrapper">

<div class="yaml-content">

<pre><code>apiVersion: platform.axio.io/v1
kind: Workspace

metadata:
  name: development

spec:
  displayName: Development Workspace
  project: ecommerce
  description: Development workspace
</code></pre>

</div>

<div class="json-content">

<pre><code>{
  "apiVersion": "platform.axio.io/v1",
  "kind": "Workspace",
  "metadata": {
    "name": "development"
  },
  "spec": {
    "displayName": "Development Workspace",
    "project": "ecommerce",
    "description": "Development workspace"
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
└── workspaces/
    ├── development.yaml
    └── staging.yaml
</code></pre>

<p>
<code>spec.project: ecommerce</code> must match the Project manifest's <code>metadata.name</code> (slug). Apply Project manifests before Workspace manifests in the same sync when both are new.
</p>

</div>

</div>

</div>

<hr>

<h2>Field reference</h2>

| Field | Required | Description |
|-------|:--------:|-------------|
| <code>apiVersion</code> | Yes | Must be <code>platform.axio.io/v1</code> |
| <code>kind</code> | Yes | Must be <code>Workspace</code> |
| <code>metadata.name</code> | Yes | Unique workspace slug within the parent project. Used to match the workspace on updates. |
| <code>spec.displayName</code> | No | Display name in the Axio UI |
| <code>spec.project</code> | Yes | Parent Project slug or ID. Validation fails if the project cannot be resolved. |
| <code>spec.description</code> | No | Optional description |
| <code>status</code> | No | **Do not author** — system-managed |

<p><strong>Naming rules:</strong> Workspace slugs must be unique within the parent project. Renaming <code>metadata.name</code> changes the slug; conflicting slugs fail validation during synchronization.</p>

<p><strong>System workspaces:</strong> The auto-provisioned <strong>Default Workspace</strong> is a protected system resource and cannot be modified or deleted through Platform as Code.</p>

<p><strong>Project assignment:</strong> New workspaces are created under the project referenced in <code>spec.project</code>. Moving a workspace to another project is handled through the UI edit flow, not by changing <code>spec.project</code> on an existing Git-managed workspace.</p>

<hr>

<h2>What happens next?</h2>

<ul>
<li>The Workspace is created or updated in Axio after a successful synchronization.</li>
<li>The Workspace appears under the referenced Project on <strong>Organization → Workspaces</strong> with a <strong>Git-managed</strong> badge.</li>
<li>Future changes flow through Git — edit the manifest, commit, push, and synchronize again.</li>
<li>You can run <strong>Sync now</strong> at any time for immediate reconciliation.</li>
<li>You can enable <strong>Auto</strong> scheduled synchronization to apply Git changes on a recurring interval.</li>
<li>Push webhooks (when configured) can trigger synchronization without manual <strong>Sync now</strong>.</li>
<li>Review sync results under <strong>Recent runs</strong> and <strong>Platform as Code → History</strong>.</li>
<li>Define an <strong>Environment</strong> manifest referencing this workspace and project, then synchronize it next.</li>
</ul>

<div class="resource-grid-info">

<div class="resource-card workspace">

    <div class="card-title">

        <img class="workspace-icon" src="{{ '/assets/icons/boxes.svg' | relative_url }}"
             alt="Git-managed">

        <h3>Git-managed workspaces</h3>

    </div>

    <p>
        Workspaces created through Platform as Code are managed from Git. The UI shows a <strong>Git-managed</strong> badge.
    </p>

    <ul>
        <li>Update the workspace by editing the manifest in Git and synchronizing</li>
        <li>Manual rename/delete in the UI is blocked for Git-managed workspaces</li>
        <li>Git-managed workspaces cannot be unassigned from their project via the UI</li>
        <li>Removing a workspace from Git may stage a <strong>pending removal</strong> — review under Synchronizations</li>
    </ul>

</div>

<div class="resource-card project">

    <div class="card-title">

        <img class="project-icon" src="{{ '/assets/icons/folder.svg' | relative_url }}"
             alt="Sensitive">

        <h3>Sensitive manifests and approval</h3>

    </div>

    <p>
        Optional <code>metadata.sensitive: true</code> (or label <code>platform.axio.io/sensitive: "true"</code>) marks a manifest so Git-driven <strong>updates or removals</strong> require sync plan approval before apply.
    </p>

    <p>
        This is separate from the UI <strong>Sensitive</strong> checkbox (delete/archive/destroy protection), which is configured when editing a workspace in the UI.
    </p>

</div>

</div>

<div class="tip-box">

<div class="tip-header">
<img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}" alt="Tip">
<h3>Tip</h3>
</div>

<p>
  Keep Workspace definitions in Git to maintain version history and manage changes through pull requests. Browse resource kinds and templates under <strong>Platform as Code → Catalog</strong>. Define Projects and Workspaces in the same repository so dependency order is satisfied on each sync.
</p>

</div>


<div class="page-navigation">

<a class="nav-button previous"
href="{{ '/axio/organization/workspace/create-workspace-ui/' | relative_url }}">
← Create Workspace from UI
</a>

<a class="nav-button next"
href="{{ '/axio/organization/environment/create-environment-ui/' | relative_url }}">
Create Environment from UI →
</a>

</div>
