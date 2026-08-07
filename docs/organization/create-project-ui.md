---
layout: default
title: Create Project from UI
parent: Projects
grand_parent: Organization
nav_order: 1
---

# <img src="{{ '/assets/icons/folder.svg' | relative_url }}" class="page-icon" alt="Project"> Create a Project from UI

Follow these simple steps to create a Project using the Axio web interface.

<div class="prerequisite-box">

<div class="prerequisite-header">

<img src="{{ '/assets/icons/info.svg' | relative_url }}" alt="Info">

<h3>Prerequisite</h3>

</div>

<p>
Ensure that you have permission to create Projects in your Organization before creating a Project.
</p>

</div>

---

## Step-by-Step Guide

<div class="step-layout">

<div class="step-left">

<div class="step-item">

<div class="step-circle-ui">1</div>

<div class="step-content">

<h3>Login to Axio</h3>

<p>Sign in to the Axio platform using your credentials.</p>

</div>

</div>

<div class="step-item">

<div class="step-circle-ui">2</div>

<div class="step-content">

<h3>Go to Projects</h3>

<p>Navigate to:</p>

<p><strong>Organization → Projects</strong></p>

</div>

</div>

<div class="step-item">

<div class="step-circle-ui">3</div>

<div class="step-content">

<h3>Click Create Project</h3>

<p>Click the <strong>Create Project</strong> button from the Projects page.</p>

</div>

</div>

<div class="step-item">

<div class="step-circle-ui">4</div>

<div class="step-content">

<h3>Fill in Project Details</h3>

<p>Provide the required information:</p>

<ul>
<li><strong>Name</strong> (Unique identifier)</li>
<li><strong>Description</strong> (Optional)</li>
</ul>

</div>

</div>

<div class="step-item">

<div class="step-circle-ui">5</div>

<div class="step-content">

<h3>Review and Confirm</h3>

<p>Review all the entered information and click <strong>Create</strong>.</p>

</div>

</div>

<div class="step-item">

<div class="step-circle-ui">6</div>

<div class="step-content">

<h3>Project Created</h3>

<p>
The new Project will appear in the <strong>Projects</strong> page and is now ready to contain Workspaces and Environments.
</p>

</div>

</div>

</div>

<div class="step-right">

<div class="project-form">

<div class="form-header">

<h2>Create Project</h2>

</div>

<label>

Name *

<input
type="text"
placeholder="e.g. ecommerce">

</label>

<label>

Description

<textarea
placeholder="Enter description (optional)"
rows="4"></textarea>

</label>

<div class="form-actions">

<button class="cancel-btn">

Cancel

</button>

<button class="create-btn">

Create

</button>

</div>

</div>

</div>

</div>

---

## What Happens Next?

After creating the Project:

- The Project becomes available under **Organization → Projects**.
- You can add one or more **Workspaces** to the Project.
- Configure access permissions and policies.
- Create Environments within Workspaces.
- Manage all project resources from a single location.


<div class="tip-box">

    <div class="tip-header">

        <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
             alt="Tip">

        <h3>Tip</h3>

    </div>

<p>
A Project is the top-level resource container in Axio.
</p>

<p>
Create a Project first before creating Workspaces and Environments.
</p>

</div>


<div class="page-navigation">

<a
class="nav-button previous"
href="{{ '/docs/organization/overview/' | relative_url }}">

← Overview

</a>

<a
class="nav-button next"
href="{{ '/docs/organization/create-project-platform-as-code/' | relative_url }}">

Create Projects using Platform as Code →

</a>

</div>
