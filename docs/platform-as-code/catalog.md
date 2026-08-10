---
layout: default
title: Catalog
has_toc: false
Parent: Platform as Code
nav_order: 1
---

<div class="catalog-header-box">

    <div>
        <h2>Catalog</h2>

        <p>
            Browse the resource kinds available for Platform as Code and
            learn how to define them in YAML.
        </p>
    </div>

</div>

<div class="catalog-prerequisite">

    <div class="prerequisite-header">

        <img src="{{ '/assets/icons/info.svg' | relative_url }}"
             alt="Info">

        <h3>What is the Catalog?</h3>

    </div>

    <p>
        The Catalog is the read-only reference for every Platform as Code
        resource kind. It provides schemas, required fields, dependencies,
        field types, and YAML examples that you can use when authoring
        manifests in Git.
    </p>

</div>

<div class="catalog-layout">

    <!-- LEFT -->

    <div class="catalog-workflow">

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

    <!-- RIGHT -->

    <div class="catalog-content">

        <div class="catalog-info-card">

            <div class="catalog-info-icon">
                <img src="{{ '/assets/icons/info.svg' | relative_url }}"
                     alt="Catalog">
            </div>

            <div>
                <h3>What is the Catalog?</h3>

                <p>
                    The Catalog contains the schema registry for every
                    Platform as Code resource kind. It includes metadata
                    about available fields, their types, default values,
                    validation rules, and usage examples. Use it as a
                    reference before authoring manifests in Git.
                </p>
            </div>

        </div>

        <div class="catalog-resource-layout">

            <div class="resource-categories">

                <h3>Resource Categories</h3>

                <p class="resource-subtitle">
                    Explore resources by category
                </p>

                <div class="resource-category-item">
                    <span class="resource-category-icon organization">♙</span>
                    <strong>Organization</strong>
                    <span class="category-arrow">›</span>
                </div>

                <div class="resource-category-item">
                    <span class="resource-category-icon project">▣</span>
                    <strong>Project</strong>
                    <span class="category-arrow">›</span>
                </div>

                <div class="resource-category-item">
                    <span class="resource-category-icon workspace">▤</span>
                    <strong>Workspace</strong>
                    <span class="category-arrow">›</span>
                </div>

                <div class="resource-category-item">
                    <span class="resource-category-icon environment">▦</span>
                    <strong>Environment</strong>
                    <span class="category-arrow">›</span>
                </div>

                <div class="resource-category-item">
                    <span class="resource-category-icon stack">◈</span>
                    <strong>Stack</strong>
                    <span class="category-arrow">›</span>
                </div>

                <div class="resource-category-item">
                    <span class="resource-category-icon credentials">▣</span>
                    <strong>Credentials</strong>
                    <span class="category-arrow">›</span>
                </div>

                <div class="resource-category-item">
                    <span class="resource-category-icon policy">◇</span>
                    <strong>Policy</strong>
                    <span class="category-arrow">›</span>
                </div>

                <div class="resource-category-item">
                    <span class="resource-category-icon runner">▥</span>
                    <strong>Runner</strong>
                    <span class="category-arrow">›</span>
                </div>

                <div class="resource-category-item">
                    <span class="resource-category-icon integration">✣</span>
                    <strong>Integration</strong>
                    <span class="category-arrow">›</span>
                </div>

                <div class="resource-more">... and more</div>

            </div>

            <div class="catalog-schema-card">

                <h3>Resource Schema Example</h3>

                <p class="resource-kind">
                    Resource Kind:
                    <span>Environment</span>
                </p>

                <div class="schema-tabs">
                    <span class="active">Schema</span>
                    <span>Example Manifest</span>
                    <span>Field Reference</span>
                </div>

                <div class="yaml-box">

                    <button class="yaml-copy" type="button">
                        Copy
                    </button>

                    <pre><code>apiVersion: platform.axio.io/v1
kind: Environment
metadata:
  name: production
  labels:
    team: platform
spec:
  displayName: Production Environment
  workspace: production-ws
  description: Production deployment environment
  sensitive: true
  tags:
    - production</code></pre>

                </div>

            </div>

        </div>

        <div class="schema-fields-card">

            <h3>Schema Fields (Environment)</h3>

            <div class="schema-table-wrapper">

                <table class="schema-table">

                    <thead>
                        <tr>
                            <th>Field</th>
                            <th>Type</th>
                            <th>Required</th>
                            <th>Description</th>
                        </tr>
                    </thead>

                    <tbody>

                        <tr>
                            <td>metadata.name</td>
                            <td>string</td>
                            <td><span class="required-yes">Yes</span></td>
                            <td>Unique name of the environment (lowercase, hyphens allowed)</td>
                        </tr>

                        <tr>
                            <td>spec.displayName</td>
                            <td>string</td>
                            <td><span class="required-yes">Yes</span></td>
                            <td>Display name for the environment</td>
                        </tr>

                        <tr>
                            <td>spec.workspace</td>
                            <td>string</td>
                            <td><span class="required-yes">Yes</span></td>
                            <td>Name of the workspace this environment belongs to</td>
                        </tr>

                        <tr>
                            <td>spec.description</td>
                            <td>string</td>
                            <td><span class="required-no">No</span></td>
                            <td>Description of the environment</td>
                        </tr>

                        <tr>
                            <td>spec.sensitive</td>
                            <td>boolean</td>
                            <td><span class="required-no">No</span></td>
                            <td>Marks environment as sensitive (default: false)</td>
                        </tr>

                        <tr>
                            <td>spec.tags</td>
                            <td>array(string)</td>
                            <td><span class="required-no">No</span></td>
                            <td>List of tags for classification and filtering</td>
                        </tr>

                    </tbody>

                </table>

            </div>

        </div>

    </div>

</div>

<div class="catalog-tip">

    <div class="tip-header">
        <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
             alt="Tip">
        <h3>Tip</h3>
    </div>

    <p>
        Use the Catalog as the source of truth for resource schemas.
        Always check the selected resource's required fields and dependencies
        before committing a manifest to Git.
    </p>

</div>
