---
layout: default
title: Create Stack Manually
parent: Stacks
nav_order: 2
---

# Create a Stack Manually

Create a Stack by providing the Stack configuration directly in Axio instead of using an `axio.yaml` file from a repository.

<div class="axio-manual-page">

  <div class="axio-manual-hero">
    <div>
      <div class="axio-manual-eyebrow">STACK CREATION</div>
      <h2>Create Stack from <span>Manual Steps</span></h2>
      <p>
        Create a Stack by manually providing the project, workspace, environment,
        repository, AWS credentials, IaC configuration, backend, workflow template,
        variables, secrets, and policy packs.
      </p>
    </div>
    <div class="axio-manual-badge">Manual Setup</div>
  </div>

  <div class="axio-manual-info">
    <span class="axio-manual-info-icon">i</span>
    <div>
      <strong>Manual configuration gives you full control over the Stack.</strong>
      <p>
        Configure the required infrastructure and workflow settings directly in Axio.
      </p>
    </div>
  </div>

  <div class="axio-manual-layout">

    <aside class="axio-manual-steps" aria-label="Manual Stack creation steps">
      <div class="axio-manual-section-title">Steps</div>

      <button class="axio-manual-step active" data-step="1">
        <span class="axio-manual-number">1</span>
        <span>
          <strong>Choose Project</strong>
          <small>Select the project under which you want to create the Stack.</small>
        </span>
      </button>

      <button class="axio-manual-step" data-step="2">
        <span class="axio-manual-number">2</span>
        <span>
          <strong>Select Workspace</strong>
          <small>Choose the workspace for your Stack.</small>
        </span>
      </button>

      <button class="axio-manual-step" data-step="3">
        <span class="axio-manual-number">3</span>
        <span>
          <strong>Select Environment</strong>
          <small>Choose the environment, such as Dev, Staging, or Prod.</small>
        </span>
      </button>

      <button class="axio-manual-step" data-step="4">
        <span class="axio-manual-number">4</span>
        <span>
          <strong>Enter Stack Name</strong>
          <small>Provide a unique name for your Stack.</small>
        </span>
      </button>

      <button class="axio-manual-step" data-step="5">
        <span class="axio-manual-number">5</span>
        <span>
          <strong>Select Repository</strong>
          <small>Select the repository and choose a branch, tag, or commit.</small>
        </span>
      </button>

      <button class="axio-manual-step" data-step="6">
        <span class="axio-manual-number">6</span>
        <span>
          <strong>Provide AWS Credentials</strong>
          <small>Select or add AWS credentials used to deploy the Stack.</small>
        </span>
      </button>

      <button class="axio-manual-step" data-step="7">
        <span class="axio-manual-number">7</span>
        <span>
          <strong>Configure Stack</strong>
          <small>Configure IaC, backend, workflow, variables, secrets, and policy packs.</small>
        </span>
      </button>

      <button class="axio-manual-step" data-step="8">
        <span class="axio-manual-number">8</span>
        <span>
          <strong>Review &amp; Create</strong>
          <small>Review the configuration and create the Stack.</small>
        </span>
      </button>
    </aside>

    <section class="axio-manual-card" id="manualWizard">

      <div class="axio-manual-card-header">
        <div>
          <div class="axio-manual-kicker">Create Stack</div>
          <h3>Manual Steps</h3>
        </div>
        <div class="axio-manual-progress">
          <span id="manualProgressBar"></span>
        </div>
      </div>

      <div class="axio-manual-form-step active" data-panel="1">
        <label>Project <em>*</em></label>
        <select>
          <option>Acme Corp</option>
          <option>Demo Project</option>
          <option>Platform Project</option>
        </select>
        <div class="axio-manual-help">Select the project where the Stack should be created.</div>
      </div>

      <div class="axio-manual-form-step" data-panel="2">
        <label>Workspace <em>*</em></label>
        <select>
          <option>platform-team</option>
          <option>engineering</option>
          <option>devops</option>
        </select>
        <div class="axio-manual-help">Choose the workspace that will manage this Stack.</div>
      </div>

      <div class="axio-manual-form-step" data-panel="3">
        <label>Environment <em>*</em></label>
        <select>
          <option>Development</option>
          <option>Staging</option>
          <option>Production</option>
        </select>
        <div class="axio-manual-help">Choose the environment for this Stack.</div>
      </div>

      <div class="axio-manual-form-step" data-panel="4">
        <label>Stack Name <em>*</em></label>
        <input type="text" value="my-app-stack" placeholder="Enter Stack name">

        <label class="axio-extra-label">Description</label>
        <textarea rows="3" placeholder="Describe your Stack">Stack created manually</textarea>

        <div class="axio-manual-help">Use a meaningful Stack name and description.</div>
      </div>

      <div class="axio-manual-form-step" data-panel="5">
        <label>Repository <em>*</em></label>
        <div class="axio-manual-repo">
          <input type="text" value="github.com/acme/my-infra">
          <span>↗</span>
        </div>

        <div class="axio-manual-two">
          <div>
            <label>Source</label>
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
      </div>

      <div class="axio-manual-form-step" data-panel="6">
        <label>AWS Credentials <em>*</em></label>
        <select>
          <option>acme-aws-prod</option>
          <option>acme-aws-dev</option>
          <option>Add new credentials...</option>
        </select>

        <div class="axio-manual-help">
          Select or add the AWS credentials that will be used to deploy the Stack.
        </div>
      </div>

      <div class="axio-manual-form-step" data-panel="7">

        <div class="axio-config-grid">

          <div class="axio-config-box">
            <h4>IaC Configuration</h4>
            <label>Tool <em>*</em></label>
            <select>
              <option>Terraform</option>
              <option>Pulumi</option>
              <option>OpenTofu</option>
            </select>
          </div>

          <div class="axio-config-box">
            <h4>Backend</h4>
            <label>Backend</label>
            <select>
              <option>S3</option>
              <option>Azure Storage</option>
              <option>GCS</option>
            </select>
          </div>

          <div class="axio-config-box">
            <h4>Workflow Template</h4>
            <label>Template</label>
            <select>
              <option>Terraform Default</option>
              <option>Terraform Plan & Apply</option>
              <option>Custom Workflow</option>
            </select>
          </div>

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
            <button type="button" class="axio-add-box">🔒 Add Secrets</button>
          </div>

          <div class="axio-config-box axio-policy">
            <h4>Policy Packs</h4>
            <select>
              <option>Select Policy Packs</option>
              <option>AWS Security Policies</option>
              <option>Cost Policies</option>
              <option>Organization Policies</option>
            </select>
          </div>

        </div>

      </div>

      <div class="axio-manual-form-step" data-panel="8">

        <div class="axio-manual-review">
          <div><span>Project</span><strong>Acme Corp</strong></div>
          <div><span>Workspace</span><strong>platform-team</strong></div>
          <div><span>Environment</span><strong>Development</strong></div>
          <div><span>Stack Name</span><strong>my-app-stack</strong></div>
          <div><span>Repository</span><strong>github.com/acme/my-infra</strong></div>
          <div><span>AWS Credentials</span><strong>acme-aws-prod</strong></div>
          <div><span>IaC Configuration</span><strong>Terraform</strong></div>
          <div><span>Backend</span><strong>S3</strong></div>
          <div><span>Workflow Template</span><strong>Terraform Default</strong></div>
          <div><span>Variables</span><strong>region = ap-south-1</strong></div>
          <div><span>Secrets</span><strong>Configured</strong></div>
          <div><span>Policy Packs</span><strong>Selected</strong></div>
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
      <span>Your Stack will be created with the provided manual configuration.</span>
    </div>
  </div>

  <div class="axio-manual-note">
    <div class="axio-manual-note-icon">!</div>
    <div>
      <strong>Review your configuration</strong>
      <p>
        Verify the repository, credentials, IaC configuration, backend,
        workflow template, variables, secrets, and policy packs before creating the Stack.
      </p>
    </div>
  </div>

  <div class="axio-manual-best">
    <h3>Best Practices</h3>
    <ul>
      <li>Use meaningful Stack names and descriptions.</li>
      <li>Keep sensitive values in secrets instead of plain variables.</li>
      <li>Select the appropriate backend for your infrastructure state.</li>
      <li>Review policy packs before creating the Stack.</li>
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

    progress.style.width = ((current - 1) / 7) * 100 + "%";
    prev.style.visibility = current === 1 ? "hidden" : "visible";
    next.textContent = current === 8 ? "Create Stack" : "Continue";

    if (current < 8) {
      complete.classList.remove("show");
    }
  }

  steps.forEach((step) => {
    step.addEventListener("click", function () {
      render(Number(this.dataset.step));
    });
  });

  next.addEventListener("click", function () {
    if (current < 8) {
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
href="{{ '/docs/stack/from-axio/' | relative_url }}">

← Create Stack from axio.yaml

</a>

<a
class="nav-button next"
href="{{ '/docs/stack/workflow-template/' | relative_url }}">

Workflow Template →

</a>

</div>
