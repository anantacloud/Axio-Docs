---
layout: default
title: Built-In Template
parent: Workflow Template
nav_order: 2
permalink: /axio/stack/built-in/
---

<link rel="stylesheet" href="{{ '/assets/css/built-in.css' | relative_url }}">

<div class="builtin-workflow-page">

<section class="builtin-hero">
  <div class="builtin-hero-copy">
    <div class="section-eyebrow">WORKFLOW TEMPLATES</div>
    <h1>Built-in Workflow Templates</h1>
    <p>
      Built-in workflow templates are platform-provided pipelines for each supported IaC engine and operation
      (deploy, destroy, drift). They appear in <strong>Stacks → Workflow Templates</strong> as
      <strong>Built-in</strong>, are always available without publishing, and <strong>cannot be edited</strong>.
      Use <strong>Duplicate</strong> on a built-in template to create an editable organization copy with a new ID.
    </p>
  </div>

  <div class="pipeline-card">
    <h2>Typical Built-in Pipeline (Terraform Deploy)</h2>
    <div class="pipeline-flow">
      <div class="pipeline-step purple"><span class="pipeline-icon">↓</span><strong>Checkout</strong></div><span class="pipeline-arrow">→</span>
      <div class="pipeline-step indigo"><span class="pipeline-icon">⚙</span><strong>Init</strong></div><span class="pipeline-arrow">→</span>
      <div class="pipeline-step blue"><span class="pipeline-icon">✓</span><strong>Validate</strong></div><span class="pipeline-arrow">→</span>
      <div class="pipeline-step cyan"><span class="pipeline-icon">&lt;/&gt;</span><strong>Format /<br>Lint /<br>Security</strong></div><span class="pipeline-arrow">→</span>
      <div class="pipeline-step teal"><span class="pipeline-icon">≡</span><strong>Plan</strong></div><span class="pipeline-arrow">→</span>
      <div class="pipeline-step orange"><span class="pipeline-icon">●</span><strong>Approval</strong></div><span class="pipeline-arrow">→</span>
      <div class="pipeline-step green"><span class="pipeline-icon">▶</span><strong>Apply</strong></div><span class="pipeline-arrow">→</span>
      <div class="pipeline-step light-blue"><span class="pipeline-icon">♧</span><strong>Notify</strong></div>
    </div>
    <div class="parallel-label"><span></span>Parallel (Format / Lint / Security)</div>
    <p class="axio-manual-help" style="margin-top: 1rem;">
      Other engines use equivalent stages (for example Pulumi <em>Preview / Up</em>, CloudFormation <em>Changeset / Deploy</em>,
      ARM/Bicep <em>What-If / Deploy</em>). Exact steps vary by engine — open a template in the catalog to view its pipeline.
    </p>
  </div>
</section>

<section class="builtin-main-grid">

<aside class="template-kinds-card">
  <h2><span class="card-heading-icon">▱</span> Two Kinds of Templates</h2>

  <div class="template-kind platform-kind">
    <div class="kind-icon">☁</div>
    <div>
      <h3>Platform (Built-in)</h3>
      <ul>
        <li>Provided by Axio — one deploy, destroy, and drift template per IaC engine</li>
        <li>Read-only in the UI; labeled <strong>Built-in</strong></li>
      </ul>
    </div>
  </div>

  <div class="kind-divider"></div>

  <div class="template-kind org-kind">
    <div class="kind-icon">▣</div>
    <div>
      <h3>Organization (Catalog)</h3>
      <ul>
        <li>Created, imported, or duplicated by your organization</li>
        <li>Editable in the UI (draft → publish → version → deprecate)</li>
        <li>Can <strong>override</strong> a built-in template when a published org template uses the <strong>same template ID</strong></li>
      </ul>
    </div>
  </div>

  <div class="published-note">
    <span>ⓘ</span>
    <p>
      <strong>Built-in templates</strong> are always selectable on stack runs.
      <strong>Organization templates</strong> must be <strong>Published</strong> before they appear in create/run pickers.
    </p>
  </div>
</aside>

