---
layout: default
title: Create Stack Manually
parent: Stacks
nav_order: 2
permalink: /axio/stack/manual-step/
---


<link rel="stylesheet" href="{{ '/assets/css/stack-manual.css' | relative_url }}">

# Create a Stack Manually

Configure a stack step by step in Axio — repository, cloud runtime, state backend, workflow template, variables, secrets, and policy packs — without uploading an `axio.yaml` manifest.

<div class="important-box">
  <div class="important-header">
    <img src="{{ '/assets/icons/triangle-alert.svg' | relative_url }}" alt="Warning">
    <h3>Important</h3>
  </div>

  <p>
    <strong>Manual setup does not read <code>axio.yaml</code>.</strong> The repository step connects Git for your IaC source code only; Axio does not discover or import a stack manifest during manual creation. If your repository already has <code>axio.yaml</code>, use
    <a href="{{ '/axio/stack/from-axio/' | relative_url }}">Create Stack from axio.yaml</a> instead.
  </p>

  <p>
    Your progress is <strong>saved automatically</strong> in the browser on each step. When you return to <strong>Stacks → New Stack → Manual setup</strong>, you can resume the draft or start fresh.
  </p>
</div>

<div class="prerequisite-box">

<div class="prerequisite-header">

<img src="{{ '/assets/icons/info.svg' | relative_url }}" alt="Info">

<h3>Prerequisites</h3>

</div>

<ul>
<li>Permission to create stacks (<strong>Member</strong> or higher with <code>iac:manage</code> in the target project, workspace, or environment scope).</li>
<li>A <strong>Project</strong>, <strong>Team workspace</strong>, and <strong>Environment</strong> where the stack will live (create them inline from the General step if needed).</li>
<li>A Git connection under <strong>Administration → Integrations → Source Control</strong> for the repository that contains your IaC code.</li>
<li>Cloud credentials under <strong>Administration → Integrations → Cloud providers</strong> when deploying to AWS, Azure, GCP, OCI, or DigitalOcean.</li>
<li>At least one <strong>published</strong> workflow template compatible with your chosen IaC engine (and cloud provider, if applicable).</li>
</ul>

</div>

