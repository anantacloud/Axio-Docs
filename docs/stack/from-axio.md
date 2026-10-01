---
layout: default
title: Create Stack from axio.yaml
parent: Stacks
nav_order: 1
permalink: /axio/stack/from-axio/
---


<link rel="stylesheet" href="{{ '/assets/css/stack-axio.css' | relative_url }}">

# Create a Stack from `axio.yaml`

Upload a valid **`axio.yaml`** or **`axio.yml`** stack blueprint. Axio parses the manifest and imports placement, runtime, variables, secrets, policies, and runner settings — then you review and create the stack.

<div class="important-box">
  <div class="important-header">
    <img src="{{ '/assets/icons/triangle-alert.svg' | relative_url }}" alt="Warning">
    <h3>Important</h3>
  </div>

  <p>
    <strong><code>axio.yaml</code> is not Platform as Code.</strong> Stack blueprints live in IaC repositories and describe how to provision a stack (variables, runtime, workflow). PaC manifests under <code>platform-config/</code> declare organization resources such as projects, workspaces, and environments. See <a href="{{ '/axio/organization/overview/' | relative_url }}">Organization overview</a>.
  </p>

  <p>
    <strong>This path is different from Manual setup.</strong> Manual setup walks through repository, engine, backend, workflow, and policies in the Axio UI and does <strong>not</strong> read <code>axio.yaml</code> during creation. Use <strong>From axio.yaml</strong> when your repository already contains a manifest.
  </p>
</div>

<div class="prerequisite-box">

<div class="prerequisite-header">

<img src="{{ '/assets/icons/info.svg' | relative_url }}" alt="Info">

<h3>Prerequisites</h3>

</div>

<ul>
<li>Permission to create stacks (<strong>Member</strong> or higher with <code>iac:manage</code> in the target project, workspace, or environment scope).</li>
<li>A valid <code>axio.yaml</code> or <code>axio.yml</code> file on your computer.</li>
<li>The <strong>Project</strong>, <strong>Team workspace</strong>, and <strong>Environment</strong> named in the manifest <code>placement</code> section must already exist in Axio (or match defaults such as <em>Default Project</em> / <em>Default Workspace</em>).</li>
<li>If the manifest declares <code>runtime.cloud.provider</code>, a matching cloud credential must exist under <strong>Administration → Integrations → Cloud providers</strong>, or you select one on the review step.</li>
<li>Optional: if the manifest includes a <code>sourceControl</code> block, the named Git connection must exist under <strong>Administration → Integrations → Source Control</strong>.</li>
</ul>

</div>

