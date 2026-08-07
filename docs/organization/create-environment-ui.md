---
layout: default
title: Create Environment from UI
parent: Environments
grand_parent: Organization
nav_order: 1
---

<div class="announcement-box">

<div class="announcement-content">

<img src="{{ '/assets/icons/layers.svg' | relative_url }}"
     class="page-icon"
     alt="Environment">

# Create Environment from UI

Create an Environment through the Axio web interface. Environments help isolate deployments, configurations, credentials, and infrastructure for different stages such as Development, Staging, and Production.

</div>

</div>

---

## Prerequisite

<div class="prerequisite-header">

    <img src="{{ '/assets/icons/info.svg' | relative_url }}"
         alt="Info">

    <h3>Prerequisite</h3>

</div>

<p>
    Ensure that you have permission to create Environments and that a Workspace already exists.
</p>

---

## Step-by-Step Guide

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
                The Environment will appear under the selected Workspace and is now ready for deploying applications and managing resources.
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

            <input type="text" placeholder="e.g. production">

        </label>

        <label>

            Display Name *

            <input type="text" placeholder="Production Environment">

        </label>

        <label>

            Workspace *

            <select>

                <option>Select Workspace</option>
                <option>Development Workspace</option>
                <option>Production Workspace</option>

            </select>

        </label>

        <label>

            Description

            <textarea rows="4"
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

---

## Expected Result

<li>
    The Environment becomes available under the selected Workspace.
</li>

<li>
    Deploy applications and services into the Environment.
</li>

<li>
    Configure environment-specific credentials and secrets.
</li>

<li>
    Apply governance and security policies.
</li>

<li>
    Monitor and manage environment resources.
</li>

---

## Tip

<div class="tip-header">

    <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
         alt="Tip">

    <h3>Tip</h3>

</div>

<p>

Use clear names such as <strong>Development</strong>, <strong>Staging</strong>, and <strong>Production</strong> to make environments easy to identify and manage across Workspaces.

</p>

---

<a
    class="nav-button previous"
    href="{{ '/docs/organization/environments/' | relative_url }}">

    ← Environments

</a>

<a
    class="nav-button next"
    href="{{ '/docs/organization/environments/create-environment-platform-as-code/' | relative_url }}">

    Create using Platform as Code →

</a>
