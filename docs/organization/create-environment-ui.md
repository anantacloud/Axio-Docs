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
Create an Environment from the Axio user interface to organize infrastructure deployments within a Workspace. Environments help separate resources for development, testing, staging, and production while maintaining consistent configurations.
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

<h2>What Happens Next?</h2>

<p>
After creating the Environment:
</p>

<ul>

    <li>
        The Environment becomes available under the selected Workspace.
    </li>

    <li>
        You can deploy one or more Infrastructure Stacks.
    </li>

    <li>
        Manage environment-specific configurations and credentials.
    </li>

    <li>
        Isolate deployments for development, staging, or production.
    </li>

    <li>
        Enable secure collaboration across deployment environments.
    </li>

</ul>

<div class="tip-box">

    <div class="tip-header">

        <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
             alt="Tip">

        <h3>Tip</h3>

    </div>

    <p>

        Create separate Environments for development, staging, and production to isolate deployments and maintain consistent infrastructure management.

    </p>

</div>

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
