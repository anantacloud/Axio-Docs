---
layout: default
title: Create Stack from Repository
nav_order: 1
parent: Stack
---

<div class="axio-stack-page">

  <!-- Breadcrumb -->
  <div class="stack-breadcrumb">
    <span>Home</span>
    <span class="breadcrumb-arrow">›</span>
    <span>Stacks</span>
    <span class="breadcrumb-arrow">›</span>
    <span>Create Stack</span>
    <span class="breadcrumb-arrow">›</span>
    <span class="breadcrumb-current">From Repository</span>
  </div>

  <!-- Header -->
  <div class="stack-header-row">
    <div class="stack-page-title">
      <h1>Create Stack from Repository</h1>
      <p>Create a Stack using an existing Axio configuration in your repository.</p>
    </div>

    <div class="axio-yaml-reference">
      <div class="reference-icon">
        <img src="{{ '/assets/icons/file-text.svg' | relative_url }}" alt="File">
      </div>
      <div>
        <h3>axio.yaml Reference</h3>
        <p>Your repository must contain an <strong>axio.yaml</strong> file in the root directory.</p>
        <a href="{{ '/docs/reference/axio-yaml' | relative_url }}">
          View axio.yaml reference
          <span class="external-arrow">↗</span>
        </a>
      </div>
    </div>
  </div>

  <!-- Progress -->
  <div class="stack-progress">
    <div class="progress-step active">
      <div class="progress-number">1</div>
      <div>
        <strong>Connect Repository</strong>
        <span>Select your repository and branch</span>
      </div>
    </div>

    <div class="progress-line"></div>

    <div class="progress-step">
      <div class="progress-number">2</div>
      <div>
        <strong>Validate axio.yaml</strong>
        <span>Axio validates the configuration</span>
      </div>
    </div>

    <div class="progress-line"></div>

    <div class="progress-step">
      <div class="progress-number">3</div>
      <div>
        <strong>Configure Stack</strong>
        <span>Review and configure settings</span>
      </div>
    </div>

    <div class="progress-line"></div>

    <div class="progress-step">
      <div class="progress-number">4</div>
      <div>
        <strong>Review &amp; Create</strong>
        <span>Confirm and create the stack</span>
      </div>
    </div>
  </div>

  <!-- Main content -->
  <div class="stack-content-grid">

    <!-- Connect repository card -->
    <section class="stack-card repository-card">
      <h2>1. Connect Repository</h2>
      <p class="card-description">
        Axio will clone your repository and read the axio.yaml file to configure the Stack.
      </p>

      <div class="form-field">
        <label>Git Provider</label>
        <div class="select-field">
          <span class="github-mark">◉</span>
          <span>GitHub</span>
          <span class="select-chevron">⌄</span>
        </div>
      </div>

      <div class="form-field">
        <label>Repository <span class="required">*</span></label>
        <div class="input-field">
          <span class="input-icon">◌</span>
          <span>anantacloud/pulumi-aws-template</span>
        </div>
        <small>Select the repository that contains the axio.yaml file.</small>
      </div>

      <div class="form-field">
        <label>Branch <span class="required">*</span></label>
        <div class="select-field">
          <span class="branch-icon">⑂</span>
          <span>main</span>
          <span class="select-chevron">⌄</span>
        </div>
        <small>Select the branch where axio.yaml is present.</small>
      </div>

      <div class="repository-success">
        <div class="success-icon">✓</div>
        <div>
          <strong>Axio will look for axio.yaml in the root directory of the repository.</strong>
          <span>Make sure your repository contains a valid axio.yaml file.</span>
        </div>
      </div>

      <div class="button-row">
        <button class="axio-next-button" type="button">
          Next <span>→</span>
        </button>
      </div>
    </section>

    <!-- Information card -->
    <section class="stack-card about-card">
      <h2>About Creating from Repository</h2>
      <p class="card-description">
        Axio uses the axio.yaml file in your repository to automatically configure your Stack.
      </p>

      <div class="repository-info-list">

        <div class="repository-info-item">
          <div class="info-step-icon">
            <img src="{{ '/assets/icons/file-text.svg' | relative_url }}" alt="">
          </div>
          <div>
            <strong>1. axio.yaml Required</strong>
            <p>Your repository must contain a valid axio.yaml file in the root directory.</p>
          </div>
        </div>

        <div class="repository-info-item">
          <div class="info-step-icon">
            <img src="{{ '/assets/icons/download.svg' | relative_url }}" alt="">
          </div>
          <div>
            <strong>2. Repository Cloned</strong>
            <p>Axio clones the repository and reads the axio.yaml configuration.</p>
          </div>
        </div>

        <div class="repository-info-item">
          <div class="info-step-icon">
            <img src="{{ '/assets/icons/shield-check.svg' | relative_url }}" alt="">
          </div>
          <div>
            <strong>3. Configuration Loaded</strong>
            <p>Axio validates and loads the configuration defined in axio.yaml.</p>
          </div>
        </div>

        <div class="repository-info-item">
          <div class="info-step-icon rocket-icon">↗</div>
          <div>
            <strong>4. Stack Created</strong>
            <p>Axio creates the Stack with the loaded configuration.</p>
          </div>
        </div>

      </div>

      <div class="example-info-box">
        <div class="example-info-icon">i</div>
        <div>
          <strong>Example: axio.yaml</strong>
          <p>A sample axio.yaml structure is shown below.</p>
        </div>
      </div>
    </section>

  </div>

  <!-- YAML example -->
  <section class="stack-card yaml-card">
    <h2>Example: axio.yaml</h2>
    <p class="card-description">A sample axio.yaml file might look like this:</p>

    <div class="yaml-content">
      <div class="yaml-code">
        <div class="code-line"><span class="line-number">1</span><span class="yaml-key">stack:</span></div>
        <div class="code-line"><span class="line-number">2</span><span class="yaml-indent">  </span><span class="yaml-key">name:</span> <span class="yaml-value">my-pulumi-stack</span></div>
        <div class="code-line"><span class="line-number">3</span><span class="yaml-indent">  </span><span class="yaml-key">description:</span> <span class="yaml-value">Example Pulumi stack</span></div>
        <div class="code-line"><span class="line-number">4</span><span class="yaml-indent">  </span><span class="yaml-key">tool:</span> <span class="yaml-value">pulumi</span></div>
        <div class="code-line"><span class="line-number">5</span><span class="yaml-indent">  </span><span class="yaml-key">vars:</span></div>
        <div class="code-line"><span class="line-number">6</span><span class="yaml-indent">    </span><span class="yaml-key">aws:</span></div>
        <div class="code-line"><span class="line-number">7</span><span class="yaml-indent">      </span><span class="yaml-key">region:</span> <span class="yaml-value">ap-south-1</span></div>
      </div>

      <div class="yaml-note">
        <div class="yaml-note-icon">💡</div>
        <div>
          <strong>Note</strong>
          <p>You can define variables, backends, and tool-specific settings in axio.yaml.</p>
          <a href="{{ '/docs/reference/axio-yaml' | relative_url }}">
            Learn more in the <strong>axio.yaml reference</strong>
            <span>↗</span>
          </a>
        </div>
      </div>
    </div>
  </section>

</div>
