---
layout: default
title: Create Project using Platform as Code
parent: Projects
grand_parent: Organization
nav_order: 2
---

# <img src="{{ '/assets/icons/code.svg' | relative_url }}" class="page-icon" alt="Platform as Code"> Create a Project using Platform as Code

Define a Project in a YAML or JSON file and synchronize it from your Git repository.

<div class="prerequisite-box">

<div class="prerequisite-header">

<img src="{{ '/assets/icons/triangle-alert.svg' | relative_url }}" alt="Warning">

<h3>Important</h3>

</div>

<p>

Ensure that your Git repository is connected and synchronized with Axio before proceeding.

</p>

</div>

---

## Step-by-Step Guide

<div class="step-layout">

<div class="step-left">

<div class="step-item">

<div class="step-circle">1</div>

<div class="step-content">

<h3>Define Project</h3>

<p>

Create a YAML or JSON file containing the Project definition.

</p>

</div>

</div>

<div class="step-item">

<div class="step-circle">2</div>

<div class="step-content">

<h3>Commit and Push</h3>

<p>

Commit the Project definition file and push it to your Git repository.

</p>

</div>

</div>

<div class="step-item">

<div class="step-circle">3</div>

<div class="step-content">

<h3>Platform Sync</h3>

<p>

The Axio platform automatically synchronizes with your repository and reads the Project definition.

</p>

</div>

</div>

<div class="step-item">

<div class="step-circle">4</div>

<div class="step-content">

<h3>Project Created</h3>

<p>

The Project will appear in the <strong>Projects</strong> page and is ready for creating Workspaces.

</p>

</div>

</div>

</div>

<div class="step-right">

<div class="project-form">

<div class="form-header">

<h2>YAML</h2>

<button class="cancel-btn">Copy</button>

</div>

<pre><code>apiVersion: platform.axio.io/v1
kind: Project

metadata:
  name: ecommerce

spec:
  displayName: Ecommerce Project
  description: Project for ecommerce services
</code></pre>

<hr>

<h3>Repository Structure</h3>

<pre><code>platform-resources/
└── projects/
    ├── ecommerce.yaml
    ├── payments.yaml
    └── README.md
</code></pre>

</div>

</div>

</div>

---

## What Happens Next?

After synchronizing the Project:

- The Project is automatically created in Axio.
- The Project appears under **Organization → Projects**.
- Changes committed to Git automatically update the Project.
- You can begin creating Workspaces inside the Project.
- Your Git repository remains the single source of truth.

---

<div class="tip-box">

<div class="tip-header">

<img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}" alt="Tip">

<h3>Tip</h3>

</div>

<p>

Store Project definitions in a dedicated Git repository to enable version control, code reviews, and GitOps workflows.

</p>

</div>

---

<div class="page-navigation">

<a
class="nav-button previous"
href="{{ '/docs/organization/create-project-ui/' | relative_url }}">

← Create Project from UI

</a>

<a
class="nav-button next"
href="{{ '/docs/organization/workspaces/' | relative_url }}">

Workspaces →

</a>

</div>
