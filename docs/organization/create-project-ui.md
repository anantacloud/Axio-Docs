---
layout: default
title: Create Project from UI
parent: Projects
grand_parent: Organization
nav_order: 1
permalink: /axio/organization/project/create-project-ui/
---

# <img src="{{ '/assets/icons/folder.svg' | relative_url }}" class="page-icon" alt="Project"> Create a Project from UI

Follow these steps to create a Project using the Axio web interface.

<div class="prerequisite-box">

<div class="prerequisite-header">

<img src="{{ '/assets/icons/info.svg' | relative_url }}" alt="Info">

<h3>Prerequisite</h3>

</div>

<p>
Ensure that you have permission to create Projects in your Organization before creating a Project.
</p>

<p><strong>Who can create projects:</strong></p>

<ul>
<li><strong>Owner</strong> and <strong>Admin</strong> — can always create projects (when the Create Project action is available).</li>
<li><strong>Member</strong> — can create projects when granted organization-wide access. Members with <strong>project-, workspace-, or environment-scoped</strong> access only cannot create new projects.</li>
<li><strong>Viewer</strong> and <strong>Unassigned</strong> — cannot create projects.</li>
</ul>

<p>
If you lack permission, the <strong>Create Project</strong> button is disabled and a tooltip explains why. Contact an organization Owner or Admin to assign the appropriate role via <strong>Administration → Roles & Access</strong>.
</p>

</div>

---

## Step-by-Step Guide

<div class="step-layout">

<div class="step-left">

<div class="step-item">

<div class="step-circle-ui">1</div>

<div class="step-content">

<h3>Sign in to Axio</h3>

<p>
Sign in to the Axio platform using your email and password, plus your <strong>Organization ID</strong> — an 8-character code shown on <strong>Organization → Overview</strong>. Use the Organization ID at sign-in, not the organization display name or slug.
</p>

</div>

</div>

<div class="step-item">

<div class="step-circle-ui">2</div>

<div class="step-content">

<h3>Go to Projects</h3>

<p>Navigate to:</p>

<p><strong>Organization → Projects</strong></p>

<p>
If no projects exist yet, you can also click <strong>Create Your First Project</strong> from the empty state on the same page.
</p>

</div>

</div>

<div class="step-item">

<div class="step-circle-ui">3</div>

<div class="step-content">

<h3>Click Create Project</h3>

<p>
Click the <strong>Create Project</strong> button on the Projects page toolbar (or <strong>Create Your First Project</strong> when the list is empty).
</p>

</div>

</div>

<div class="step-item">

<div class="step-circle-ui">4</div>

<div class="step-content">

<h3>Fill in Project Details</h3>

<p>Provide the following information in the Create Project dialog:</p>

<ul>
<li><strong>Name</strong> (required) — A unique display name for the project within your organization. Axio auto-generates an internal slug from the name. Names are compared case-insensitively (<code>ecommerce</code> and <code>Ecommerce</code> cannot both exist).</li>
<li><strong>Description</strong> (optional) — A short summary of the project's purpose.</li>
<li><strong>Sensitive</strong> (optional) — Enable additional protection for production-critical or compliance-bound projects. See <a href="#make-a-project-sensitive">Make a Project Sensitive</a> below. You can also set this later when editing the project.</li>
</ul>

</div>

</div>

<div class="step-item">

<div class="step-circle-ui">5</div>

<div class="step-content">

<h3>Review and Confirm</h3>

<p>
Review the entered information and click <strong>Create</strong> to save the project. Click <strong>Cancel</strong> or the back arrow to close the dialog without saving — no changes are made.
</p>

<p>
While the project is being created, the button shows <strong>Saving…</strong>. If the name already exists or validation fails, an error message appears in the dialog.
</p>

</div>

</div>

<div class="step-item">

<div class="step-circle-ui">6</div>

<div class="step-content">

<h3>Project Created</h3>

<p>
On success, the dialog closes and the new project appears in the <strong>Organization → Projects</strong> list. You are automatically granted access to the project you created.
</p>

<p>
The project is now ready to contain <strong>Workspaces</strong>. Environments are created within workspaces, not directly on the project.
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

<label class="sensitive-field">

<input type="checkbox">

Sensitive

<p class="field-hint">
Sensitive projects cannot be deleted and block destroy deployments for linked stacks.
</p>

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

## Field reference

| Field | Required | Rules |
|-------|:--------:|-------|
| **Name** | Yes | Must not be empty. Must be unique within the organization (case-insensitive). A URL-safe slug is generated automatically. |
| **Description** | No | Free text. Shown on the Projects list and project detail page. |
| **Sensitive** | No | Defaults to off. When enabled, restricts delete, archive, and destroy operations — see below. Requires permission to update the project to change later. |

---

## What Happens Next?

After creating the Project:

