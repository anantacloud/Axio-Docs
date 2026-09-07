---
layout: default
title: Create Project using Platform as Code
parent: Projects
grand_parent: Organization
nav_order: 2
---

<h1>
    <img src="{{ '/assets/icons/code.svg' | relative_url }}"
         class="page-icon"
         alt="Platform as Code">
    Create a Project using Platform as Code
</h1>

<p class="page-description">
   Define a Project in a YAML or JSON file and synchronize the Project with Axio from your Git repository.
</p>

<div class="important-box">
  <div class="important-header">
    <img src="{{ '/assets/icons/triangle-alert.svg' | relative_url }}" alt="Warning">
    <h3>Important</h3>
  </div>

  <p>
       Ensure that your Git repository is connected to Axio before proceeding. Synchronization can be triggered manually or configured on a schedule from             <strong>Platform as Code → Synchronizations</strong>
  </p>
</div>

<hr>

<h2>Step-by-Step Guide</h2>

<div class="step-layout">

<div class="step-left">

<div class="step-item">
<div class="step-circle-pac">1</div>
<div class="step-content">
<h3>Define Project</h3>
<p>Create a YAML or JSON file containing the Project definition.</p>
</div>
</div>

<div class="step-item">
<div class="step-circle-pac">2</div>
<div class="step-content">
<h3>Commit and Push</h3>
<p>Commit the Project definition file and push it to your Git repository.</p>
</div>
</div>

<div class="step-item">
<div class="step-circle-pac">3</div>
<div class="step-content">
<h3>Synchronize with Axio</h3>
<p>Go to <strong>Platform as Code → Synchronizations</strong> and synchronize the connected repository with Axio.</p>
<h4>Manual Synchronization</h4>
<p>Click <strong>Sync now</strong> to immediately synchronize the repository and apply the Project definition.</p>
<h4>Scheduled Synchronization</h4>
<p>Enable <strong>Auto</strong> and configure a synchronization schedule to periodically synchronize the repository.</p>
</div>
</div>

<div class="step-item">
<div class="step-circle-pac">4</div>
<div class="step-content">
<h3>Project Created</h3>
<p>After a successful synchronization, the Project appears under **Organization → Projects**.</p>
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
<h3>Repository Structure</h3>

<pre><code>platform-resources/
└── projects/
    ├── ecommerce.yaml
    ├── payments.yaml
</code></pre>

</div>

</div>
</div>

<hr>

<h2>What Happens Next?</h2>

<ul>
<li>The Project is created in Axio after a successful synchronization.</li>
<li>The Project appears under <strong>Organization → Projects</strong>.</li>
<li>You can synchronize changes manually using <strong>Sync now</strong>.</li>
<li>You can enable <strong>scheduled synchronization</strong> to periodically apply Git changes.</li>
<li>You can begin creating Workspaces inside the Project.</li>
</ul>

<div class="tip-box">

<div class="tip-header">
<img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}" alt="Tip">
<h3>Tip</h3>
</div>

<p>
   Store Project definitions in Git to maintain version history and manage changes through your repository workflow.
</p>

</div>

<div class="page-navigation">

<a class="nav-button previous"
href="{{ '/docs/organization/create-project-ui/' | relative_url }}">
← Create Project from UI
</a>

<a class="nav-button next"
href="{{ '/docs/organization/create-workspace-ui/' | relative_url }}">
Create Workspace from UI →
</a>

</div>
