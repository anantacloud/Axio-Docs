---
layout: default
title: Create Stack from axio.yaml
parent: Stacks
nav_order: 1
---

# Create a Stack from `axio.yaml`

Create a Stack from an existing repository that contains a valid `axio.yaml` file in the **root directory** of the repository.

<div class="axio-page">

  <div class="axio-hero">
    <div>
      <div class="axio-eyebrow">STACK CREATION</div>
      <h2>Create Stack from <span>axio.yaml</span></h2>
      <p>
        Create a Stack by selecting a repository that contains an
        <code>axio.yaml</code> file. Axio reads the configuration and uses it
        to configure the Stack automatically.
      </p>
    </div>
    <div class="axio-badge">Recommended</div>
  </div>

  <div class="axio-info">
    <span class="axio-info-icon">i</span>
    <div>
      <strong>The axio.yaml file defines your infrastructure configuration and workflow.</strong>
      <p>
        Make sure the file exists in the root of the selected repository before creating the Stack.
      </p>
    </div>
  </div>

  <div class="axio-layout">

    <aside class="axio-steps" aria-label="Stack creation steps">
      <div class="axio-section-title">Steps</div>

      <button class="axio-step active" data-step="1">
        <span class="axio-step-number">1</span>
        <span>
          <strong>Choose Project</strong>
          <small>Select the project under which you want to create the Stack.</small>
        </span>
      </button>

      <button class="axio-step" data-step="2">
        <span class="axio-step-number">2</span>
        <span>
          <strong>Select Workspace</strong>
          <small>Choose the workspace for your Stack.</small>
        </span>
      </button>

      <button class="axio-step" data-step="3">
        <span class="axio-step-number">3</span>
        <span>
          <strong>Select Environment</strong>
          <small>Choose the environment, such as Dev, Staging, or Prod.</small>
        </span>
      </button>

      <button class="axio-step" data-step="4">
        <span class="axio-step-number">4</span>
        <span>
          <strong>Enter Stack Name</strong>
          <small>Provide a unique name for your Stack.</small>
        </span>
      </button>

      <button class="axio-step" data-step="5">
        <span class="axio-step-number">5</span>
        <span>
          <strong>Select Repository</strong>
          <small>Choose a repository containing <code>axio.yaml</code>, then select a branch, tag, or commit.</small>
        </span>
      </button>

      <button class="axio-step" data-step="6">
        <span class="axio-step-number">6</span>
        <span>
          <strong>Provide AWS Credentials</strong>
          <small>Select or add AWS credentials that will be used to deploy the Stack.</small>
        </span>
      </button>

      <button class="axio-step" data-step="7">
        <span class="axio-step-number">7</span>
        <span>
          <strong>Review &amp; Create</strong>
          <small>Review the details and click <strong>Create Stack</strong> to get started.</small>
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
        <label>Project <em>*</em></label>
        <select>
          <option>Acme Corp</option>
          <option>Demo Project</option>
          <option>Platform Project</option>
        </select>

        <div class="axio-step-help">
          The selected project determines where the Stack will be created.
        </div>
      </div>

      <div class="axio-form-step" data-panel="2">
        <label>Workspace <em>*</em></label>
        <select>
          <option>platform-team</option>
          <option>engineering</option>
          <option>devops</option>
        </select>

        <div class="axio-step-help">
          Select the workspace that should own and manage this Stack.
        </div>
      </div>

      <div class="axio-form-step" data-panel="3">
        <label>Environment <em>*</em></label>
        <select>
          <option>Development</option>
          <option>Staging</option>
          <option>Production</option>
        </select>

        <div class="axio-step-help">
          Choose the environment in which the Stack will be managed.
        </div>
      </div>

      <div class="axio-form-step" data-panel="4">
        <label>Stack Name <em>*</em></label>
        <input type="text" value="my-app-stack" placeholder="Enter Stack name">

        <div class="axio-step-help">
          Use a meaningful and unique name for the Stack.
        </div>
      </div>

      <div class="axio-form-step" data-panel="5">
        <label>Repository <em>*</em></label>
        <div class="axio-input-with-icon">
          <input type="text" value="github.com/acme/my-infra" aria-label="Repository">
          <span>↗</span>
        </div>

        <div class="axio-two-columns">
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

        <div class="axio-found">
          <span>✓</span>
          <div>
            <strong>axio.yaml found</strong>
            <small>Configuration loaded successfully from the repository.</small>
          </div>
        </div>
      </div>

      <div class="axio-form-step" data-panel="6">
        <label>AWS Credentials <em>*</em></label>
        <select>
          <option>acme-aws-prod</option>
          <option>acme-aws-dev</option>
          <option>Add new credentials...</option>
        </select>

        <div class="axio-step-help">
          These credentials are used by the Stack workflow to access AWS resources.
        </div>
      </div>

      <div class="axio-form-step" data-panel="7">
        <div class="axio-review">
          <div><span>Project</span><strong>Acme Corp</strong></div>
          <div><span>Workspace</span><strong>platform-team</strong></div>
          <div><span>Environment</span><strong>Development</strong></div>
          <div><span>Stack Name</span><strong>my-app-stack</strong></div>
          <div><span>Repository</span><strong>github.com/acme/my-infra</strong></div>
          <div><span>AWS Credentials</span><strong>acme-aws-prod</strong></div>
        </div>

        <div class="axio-auto">
          <span>✓</span>
          <div>
            <strong>Axio will automatically configure the Stack</strong>
            <small>The configuration is loaded from the valid <code>axio.yaml</code> file.</small>
          </div>
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
      <span>Your Stack will be created and ready to run.</span>
    </div>
  </div>

  <div class="axio-reference">
    <div class="axio-reference-icon">&lt;/&gt;</div>
    <div>
      <strong>Repository requirement</strong>
      <p>
        Your repository must contain a valid <code>axio.yaml</code> file in the root directory.
      </p>
    </div>
    <a href="#">View axio.yaml reference ↗</a>
  </div>

  <div class="axio-best-practices">
    <h3>Best Practices</h3>
    <ul>
      <li>Keep <code>axio.yaml</code> in the root of your repository.</li>
      <li>Use meaningful Stack names and descriptions.</li>
      <li>Store sensitive values securely using Axio credentials or secrets.</li>
      <li>Review the configuration before creating the Stack.</li>
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

    progress.style.width = ((current - 1) / 6) * 100 + "%";
    prev.style.visibility = current === 1 ? "hidden" : "visible";
    next.textContent = current === 7 ? "Create Stack" : "Continue";

    if (current < 7) {
      complete.classList.remove("show");
    }
  }

  steps.forEach((step) => {
    step.addEventListener("click", function () {
      render(Number(this.dataset.step));
    });
  });

  next.addEventListener("click", function () {
    if (current < 7) {
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

