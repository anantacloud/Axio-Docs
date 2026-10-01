---
layout: default
title: Create Workspace from UI
parent: Workspaces
grand_parent: Organization
nav_order: 1
permalink: /axio/organization/workspace/create-workspace-ui/
---

<link rel="stylesheet" href="{{ '/assets/css/workspace-ui.css' | relative_url }}">


<h1>
    <img src="{{ '/assets/icons/blocks.svg' | relative_url }}"
         class="page-icon"
         alt="Workspace">
    Create a Workspace from UI
</h1>

<p class="page-description">
   Create a Workspace using the Axio web interface. A Workspace belongs to a Project and contains Environments.
</p>

<div class="prerequisite-box">

    <div class="prerequisite-header">

        <img src="{{ '/assets/icons/info.svg' | relative_url }}"
             alt="Info">

        <h3>Prerequisites</h3>

    </div>

    <p>
        Ensure that you have permission to create Workspaces and that at least one <strong>Project</strong> already exists. If no projects exist, create one first under <strong>Organization → Projects</strong>.
    </p>

    <p><strong>Who can create workspaces:</strong></p>

    <ul>
        <li><strong>Owner</strong> and <strong>Admin</strong> — can create workspaces in projects they can manage.</li>
        <li><strong>Member</strong> — can create workspaces when granted <code>workspace:manage</code> and access to the target project. Members who are <strong>Viewers on a specific project</strong> cannot create workspaces in that project.</li>
        <li><strong>Viewer</strong> and <strong>Unassigned</strong> — cannot create workspaces.</li>
    </ul>

    <p>
        Users with <strong>workspace- or environment-scoped</strong> access can view parent projects but cannot create additional workspaces outside their assignment.
    </p>

    <p>
        If you lack permission, the <strong>Create Workspace</strong> button is disabled and a tooltip explains why. Contact an organization Owner or Admin via <strong>Administration → Roles & Access</strong>.
    </p>

</div>

<hr>

<h2>Step-by-Step Guide</h2>

<div class="step-layout">

    <div class="step-left">

        <div class="step-item">

            <div class="step-circle-ui">1</div>

            <div class="step-content">

                <h3>Sign in to Axio</h3>

                <p>
                    Sign in using your email and password, plus your <strong>Organization ID</strong> — an 8-character code shown on <strong>Organization → Overview</strong>. Use the Organization ID at sign-in, not the organization display name or slug.
                </p>

            </div>

        </div>

        <div class="step-item">

            <div class="step-circle-ui">2</div>

            <div class="step-content">

                <h3>Go to Workspaces</h3>

                <p>Navigate to:</p>

                <p><strong>Organization → Workspaces</strong></p>

                <p>
                    You can also open a project detail page and create a workspace directly within that project. From the Projects list, use a project filter link to show only workspaces for one project.
                </p>

            </div>

        </div>

        <div class="step-item">

            <div class="step-circle-ui">3</div>

            <div class="step-content">

                <h3>Click Create Workspace</h3>

                <p>
                    Click <strong>Create Workspace</strong> on the toolbar, or <strong>Create Your First Workspace</strong> when the list is empty.
                </p>

            </div>

        </div>

        <div class="step-item">

            <div class="step-circle-ui">4</div>

            <div class="step-content">

                <h3>Fill in Workspace Details</h3>

                <p>Provide the following in the Create Workspace dialog:</p>

                <ul>
                    <li><strong>Project</strong> (required) — The project this workspace belongs to.</li>
                    <li><strong>Name</strong> (required) — Unique within the selected project. Axio auto-generates an internal slug from the name. Names are compared case-insensitively within the project.</li>
                    <li><strong>Description</strong> (optional) — A short summary of the workspace purpose.</li>
                 
                </ul>

                <p><strong>Note:</strong> The UI uses a single <strong>Name</strong> field (there is no separate display name).</p>

            </div>

        </div>

        <div class="step-item">

            <div class="step-circle-ui">5</div>

            <div class="step-content">

                <h3>Review and Confirm</h3>

                <p>
                    Review the entered information and click <strong>Create</strong>. Click <strong>Cancel</strong> or the back arrow to close the dialog without saving.
                </p>

                <p>
                    While the workspace is being created, the button shows <strong>Saving…</strong>. If the name already exists in the project or validation fails, an error message appears in the dialog.
                </p>

            </div>

        </div>

        <div class="step-item">

            <div class="step-circle-ui">6</div>

            <div class="step-content">

                <h3>Workspace Created</h3>

                <p>
                    On success, the dialog closes and the workspace appears under the selected project on <strong>Organization → Workspaces</strong>. You are automatically granted access to the workspace you created.
                </p>

                <p>
                    The workspace is now ready for creating <strong>Environments</strong>.
                </p>

            </div>

        </div>

    </div>

    <div class="step-right">

        <div class="project-form">

            <div class="form-header">

                <h2>Create Workspace</h2>

            </div>

            <label>

                Project *

                <select>

                    <option>Select Project</option>

                    <option>Ecommerce</option>

                    <option>Payments</option>

                </select>

            </label>

            <label>

                Name *

                <input
                    type="text"
                    placeholder="e.g. development">

            </label>

            <label>

                Description

                <textarea
                    rows="4"
                    placeholder="Enter description (optional)"></textarea>

            </label>

                        <div class="form-actions">

                <button class="cancel-btn">Cancel</button>

                <button class="create-btn">Create</button>

            </div>

        </div>

    </div>

