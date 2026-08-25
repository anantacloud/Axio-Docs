---
layout: default
title: Resources
parent: Platform as Code
nav_order: 2
has_toc: false
---

<div class="resources-page">

    <!-- HEADER -->

    <div class="resources-header-row">

        <div class="resources-title">

            <div class="resources-breadcrumb-spacer"></div>

            <h2>Resources</h2>

            <p>
                Resources represent the current state of Platform as Code objects
                as managed by Axio. The Resources page provides a read-only view of resources discovered and reconciled from Git manifests.
            </p>

        </div>

        <div class="resources-prerequisite">

            <div class="resources-prerequisite-icon">
                <img src="{{ '/assets/icons/info.svg' | relative_url }}"
                     alt="Info">
            </div>

            <div>

                <h3>Prerequisite</h3>

                <p>
                    Platform as Code must be configured and a Git repository must be connected and synchronized to discover Git-managed resources.
                </p>

            </div>

        </div>

    </div>


    <!-- MAIN CONTENT -->

    <div class="resources-main-grid">


        <!-- LEFT WORKFLOW -->

        <div class="resources-workflow-card">

            <div class="resources-step-item">

                <div class="resources-step-circle">1</div>

                <div class="resources-step-content">

                    <h3>View Git-Managed Resources</h3>

                    <p>
                       View the platform resources discovered and reconciled from Git manifests. The Resources page provides a read-only inventory of resources                               managed by Axio.
                    </p>

                </div>

            </div>


            <div class="resources-step-item">

                <div class="resources-step-circle">2</div>

                <div class="resources-step-content">

                    <h3>Filter and Search</h3>

                    <p>
                        Use the available filters and search to find resources by name, type, or synchronization state.
                    </p>

                </div>

            </div>


            <div class="resources-step-item">

                <div class="resources-step-circle">3</div>

                <div class="resources-step-content">

                    <h3>Review Git Source</h3>

                    <p>
                        Review the Git repository, branch, manifest path, and commit associated with a Git-managed resource.
                    </p>

                </div>

            </div>


            <div class="resources-step-item">

                <div class="resources-step-circle">4</div>

                <div class="resources-step-content">

                    <h3>Check Sync Status</h3>

                    <p>
                        Review the synchronization status of each resource to determine whether it is ready, drifted, or has failed synchronization.
                    </p>

                </div>

            </div>


            <div class="resources-step-item">

                <div class="resources-step-circle">5</div>

                <div class="resources-step-content">

                    <h3>Monitor Drift and Last Sync</h3>

                    <p>
                        Check whether a resource is in sync with its Git definition and review when it was last synchronized.
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
                       Resources are Platform as Code objects discovered from Git manifests and managed by Axio.
                       They represent the resource definitions stored in Git and their current synchronization state in Axio.
                    </p>

                </div>

            </div>


            <!-- DETAILS + TIP -->

            <div class="resources-bottom-grid">


                <!-- DETAILS -->

                <div class="resource-details-card">

                    <h3>Resource Details (production)</h3>


                    <div class="resource-detail-tabs">

                        <span class="active">Overview</span>
                        <span>Spec</span>
                        <span>Status</span>
                        <span>Metadata</span>
                        <span>Dependencies</span>
                        <span>Events</span>

                    </div>


                    <div class="resource-detail-body">

                        <div class="resource-detail-fields">

                            <div>
                                <strong>Kind:</strong>
                                <span>Environment</span>
                            </div>

                            <div>
                                <strong>Category:</strong>
                                <span>Environment</span>
                            </div>

                            <div>
                                <strong>API Version:</strong>
                                <span class="api-badge">
                                    platform.axio.io/v1
                                </span>
                            </div>

                            <div>
                                <strong>Created At:</strong>
                                <span>Mar 20, 2026, 10:32 AM</span>
                            </div>

                            <div>
                                <strong>Last Sync:</strong>
                                <span>1 minute ago</span>
                            </div>

                            <div>
                                <strong>Sync Status:</strong>
                                <span class="mini-status synced">
                                    ● Synced
                                </span>
                            </div>

                            <div>
                                <strong>Health:</strong>
                                <span class="mini-status healthy">
                                    ● Healthy
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
  workspace: production-ws</code></pre>

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
                        Resources show the current state as reported by Axio.
                        Use Synchronizations to reconcile any drift between
                        Git and the platform.
                    </p>

                    <hr>

                    <h4>Common statuses:</h4>

                    <ul>

                        <li>
                            <strong class="status-green">Healthy</strong>
                            – Resource is up to date with Git
                        </li>

                        <li>
                            <strong class="status-orange">Drifted</strong>
                            – Resource differs from Git
                        </li>

                        <li>
                            <strong class="status-red">Failed</strong>
                            – Resource failed to synchronize
                        </li>

                        <li>
                            <strong class="status-gray">Unknown</strong>
                            – Status is not yet available
                        </li>

                    </ul>

                </div>

            </div>

        </div>

    </div>
