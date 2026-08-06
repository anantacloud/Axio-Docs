---
layout: default
title: Create Project from UI
parent: Projects
grand_parent: Organization
nav_order: 1
---

<link rel="stylesheet" href="{{ '/assets/css/project-ui.css' | relative_url }}">

# <img src="{{ '/assets/icons/folder.svg' | relative_url }}" class="page-icon" alt="Project"> Create a Project from UI

Follow these simple steps to create a Project using the Axio web interface.

<div class="prerequisite-box">

<div class="prerequisite-header">

<img src="{{ '/assets/icons/info.svg' | relative_url }}" alt="Info">

### Prerequisite

</div>

Ensure that you have permission to create Projects in your Organization before creating a Project.

</div>

---

## Step-by-Step Guide

<div class="step-layout">

<div class="step-left">

<div class="step-item">

<div class="step-circle">1</div>

<div class="step-content">

### Login to Axio

Sign in to the Axio platform using your credentials.

</div>

</div>

<div class="step-item">

<div class="step-circle">2</div>

<div class="step-content">

### Go to Projects

Navigate to:

**Organization → Projects**

</div>

</div>

<div class="step-item">

<div class="step-circle">3</div>

<div class="step-content">

### Click Create Project

Click the **Create Project** button from the Projects page.

</div>

</div>

<div class="step-item">

<div class="step-circle">4</div>

<div class="step-content">

### Fill in Project Details

Provide the required information:

- **Name** *(Unique identifier)*
- **Display Name**
- **Description** *(Optional)*

</div>

</div>

<div class="step-item">

<div class="step-circle">5</div>

<div class="step-content">

### Review and Confirm

Review all the entered information and click **Create**.

</div>

</div>

<div class="step-item">

<div class="step-circle">6</div>

<div class="step-content">

### Project Created

The new Project will appear in the **Projects** page and is now ready to contain Workspaces and Environments.

</div>

</div>

</div>

<div class="step-right">

<div class="project-form">

<div class="form-header">

## Create Project

<span class="close-btn">✕</span>

</div>

<label>

Name *

<input
type="text"
placeholder="e.g. ecommerce">

</label>

<label>

Display Name *

<input
type="text"
placeholder="e.g. Ecommerce Platform">

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

---

<div class="tip-box">

### 💡 Tip

A Project is the top-level resource container in Axio.

Create a Project first before creating Workspaces and Environments.

</div>

---

<div class="page-navigation">

<a
class="nav-button previous"
href="{{ '/docs/organization/projects/' | relative_url }}">

← Projects

</a>

<a
class="nav-button next"
href="{{ '/docs/organization/projects/create-project-platform-as-code/' | relative_url }}">

Create using Platform as Code →

</a>

</div>
