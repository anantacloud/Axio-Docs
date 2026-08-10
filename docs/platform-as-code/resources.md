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
                as managed by Axio.
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
                    Platform as Code must be enabled and a Git repository connected
                    to view resources.
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

                    <h3>View Resource Inventory</h3>

                    <p>
                        View all resources discovered from Git and their current
                        status in Axio.
                    </p>

                </div>

            </div>


            <div class="resources-step-item">

                <div class="resources-step-circle">2</div>

                <div class="resources-step-content">

                    <h3>Filter and Search</h3>

                    <p>
                        Filter by category, resource kind, status, or search by
                        name to find the resources you need.
                    </p>

                </div>

            </div>


            <div class="resources-step-item">

                <div class="resources-step-circle">3</div>

                <div class="resources-step-content">

                    <h3>Inspect Resource Details</h3>

                    <p>
                        View detailed information about a resource including
                        spec, status, metadata, and dependencies.
                    </p>

                </div>

            </div>


            <div class="resources-step-item">

                <div class="resources-step-circle">4</div>

                <div class="resources-step-content">

                    <h3>Track Sync Status</h3>

                    <p>
                        Check the sync status, last synchronization time, and
                        health of each resource.
                    </p>

                </div>

            </div>


            <div class="resources-step-item">

                <div class="resources-step-circle">5</div>

                <div class="resources-step-content">

                    <h3>Drill Down to Related Resources</h3>

                    <p>
                        Navigate to related resources and dependencies from the
                        resource details view.
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
                        Resources are the Platform as Code objects discovered from
                        Git and managed in Axio. They reflect the desired state
                        defined in your YAML manifests along with their current
                        status in the platform.
                    </p>

                </div>

            </div>


            <!-- RESOURCE TABLE -->

            <div class="resources-table-card">

                <div class="resources-card-title-row">

                    <h3>Resources</h3>

                </div>


                <div class="resources-filters">

                    <div class="resources-search">

                        <span class="resources-search-icon">⌕</span>

                        <input
                            type="text"
                            placeholder="Search resources...">

                    </div>


                    <select>

                        <option>All Categories</option>

                        <option>Organization</option>
                        <option>Project</option>
                        <option>Workspace</option>
                        <option>Environment</option>
                        <option>Stack</option>

                    </select>


                    <select>

                        <option>All Statuses</option>

                        <option>Healthy</option>
                        <option>Degraded</option>
                        <option>Unhealthy</option>
                        <option>Unknown</option>

                    </select>


                    <div class="resources-updated">

                        <span>⟳</span>

                        Last updated: 1m ago

                    </div>

                </div>


                <div class="resources-table-wrapper">

                    <table class="resources-table">

                        <thead>

                            <tr>

                                <th>Name</th>
                                <th>Kind</th>
                                <th>Category</th>
                                <th>Status</th>
                                <th>Sync Status</th>
                                <th>Last Sync</th>
                                <th>Actions</th>

                            </tr>

                        </thead>

                        <tbody>

                            <tr>

                                <td>
                                    <a href="#">production</a>
                                </td>

                                <td>Environment</td>

                                <td>Environment</td>

                                <td>
                                    <span class="resource-status healthy">
                                        ● Healthy
                                    </span>
                                </td>

                                <td>
                                    <span class="sync-status">
                                        Synced
                                    </span>
                                </td>

                                <td>1m ago</td>

                                <td class="resource-action">⋮</td>

                            </tr>


                            <tr>

                                <td>
                                    <a href="#">production-ws</a>
                                </td>

                                <td>Workspace</td>

                                <td>Workspace</td>

                                <td>
                                    <span class="resource-status healthy">
                                        ● Healthy
                                    </span>
                                </td>

                                <td>
                                    <span class="sync-status">
                                        Synced
                                    </span>
                                </td>

                                <td>2m ago</td>

                                <td class="resource-action">⋮</td>

                            </tr>


                            <tr>

                                <td>
                                    <a href="#">platform-team</a>
                                </td>

                                <td>Project</td>

                                <td>Project</td>

                                <td>
                                    <span class="resource-status healthy">
                                        ● Healthy
                                    </span>
                                </td>

                                <td>
                                    <span class="sync-status">
                                        Synced
                                    </span>
                                </td>

                                <td>3m ago</td>

                                <td class="resource-action">⋮</td>

                            </tr>


                            <tr>

                                <td>
                                    <a href="#">axio-platform</a>
                                </td>

                                <td>Organization</td>

                                <td>Organization</td>

                                <td>
                                    <span class="resource-status healthy">
                                        ● Healthy
                                    </span>
                                </td>

                                <td>
                                    <span class="sync-status">
                                        Synced
                                    </span>
                                </td>

                                <td>5m ago</td>

                                <td class="resource-action">⋮</td>

                            </tr>


                            <tr>

                                <td>
                                    <a href="#">prod-stack</a>
                                </td>

                                <td>Stack</td>

                                <td>Stack</td>

                                <td>
                                    <span class="resource-status degraded">
                                        ● Degraded
                                    </span>
                                </td>

                                <td>
                                    <span class="sync-status">
                                        Synced
                                    </span>
                                </td>

                                <td>7m ago</td>

                                <td class="resource-action">⋮</td>

                            </tr>

                        </tbody>

                    </table>

                </div>


                <div class="resources-pagination-row">

                    <span>
                        Showing 1 to 5 of 24 resources
                    </span>

                    <div class="resources-pagination">

                        <button>‹</button>

                        <button class="active">1</button>

                        <button>2</button>
                        <button>3</button>
                        <button>4</button>
                        <button>5</button>

                        <button>›</button>

                    </div>

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
                            – Resource is up to date
                        </li>

                        <li>
                            <strong class="status-orange">Degraded</strong>
                            – Issues detected that need attention
                        </li>

                        <li>
                            <strong class="status-red">Unhealthy</strong>
                            – Resource is in a failed state
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