</div>

<hr>

<h2>Field reference</h2>

| Field | Required | Rules |
|-------|:--------:|-------|
| **Project** | Yes | Must select an existing project. Creation is blocked if you lack manage access on that project. |
| **Name** | Yes | Must not be empty. Must be unique within the project (case-insensitive). A URL-safe slug is generated automatically. |
| **Description** | No | Free text shown on the Workspaces list and workspace detail page. |
| **Sensitive** | No | Defaults to off. When enabled, restricts delete, archive, and destroy operations — see below. |

<hr>

<h2>What Happens Next?</h2>

<p>After creating the Workspace:</p>

<ul>
    <li>The Workspace becomes available under the selected Project on <strong>Organization → Workspaces</strong>.</li>
    <li>You can create one or more <strong>Environments</strong> within the Workspace.</li>
    <li>You can mark the Workspace as <strong>Sensitive</strong> during creation or when editing it later.</li>
    <li>You can <strong>archive</strong> the Workspace when it is no longer required (see below).</li>
    <li>You can <strong>reassign</strong> the Workspace to another project when editing it, or <strong>unassign</strong> it to move it to the system Default Project (edit flow only).</li>
</ul>

<div class="resource-grid-info">

<div class="resource-card workspace" id="sensitive-workspaces">

    <div class="card-title">

        <img class="workspace-icon" src="{{ '/assets/icons/boxes.svg' | relative_url }}"
             alt="Sensitive">

        <h3>Sensitive workspaces</h3>

    </div>

    <p>
        A Workspace can be marked as <strong>Sensitive</strong> when creating it or when editing it later.
    </p>

    <ul>
        <li>Sensitive workspaces cannot be deleted</li>
        <li>Sensitive workspaces cannot be archived</li>
        <li>Destroy deployments for linked stacks are blocked</li>
    </ul>

</div>

<div class="resource-card-workspace project">

    <div class="card-title">

        <img class="project-icon" src="{{ '/assets/icons/folder.svg' | relative_url }}"
             alt="Archive">

        <h3>Archive a workspace</h3>

    </div>

    <p>
        Archive a workspace when it is no longer actively required. Archiving is a reversible soft deactivation.
    </p>

    <ul>
        <li>Archived workspaces are retained for reference and can be <strong>unarchived</strong></li>
        <li>Sensitive workspaces cannot be archived</li>
        <li><strong>System</strong> and <strong>Git-managed</strong> workspaces cannot be archived from the UI</li>
        <li><strong>Delete</strong> is permanent and requires the workspace to contain <strong>no environments</strong></li>
    </ul>

    <p>
        <strong>How to archive:</strong> On <strong>Organization → Workspaces</strong>, open the row actions menu and choose <strong>Archive</strong>.
    </p>

</div>

</div>

<div class="tip-box">

    <div class="tip-header">

        <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
             alt="Tip">

        <h3>Unassigning a workspace from a project</h3>

    </div>

    <p>
        When <strong>editing</strong> a workspace, you can click <strong>Unassign from project</strong> to move the workspace (and its environments) to the system <strong>Default Project</strong>.
    </p>

    <p>
        System workspaces, Git-managed workspaces, and workspaces already on the Default Project cannot be unassigned.
    </p>

</div>

<div class="page-navigation">

    <a class="nav-button previous"
        href="{{ '/axio/organization/project/create-project-platform-as-code/' | relative_url }}">
        ← Create Project using Platform as Code
    </a>

    <a class="nav-button next"
        href="{{ '/axio/organization/workspace/create-workspace-platform-as-code/' | relative_url }}">
        Create Workspace using Platform as Code →
    </a>

</div>