<div class="axio-manual-page">

  <div class="axio-manual-hero">
    <div>
      <div class="axio-manual-eyebrow">STACK CREATION</div>
      <h2>Create Stack with <span>Manual Setup</span></h2>
      <p>
        Go to <strong>Stacks → New Stack</strong> and choose <strong>Manual setup</strong>.
        Walk through eight wizard steps to define scope, repository, runtime, backend, workflow, and policies.
      </p>
    </div>
    <div class="axio-manual-badge">Manual Setup</div>
  </div>

  <div class="axio-manual-info">
    <span class="axio-manual-info-icon">i</span>
    <div>
      <strong>Manual configuration gives you full control over the stack.</strong>
      <p>
        Best when the repository has no <code>axio.yaml</code> yet, or you prefer to configure engine, backend, and workflow in the Axio UI.
      </p>
    </div>
  </div>

  <div class="axio-manual-layout">

    <aside class="axio-manual-steps" aria-label="Manual Stack creation steps">
      <div class="axio-manual-section-title">Steps</div>

      <button class="axio-manual-step active" data-step="1">
        <span class="axio-manual-number">1</span>
        <span>
          <strong>General</strong>
          <small>Project, team workspace, environment, stack name, and description.</small>
        </span>
      </button>

      <button class="axio-manual-step" data-step="2">
        <span class="axio-manual-number">2</span>
        <span>
          <strong>Repository Connect</strong>
          <small>Git connection, repository, ref, and working directory.</small>
        </span>
      </button>

      <button class="axio-manual-step" data-step="3">
        <span class="axio-manual-number">3</span>
        <span>
          <strong>IaC Configuration</strong>
          <small>Cloud provider, credential, region, IaC engine, and version.</small>
        </span>
      </button>

      <button class="axio-manual-step" data-step="4">
        <span class="axio-manual-number">4</span>
        <span>
          <strong>Backend</strong>
          <small>State storage for Terraform and OpenTofu stacks.</small>
        </span>
      </button>

      <button class="axio-manual-step" data-step="5">
        <span class="axio-manual-number">5</span>
        <span>
          <strong>Workflow Template</strong>
          <small>Select a published provisioning workflow.</small>
        </span>
      </button>

      <button class="axio-manual-step" data-step="6">
        <span class="axio-manual-number">6</span>
        <span>
          <strong>Variables &amp; Secrets</strong>
          <small>Stack input variables and secret references.</small>
        </span>
      </button>

      <button class="axio-manual-step" data-step="7">
        <span class="axio-manual-number">7</span>
        <span>
          <strong>Policy Packs</strong>
          <small>Attach optional compliance policy packs.</small>
        </span>
      </button>

      <button class="axio-manual-step" data-step="8">
        <span class="axio-manual-number">8</span>
        <span>
          <strong>Review &amp; Create</strong>
          <small>Review the configuration and create the stack.</small>
        </span>
      </button>
    </aside>

    <section class="axio-manual-card" id="manualWizard">

      <div class="axio-manual-card-header">
        <div>
          <div class="axio-manual-kicker">Create Stack</div>
          <h3>Manual Setup</h3>
        </div>
        <div class="axio-manual-progress">
          <span id="manualProgressBar"></span>
        </div>
      </div>

      <div class="axio-manual-form-step active" data-panel="1">
        <label>Organization</label>
        <input type="text" value="Acme Corp" readonly aria-label="Organization">

        <div class="axio-manual-two" style="margin-top: 1rem;">
          <div>
            <label>Project <em>*</em></label>
            <select>
              <option>Acme Corp</option>
              <option>Demo Project</option>
              <option>Platform Project</option>
            </select>
          </div>
          <div>
            <label>Team workspace <em>*</em></label>
            <select>
              <option>platform-team</option>
              <option>engineering</option>
              <option>devops</option>
            </select>
          </div>
        </div>

        <label>Environment <em>*</em></label>
        <select>
          <option>Development</option>
          <option>Staging</option>
          <option>Production</option>
        </select>

        <label>Stack name <em>*</em></label>
        <input type="text" value="my-app-stack" placeholder="Enter stack name">

        <label class="axio-extra-label">Description</label>
        <textarea rows="3" placeholder="Describe your stack">Stack created manually</textarea>

        <div class="axio-manual-help">
          Stack name must start with a letter and contain only letters, numbers, hyphens, and underscores.
          Use <strong>Create project</strong>, <strong>Create workspace</strong>, or <strong>Create environment</strong> links if hierarchy resources are missing.
        </div>
      </div>

      <div class="axio-manual-form-step" data-panel="2">
        <label>Source control provider <em>*</em></label>
        <select>
          <option>my-github (GitHub)</option>
          <option>acme-gitlab (GitLab)</option>
          <option>acme-bitbucket (Bitbucket)</option>
        </select>

        <label>Repository <em>*</em></label>
        <div class="axio-manual-repo">
          <input type="text" value="acme/my-infra" aria-label="Repository">
          <span>↗</span>
        </div>

        <div class="axio-manual-two">
          <div>
            <label>Ref type</label>
            <select>
              <option>Branch</option>
              <option>Tag</option>
              <option>Commit</option>
            </select>
          </div>
          <div>
            <label>Branch</label>
            <select>
              <option>main</option>
            </select>
          </div>
        </div>

        <label>Repository path <em>*</em></label>
        <input type="text" value="." aria-label="Repository path">

        <div class="axio-manual-help">
          Enter <code>owner/repository</code> (not a full URL). <strong>Repository path</strong> is the working directory for IaC files (use <code>.</code> for the repo root).
          Manual setup does <strong>not</strong> discover <code>axio.yaml</code> from the repository.
        </div>
      </div>

      <div class="axio-manual-form-step" data-panel="3">
        <div class="axio-config-grid">

          <div class="axio-config-box">
            <h4>Cloud</h4>
            <label>Cloud provider <em>*</em></label>
            <select>
              <option>AWS</option>
              <option>Azure</option>
              <option>GCP</option>
              <option>OCI</option>
              <option>DigitalOcean</option>
            </select>

            <label>Cloud credential <em>*</em></label>
            <select>
              <option>acme-aws-prod</option>
              <option>acme-aws-dev</option>
            </select>

            <label>Region <em>*</em></label>
            <input type="text" value="ap-south-1" aria-label="Region">
          </div>

          <div class="axio-config-box">
            <h4>IaC engine</h4>
            <label>Engine <em>*</em></label>
            <select>
              <option>Terraform</option>
              <option>OpenTofu</option>
              <option>Pulumi</option>
              <option>Crossplane</option>
              <option>CloudFormation</option>
              <option>Azure ARM / Bicep</option>
            </select>

            <label>Engine version <em>*</em></label>
            <select>
              <option>1.15.9</option>
              <option>1.9.5</option>
            </select>
          </div>

        </div>

        <div class="axio-manual-help">
          Available cloud providers depend on the selected IaC engine. Provider plugin versions (for example AWS provider for Terraform) may also be required.
        </div>
      </div>

      <div class="axio-manual-form-step" data-panel="4">
        <label>State backend provider</label>
        <select>
          <option>Axio database (default)</option>
          <option>Amazon S3</option>
          <option>Azure Blob Storage</option>
          <option>Google Cloud Storage</option>
          <option>MinIO</option>
        </select>

        <div class="axio-manual-help">
          <strong>Axio database</strong> is the default managed option for Terraform and OpenTofu — state is stored in the platform with an HTTP remote backend URL after creation.
          Pulumi, Crossplane, CloudFormation, and ARM/Bicep use engine-native state management; backend configuration applies to Terraform and OpenTofu only.
        </div>
      </div>

      <div class="axio-manual-form-step" data-panel="5">
        <label>Workflow template <em>*</em></label>
        <select>
          <option>Terraform Standard Deploy</option>
          <option>Terraform Plan &amp; Apply</option>
          <option>OpenTofu Standard Deploy</option>
        </select>

        <div class="axio-manual-help">
          Only <strong>published</strong> templates compatible with your IaC engine (and cloud provider) are shown.
          Axio may recommend a template based on your selections. Browse all templates or open a template link from Administration to pre-fill this step.
        </div>
      </div>

      <div class="axio-manual-form-step" data-panel="6">

        <div class="axio-config-grid">

          <div class="axio-config-box">
            <h4>Variables</h4>
            <div class="axio-variable-row">
              <input value="region" aria-label="Variable name">
              <span>=</span>
              <input value="ap-south-1" aria-label="Variable value">
              <button type="button" class="axio-delete">×</button>
            </div>
            <button type="button" class="axio-add">+ Add Variable</button>
          </div>

          <div class="axio-config-box">
            <h4>Secrets</h4>
            <button type="button" class="axio-add-box">🔒 Add secret reference</button>
            <div class="axio-manual-help" style="margin-top: 0.75rem;">
              Assign saved secrets from Axio — do not store sensitive values in plain variables.
            </div>
          </div>

        </div>

      </div>

      <div class="axio-manual-form-step" data-panel="7">

        <div class="axio-config-box axio-policy">
          <h4>Policy packs</h4>
          <select>
            <option>None (optional)</option>
            <option>AWS Security Policies</option>
            <option>Cost Policies</option>
            <option>Organization Policies</option>
          </select>
        </div>

        <div class="axio-manual-help">
          Policy packs are optional. Attach published packs to run compliance checks during Plan and Apply workflows.
        </div>

      </div>

      <div class="axio-manual-form-step" data-panel="8">

        <div class="axio-manual-review">
          <div><span>Project</span><strong>Acme Corp</strong></div>
          <div><span>Team workspace</span><strong>platform-team</strong></div>
          <div><span>Environment</span><strong>Development</strong></div>
          <div><span>Stack name</span><strong>my-app-stack</strong></div>
          <div><span>Repository</span><strong>acme/my-infra @ main</strong></div>
          <div><span>Repository path</span><strong>.</strong></div>
          <div><span>Cloud</span><strong>AWS · acme-aws-prod · ap-south-1</strong></div>
          <div><span>IaC engine</span><strong>Terraform 1.15.9</strong></div>
          <div><span>Backend</span><strong>Axio database</strong></div>
          <div><span>Workflow template</span><strong>Terraform Standard Deploy</strong></div>
          <div><span>Variables</span><strong>region = ap-south-1</strong></div>
          <div><span>Policy packs</span><strong>None</strong></div>
        </div>

        <div class="axio-manual-help">
          Click any section on the review screen in Axio to jump back and edit that step. Axio validates the full configuration before creation.
        </div>

      </div>

      <div class="axio-manual-actions">
        <button class="axio-manual-btn secondary" id="manualPrev">Back</button>
        <button class="axio-manual-btn primary" id="manualNext">Continue</button>
      </div>

    </section>
  </div>

  <div class="axio-manual-complete" id="manualComplete">
    <span class="axio-manual-check">✓</span>
    <div>
      <strong>You're all set!</strong>
      <span>Your stack is created and appears in the Stacks inventory.</span>
    </div>
  </div>

  <div class="axio-manual-note">
    <div class="axio-manual-note-icon">!</div>
    <div>
      <strong>Review before you create</strong>
      <p>
        Verify repository access, cloud credentials, backend settings, workflow template compatibility,
        variables, secrets, and policy packs on the <strong>Review &amp; Create</strong> step.
        Deployment runs (Plan / Apply / Destroy) require a valid cloud connection when a provider is configured.
      </p>
    </div>
  </div>

  <div class="axio-manual-best">
    <h3>Best Practices</h3>
    <ul>
      <li>Use meaningful stack names and descriptions scoped to the correct project, workspace, and environment.</li>
      <li>Keep sensitive values in <strong>secrets</strong>, not plain variables.</li>
      <li>Start with the <strong>Axio database</strong> backend unless your organization requires a dedicated S3, Azure, or GCS bucket.</li>
      <li>Pick a workflow template that matches your IaC engine and cloud provider.</li>
      <li>Set the repository path to the subdirectory that contains your Terraform, OpenTofu, or Pulumi code.</li>
      <li>If you later add <code>axio.yaml</code> to the repo, use <strong>Sync from repository</strong> on the stack detail page — or recreate via <a href="{{ '/axio/stack/from-axio/' | relative_url }}">From axio.yaml</a> for manifest-driven stacks.</li>
    </ul>
  </div>

