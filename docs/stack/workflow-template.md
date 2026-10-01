---
layout: default
title: Workflow Template
parent: Stacks
nav_order: 3
has_children: true
has_toc: false
permalink: /axio/stack/workflow-template/
---

<link rel="stylesheet" href="{{ '/assets/css/workflow.css' | relative_url }}">

# Workflow Templates

Workflow templates define reusable **deployment pipelines** for Axio stacks — the ordered stages executed when you **Run stack** (Plan, Apply, Destroy, Drift detection, and related operations). A template specifies supported IaC engines and cloud providers, pipeline steps (checkout, validate, plan, approval, apply, notifications, policy checks, and security scans), and optional governance metadata.

Manage templates under **Stacks → Workflow Templates** (`/stacks/workflow-templates`). Attach a template when creating a stack manually, reference one in `axio.yaml`, or select one each time you start a run.

<div class="important-box">
  <div class="important-header">
    <img src="{{ '/assets/icons/triangle-alert.svg' | relative_url }}" alt="Warning">
    <h3>Important</h3>
  </div>

  <p>
    <strong>Workflow templates are not the same as PaC <code>kind: Workflow</code>.</strong>
    Templates describe the <em>deployment pipeline</em> for stack runs (Plan / Apply / Destroy).
    PaC <code>Workflow</code> resources are a separate automation catalog kind. Stack blueprints use
    <code>axio.yaml</code> (<code>kind: Stack</code>), not Platform as Code project manifests.
  </p>

  <p>
    Only <strong>published</strong> organization templates appear in stack run pickers.
    <strong>Built-in</strong> platform templates (standard deploy, destroy, and drift per IaC engine) are available immediately without publishing.
  </p>
</div>

<div class="prerequisite-box">

<div class="prerequisite-header">

<img src="{{ '/assets/icons/info.svg' | relative_url }}" alt="Info">

<h3>Prerequisites</h3>

</div>

<ul>
<li><strong>View templates</strong> — <code>workflow:template:read</code> (all organization roles).</li>
<li><strong>Create, edit, import, or publish</strong> — <code>workflow:template:create</code>, <code>workflow:template:edit</code>, <code>workflow:template:publish</code> (Administrators and Members).</li>
<li><strong>Run stack with a template</strong> — <code>workflow:template:execute</code> and <code>iac:manage</code> in the target scope.</li>
<li>For Git-backed org templates via Platform as Code — a connected repository registered under <strong>Platform as Code → Synchronizations</strong>.</li>
</ul>

</div>

Axio supports two YAML shapes when authoring or importing workflow templates.

<div class="workflow-format-grid">

  <!-- Deployment Template -->
  <div class="workflow-format-card workflow-card-blue">

    <div class="workflow-card-header">

      <div class="workflow-icon-deployment workflow-icon-blue">
        <svg viewBox="0 0 24 24" aria-hidden="true">
          <path d="M8 6h12M8 12h12M8 18h12"/>
          <path d="M3 6h.01M3 12h.01M3 18h.01"/>
        </svg>
      </div>

      <div class="workflow-card-title">
        <h3>1. Deployment Template Format</h3>
        <span class="workflow-badge">Recommended</span>
      </div>

    </div>

    <p>
      Steps-based YAML used for built-in platform templates, the admin <strong>Import YAML</strong> wizard,
      the template editor YAML tab, and raw files in Git repositories.
    </p>

    <ul>
      <li>Human-readable and easy to version in Git</li>
      <li>Ordered pipeline with sequential and <code>parallel:</code> step blocks</li>
      <li>Required fields: <code>id</code>, <code>name</code>, <code>supportedIacEngines</code>, <code>supportedOperations</code>, <code>steps</code></li>
      <li>Recommended for most custom templates</li>
    </ul>

  </div>


  <!-- Designer Graph -->
  <div class="workflow-format-card workflow-card-purple">

    <div class="workflow-card-header">

      <div class="workflow-icon-deployment workflow-icon-purple">
        <svg viewBox="0 0 24 24" aria-hidden="true">
          <circle cx="6" cy="12" r="2"/>
          <circle cx="18" cy="6" r="2"/>
          <circle cx="18" cy="18" r="2"/>
          <path d="M8 11l8-4M8 13l8 4"/>
        </svg>
      </div>

      <div class="workflow-card-title">
        <h3>2. Designer Graph Format</h3>
      </div>

    </div>

    <p>
      Visual graph (<code>nodes</code> and <code>edges</code>) used by the workflow template editor.
      Imported YAML with a top-level <code>nodes</code> array is converted to executable steps automatically.
    </p>

    <ul>
      <li>Graph-based workflow design in the UI</li>
      <li>Automatic conversion to the steps pipeline at save or publish time</li>
      <li>Use <code>config.catalogStage</code> on nodes to reference catalog stage IDs explicitly</li>
    </ul>

  </div>

</div>


## Where templates come from

| Source | How it is loaded | In the UI |
|--------|------------------|-----------|
| **Built-in platform templates** | Registered in the API at startup (code registry plus optional YAML under <code>apps/api/workflow-templates/</code>) | Shown as <strong>Built-in</strong>; read-only; available immediately |
| **Organization catalog** | Created or imported in **Stacks → Workflow Templates**, versioned in PostgreSQL, published per version | <strong>User Managed</strong>; editable; must be <strong>Published</strong> to select on stack runs |
| **Platform as Code Git sync** | <code>kind: WorkflowTemplate</code> manifests (or raw deployment-template YAML) in PaC repositories, synchronized from **Platform as Code → Synchronizations** | Appears in the org catalog after sync; use <code>spec.publish: true</code> or <code>status: ACTIVE</code> for auto-publish |

