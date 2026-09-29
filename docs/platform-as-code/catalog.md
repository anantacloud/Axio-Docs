---
layout: default
title: Catalog
has_toc: false
parent: Platform as Code
nav_order: 1
permalink: /axio/platform-as-code/catalog/
---

# Catalog

Browse the **145+** resource kinds available for Platform as Code and learn how to define them in YAML. Open **Platform as Code → Catalog** in the Axio UI.

<div class="important-box">
  <div class="important-header">
    <img src="{{ '/assets/icons/triangle-alert.svg' | relative_url }}" alt="Warning">
    <h3>Important</h3>
  </div>

  <p>
    The Catalog is a <strong>read-only schema registry</strong>. It documents fields, validation rules, and examples —
    it does <strong>not</strong> create or edit platform resources. Author manifests in Git and apply them through
    <strong>Platform as Code → Synchronizations</strong>.
  </p>

  <p>
    Do not author a <code>status</code> block in manifests — Axio generates and manages status automatically.
    Optional <code>metadata.sensitive: true</code> requires sync plan approval before Git-driven updates or deletions.
  </p>
</div>

<div class="prerequisite-box">

<div class="prerequisite-header">

<img src="{{ '/assets/icons/info.svg' | relative_url }}" alt="Info">

<h3>Prerequisites</h3>

</div>

<ul>
<li>Permission to view Platform as Code (<code>pac:read</code> or higher).</li>
<li>For Git-managed instances to appear in the catalog — a connected repository registered under <strong>Platform as Code → Synchronizations</strong>.</li>
</ul>

</div>