</div>

<script>
document.addEventListener("DOMContentLoaded", function () {
  const steps = Array.from(document.querySelectorAll(".axio-manual-step"));
  const panels = Array.from(document.querySelectorAll(".axio-manual-form-step"));
  const next = document.getElementById("manualNext");
  const prev = document.getElementById("manualPrev");
  const progress = document.getElementById("manualProgressBar");
  const complete = document.getElementById("manualComplete");

  const TOTAL_STEPS = 8;
  let current = 1;

  function render(step) {
    current = step;

    steps.forEach((item) => {
      const number = Number(item.dataset.step);
      item.classList.toggle("active", number === current);
      item.classList.toggle("done", number < current);
    });

    panels.forEach((panel) => {
      panel.classList.toggle("active", Number(panel.dataset.panel) === current);
    });

    progress.style.width = ((current - 1) / (TOTAL_STEPS - 1)) * 100 + "%";
    prev.style.visibility = current === 1 ? "hidden" : "visible";
    next.textContent = current === TOTAL_STEPS ? "Create stack" : "Continue";

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

  document.querySelectorAll(".axio-add").forEach((button) => {
    button.addEventListener("click", function () {
      const box = this.closest(".axio-config-box");
      const row = document.createElement("div");
      row.className = "axio-variable-row";
      row.innerHTML =
        '<input placeholder="variable" aria-label="Variable name">' +
        '<span>=</span>' +
        '<input placeholder="value" aria-label="Variable value">' +
        '<button type="button" class="axio-delete">×</button>';
      box.insertBefore(row, this);
      row.querySelector(".axio-delete").addEventListener("click", () => row.remove());
    });
  });

  document.querySelectorAll(".axio-delete").forEach((button) => {
    button.addEventListener("click", function () {
      this.closest(".axio-variable-row").remove();
    });
  });

  render(1);
});
</script>

<div class="page-navigation">

<a
class="nav-button previous"
href="{{ '/axio/stack/from-axio/' | relative_url }}">

← Create Stack from axio.yaml

</a>

<a
class="nav-button next"
href="{{ '/axio/stack/workflow-template/' | relative_url }}">

Workflow Template →

</a>

</div>
