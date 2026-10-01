---
layout: default
title: Resources
parent: Platform as Code
nav_order: 2
has_toc: false
permalink: /axio/platform-as-code/resources/
---

# Resources

<div class="resources-page">

    <!-- HEADER -->

    <div class="resources-header-row">

        <div class="resources-title">

            <div class="resources-breadcrumb-spacer"></div>

            <h2>Git-Managed Resources</h2>

            <p>
                Open <strong>Platform as Code → Resources</strong> for a read-only inventory of platform objects
                discovered from Git manifests and reconciled by Axio. To change a resource, edit its YAML in the
                source repository, commit, push, and synchronize — not from this screen.
            </p>

        </div>

        <div class="resources-prerequisite">

            <div class="resources-prerequisite-icon">
                <img src="{{ '/assets/icons/info.svg' | relative_url }}"
                     alt="Info">
            </div>

            <div>

                <h3>Prerequisites</h3>

                <p>
                    A Git repository connected under <strong>Administration → Integrations → Source Control</strong>,
                    registered for Platform as Code, with at least one successful synchronization from
                    <strong>Platform as Code → Synchronizations</strong>.
                    Viewing requires <code>pac:read</code> or higher.
                </p>

            </div>

        </div>

    </div>

    <div class="important-box" style="margin-bottom: 1.5rem;">
      <div class="important-header">
        <img src="{{ '/assets/icons/triangle-alert.svg' | relative_url }}" alt="Warning">
        <h3>Important</h3>
      </div>
      <p>
        This page is an <strong>observability and inventory</strong> view — not an editor. Git-managed resources show a
        <strong>Git-managed</strong> indicator in Organization views; manual UI edits to those resources are restricted.
        When drift is detected, you can reconcile from Git via <strong>Sync now</strong> or open a pull request to align Git with the platform (Administrators).
      </p>
    </div>


    <!-- MAIN CONTENT -->

    <div class="resources-main-grid">


        <!-- LEFT WORKFLOW -->

        <div class="resources-workflow-card">

            <div class="resources-step-item">

                <div class="resources-step-circle">1</div>

                <div class="resources-step-content">

                    <h3>Browse the inventory</h3>

                    <p>
                        Review the table of Platform as Code resources — name, kind (type), repository, branch,
                        manifest path, commit, sync status, drift, and last sync time. Use pagination to move through large lists.
                    </p>

                </div>

            </div>


            <div class="resources-step-item">

                <div class="resources-step-circle">2</div>

                <div class="resources-step-content">

                    <h3>Open resource details</h3>

                    <p>
                        Click a row to open the detail dialog. Review sync status chips, repository, manifest path,
                        applied commit, and the read-only manifest YAML (<code>sourceYaml</code>).
                    </p>

                </div>

            </div>


            <div class="resources-step-item">

                <div class="resources-step-circle">3</div>

                <div class="resources-step-content">

                    <h3>Review Git source</h3>

                    <p>
                        Confirm which repository, branch, manifest file path, and commit SHA last applied the resource.
                        The manifest path is relative to the repository working directory (for example
                        <code>platform-config/environments/production.yaml</code>).
                    </p>

                </div>

            </div>


            <div class="resources-step-item">

                <div class="resources-step-circle">4</div>

                <div class="resources-step-content">

                    <h3>Check sync status</h3>

                    <p>
                        Inspect <strong>Sync Status</strong> — for example <code>READY</code>, <code>PENDING</code>,
                        <code>FAILED</code>, <code>DRIFTED</code>, or <code>AWAITING APPROVAL</code> when a sync plan
                        includes the resource and requires approval.
                    </p>

                </div>

            </div>


            <div class="resources-step-item">

                <div class="resources-step-circle">5</div>

                <div class="resources-step-content">

                    <h3>Monitor drift and dependencies</h3>

                    <p>
                        The <strong>Drift</strong> column shows <em>In sync</em> or <em>Drifted</em> when live platform
                        state differs from Git. Pending resources may list blocked dependencies (for example a Workspace
                        that must reconcile before an Environment).
                    </p>

                </div>

            </div>

            <div class="resources-step-item">

                <div class="resources-step-circle">6</div>

                <div class="resources-step-content">

                    <h3>Act on drift or approval</h3>

                    <p>
                        For drift, go to <strong>Synchronizations</strong> and <strong>Sync now</strong> to reconcile from Git,
                        or use <strong>Open PR to fix drift</strong> (Administrators) to update the manifest to match the platform.
                        Approve or reject pending sync plans from the detail dialog or <strong>Operations → Approvals</strong>.
                    </p>

                </div>

            </div>

        </div>


        <!-- RIGHT CONTENT -->

        <div class="resources-content">


            <!-- WHAT ARE RESOURCES -->

            <div class="resources-info-card">

                <div class="resources-info-icon">

                    <img src="{{ '/assets/icons/info.svg' | relative_url }}"
                         alt="Resources">

                </div>

                <div>

                    <h3>What are Resources?</h3>

                    <p>
                        Resources are Platform as Code objects tracked by Axio after manifest discovery and reconciliation.
                        Each row represents a kind and name (for example <code>Environment/production</code>), its
                        synchronization state, drift relative to Git, and the repository commit that last applied it.
                        Resources with a linked repository are <strong>Git-managed</strong>; others may appear with
                        <strong>Git Managed: No</strong> until synchronized from a repo.
                    </p>

                </div>

            </div>


            <!-- TABLE COLUMNS -->

            <div class="resources-info-card" style="margin-top: 1rem;">

                <div class="resources-info-icon">
                    <img src="{{ '/assets/icons/clipboard-list.svg' | relative_url }}" alt="Columns">
                </div>

                <div>
                    <h3>Inventory columns</h3>
                    <ul>
                        <li><strong>Name</strong> — Resource name (<code>metadata.name</code>)</li>
                        <li><strong>Type</strong> — Resource kind (Project, Workspace, Environment, …)</li>
                        <li><strong>Git Managed</strong> — Whether the resource is tied to a synchronized repository</li>
                        <li><strong>Repository / Branch</strong> — Source repo and branch</li>
                        <li><strong>Manifest Path</strong> — File path within the working directory</li>
                        <li><strong>Commit</strong> — Short SHA of the last applied commit</li>
                        <li><strong>Sync Status</strong> — Reconciliation phase (see statuses below)</li>
                        <li><strong>Drift</strong> — <em>In sync</em> or <em>Drifted</em> vs Git definition</li>
                        <li><strong>Last Sync</strong> — Timestamp of last reconciliation</li>
                    </ul>
                </div>

            </div>


            <!-- DETAILS + TIP -->

            <div class="resources-bottom-grid">


                <!-- DETAILS -->

                <div class="resource-details-card">

                    <h3>Resource detail (Environment/production)</h3>


                    <div class="resource-detail-tabs">

                        <span class="active">Summary</span>
                        <span>Manifest (read-only)</span>
                        <span>Alerts</span>

                    </div>


                    <div class="resource-detail-body">

                        <div class="resource-detail-fields">

                            <div>
                                <strong>Kind:</strong>
                                <span>Environment</span>
                            </div>

                            <div>
                                <strong>API Version:</strong>
                                <span class="api-badge">
                                    platform.axio.io/v1
                                </span>
                            </div>

                            <div>
                                <strong>Repository:</strong>
                                <span>abcd-platform-config</span>
                            </div>

                            <div>
                                <strong>Branch:</strong>
                                <span>main</span>
                            </div>

                            <div>
                                <strong>Manifest path:</strong>
                                <span>platform-config/environments/production.yaml</span>
                            </div>

                            <div>
                                <strong>Commit:</strong>
                                <span>a1b2c3d</span>
                            </div>

                            <div>
                                <strong>Last Sync:</strong>
                                <span>Mar 20, 2026, 10:32 AM</span>
                            </div>

                            <div>
                                <strong>Sync Status:</strong>
                                <span class="mini-status synced">
                                    ● READY
                                </span>
                            </div>

                            <div>
                                <strong>Drift:</strong>
                                <span class="mini-status healthy">
                                    ● In sync
                                </span>
                            </div>

                        </div>


                        <div class="resource-yaml">

                            <button type="button">Copy</button>

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
  type: PRODUCTION</code></pre>

                        </div>

                    </div>

                </div>


                <!-- TIP -->

                <div class="resources-tip-card">

                    <div class="resources-tip-header">

                        <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
                             alt="Tip">

                        <h3>Tip</h3>

                    </div>

                    <p>
                        Resources reflect state as reported by Axio after the last sync run.
                        Use <strong>Synchronizations → Sync now</strong> to reconcile Git with the platform, or
                        <strong>History</strong> for a read-only audit of past runs.
                    </p>

                    <hr>

                    <h4>Common sync statuses:</h4>

                    <ul>

                        <li>
                            <strong class="status-green">READY</strong>
                            – Reconciled and available in the platform
                        </li>

                        <li>
                            <strong class="status-orange">PENDING</strong>
                            – Waiting to apply (often blocked on a parent dependency)
                        </li>

                        <li>
                            <strong class="status-orange">AWAITING APPROVAL</strong>
                            – Included in a sync plan that requires approval
                        </li>

                        <li>
                            <strong class="status-orange">Drifted</strong>
                            – Live platform state differs from the Git manifest (see Drift column)
                        </li>

                        <li>
                            <strong class="status-red">FAILED</strong>
                            – Reconciliation or validation failed (check Synchronizations / History)
                        </li>

                        <li>
                            <strong class="status-gray">UNKNOWN</strong>
                            – Status not yet determined
                        </li>

                    </ul>

                    <p style="margin-top: 1rem;">
                        Browse kind schemas in <a href="{{ '/axio/platform-as-code/catalog/' | relative_url }}">Catalog</a>
                        before authoring new manifests.
                    </p>

                </div>

            </div>

        </div>

    </div>

</div>


<div class="page-navigation">

<a
class="nav-button previous"
href="{{ '/axio/platform-as-code/catalog/' | relative_url }}">

← Catalog

</a>

<a
class="nav-button next"
href="{{ '/axio/platform-as-code/' | relative_url }}">

Platform as Code →

</a>

</div>