Built-in templates include one standard **deploy**, **destroy**, and **drift** workflow per IaC engine (Terraform, OpenTofu, Pulumi, CloudFormation, Crossplane, and Azure ARM/Bicep), for example <code>terraform-standard-deploy</code> and <code>opentofu-standard-deploy</code>.


## How templates are used

1. **Manual stack creation** — select a compatible published template on the <strong>Workflow Template</strong> wizard step (see <a href="{{ '/axio/stack/manual-step/' | relative_url }}">Create Stack Manually</a>).
2. **From axio.yaml** — set <code>workflowTemplate</code> or <code>workflowHint</code> in the manifest; Axio resolves a matching template after upload (see <a href="{{ '/axio/stack/from-axio/' | relative_url }}">Create Stack from axio.yaml</a>).
3. **Run stack** — choose a template when starting Plan, Apply, Destroy, or other operations; the stack may remember a default template from provisioning.
4. **Stack detail** — view or change the linked template; deprecated versions show a banner with upgrade guidance.


## What's on this page?

This section is the overview for workflow templates. Use the topics below and child pages for format details, built-in templates, and authoring guidance.

<div class="workflow-capability-grid">

  <div class="workflow-capability-card workflow-capability-blue">

    <div class="workflow-capability-icon">
      <svg viewBox="0 0 24 24" aria-hidden="true">
        <path d="M7 3h8l4 4v14H7z"/>
        <path d="M15 3v5h4"/>
        <path d="M10 12l-2 2 2 2"/>
        <path d="M14 12l2 2-2 2"/>
      </svg>
    </div>

    <h4>YAML Formats</h4>

    <p>
      Deployment-template <code>steps</code> syntax and designer <code>nodes</code>/<code>edges</code> graphs.
      See <a href="{{ '/docs/WORKFLOW_TEMPLATE_YAML.html' | relative_url }}">Workflow template YAML reference</a>.
    </p>

  </div>


  <div class="workflow-capability-card workflow-capability-green">

    <div class="workflow-capability-icon">
      <svg viewBox="0 0 24 24" aria-hidden="true">
        <path d="M7 18a4 4 0 1 1 1-7.87A5 5 0 0 1 18 12a3 3 0 0 1 0 6H7z"/>
        <path d="M12 12v7"/>
        <path d="M9.5 16l2.5 3 2.5-3"/>
      </svg>
    </div>

    <h4>Loading &amp; Git</h4>

    <p>
      Built-in YAML at API startup, org import/publish, and PaC <code>WorkflowTemplate</code> sync from connected repositories.
    </p>

  </div>


  <div class="workflow-capability-card workflow-capability-orange">

    <div class="workflow-capability-icon">
      <svg viewBox="0 0 24 24" aria-hidden="true">
        <path d="M7 3h8l4 4v14H7z"/>
        <path d="M15 3v5h4"/>
        <path d="M10 12h6M10 16h6"/>
      </svg>
    </div>

    <h4>axio.yaml Integration</h4>

    <p>
      Reference <code>workflowTemplate: terraform-standard-deploy</code> or <code>workflowHint</code> in your stack manifest so Create Stack and Run stack resolve the right pipeline.
    </p>

  </div>


  <div class="workflow-capability-card workflow-capability-purple">

    <div class="workflow-capability-icon">
      <svg viewBox="0 0 24 24" aria-hidden="true">
        <path d="M12 3l7 3v5c0 4.5-3 8-7 10-4-2-7-5.5-7-10V6z"/>
        <path d="M9 12l2 2 4-4"/>
      </svg>
    </div>

    <h4>Validation &amp; Governance</h4>

    <p>
      Parse-time checks (valid YAML, non-empty steps, well-formed parallel blocks), publish-time graph integrity, and org governance rules (production approval, plan-before-apply, valid stage IDs).
    </p>

  </div>


  <div class="workflow-capability-card workflow-capability-blue">

    <div class="workflow-capability-icon">
      <svg viewBox="0 0 24 24" aria-hidden="true">
        <path d="M12 16V4"/>
        <path d="M8 8l4-4 4 4"/>
        <path d="M5 12v7h14v-7"/>
      </svg>
    </div>

    <h4>Export</h4>

    <p>
      Export published org template versions as YAML from the template detail page or via the admin API for reuse in Git or other environments.
    </p>

  </div>

</div>


<div class="workflow-start-callout">

  <div class="workflow-start-icon">
    <svg viewBox="0 0 24 24" aria-hidden="true">
      <circle cx="12" cy="12" r="9"/>
      <path d="M12 10v6"/>
      <path d="M12 7h.01"/>
    </svg>
  </div>

  <div class="workflow-start-content">

    <h4>Where to start?</h4>

    <p>
      If you are new to workflow templates, start with the built-in standard deploy templates —
      then read the deployment-template YAML format before authoring custom pipelines.
    </p>

</div>

  <a href="{{ '/axio/stack/built-in/' | relative_url }}"
     class="workflow-start-button">
    Next: Built-In Templates
    <span>→</span>
  </a>

</div>


<div class="page-navigation">

<a
class="nav-button previous"
href="{{ '/axio/stack/manual-step/' | relative_url }}">

← Create Stack Manually

</a>

<a
class="nav-button next"
href="{{ '/axio/stack/built-in/' | relative_url }}">

Built-In Templates →

</a>

</div>
