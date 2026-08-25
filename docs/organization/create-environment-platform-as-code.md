---
layout: default
title: Create Environment using Platform as Code
parent: Environments
grand_parent: Organization
nav_order: 2
---

<h1>
  <img src="{{ '/assets/icons/layout-dashboard.svg' | relative_url }}"
       class="page-icon"
       alt="Environment">
  Create a Environment using Platform as Code
</h1>

<p class="page-description">
Define a Environment in a YAML or JSON file and synchronize it from your Git repository.
</p>

<div class="important-box">
  <div class="important-header">
    <img src="{{ '/assets/icons/triangle-alert.svg' | relative_url }}" alt="Warning">
    <h3>Important</h3>
  </div>
  <p>
    Ensure that your Git repository is connected to Axio before creating Environments using Platform as Code. After committing the Environment definition,     synchronize the repository from <strong>Platform as Code → Synchronizations</strong> manually or using a configured schedule.
  </p>
</div>

<hr>

<h2>Step-by-Step Guide</h2>

<div class="step-layout">

<div class="step-left">

<div class="step-item">
<div class="step-circle-pac">1</div>
<div class="step-content">
<h3>Define Environment</h3>
<p>Create a Environment definition in YAML or JSON.</p>
</div>
</div>

<div class="step-item">
<div class="step-circle-pac">2</div>
<div class="step-content">
<h3>Commit and Push</h3>
<p>Commit the Environment definition and push it to your Git repository.</p>
</div>
</div>

<div class="step-item">
<div class="step-circle-pac">3</div>
<div class="step-content">
<h3>Synchronize with Axio</h3>
<p>Go to <strong>Platform as Code → Synchronizations</strong> and synchronize the connected repository manually using <strong>Sync now</strong>, or configure a schedule for automatic synchronization.</p>
</div>
</div>

<div class="step-item">
<div class="step-circle-pac">4</div>
<div class="step-content">
<h3>Environment Created</h3>
<p>After a successful synchronization, the Environment appears under the Workspace specified in its definition.</p>
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
  name: development

spec:
  displayName: Development Environment
  project: ecommerce
  description: Development workspace
</code></pre>

</div>

<div class="json-content">

<pre><code>{
  "apiVersion": "platform.axio.io/v1",
  "kind": "Environment",
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

<h3>Repository Structure</h3>

<pre><code>platform-resources/
└── environments/
    ├── development.yaml
    ├── production.yaml
</code></pre>

</div>

</div>

</div>

<hr>

<h2>What Happens Next?</h2>

<ul>
<li>The Environment is created in Axio.</li>
<li>The Environment appears under the Workspace specified in its definition.</li>
<li>You can manually synchronize the repository again using <strong>Sync now</strong>.</li>
<li>You can configure a synchronization schedule to periodically reconcile repository changes.</li>
<li>You can manage the Environment and its associated infrastructure from the Axio platform.</li>
</ul>


<div class="page-navigation">

<a class="nav-button previous"
href="{{ '/docs/organization/create-environment-ui/' | relative_url }}">
← Create Environment from UI
</a>

<a class="nav-button next"
href="{{ '/docs/platform-as-code/' | relative_url }}">
Platform As Code→
</a>

</div>
