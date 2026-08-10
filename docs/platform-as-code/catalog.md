---
layout: default
title: Catalog
parent: Platform as Code
nav_order: 1
---

<div class="announcement-box">
    <div class="announcement-content">

        <div>
            <h2>Catalog</h2>

            <p>
                Browse the resource kinds available for Platform as Code and
                learn how to define them in YAML.
            </p>

        </div>

    </div>
</div>

<div class="prerequisite-header">

    <img src="{{ '/assets/icons/info.svg' | relative_url }}"
         alt="Info">

    <h3>What is the Catalog?</h3>

</div>

<p>
    The Catalog is the read-only reference for Platform as Code resource kinds.
    It provides the information required to author valid manifests before they
    are committed to Git.
</p>

<div class="step-left">

    <div class="step-item">

        <div class="step-circle-ui">1</div>

        <div class="step-content">

            <h3>Select a Resource Kind</h3>

            <p>
                Browse the available resource kinds grouped by category and
                select the resource you want to configure.
            </p>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">2</div>

        <div class="step-content">

            <h3>Review the API Version</h3>

            <p>
                Check the API version required by the selected resource kind.
            </p>

            <pre><code>apiVersion: platform.axio.io/v1</code></pre>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">3</div>

        <div class="step-content">

            <h3>Review Dependencies</h3>

            <p>
                Check whether the selected resource depends on another Axio
                resource before creating its manifest.
            </p>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">4</div>

        <div class="step-content">

            <h3>Review Metadata and Spec Fields</h3>

            <p>
                Review required and optional fields, their types, and their
                descriptions before authoring the YAML.
            </p>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">5</div>

        <div class="step-content">

            <h3>Use the YAML Example</h3>

            <p>
                Use the provided example as a starting point for your
                Git-managed manifest.
            </p>

        </div>

    </div>

</div>

<div class="tip-header">

    <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
         alt="Tip">

    <h3>Tip</h3>

</div>

<p>
    Always check the Catalog before creating a new manifest. It helps you use
    the correct API version, fields, dependencies, and resource structure.
</p>

<a class="nav-button previous"
   href="{{ '/docs/platform-as-code/' | relative_url }}">
    ← Platform as Code
</a>

<a class="nav-button next"
   href="{{ '/docs/platform-as-code/resources/' | relative_url }}">
    Resources →
</a>