<div class="catalog-layout">

    <!-- LEFT -->

    <div class="catalog-workflow">

        <div class="step-item">
            <div class="step-circle-ui">1</div>
            <div class="step-content">
                <h3>Select a Resource Kind</h3>
                <p>
                    Browse kinds grouped by category (Organization, Projects, Environment, Infrastructure, Automation, Governance, and more).
                    Click a kind such as <strong>Project</strong>, <strong>Workspace</strong>, or <strong>Environment</strong> to load its documentation.
                </p>
            </div>
        </div>

        <div class="step-item">
            <div class="step-circle-ui">2</div>
            <div class="step-content">
                <h3>Review the API Version</h3>
                <p>
                    Confirm the API version required by the selected kind. All current kinds use:
                </p>
                <pre><code>apiVersion: platform.axio.io/v1</code></pre>
            </div>
        </div>

        <div class="step-item">
            <div class="step-circle-ui">3</div>
            <div class="step-content">
                <h3>Review Dependencies</h3>
                <p>
                    Check <strong>Dependencies</strong> (parent kinds) for the resource. For example, an
                    <strong>Environment</strong> requires a parent <strong>Workspace</strong> (and typically a
                    <strong>Project</strong>). Synchronize parent manifests before or together with child resources.
                </p>
            </div>
        </div>

        <div class="step-item">
            <div class="step-circle-ui">4</div>
            <div class="step-content">
                <h3>Review Metadata and Spec Fields</h3>
                <p>
                    Read <strong>Metadata Fields</strong> (common to every kind, including optional
                    <code>sensitive</code>) and <strong>Spec Fields</strong> with required flags, types, and descriptions.
                </p>
            </div>
        </div>

        <div class="step-item">
            <div class="step-circle-ui">5</div>
            <div class="step-content">
                <h3>Use the Example YAML</h3>
                <p>
                    Copy the <strong>Example YAML</strong> (or inspect the JSON Schema) as a starting point for your
                    Git-managed manifest under the repository working directory (default: <code>platform-config/</code>).
                </p>
            </div>
        </div>

        <div class="step-item">
            <div class="step-circle-ui">6</div>
            <div class="step-content">
                <h3>Inspect Git-Managed Instances</h3>
                <p>
                    The <strong>Git-Managed Instances</strong> table lists synchronized resources of the selected kind —
                    name, status, drift, and source repository. Empty until you add manifests and run <strong>Sync now</strong>.
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
                    The Catalog is the schema registry for every Platform as Code resource kind. For each kind it shows
                    API version, dependencies, metadata and spec field definitions, validation rules, example YAML, JSON Schema,
                    and synchronized instances from your Git repositories. Use it as a reference before authoring manifests —
                    not as an editor.
                </p>
            </div>

        </div>

        <div class="catalog-resource-layout">

            <div class="resource-categories">

                <h3>Resource Categories</h3>

                <p class="resource-subtitle">
                    Explore kinds by category (145+ kinds in the product catalog)
                </p>

                <div class="resource-category-item">
                    <span class="resource-category-icon organization">♙</span>
                    <strong>Organization</strong>
                    <span class="category-arrow">›</span>
                </div>

                <div class="resource-category-item">
                    <span class="resource-category-icon project">▣</span>
                    <strong>Projects</strong>
                    <span class="category-arrow">›</span>
                </div>

                <div class="resource-category-item">
                    <span class="resource-category-icon environment">▦</span>
                    <strong>Environment</strong>
                    <span class="category-arrow">›</span>
                </div>

                <div class="resource-category-item">
                    <span class="resource-category-icon stack">◈</span>
                    <strong>Infrastructure</strong>
                    <span class="category-arrow">›</span>
                </div>

                <div class="resource-category-item">
                    <span class="resource-category-icon policy">◇</span>
                    <strong>Automation</strong>
                    <span class="category-arrow">›</span>
                </div>

                <div class="resource-category-item">
                    <span class="resource-category-icon runner">▥</span>
                    <strong>Execution Service</strong>
                    <span class="category-arrow">›</span>
                </div>

                <div class="resource-category-item">
                    <span class="resource-category-icon policy">◆</span>
                    <strong>Governance</strong>
                    <span class="category-arrow">›</span>
                </div>

                <div class="resource-category-item">
                    <span class="resource-category-icon integration">✣</span>
                    <strong>Integrations</strong>
                    <span class="category-arrow">›</span>
                </div>

                <div class="resource-category-item">
                    <span class="resource-category-icon credentials">▣</span>
                    <strong>Identity &amp; Security</strong>
                    <span class="category-arrow">›</span>
                </div>

                <div class="resource-more">… and more (FinOps, Observability, AI Platform, Marketplace, GitOps, Reconciliation)</div>

            </div>

            <div class="catalog-schema-card">

                <h3>Resource Schema Example</h3>

                <p class="resource-kind">
                    Resource Kind:
                    <span>Environment</span>
                </p>

                <div class="schema-tabs">
                    <span class="active">Metadata &amp; Spec</span>
                    <span>Example YAML</span>
                    <span>JSON Schema</span>
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
  project: ecommerce
  workspace: development
  description: Production deployment target
  type: PRODUCTION</code></pre>

                </div>

            </div>

        </div>

        <div class="schema-fields-card">

            <h3>Schema Fields (Environment)</h3>

            <p class="resource-subtitle">
                Representative fields — always confirm the live Catalog for the selected kind and version.
            </p>

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
                            <td>Unique environment slug within the parent workspace</td>
                        </tr>

                        <tr>
                            <td>metadata.sensitive</td>
                            <td>boolean</td>
                            <td><span class="required-no">No</span></td>
                            <td>When true, Git-driven updates or deletions require sync plan approval</td>
                        </tr>

                        <tr>
                            <td>spec.displayName</td>
                            <td>string</td>
                            <td><span class="required-no">No</span></td>
                            <td>Human-readable name shown in the Axio UI</td>
                        </tr>

                        <tr>
                            <td>spec.workspace</td>
                            <td>string</td>
                            <td><span class="required-yes">Yes</span></td>
                            <td>Parent workspace slug (<code>metadata.name</code> of the Workspace manifest)</td>
                        </tr>

                        <tr>
                            <td>spec.project</td>
                            <td>string</td>
                            <td><span class="required-no">Recommended</span></td>
                            <td>Parent project slug; required when the workspace name is ambiguous across projects</td>
                        </tr>

                        <tr>
                            <td>spec.description</td>
                            <td>string</td>
                            <td><span class="required-no">No</span></td>
                            <td>Optional description</td>
                        </tr>

                        <tr>
                            <td>spec.type</td>
                            <td>enum</td>
                            <td><span class="required-no">No</span></td>
                            <td><code>DEVELOPMENT</code>, <code>STAGING</code>, <code>PRODUCTION</code>, or <code>CUSTOM</code> (default <code>DEVELOPMENT</code>)</td>
                        </tr>

                        <tr>
                            <td>spec.deploymentGovernance</td>
                            <td>object</td>
                            <td><span class="required-no">No</span></td>
                            <td>Owners, approvers, and self-approval policy for deployments</td>
                        </tr>

                    </tbody>

                </table>

            </div>

            <p class="axio-manual-help" style="margin-top: 1rem;">
                See <a href="{{ '/axio/organization/environment/create-environment-platform-as-code/' | relative_url }}">Create Environment using Platform as Code</a>
                for a full walkthrough. For Project and Workspace kinds, see the corresponding Platform as Code guides under Organization.
            </p>

        </div>

    </div>

</div>


<div class="page-navigation">

<a
class="nav-button previous"
href="{{ '/axio/platform-as-code/' | relative_url }}">

← Platform as Code

</a>

<a
class="nav-button next"
href="{{ '/axio/organization/overview/' | relative_url }}">

Organization Overview →

</a>

</div>
