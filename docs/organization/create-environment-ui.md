---
layout: default
title: Create Environment from UI
parent: Environments
grand_parent: Organization
nav_order: 1
permalink: /axio/organization/environment/create-environment-ui/
---

<h1>
    <img src="{{ '/assets/icons/layers.svg' | relative_url }}"
         class="page-icon"
         alt="Environment">
    Create an Environment from UI
</h1>

<p class="page-description">
Create an Environment using the Axio web interface. An Environment belongs to a Workspace and serves as a deployment target for infrastructure stacks.
</p>

<div class="prerequisite-box">

    <div class="prerequisite-header">

        <img src="{{ '/assets/icons/info.svg' | relative_url }}"
             alt="Info">

        <h3>Prerequisites</h3>

    </div>

    <p>
        Ensure that you have permission to create Environments and that at least one <strong>Workspace</strong> already exists. If no workspaces exist, create one first under <strong>Organization → Workspaces</strong>.
    </p>

    <p><strong>Who can create environments:</strong></p>

    <ul>
        <li><strong>Owner</strong> and <strong>Admin</strong> — can create environments in workspaces they can manage.</li>
        <li><strong>Member</strong> — can create environments when granted <code>environment:manage</code> and manage access on the target workspace. Members who are <strong>Viewers on a specific workspace</strong> cannot create environments there.</li>
        <li><strong>Viewer</strong> and <strong>Unassigned</strong> — cannot create environments.</li>
    </ul>

    <p>
        Users with <strong>environment-scoped</strong> access cannot create additional environments outside their assignment.
    </p>

    <p>
        If you lack permission, the <strong>Create Environment</strong> button is disabled and a tooltip explains why. Contact an organization Owner or Admin via <strong>Administration → Roles & Access</strong>.
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

                <h3>Go to Environments</h3>

                <p>Navigate to:</p>

                <p><strong>Organization → Environments</strong></p>

                <p>
                    You can filter the list by project or workspace using scope links from the Projects or Workspaces pages.
                </p>

            </div>

        </div>

        <div class="step-item">

            <div class="step-circle-ui">3</div>

            <div class="step-content">

                <h3>Click Create Environment</h3>

                <p>
                    Click <strong>Create Environment</strong> on the toolbar, or <strong>Create Your First Environment</strong> when the list is empty.
                </p>

            </div>

        </div>

        <div class="step-item">

            <div class="step-circle-ui">4</div>

            <div class="step-content">

                <h3>Fill in Environment Details</h3>

                <p>Provide the following in the Create Environment dialog:</p>

                <ul>
                    <li><strong>Project</strong> (required) — The project that contains the target workspace.</li>
                    <li><strong>Workspace</strong> (required) — The workspace this environment belongs to. The list is filtered by the selected project.</li>
                    <li><strong>Name</strong> (required) — Unique within the selected workspace. Axio auto-generates an internal slug. Names are compared case-insensitively within the workspace.</li>
                    <li><strong>Description</strong> (optional) — A short summary of the environment purpose.</li>
                    
                </ul>

                <p><strong>Note:</strong> The UI uses a single <strong>Name</strong> field (there is no separate display name). Environment owners and self-approval are configured <strong>after creation</strong> using <strong>Assign owner</strong> on the Environments list — not in the create dialog.</p>

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
                    While the environment is being created, the button shows <strong>Saving…</strong>. If the name already exists in the workspace or validation fails, an error message appears in the dialog.
                </p>

            </div>

        </div>

        <div class="step-item">

            <div class="step-circle-ui">6</div>

            <div class="step-content">

                <h3>Environment Created</h3>

                <p>
                    On success, the dialog closes and the environment appears on <strong>Organization → Environments</strong>. You are automatically granted access to the environment you created.
                </p>

                <p>
                    <strong>Recommended next step:</strong> Open the row actions menu and choose <strong>Assign owner</strong> to add environment owners and configure self-approval before running deployments.
                </p>

            </div>

        </div>

    </div>

    <div class="step-right">

        <div class="project-form">

            <div class="form-header">

                <h2>Create Environment</h2>

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

                Workspace *

                <select>
                    <option>Select Workspace</option>
                    <option>Development</option>
                    <option>Production</option>
                </select>

            </label>

            <label>

                Name *

                <input
                    type="text"
                    placeholder="e.g. production">

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
| **Project** | Yes | Must select a project that contains the target workspace. |
| **Workspace** | Yes | Must select a workspace within the chosen project. Creation requires manage access on that workspace. |
| **Name** | Yes | Must not be empty. Must be unique within the workspace (case-insensitive). A URL-safe slug is generated automatically. |
| **Description** | No | Free text shown on the Environments list. |
| **Sensitive** | No | Defaults to off. When enabled, restricts delete, archive, and destroy operations — see below. |

<hr>

<h2>Assign owners and self-approval (after creation)</h2>

