---
layout: default
title: Create Project using Platform as Code
parent: Projects
grand_parent: Organization
nav_order: 2
permalink: /axio/organization/project/create-project-platform-as-code/
---

<link rel="stylesheet" href="{{ '/assets/css/project-pac.css' | relative_url }}">


<h1>
    <img src="{{ '/assets/icons/code.svg' | relative_url }}"
         class="page-icon"
         alt="Platform as Code">
    Create a Project using Platform as Code
</h1>

<p class="page-description">
   Define a Project in a YAML or JSON file and synchronize it with Axio from your Git repository.
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
    Ensure that your Git repository is connected to Axio before proceeding. Connect repositories under <strong>Administration → Integrations → Source Control</strong>, then synchronize from <strong>Platform as Code → Synchronizations</strong>.
  </p>
</div>

<div class="prerequisite-box">

<div class="prerequisite-header">

<img src="{{ '/assets/icons/info.svg' | relative_url }}" alt="Info">

<h3>Prerequisites</h3>

</div>

<ul>
<li>A Git provider connection (GitHub, GitLab, Bitbucket, or Azure DevOps) configured in <strong>Administration → Integrations → Source Control</strong>.</li>
<li>A repository registered for Platform as Code synchronization (created automatically on first <strong>Sync now</strong>, or configured explicitly).</li>
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
<h3>Connect your Git repository</h3>
<p>
If not already connected, go to <strong>Administration → Integrations → Source Control</strong>, connect your provider, and register the repository. Set the <strong>working directory</strong> to the folder that contains your platform manifests (default: <code>platform-config</code>).
</p>
</div>
</div>

<div class="step-item">
<div class="step-circle-pac">2</div>
<div class="step-content">
<h3>Define the Project</h3>
<p>Create a YAML or JSON file containing the Project definition.</p>
<ul>
<li><strong><code>metadata.name</code></strong> — Stable identifier; becomes the project slug (URL-safe).</li>
<li><strong><code>spec.displayName</code></strong> — Human-readable name shown in the UI (falls back to <code>metadata.name</code> if omitted).</li>
<li><strong><code>spec.description</code></strong> — Optional summary.</li>
</ul>
<p>Do <strong>not</strong> author a <code>status</code> block — Axio generates and manages status automatically.</p>
</div>
</div>

<div class="step-item">
<div class="step-circle-pac">3</div>
<div class="step-content">
<h3>Commit and push</h3>
<p>Commit the Project definition file and push it to the branch configured for synchronization (typically <code>main</code>).</p>
</div>
</div>

<div class="step-item">
<div class="step-circle-pac">4</div>
<div class="step-content">
<h3>Synchronize with Axio</h3>
<p>Go to <strong>Platform as Code → Synchronizations</strong> and synchronize the connected repository.</p>
<h4>Manual synchronization</h4>
<p>Click <strong>Sync now</strong> to immediately fetch Git changes, validate manifests, build a sync plan, and apply the Project definition.</p>
<h4>Scheduled synchronization</h4>
<p>Enable the <strong>Auto</strong> switch and choose an interval (or daily schedule) to periodically reconcile the repository with Axio.</p>
<h4>Review the sync run</h4>
<p>Check <strong>Recent runs</strong> on the same page for validation results, resources created/updated, and any approval required. Some changes to sensitive manifests require approval before apply.</p>
</div>
</div>

<div class="step-item">
<div class="step-circle-pac">5</div>
<div class="step-content">
<h3>Project created</h3>
<p>
After a successful synchronization, the Project appears under <strong>Organization → Projects</strong> with a <strong>Git-managed</strong> badge. Git-managed projects must be updated through Git synchronization — manual edits in the UI are restricted.
</p>
</div>
</div>

</div>

<div class="step-right">

<div class="code-card">

<div class="tabs">

<input type="radio" id="yaml-tab" name="project-code" checked>
<label for="yaml-tab" class="tab-label">YAML</label>

<input type="radio" id="json-tab" name="project-code">
<label for="json-tab" class="tab-label">JSON</label>

<div class="content-wrapper">

<div class="yaml-content">

<pre><code>apiVersion: platform.axio.io/v1
kind: Project

metadata:
  name: ecommerce

spec:
  displayName: Ecommerce Project
  description: Project for ecommerce services
</code></pre>

</div>

<div class="json-content">

