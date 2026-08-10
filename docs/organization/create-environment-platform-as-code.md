---
layout: default
title: Create Environment using Platform as Code
parent: Environments

---

<div class="prerequisite-header">

    <img src="{{ '/assets/icons/info.svg' | relative_url }}"
         alt="Info">

    <h3>Prerequisite</h3>

</div>

<p>
   Ensure that you have permission to create Environments and that a Workspace already exists.
</p>

<!-- LEFT -->

<div class="step-left">

    <div class="step-item">

        <div class="step-circle-ui">1</div>

        <div class="step-content">

            <h3>Create an Environment Manifest</h3>

            <p>
                Create a YAML manifest that defines the Environment you want to provision using Platform as Code.
            </p>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">2</div>

        <div class="step-content">

            <h3>Define the Environment</h3>

            <p>
                Specify the Environment resource using the Axio Platform as Code API version and resource kind.
            </p>

            <p>
                <strong>apiVersion: platform.axio.io/v1</strong>
            </p>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">3</div>

        <div class="step-content">

            <h3>Configure Environment Details</h3>

            <p>
                Provide the required information:
            </p>

            <ul>

                <li><strong>Name</strong> (Unique identifier)</li>

                <li><strong>Display Name</strong></li>

                <li><strong>Workspace</strong></li>

                <li><strong>Sensitive</strong> (Optional)</li>

            </ul>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">4</div>

        <div class="step-content">

            <h3>Save the YAML Manifest</h3>

            <p>
                Save the configuration as an Environment YAML file, for example
                <strong>environment.yaml</strong>.
            </p>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">5</div>

        <div class="step-content">

            <h3>Apply the Manifest</h3>

            <p>
                Apply the Environment manifest using the Axio Platform as Code workflow.
            </p>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">6</div>

        <div class="step-content">

            <h3>Environment Created</h3>

            <p>
                The Environment will be created under the specified Workspace and can be used to deploy infrastructure stacks.
            </p>

        </div>

    </div>

</div>

<!-- RIGHT -->

<div class="step-right">

    <div class="project-form">

        <div class="form-header">

            <h2>Environment Manifest</h2>

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

            Sensitive

            <select>

                <option>false</option>

                <option>true</option>

            </select>

        </label>

        <div class="form-actions">

            <button class="cancel-btn">

                Cancel

            </button>

            <button class="create-btn">

                Apply

            </button>

        </div>

    </div>

</div>

<li>
    The Environment becomes available under the selected Workspace.
</li>

<li>
    The Environment configuration can be managed through a YAML manifest.
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

<div class="tip-header">

    <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
         alt="Tip">

    <h3>Tip</h3>

</div>

<p>

    Store Environment manifests in Git so that configuration changes can be version controlled, reviewed, and consistently applied across development, staging, and production environments.

</p>

<a
    class="nav-button previous"
    href="{{ '/docs/organization/create-workspace-platform-as-code/' | relative_url }}">

    ← Create Workspace using Platform as Code

</a>

<a
    class="nav-button next"
    href="{{ '/docs/organization/create-environment-ui/' | relative_url }}">

    Create Environment from UI →

</a>


