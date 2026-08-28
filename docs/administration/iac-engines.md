---
layout: default
title: IaC Engines
parent: Administration
nav_order: 10
---

<div class="iac-engines-page">

  <main class="iac-main">

    <header class="iac-hero">
      <h1>Administration — IaC Engines</h1>
      <p>Manage infrastructure-as-code engines, versions and runtime images for your organization.</p>
    </header>

    <div class="iac-info">
      <span class="info-icon">i</span>
      <span>Overview: <code>ADMINISTRATION.md</code></span>
      <b>•</b>
      <span>Workflow templates: <code>WORKFLOW_UX.md</code></span>
      <b>•</b>
      <span>Template YAML: <code>WORKFLOW_TEMPLATE_YAML.md</code></span>
    </div>

    <section class="iac-shell">

      <div class="iac-tabs">
        <button class="active">▣ &nbsp; Directory</button>
        <button>◷ &nbsp; Versions</button>
        <button>▣ &nbsp; Runtime images</button>
        <button>♮ &nbsp; Insights</button>
      </div>

      <div class="iac-stats">
        <div class="stat-card">
          <div class="stat-icon purple">◇</div>
          <div><span>Total engines</span><strong>6</strong><small>Supported IaC engines</small></div>
        </div>
        <div class="stat-card">
          <div class="stat-icon green">✓</div>
          <div><span>Healthy</span><strong>5</strong><small>Engines ready to use</small></div>
        </div>
        <div class="stat-card">
          <div class="stat-icon orange">!</div>
          <div><span>Needs attention</span><strong>1</strong><small>Requires action (deprecated)</small></div>
        </div>
        <div class="stat-card">
          <div class="stat-icon blue">▱</div>
          <div><span>Stacks using engines</span><strong>42</strong><small>Across all projects</small></div>
        </div>
      </div>

      <div class="iac-section-heading">
        <div>
          <h2>Supported IaC engines</h2>
          <p>Configure and manage engines for your organization.</p>
        </div>
        <div class="iac-heading-actions">
          <div class="engine-search">⌕ <span>Search engines...</span></div>
          <button class="primary">＋ &nbsp; Add engine</button>
        </div>
      </div>

      <div class="engine-grid">

        <article class="engine-card">
          <div class="engine-head">
            <div class="engine-logo terraform">◆</div>
            <div><h3>Terraform <code>terraform</code></h3><span class="status active">• Active</span></div>
            <b>⋮</b>
          </div>
          <p>HashiCorp Terraform for multi-cloud infrastructure.</p>
          <div class="engine-meta"><span>12 stacks</span><span>8 versions</span><span>Default: 1.7.5</span></div>
        </article>

        <article class="engine-card">
          <div class="engine-head">
            <div class="engine-logo opentofu">◆</div>
            <div><h3>OpenTofu <code>opentofu</code></h3><span class="status active">• Active</span></div>
            <b>⋮</b>
          </div>
          <p>OpenTofu, the open source Terraform alternative.</p>
          <div class="engine-meta"><span>10 stacks</span><span>6 versions</span><span>Default: 1.6.4</span></div>
        </article>

        <article class="engine-card">
          <div class="engine-head">
            <div class="engine-logo pulumi">●</div>
            <div><h3>Pulumi <code>pulumi</code></h3><span class="status active">• Active</span></div>
            <b>⋮</b>
          </div>
          <p>Pulumi for multi-language infrastructure.</p>
          <div class="engine-meta"><span>8 stacks</span><span>5 versions</span><span>Default: 3.112.0</span></div>
        </article>

        <article class="engine-card">
          <div class="engine-head">
            <div class="engine-logo crossplane">☁</div>
            <div><h3>Crossplane <code>crossplane</code></h3><span class="status active">• Active</span></div>
            <b>⋮</b>
          </div>
          <p>Kubernetes control plane for cloud resources.</p>
          <div class="engine-meta"><span>6 stacks</span><span>4 versions</span><span>Default: 1.15.0</span></div>
        </article>

        <article class="engine-card">
          <div class="engine-head">
            <div class="engine-logo cloudformation">▣</div>
            <div><h3>CloudFormation <code>cloudformation</code></h3><span class="status active">• Active</span></div>
            <b>⋮</b>
          </div>
          <p>AWS CloudFormation templates.</p>
          <div class="engine-meta"><span>4 stacks</span><span>4 versions</span><span>Default: 2023-10-01</span></div>
        </article>

        <article class="engine-card">
          <div class="engine-head">
            <div class="engine-logo bicep">&lt;&gt;</div>
            <div><h3>ARM / Bicep <code>arm-bicep</code></h3><span class="status deprecated">Deprecated</span></div>
            <b>⋮</b>
          </div>
          <p>Azure ARM and Bicep templates.</p>
          <div class="engine-meta"><span>2 stacks</span><span>3 versions</span><span>Default: 0.25.0</span></div>
        </article>

      </div>

      <div class="iac-bottom-grid">
        <div class="lifecycle-card">
          <div class="bottom-icon">♢</div>
          <div>
            <h3>Version lifecycle</h3>
            <ul>
              <li><b>Supported:</b> Recommended for production use</li>
              <li><b>LTS:</b> Long term support with security updates</li>
              <li><b>Deprecated:</b> Available but not recommended</li>
              <li><b>Default:</b> Version used for new stacks</li>
            </ul>
          </div>
        </div>

        <div class="runtime-card">
          <div class="bottom-icon">◇</div>
          <div>
            <h3>Runtime images</h3>
            <p>Runners use pre-built images with the configured engine versions for plan and apply operations.</p>
            <button>Manage runtime images &nbsp; →</button>
          </div>
        </div>
      </div>

    </section>
  </main>
</div>
