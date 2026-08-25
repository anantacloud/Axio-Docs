---
layout: default
title: Built-In Template
parent: Workflow Template
nav_order: 2
---

<div class="builtin-workflow-page">

<section class="builtin-hero">
  <div class="builtin-hero-copy">
    <div class="section-eyebrow">WORKFLOW TEMPLATES</div>
    <h1>Built-in Workflow Templates</h1>
    <p>Built-in workflow templates are platform-provided pipelines for different IaC engines and operations. They are always available and <strong>cannot be edited</strong>. Duplicate a template to customize it.</p>
  </div>

  <div class="pipeline-card">
    <h2>Typical Built-in Pipeline (Deploy)</h2>
    <div class="pipeline-flow">
      <div class="pipeline-step purple"><span class="pipeline-icon">↓</span><strong>Checkout</strong></div><span class="pipeline-arrow">→</span>
      <div class="pipeline-step blue"><span class="pipeline-icon">✓</span><strong>Validate</strong></div><span class="pipeline-arrow">→</span>
      <div class="pipeline-step cyan"><span class="pipeline-icon">&lt;/&gt;</span><strong>Format /<br>Lint /<br>Security</strong></div><span class="pipeline-arrow">→</span>
      <div class="pipeline-step teal"><span class="pipeline-icon">≡</span><strong>Plan</strong></div><span class="pipeline-arrow">→</span>
      <div class="pipeline-step orange"><span class="pipeline-icon">●</span><strong>Approval</strong></div><span class="pipeline-arrow">→</span>
      <div class="pipeline-step green"><span class="pipeline-icon">▶</span><strong>Apply</strong></div><span class="pipeline-arrow">→</span>
      <div class="pipeline-step light-blue"><span class="pipeline-icon">♧</span><strong>Notify</strong></div>
    </div>
    <div class="parallel-label"><span></span>Parallel</div>
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
        <li>Provided by Axio</li>
        <li>Stored in API registry + YAML files</li>
        <li>Not editable in the UI</li>
      </ul>
    </div>
  </div>

  <div class="kind-divider"></div>

  <div class="template-kind org-kind">
    <div class="kind-icon">▣</div>
    <div>
      <h3>Organization (Catalog)</h3>
      <ul>
        <li>Created and managed by your organization</li>
        <li>Editable in the UI (draft → publish → version)</li>
        <li>Can override a built-in template using the same ID</li>
      </ul>
    </div>
  </div>

  <div class="published-note">
    <span>ⓘ</span>
    <p>Only <strong>published templates</strong> can be selected when creating or running a stack.</p>
  </div>
</aside>

<section class="builtin-table-card">
  <h2><span class="card-heading-icon">◇</span> Built-in Templates</h2>

  <div class="template-table-wrap">
    <table class="builtin-template-table">
      <thead>
        <tr><th>Template ID</th><th>IaC Engine</th><th>Supported Operations</th><th>Purpose</th></tr>
      </thead>
      <tbody>
        <tr><td><strong class="template-id terraform">◆ terraform-standard-deploy</strong></td><td>Terraform</td><td>PLAN, APPLY, VALIDATE</td><td>Standard deploy pipeline with plan, approval and apply</td></tr>
        <tr><td><strong class="template-id opentofu">◆ opentofu-standard-deploy</strong></td><td>OpenTofu</td><td>PLAN, APPLY, VALIDATE</td><td>Standard deploy pipeline for OpenTofu</td></tr>
        <tr><td><strong class="template-id pulumi">◆ pulumi-standard-deploy</strong></td><td>Pulumi</td><td>PLAN, APPLY, VALIDATE</td><td>Standard deploy pipeline for Pulumi</td></tr>
        <tr><td><strong class="template-id cloudformation">◆ cloudformation-standard-deploy</strong></td><td>AWS CloudFormation</td><td>PLAN, APPLY, VALIDATE</td><td>Standard deploy pipeline for CloudFormation</td></tr>
        <tr><td><strong class="template-id crossplane">◆ crossplane-standard-deploy</strong></td><td>Crossplane</td><td>PLAN, APPLY, VALIDATE</td><td>Standard deploy pipeline for Crossplane</td></tr>
        <tr><td><strong class="template-id bicep">◆ arm-bicep-standard-deploy</strong></td><td>ARM / Bicep</td><td>PLAN, APPLY, VALIDATE</td><td>Standard deploy pipeline for ARM / Bicep</td></tr>
      </tbody>
    </table>

    <div class="operation-heading">Operation-specific Built-in Templates (available for the above engines)</div>
    <table class="builtin-template-table operation-table">
      <tbody>
        <tr><td><strong class="template-id destroy">▣ *-standard-destroy</strong></td><td>Same engines</td><td>DESTROY</td><td>Pipeline to destroy infrastructure</td></tr>
        <tr><td><strong class="template-id drift">◎ *-standard-drift-detection</strong></td><td>Same engines</td><td>DRIFT_DETECTION</td><td>Pipeline to detect configuration drift</td></tr>
      </tbody>
    </table>
  </div>
</section>

</section>

<section class="selection-card">
  <h2><span class="selection-icon">◎</span> How Axio Selects a Built-in Template</h2>
  <div class="selection-grid">
    <div class="selection-item"><span class="check-icon">✓</span><p>Matches the stack's IaC engine, cloud and operation</p></div>
    <div class="selection-item"><span class="check-icon">✓</span><p>Uses stack default template if already set</p></div>
    <div class="selection-item"><span class="check-icon">✓</span><p>Uses <code>workflowTemplate</code> in <code>axio.yaml</code> (highest priority)</p></div>
    <div class="selection-item"><span class="check-icon">✓</span><p>Considers category (deploy, destroy, drift) and default template flag</p></div>
    <div class="selection-item"><span class="check-icon">✓</span><p>Considers required runner labels and policy/test stages</p></div>
  </div>
</section>

</div>

