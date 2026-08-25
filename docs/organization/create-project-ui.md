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
  The new Project is now ready to contain Workspaces. Environments are created within Workspaces.
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
- Workspaces can contain **Environments**.
- You can mark the Project as **Sensitive** when additional protection is required.
- You can **archive the Project** when it is no longer required.


<div class="resource-grid-info">

<div class="resource-card project">

    <div class="card-title">

        <img class="project-icon" src="{{ '/assets/icons/folder.svg' | relative_url }}"
             alt="Projects">

        <h3>Make a Project Sensitive</h3>

    </div>

    <p>
        A Project can be marked as sensitive to provide additional protection.
    </p>

    <ul>

        <li>Sensitive Projects cannot be deleted</li>

        <li>Sensitive Projects cannot be archived</li>

        <li>Destroy deployments for linked stack are blocked</li>

        <li>Resources created by linked stacks cannot be destroyed through destroy deployments</li>

    </ul>

</div>


<div class="resource-card workspace">

    <div class="card-title">

        <img class="workspace-icon" src="{{ '/assets/icons/boxes.svg' | relative_url }}"
             alt="Workspaces">

        <h3>Archive a Project</h3>

    </div>

    <p>
       Archive a Project when it is no longer actively required.
    </p>

    <h4>Features</h4>

    <ul>

        <li>Archived Projects are retained for reference</li>

        <li>Archive Projects are not available for ongoing operations</li>

        <li>Sensitive Projects cannot be archived</li>

    </ul>

 </div>

</div>


<div class="tip-box">

    <div class="tip-header">

        <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
             alt="Tip">

        <h3>Unassigning a Workspace from a Project</h3>

    </div>

    <p>
        A Workspace can be unassigned from its current Project. When a Workspace is unassigned, the Workspace and any Environment associated with it are         moved to the default project.
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

Create Project using Platform as Code →

</a>

</div>
