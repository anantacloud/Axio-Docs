---
layout: default
title: Create Environment using Platform as Code
parent: Environment
nav_order: 2
---

<div class="announcement-box">
    <div class="announcement-content">
        <img src="{{ '/assets/icons/environment.svg' | relative_url }}"
             alt="Environment">

        <div>
            <h2>Create Environment using Platform as Code</h2>

            <p>
                Define and create environments declaratively using Axio Platform as Code.
            </p>
        </div>
    </div>
</div>

<div class="prerequisite-header">

    <img src="{{ '/assets/icons/info.svg' | relative_url }}"
         alt="Info">

    <h3>Prerequisite</h3>

</div>

<p>
    Ensure that you have permission to create Environments and that a Workspace
    already exists.
</p>

<div class="steps-container">

    <!-- LEFT -->

    <div class="step-left">

        <div class="step-item">

            <div class="step-circle-ui">1</div>

            <div class="step-content">

                <h3>Create an Environment YAML file</h3>

                <p>
                    Create a YAML file that defines the Environment you want to
                    provision in Axio.
                </p>

                <pre><code>apiVersion: platform.axio.io/v1
kind: Environment
metadata:
  name: my-environment
spec:
  displayName: Environment-testing
  workspace: production</code></pre>

            </div>

        </div>

        <div class="step-item">

            <div class="step-circle-ui">2</div>

            <div class="step-content">

                <h3>Define the Environment configuration</h3>

                <p>
                    Update the manifest with the required Environment name,
                    display name, and Workspace.
                </p>

                <pre><code>metadata:
  name: my-environment

spec:
  displayName: Environment-testing
  workspace: production</code></pre>

                <p>
                    The Workspace referenced in the manifest must already exist
                    and you must have permission to use it.
                </p>

            </div>

        </div>

    </div>

    <!-- RIGHT -->

    <div class="step-right">

        <div class="step-item">

            <div class="step-circle-ui">3</div>

            <div class="step-content">

                <h3>Apply the manifest</h3>

                <p>
                    Apply the YAML manifest using the Axio Platform as Code
                    workflow.
                </p>

                <pre><code>axio apply -f environment.yaml</code></pre>

                <p>
                    Axio reads the manifest and creates the Environment in the
                    specified Workspace.
                </p>

            </div>

        </div>

        <div class="step-item">

            <div class="step-circle-ui">4</div>

            <div class="step-content">

                <h3>Verify the Environment</h3>

                <p>
                    After applying the manifest, verify that the Environment
                    was created successfully.
                </p>

                <pre><code>axio get environments</code></pre>

                <p>
                    The newly created Environment should appear in the list of
                    available Environments.
                </p>

            </div>

        </div>

    </div>

</div>

<div class="tip-box">

    <h3>Tip</h3>

    <p>
        Store your Environment YAML manifests in Git so that configuration
        changes can be version controlled, reviewed, and reused across
        environments.
    </p>

</div>

---

← [Create Workspace from UI](create-workspace-ui)

[Create Environment from UI →](create-environment-ui)

