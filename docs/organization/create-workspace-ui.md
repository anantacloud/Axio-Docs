---
layout: default
title: Create Workspace from UI
parent: Workspaces
grand_parent: Organization
nav_order: 1
---

<h1>
    <img src="{{ '/assets/icons/blocks.svg' | relative_url }}"
         class="page-icon"
         alt="Workspace">
    Create a Workspace from UI
</h1>

<p class="page-description">
Create a Workspace using the Axio web interface. A Workspace belongs to a Project and provides an isolated area for managing Environments and resources.
</p>

<div class="prerequisite-box">

    <div class="prerequisite-header">

        <img src="{{ '/assets/icons/info.svg' | relative_url }}"
             alt="Info">

        <h3>Prerequisite</h3>

    </div>

    <p>
        Ensure that you have permission to create Workspaces and that a Project already exists.
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

                <h3>Go to Workspaces</h3>

                <p>
                    Navigate to:
                </p>

                <p>
                    <strong>Organization → Workspaces</strong>
                </p>

            </div>

        </div>

        <div class="step-item">

            <div class="step-circle-ui">3</div>

            <div class="step-content">

                <h3>Click Create Workspace</h3>

                <p>
                    Click the <strong>Create Workspace</strong> button.
                </p>

            </div>

        </div>

        <div class="step-item">

            <div class="step-circle-ui">4</div>

            <div class="step-content">

                <h3>Fill in Workspace Details</h3>

                <p>
                    Provide the required information:
                </p>

                <ul>

                    <li><strong>Name</strong> (Unique identifier)</li>

                    <li><strong>Display Name</strong></li>

                    <li><strong>Project</strong></li>

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

                <h3>Workspace Created</h3>

                <p>
                    The Workspace will appear under the selected Project and is now ready for creating Environments.
                </p>

            </div>

        </div>

    </div>

    <!-- RIGHT -->

    <div class="step-right">

        <div class="project-form">

            <div class="form-header">

                <h2>Create Workspace</h2>

            </div>

            <label>

                Name *

                <input
                    type="text"
                    placeholder="e.g. development">

            </label>

            <label>

                Display Name *

                <input
                    type="text"
                    placeholder="Development Workspace">

            </label>

            <label>

                Project *

                <select>

                    <option>Select Project</option>

                    <option>Ecommerce</option>

                    <option>Payments</option>

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

<h2>What Happens Next?</h2>

<p>
After creating the Workspace:
</p>

<ul>

    <li>
        The Workspace becomes available under the selected Project.
    </li>

    <li>
        You can create one or more Environments.
    </li>

    <li>
        Configure credentials and policies.
    </li>

    <li>
        Deploy and manage application resources.
    </li>

    <li>
        Collaborate securely with your team.
    </li>

</ul>

<div class="tip-box">

    <div class="tip-header">

        <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
             alt="Tip">

        <h3>Tip</h3>

    </div>

    <p>

        Organize Workspaces based on teams, applications, or environments to simplify access management and resource isolation.

    </p>

</div>

<div class="page-navigation">

    <a
        class="nav-button previous"
        href="{{ '/docs/organization/create-project-ui/' | relative_url }}">

        ← Create Project from UI

    </a>

    <a
        class="nav-button next"
        href="{{ '/docs/organization/create-workspace-platform-as-code/' | relative_url }}">

        Create Workspace using Platform as Code →

    </a>

</div>
