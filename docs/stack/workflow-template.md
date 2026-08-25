---
layout: default
title: Workflow Template
parent: Stacks
nav_order: 3
has_children: true
has_toc: false
---

# Workflow Templates

Workflow Templates define reusable deployment workflows for Axio stacks. They specify the IaC engines, operations, pipeline stages, approvals, policy checks, security checks, and notifications that should be executed during a deployment.

Axio supports two YAML formats for Workflow Templates.

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
      Steps-based YAML format used for Git-backed platform templates,
      Admin catalog import, and catalog import.
    </p>

    <ul>
      <li>Human-readable and easy to version</li>
      <li>Ordered pipeline with sequential/parallel steps</li>
      <li>Recommended for most use cases</li>
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
      Visual graph (nodes &amp; edges) converted to
      steps automatically.
    </p>

    <ul>
      <li>Graph-based workflow design</li>
      <li>Automatic conversion to executable steps</li>
      <li>Ideal for complex workflow visualisation</li>
    </ul>

  </div>

</div>


## What's on this page?

This section provides a high-level overview of Workflow Templates and how they are used in Axio.

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
      Understand the two supported YAML formats.
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

    <h4>Git Auto-Loading</h4>

    <p>
      Learn how templates are loaded from Git and repositories.
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
      See how to reference templates in your axio.yaml file.
    </p>

  </div>


  <div class="workflow-capability-card workflow-capability-purple">

    <div class="workflow-capability-icon">
      <svg viewBox="0 0 24 24" aria-hidden="true">
        <path d="M12 3l7 3v5c0 4.5-3 8-7 10-4-2-7-5.5-7-10V6z"/>
        <path d="M9 12l2 2 4-4"/>
      </svg>
    </div>

    <h4>Validation</h4>

    <p>
      Learn the validation rules and governance checks.
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
      Export published templates as YAML for reuse.
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
      If you are new to Workflow Templates, we recommend starting
      with the Deployment Template Format.
    </p>

</div>

  <a href="{{ '/docs/stack/built-in/' | relative_url }}"
     class="workflow-start-button">
    Next: Built-In Template
    <span>→</span>
  </a>

</div>