- The Project becomes available under **Organization → Projects** and on the project detail page.
- You can add one or more **Workspaces** to the Project.
- Workspaces can contain **Environments**.
- You can mark the Project as **Sensitive** during creation or when editing the project.
- You can **archive the Project** when it is no longer required (see below).
- To change the name, description, or sensitive flag later, open the project row actions and choose **Edit**, or edit from the project detail page.

**Suggested next steps:**

- [Create a Workspace]({{ '/axio/organization/workspace/create-workspace-ui/' | relative_url }}) *(link when published)*
- [Organization overview]({{ '/axio/organization/overview/' | relative_url }})
- [Create Project using Platform as Code]({{ '/axio/organization/project/create-project-platform-as-code/' | relative_url }}) — for Git-managed projects

<div class="resource-grid-info">

<div class="resource-card project" id="make-a-project-sensitive">

    <div class="card-title">

        <img class="project-icon" src="{{ '/assets/icons/folder.svg' | relative_url }}"
             alt="Projects">

        <h3>Make a Project Sensitive</h3>

    </div>

    <p>
        A Project can be marked as <strong>Sensitive</strong> when creating it or when editing it later. Use this for production-critical or compliance-bound projects that must not be accidentally removed or destroyed.
    </p>

    <ul>

        <li>Sensitive Projects cannot be deleted</li>

        <li>Sensitive Projects cannot be archived</li>

        <li>Destroy deployments for linked stacks are blocked</li>

        <li>Infrastructure managed through linked stacks cannot be torn down via destroy deployments while the project remains sensitive</li>

    </ul>

    <p>
        <strong>Who can change it:</strong> Users with permission to update projects (typically Owner, Admin, or an authorized Member).
    </p>

</div>


<div class="resource-card workspace" id="archive-a-project">

    <div class="card-title">

        <img class="workspace-icon" src="{{ '/assets/icons/boxes.svg' | relative_url }}"
             alt="Workspaces">

        <h3>Archive a Project</h3>

    </div>

    <p>
       Archive a Project when it is no longer actively required. Archiving is a soft deactivation — the project is retained for reference but treated as inactive.
    </p>

    <h4>Behavior</h4>

    <ul>

        <li>Archived Projects are retained for reference and can be <strong>unarchived</strong> later</li>

        <li>Archived Projects are not available for ongoing operations</li>

        <li>Sensitive Projects cannot be archived</li>

        <li><strong>System</strong> and <strong>Git-managed</strong> projects (including the auto-provisioned Default Project) cannot be archived from the UI</li>

    </ul>

    <h4>Archive vs delete</h4>

    <ul>
        <li><strong>Archive</strong> — Reversible; project data is kept; workspaces may remain attached</li>
        <li><strong>Delete</strong> — Permanent; requires typed confirmation; the project must contain <strong>no workspaces</strong> and must not be sensitive</li>
    </ul>

    <p>
        <strong>How to archive:</strong> On <strong>Organization → Projects</strong>, open the row actions menu for the project and choose <strong>Archive</strong>. To restore, choose <strong>Unarchive</strong> on an archived project.
    </p>

 </div>

</div>


<div class="tip-box">

    <div class="tip-header">

        <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
             alt="Tip">

        <h3>Default project and unassigning workspaces</h3>

    </div>

    <p>
        Every organization is provisioned with a system <strong>Default Project</strong> (with a Default Workspace and Default Environment). This resource cannot be archived or deleted from the UI.
    </p>

    <p>
        A Workspace can be unassigned from its current Project. When unassigned, the workspace and any environments inside it are moved to the <strong>Default Project</strong>. Git-managed and system workspaces cannot be unassigned.
    </p>

</div>

---

## UI vs Platform as Code

This guide covers **manual creation in the web UI**. To define projects declaratively in Git and reconcile them through Platform as Code, use [Create Project using Platform as Code]({{ '/axio/organization/project/create-project-platform-as-code/' | relative_url }}). Git-managed projects show a <strong>Git-managed</strong> badge in the UI and have limited manual edit rules.

---

## Troubleshooting

| Issue | Cause | What to do |
|-------|--------|------------|
| **Create Project** button disabled | Insufficient role or scoped access | Ask an Owner or Admin to grant organization-wide Member (or higher) access |
| **Name is required** | Empty name field | Enter a non-empty project name |
| **Project name already exists** | Duplicate name in the organization | Choose a different name (names are unique case-insensitively) |
| **Failed to save project** | Network or server error | Retry; contact support if the error persists |
| Cannot archive project | Project is sensitive, system, or Git-managed | Remove sensitive flag (if appropriate), or manage via Platform as Code for Git-managed resources |
| Cannot delete project | Project is sensitive or contains workspaces | Remove or reassign workspaces first; sensitive projects cannot be deleted |

---

<div class="page-navigation">

<a
class="nav-button previous"
href="{{ '/axio/organization/overview/' | relative_url }}">

← Overview

</a>

<a
class="nav-button next"
href="{{ '/axio/organization/project/create-project-platform-as-code/' | relative_url }}">

Create Project using Platform as Code →

</a>

</div>