<section class="builtin-table-card">
  <h2><span class="card-heading-icon">◇</span> Built-in Deploy Templates</h2>

  <div class="template-table-wrap">
    <table class="builtin-template-table">
      <thead>
        <tr><th>Template ID</th><th>IaC Engine</th><th>Supported Operations</th><th>Cloud Providers</th><th>Purpose</th></tr>
      </thead>
      <tbody>
        <tr><td><strong class="template-id terraform">◆ terraform-standard-deploy</strong></td><td>Terraform</td><td>PLAN, APPLY</td><td>AWS, Azure, GCP, OCI, DigitalOcean</td><td>Init, validate, scan, plan, approval, apply, notify</td></tr>
        <tr><td><strong class="template-id opentofu">◆ opentofu-standard-deploy</strong></td><td>OpenTofu</td><td>PLAN, APPLY</td><td>AWS, Azure, GCP, OCI, DigitalOcean</td><td>Standard deploy pipeline for OpenTofu</td></tr>
        <tr><td><strong class="template-id pulumi">◆ pulumi-standard-deploy</strong></td><td>Pulumi</td><td>PLAN, APPLY</td><td>AWS, Azure, GCP, OCI, DigitalOcean</td><td>Login, stack select, preview, approval, up, notify</td></tr>
        <tr><td><strong class="template-id cloudformation">◆ cloudformation-standard-deploy</strong></td><td>CloudFormation</td><td>PLAN, APPLY</td><td>AWS</td><td>Validate, lint, security scan, changeset, approval, deploy</td></tr>
        <tr><td><strong class="template-id crossplane">◆ crossplane-standard-deploy</strong></td><td>Crossplane</td><td>PLAN, APPLY, VALIDATE</td><td>AWS, Azure, GCP, OCI, DigitalOcean</td><td>Validate, package, approval, apply Crossplane compositions</td></tr>
        <tr><td><strong class="template-id bicep">◆ arm-bicep-standard-deploy</strong></td><td>ARM / Bicep</td><td>PLAN, APPLY</td><td>Azure</td><td>Validate, what-if, approval, deploy Azure resources</td></tr>
      </tbody>
    </table>

    <div class="operation-heading">Operation-specific built-in templates (same engines)</div>
    <table class="builtin-template-table operation-table">
      <thead>
        <tr><th>Template ID pattern</th><th>IaC Engine</th><th>Operation</th><th>Purpose</th></tr>
      </thead>
      <tbody>
        <tr><td><strong class="template-id destroy">▣ *-standard-destroy</strong></td><td>Same engines</td><td>DESTROY</td><td>Plan or preview, approval, destroy, notify</td></tr>
        <tr><td><strong class="template-id drift">◎ *-standard-drift</strong></td><td>Same engines</td><td>DRIFT_DETECTION</td><td>Validate, plan/preview, drift detection, notify</td></tr>
      </tbody>
    </table>

    <p class="axio-manual-help" style="margin-top: 1rem;">
      Replace <code>*</code> with the engine prefix (<code>terraform</code>, <code>opentofu</code>, <code>pulumi</code>,
      <code>cloudformation</code>, <code>crossplane</code>, <code>arm-bicep</code>).
      Example drift template: <code>terraform-standard-drift</code>.
    </p>
  </div>
</section>

</section>

<section class="selection-card">
  <h2><span class="selection-icon">◎</span> How Axio Selects a Template</h2>
  <p style="margin-bottom: 1rem;">
    When you create a stack or start a run, Axio resolves a compatible template from built-in and organization catalogs.
    Resolution considers the stack's IaC engine, cloud provider, operation (Plan / Apply / Destroy / Drift), and optional hints.
  </p>
  <div class="selection-grid">
    <div class="selection-item"><span class="check-icon">✓</span><p><strong>Stack default template</strong> — highest priority when the stack already has <code>defaultWorkflowTemplateId</code> set (from manual create or <code>workflowTemplate</code> in <code>axio.yaml</code>)</p></div>
    <div class="selection-item"><span class="check-icon">✓</span><p><strong>Operation category</strong> — deploy templates for Apply, destroy templates for Destroy, drift templates for Drift detection</p></div>
    <div class="selection-item"><span class="check-icon">✓</span><p><strong>Engine and cloud</strong> — template must list the stack's IaC engine and cloud provider (when declared)</p></div>
    <div class="selection-item"><span class="check-icon">✓</span><p><strong>Default flag</strong> — built-in templates marked <code>isDefault: true</code> for their engine are preferred</p></div>
    <div class="selection-item"><span class="check-icon">✓</span><p><strong>workflowHint</strong> in <code>axio.yaml</code> — fuzzy match when the hint appears in the template ID</p></div>
    <div class="selection-item"><span class="check-icon">✓</span><p><strong>Policy and test stages</strong> — templates that support attached policy packs or test suites score higher when those are configured</p></div>
    <div class="selection-item"><span class="check-icon">✓</span><p><strong>Runner labels</strong> — templates with <code>requiredRunnerLabels</code> must match the runner pool labels on the workload</p></div>
  </div>
</section>

<section class="selection-card" style="margin-top: 1.5rem;">
  <h2><span class="selection-icon">▤</span> Customize a Built-in Template</h2>
  <div class="selection-grid">
    <div class="selection-item"><span class="check-icon">1</span><p>Open <strong>Stacks → Workflow Templates</strong>, find a built-in template, and choose <strong>Duplicate</strong> to create an editable org copy.</p></div>
    <div class="selection-item"><span class="check-icon">2</span><p>Or import YAML via <strong>New → Import YAML</strong> using the deployment-template format</a>.</p></div>
    <div class="selection-item"><span class="check-icon">3</span><p>Publish the org version, then select it when creating or running a stack — or reference its ID in <code>workflowTemplate</code> inside <code>axio.yaml</code>.</p></div>
  </div>
</section>

</div>


<div class="page-navigation">

<a
class="nav-button previous"
href="{{ '/axio/stack/workflow-template/' | relative_url }}">

← Workflow Templates

</a>

<a
class="nav-button next"
href="{{ '/axio/platform-as-code/' | relative_url }}">

Platform as Code →

</a>

</div>