<pre><code>{
  "apiVersion": "platform.axio.io/v1",
  "kind": "Project",
  "metadata": {
    "name": "ecommerce"
  },
  "spec": {
    "displayName": "Ecommerce Project",
    "description": "Project for ecommerce services"
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
└── projects/
    ├── ecommerce.yaml
    └── payments.yaml
</code></pre>

<p>Alternative layouts (e.g. <code>platform/projects/</code>) work as long as the repository <strong>working directory</strong> is configured correctly in Source Control.</p>

</div>

</div>

</div>

<hr>

<h2>Field reference</h2>

| Field | Required | Description |
|-------|:--------:|-------------|
| <code>apiVersion</code> | Yes | Must be <code>platform.axio.io/v1</code> |
| <code>kind</code> | Yes | Must be <code>Project</code> |
| <code>metadata.name</code> | Yes | Unique slug within the organization. Used to match the project on updates. Names are slugified (e.g. <code>Ecommerce Project</code> → <code>ecommerce-project</code>). |
| <code>spec.displayName</code> | No | Display name in the Axio UI |
| <code>spec.description</code> | No | Optional description |
| <code>status</code> | No | **Do not author** — system-managed |

<p><strong>Naming rules:</strong> Project slugs must be unique within the organization. Renaming <code>metadata.name</code> changes the slug; conflicting slugs fail validation during synchronization.</p>

<p><strong>System projects:</strong> The auto-provisioned <strong>Default Project</strong> is a protected system resource and cannot be modified or deleted through Platform as Code.</p>


<hr>

<h2>What happens next?</h2>

<ul>
<li>The Project is created or updated in Axio after a successful synchronization.</li>
<li>The Project appears under <strong>Organization → Projects</strong> with a <strong>Git-managed</strong> badge.</li>
<li>Future changes to the Project flow through Git — edit the manifest, commit, push, and synchronize again.</li>
<li>You can run <strong>Sync now</strong> at any time for immediate reconciliation.</li>
<li>You can enable <strong>Auto</strong> scheduled synchronization to apply Git changes on a recurring interval.</li>
<li>Push webhooks (when configured) can trigger synchronization without manual <strong>Sync now</strong>.</li>
<li>Review sync results under <strong>Recent runs</strong> and <strong>Platform as Code → History</strong>.</li>
<li>Define a <strong>Workspace</strong> manifest that references this project (<code>spec.project: ecommerce</code>) and synchronize it next.</li>
</ul>

<div class="resource-grid-info">

<div class="resource-card-pac project">

    <div class="card-title">

        <img class="project-icon" src="{{ '/assets/icons/folder.svg' | relative_url }}"
             alt="Git-managed">

        <h3>Git-managed projects</h3>

    </div>

    <p>
        Projects created through Platform as Code are managed from Git. The UI shows a <strong>Git-managed</strong> badge.
    </p>

    <ul>
        <li>Update the project by editing the manifest in Git and synchronizing</li>
        <li>Manual rename/delete in the UI is blocked for Git-managed projects</li>
        <li>Removing a project from Git may stage a <strong>pending removal</strong> — review and confirm under Synchronizations</li>
    </ul>

</div>

<div class="resource-card workspace">

    <div class="card-title">

        <img class="workspace-icon" src="{{ '/assets/icons/boxes.svg' | relative_url }}"
             alt="Sensitive">

        <h3>Sensitive manifests and approval</h3>

    </div>

    <p>
        Optional <code>metadata.sensitive: true</code> (or label <code>platform.axio.io/sensitive: "true"</code>) marks a manifest so that Git-driven <strong>updates or removals</strong> require sync plan approval before apply.
    </p>

    <p>
        This is separate from the UI <strong>Sensitive</strong> checkbox on projects (delete/archive/destroy protection), which is configured when editing a project in the UI.
    </p>

</div>

</div>

<div class="tip-box">

<div class="tip-header">
<img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}" alt="Tip">
<h3>Tip</h3>
</div>

<p>
   Store Project definitions in Git to maintain version history, review changes through pull requests, and manage configuration consistently across environments. Browse available resource kinds and generated templates under <strong>Platform as Code → Catalog</strong>.
</p>

</div>


<div class="page-navigation">

<a class="nav-button previous"
href="{{ '/axio/organization/project/create-project-ui/' | relative_url }}">
← Create Project from UI
</a>

<a class="nav-button next"
href="{{ '/axio/organization/workspace/create-workspace-ui/' | relative_url }}">
Create Workspace from UI →
</a>

</div>