<div class="axio-page">

  <div class="axio-hero">
    <div>
      <div class="axio-eyebrow">STACK CREATION</div>
      <h2>Create Stack from <span>axio.yaml</span></h2>
      <p>
        Go to <strong>Stacks → New Stack</strong> and choose <strong>From axio.yaml</strong>.
        Upload your manifest — Axio validates it and pre-fills the review screen.
      </p>
    </div>
    <div class="axio-badge">Recommended</div>
  </div>

  <div class="axio-info">
    <span class="axio-info-icon">i</span>
    <div>
      <strong>The axio.yaml file defines your stack blueprint.</strong>
      <p>
        Required fields include <code>metadata.name</code>, <code>runtime.iac.engine</code>, and
        <code>runtime.iac.version</code>. When a cloud provider is declared, <code>runtime.cloud.credential</code>
        (or <code>credentialId</code>) and <code>runtime.cloud.region</code> are required as well.
      </p>
    </div>
  </div>

  <div class="axio-layout">

    <aside class="axio-steps" aria-label="Stack creation steps">
      <div class="axio-section-title">Steps</div>

      <button class="axio-step active" data-step="1">
        <span class="axio-step-number">1</span>
        <span>
          <strong>Upload axio.yaml</strong>
          <small>Choose <code>axio.yaml</code> or <code>axio.yml</code> from your computer.</small>
        </span>
      </button>

      <button class="axio-step" data-step="2">
        <span class="axio-step-number">2</span>
        <span>
          <strong>Review &amp; Create</strong>
          <small>Confirm imported placement, runtime, credentials, variables, and policies — then create the stack.</small>
        </span>
      </button>
    </aside>

    <section class="axio-card" id="stackWizard">

      <div class="axio-card-header">
        <div>
          <div class="axio-card-kicker">Create Stack</div>
          <h3>From `axio.yaml`</h3>
        </div>
        <div class="axio-progress"><span id="progressBar"></span></div>
      </div>

      <div class="axio-form-step active" data-panel="1">
        <label>Stack blueprint file <em>*</em></label>
        <div class="axio-input-with-icon">
          <input type="text" value="axio.yaml" aria-label="Manifest file" readonly>
        </div>

        <div class="axio-step-help">
          Click <strong>Choose file</strong> and select <code>axio.yaml</code> or <code>axio.yml</code>.
          Axio parses the file immediately and shows validation errors if anything is missing or invalid.
        </div>

        <div class="axio-found">
          <span>✓</span>
          <div>
            <strong>Manifest loaded</strong>
            <small>Placement, runtime, variables, secrets, and policies imported from the file.</small>
          </div>
        </div>

      </div>

      <div class="axio-form-step" data-panel="2">
        <div class="axio-review">
          <div><span>Project</span><strong>Acme Corp</strong></div>
          <div><span>Team workspace</span><strong>platform-team</strong></div>
          <div><span>Environment</span><strong>Development</strong></div>
          <div><span>Stack name</span><strong>my-app-stack</strong></div>
          <div><span>IaC engine</span><strong>Terraform 1.9.5</strong></div>
          <div><span>Cloud provider</span><strong>AWS · us-east-1</strong></div>
          <div><span>Cloud credential</span><strong>acme-aws-prod</strong></div>
          <div><span>Variables / policies</span><strong>3 variables · 1 policy pack</strong></div>
        </div>

        <div class="axio-auto">
          <span>✓</span>
          <div>
            <strong>Axio resolves placement from the manifest</strong>
            <small>
              Values come from <code>placement.project</code>, <code>placement.workspace</code>, and
              <code>placement.environment</code> (names or IDs). Stack name comes from <code>metadata.name</code>.
            </small>
          </div>
        </div>

        <div class="axio-step-help">
          If the manifest declares a cloud provider but the credential name does not match an existing connection,
          select the correct credential on this step before creating the stack. Workflow templates are chosen when
          you <strong>Run stack</strong>, not during creation.
        </div>
      </div>

      <div class="axio-actions">
        <button class="axio-btn secondary" id="prevStep">Back</button>
        <button class="axio-btn primary" id="nextStep">Continue</button>
      </div>

    </section>
  </div>

  <div class="axio-complete" id="completeMessage">
    <span class="axio-check">✓</span>
    <div>
      <strong>That's it!</strong>
      <span>Your stack is created and appears in the Stacks inventory.</span>
    </div>
  </div>

  <div class="axio-reference">
    <div class="axio-reference-icon">&lt;/&gt;</div>
    <div>
      <strong>Repository &amp; file location</strong>
      <p>
        For upload-based creation, Git is optional. To tie the stack to a repository, include a
        <code>sourceControl</code> block in the manifest (connection, repository, branch/tag/commit, and
        <code>workingDirectory</code>). When Axio discovers manifests from Git, it looks for
        <code>axio.yaml</code> or <code>axio.yml</code> at the repository root <strong>or</strong> under the
        configured working directory (for example <code>terraform/axio.yaml</code>). After creation, use
        <strong>Sync from repository</strong> on the stack detail page to pull manifest updates.
      </p>
    </div>
  </div>

  <div class="axio-best-practices">
    <h3>Best Practices</h3>
    <ul>
      <li>Keep <code>axio.yaml</code> in the repository root or the IaC working directory referenced by <code>sourceControl.workingDirectory</code>.</li>
      <li>Use meaningful values for <code>metadata.name</code> and <code>metadata.description</code>.</li>
      <li>Declare explicit cloud credentials in the manifest — Axio does not auto-select ambient runner credentials.</li>
      <li>Store sensitive values using Axio secrets or secret references in the manifest, not plain text.</li>
      <li>Review imported variables, policies, and runner targeting on the review step before clicking <strong>New stack</strong>.</li>
      <li>Prefer <strong>From axio.yaml</strong> for GitOps-style stacks; use <a href="{{ '/axio/stack/manual-step/' | relative_url }}">Manual setup</a> only when no manifest exists yet.</li>
    </ul>
  </div>

</div>


<script>
document.addEventListener("DOMContentLoaded", function () {
  const steps = Array.from(document.querySelectorAll(".axio-step"));
  const panels = Array.from(document.querySelectorAll(".axio-form-step"));
  const next = document.getElementById("nextStep");
  const prev = document.getElementById("prevStep");
  const progress = document.getElementById("progressBar");
  const complete = document.getElementById("completeMessage");

  const TOTAL_STEPS = 2;
  let current = 1;

  function render(step) {
    current = step;

    steps.forEach((item) => {
      item.classList.toggle("active", Number(item.dataset.step) === current);
      item.classList.toggle("done", Number(item.dataset.step) < current);
    });

    panels.forEach((panel) => {
      panel.classList.toggle("active", Number(panel.dataset.panel) === current);
    });

    progress.style.width = ((current - 1) / (TOTAL_STEPS - 1)) * 100 + "%";
    prev.style.visibility = current === 1 ? "hidden" : "visible";
    next.textContent = current === TOTAL_STEPS ? "New stack" : "Continue";

    if (current < TOTAL_STEPS) {
      complete.classList.remove("show");
    }
  }

  steps.forEach((step) => {
    step.addEventListener("click", function () {
      render(Number(this.dataset.step));
    });
  });

  next.addEventListener("click", function () {
    if (current < TOTAL_STEPS) {
      render(current + 1);
    } else {
      complete.classList.add("show");
      complete.scrollIntoView({ behavior: "smooth", block: "center" });
    }
  });

  prev.addEventListener("click", function () {
    if (current > 1) render(current - 1);
  });

  render(1);
});
</script>


<div class="page-navigation">

<a
class="nav-button previous"
href="{{ '/axio/organization/environment/create-environment-platform-as-code/' | relative_url }}">

← Create Environment using Platform as Code

</a>

<a
class="nav-button next"
href="{{ '/axio/stack/manual-step/' | relative_url }}">

Create Stack manually →

</a>

</div>
