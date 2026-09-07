---
layout: default
title: Create Environment from UI
parent: Environments
grand_parent: Organization
nav_order: 1
---

<h1>
    <img src="{{ '/assets/icons/layers.svg' | relative_url }}"
         class="page-icon"
         alt="Environment">
    Create a Environment from UI
</h1>

<p class="page-description">
Create an Environment using the Axio web interface. An Environment belongs to a Workspace and serves as a deployment target for infrastructure stacks.
</p>

<div class="prerequisite-box">

    <div class="prerequisite-header">

        <img src="{{ '/assets/icons/info.svg' | relative_url }}"
             alt="Info">

        <h3>Prerequisite</h3>

    </div>

    <p>
       Ensure that you have permission to create Environments and that a Workspace already exists.
    </p>

</div>

<hr>

<h2>Step-by-Step Guide</h2>

<div class="step-layout">

    <!-- LEFT -->

    <div class="step-left">

        <div class="step-item">

            <div class="step-circle-ui">1</div>

            <div class="step-content">

                <h3>Login to Axio</h3>

                <p>
                    Sign in to the Axio platform using your credentials.
                </p>

            </div>

        </div>

        <div class="step-item">

            <div class="step-circle-ui">2</div>

            <div class="step-content">

                <h3>Go to Environments</h3>

                <p>
                    Navigate to:
                </p>

                <p>
                    <strong>Organization → Environments</strong>
                </p>

            </div>

        </div>

        <div class="step-item">

            <div class="step-circle-ui">3</div>

            <div class="step-content">

                <h3>Click Create Environment</h3>

                <p>
                    Click the <strong>Create Environment</strong> button.
                </p>

            </div>

        </div>

        <div class="step-item">

            <div class="step-circle-ui">4</div>

            <div class="step-content">

                <h3>Fill in Environment Details</h3>

                <p>
                    Provide the required information:
                </p>

                <ul>

                    <li><strong>Name</strong> (Unique identifier)</li>

                    <li><strong>Display Name</strong></li>

                    <li><strong>Workspace</strong></li>

                    <li><strong>Description</strong> (Optional)</li>

                </ul>

            </div>

        </div>

        <div class="step-item">

            <div class="step-circle-ui">5</div>

            <div class="step-content">

                <h3>Review and Confirm</h3>

                <p>
                    Verify all the entered information and click
                    <strong>Create</strong>.
                </p>

            </div>

        </div>

        <div class="step-item">

            <div class="step-circle-ui">6</div>

            <div class="step-content">

                <h3>Environment Created</h3>

                <p>
                    The Environment will appear under the selected Workspace and is ready for deploying infrastructure stacks.
                </p>

            </div>

        </div>

    </div>

    <!-- RIGHT -->

    <div class="step-right">

        <div class="project-form">

            <div class="form-header">

                <h2>Create Environment</h2>

            </div>

            <label>

                Name *

                <input
                    type="text"
                    placeholder="e.g. production">

            </label>

            <label>

                Display Name *

                <input
                    type="text"
                    placeholder="Production Environment">

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

                Description

                <textarea
                    rows="4"
                    placeholder="Enter description (optional)"></textarea>

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

<hr>

<div class="environment-cards">

  <!-- Environment Owners -->
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
        At least one user or group must be assigned as an
        Environment Owner.
      </p>
    </div>

  </div>


  <!-- Skip Self Approval -->
  <div class="environment-card environment-card-green">

    <div class="environment-card-header">
      <div class="environment-card-icon">🛡</div>
      <h3>Skip self-approval for workflows</h3>
    </div>

    <div class="environment-card-divider"></div>

    <p class="environment-card-description">
      Controls whether the user who triggered a workflow
      can approve its deployment.
    </p>

    <div class="self-approval-option">

      <div class="self-approval-icon">🔒</div>

      <div>
        <h4>If enabled</h4>
        <p>
          The workflow initiator cannot approve their own
          deployment. Another Environment Owner must
          review and approve.
        </p>
      </div>

    </div>

    <div class="self-approval-option">

      <div class="self-approval-icon">♙</div>

      <div>
        <h4>If disabled</h4>
        <p>
          Self-approval is allowed. However, at least one
          user or group must be assigned as an Environment
          Owner.
        </p>
      </div>

    </div>

    <div class="environment-info environment-info-green">
      <div class="environment-info-icon">ⓘ</div>
      <p>
        This setting helps maintain secure and compliant
        deployment practices.
      </p>
    </div>

  </div>

</div>

<div class="tip-box">

    <div class="tip-header">

        <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
             alt="Tip">

        <h3>Discover Runs</h3>

    </div>

    <p>
       Environments provide access to Discover Runs, which shows the history of PR-driven stack discovery activity. It helps you track provisioned stacks,        plans, PR-close destroy actions, discovery status, and related details.
    </p>

</div>

<h2>What Happens Next?</h2>

<p>
After creating the Environment:
</p>

<ul>
    <li>The Environment becomes available under the selected <strong>Workspace</strong>.</li>
    <li>Deploy one or more <strong>Infrastructure Stacks</strong> in the Environment.</li>
    <li>Sensitive Environments block destroy deployments for linked stacks.</li>
    <li>Sensitive Environments cannot be deleted or archived. </li>
    <li>An Environment can be <strong>unassigned from its Workspace</strong> and moved to the <strong>default workspace</strong>.</li>
    <li>Environments can be <strong>archived</strong> when eligible. </li>
</ul>

<div class="page-navigation">

    <a
        class="nav-button previous"
        href="{{ '/docs/organization/create-workspace-platform-as-code/' | relative_url }}">

        ← Create Workspace using Platform as Code

    </a>

    <a
        class="nav-button next"
        href="{{ '/docs/organization/create-environment-platform-as-code/' | relative_url }}">

        Create Environment using Platform as Code →

    </a>

</div>