<p>
After the environment is created, configure governance from the Environments list using <strong>Assign owner</strong> in the row actions menu. This opens a separate dialog — it is not part of the initial create form.
</p>

<div class="environment-cards">

  <div class="environment-card environment-card-blue">

    <div class="environment-card-header">
      <div class="environment-card-icon">👥</div>
      <h3>Environment Owners</h3>
    </div>

    <div class="environment-card-divider"></div>

    <p class="environment-card-description">
      Assign users or groups as owners of an Environment.
      Owners can run workflows in the Environment and
      approve deployments when required.
    </p>

    <div class="environment-card-label">
      KEY POINTS
    </div>

    <div class="environment-point">
      <div class="environment-point-icon">▶</div>
      <p>
        Environment Owners can run workflows within the
        Environment.
      </p>
    </div>

    <div class="environment-point">
      <div class="environment-point-icon">✓</div>
      <p>
        Environment Owners can approve deployments when
        approval is required.
      </p>
    </div>

    <div class="environment-point">
      <div class="environment-point-icon">👥</div>
      <p>
        Assign one or more users or groups as Environment
        Owners.
      </p>
    </div>

    <div class="environment-info environment-info-blue">
      <div class="environment-info-icon">ⓘ</div>
      <p>
        When using <strong>Assign owner</strong>, at least one user or group must be selected before saving.
      </p>
    </div>

  </div>

  <div class="environment-card environment-card-green">

    <div class="environment-card-header">
      <div class="environment-card-icon">🛡</div>
      <h3>Skip self-approval for workflows</h3>
    </div>

    <div class="environment-card-divider"></div>

    <p class="environment-card-description">
      Controls whether the user who triggered a workflow
      can approve its deployment. Configure this in the
      <strong>Assign owner</strong> dialog.
    </p>

    <div class="self-approval-option">

      <div class="self-approval-icon">🔒</div>

      <div>
        <h4>If enabled (default)</h4>
        <p>
          The workflow initiator cannot approve their own
          deployment — even if they are listed as an owner.
          Another Environment Owner must review and approve.
        </p>
      </div>

    </div>

    <div class="self-approval-option">

      <div class="self-approval-icon">♙</div>

      <div>
        <h4>If disabled</h4>
        <p>
          Self-approval is allowed when the initiator is an
          Environment Owner. At least one owner must still
          be assigned.
        </p>
      </div>

    </div>

    <div class="environment-info environment-info-green">
      <div class="environment-info-icon">ⓘ</div>
      <p>
        Production environments typically keep skip self-approval enabled for separation of duties.
      </p>
    </div>

  </div>

</div>

<hr>

<h2>What Happens Next?</h2>

<p>After creating the Environment:</p>

<ul>
    <li>The Environment becomes available under the selected <strong>Project</strong> and <strong>Workspace</strong> on <strong>Organization → Environments</strong>.</li>
    <li>Use <strong>Assign owner</strong> to configure owners and self-approval before production deployments.</li>
    <li>Deploy one or more <strong>Infrastructure Stacks</strong> into the Environment.</li>
    <li>Sensitive Environments cannot be deleted or archived and block destroy deployments for linked stacks.</li>
    <li>An Environment can be <strong>unassigned from its Workspace</strong> when editing (moved to the system <strong>Default Workspace</strong>) — system and Git-managed environments cannot be unassigned.</li>
    <li>Environments can be <strong>archived</strong> when eligible (not sensitive; system and Git-managed environments have UI restrictions).</li>
    <li>Organization and project lifecycle policies may apply TTL and destroy-protection rules to environments.</li>
</ul>

<div class="resource-grid-info">

<div class="resource-card environment" id="sensitive-environments">

    <div class="card-title">

        <img class="environment-icon" src="{{ '/assets/icons/globe.svg' | relative_url }}"
             alt="Sensitive">

        <h3>Sensitive environments</h3>

    </div>

    <p>
        Mark an environment as <strong>Sensitive</strong> during creation or when editing it.
    </p>

    <ul>
        <li>Sensitive environments cannot be deleted</li>
        <li>Sensitive environments cannot be archived</li>
        <li>Destroy deployments for linked stacks are blocked</li>
    </ul>

</div>

</div>

<div class="tip-box">

    <div class="tip-header">

        <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
             alt="Tip">

        <h3>Discovery runs</h3>

    </div>

    <p>
       From <strong>Organization → Environments</strong>, open <strong>Discovery runs</strong> to view PR-driven stack discovery history — provisioned stacks, plans, PR-close destroy actions, discovery status, and related details.
    </p>

</div>


<div class="page-navigation">

    <a class="nav-button previous"
        href="{{ '/axio/organization/workspace/create-workspace-platform-as-code/' | relative_url }}">
        ← Create Workspace using Platform as Code
    </a>

    <a class="nav-button next"
        href="{{ '/axio/organization/environment/create-environment-platform-as-code/' | relative_url }}">
        Create Environment using Platform as Code →
    </a>

</div>
