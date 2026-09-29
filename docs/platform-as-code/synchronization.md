---
layout: default
title: Synchronizations
parent: Platform as Code
nav_order: 3
has_toc: false
permalink: /axio/platform-as-code/synchronization/
---

# Synchronizations

<div class="sync-page">

    <!-- HEADER -->

    <div class="sync-header-row">

        <div class="sync-title">

            <h2>Synchronizations</h2>

            <p>
                Open <strong>Platform as Code → Synchronizations</strong> to reconcile Git manifests with platform
                resources in Axio. Synchronizations discover YAML, validate schemas, build a sync plan, apply changes
                (with approval when required), and record results in <strong>Recent runs</strong>.
            </p>

        </div>

        <div class="sync-prerequisite">

            <div class="sync-prerequisite-icon">
                <img src="{{ '/assets/icons/info.svg' | relative_url }}"
                     alt="Info">
            </div>

            <div>

                <h3>Prerequisites</h3>

                <p>
                    A Git repository connected under <strong>Administration → Integrations → Source Control</strong>
                    with manifests under the configured <strong>working directory</strong> (default <code>platform-config</code>).
                    <strong>Administrators</strong> (<code>pac:manage</code>) configure schedules and approve plans;
                    scoped <strong>Members</strong> can run <strong>Sync now</strong> on Admin-configured repositories.
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
        Git is the source of truth for Git-managed resources. The first <strong>Sync now</strong> on a connected
        repository registers it for Platform as Code reconciliation automatically. Removing a manifest from Git may
        stage a <strong>pending removal</strong> — review under <strong>Pending removals</strong> and approve sensitive
        changes before they apply.
      </p>
    </div>


    <!-- MAIN CONTENT -->

    <div class="sync-main-grid">


        <!-- LEFT WORKFLOW -->

        <div class="sync-workflow-card">

            <div class="sync-step-item">

                <div class="sync-step-circle">1</div>

                <div class="sync-step-content">

                    <h3>Connect repository</h3>

                    <p>
                        Connect GitHub, GitLab, Bitbucket, or Azure DevOps under
                        <strong>Administration → Integrations → Source Control</strong>. Ensure the repository
                        <strong>working directory</strong> points at your manifest folder (default <code>platform-config</code>).
                    </p>

                </div>

            </div>


            <div class="sync-step-item">

                <div class="sync-step-circle">2</div>

                <div class="sync-step-content">

                    <h3>Configure schedule (optional)</h3>

                    <p>
                        On the Synchronizations page, enable the <strong>Auto</strong> switch and choose an interval
                        (1 / 5 / 15 / 30 / 60 minutes, every 6 hours, or <strong>Daily</strong> with a local time).
                        Administrators only — Members use Admin-configured schedules.
                    </p>

                </div>

            </div>


            <div class="sync-step-item">

                <div class="sync-step-circle">3</div>

                <div class="sync-step-content">

                    <h3>Run Sync now</h3>

                    <p>
                        Click <strong>Sync now</strong> on a connected repository for an immediate reconciliation.
                        Axio fetches the latest commit, discovers manifests, validates them, and builds a sync plan.
                    </p>

                </div>

            </div>


            <div class="sync-step-item">

                <div class="sync-step-circle">4</div>

                <div class="sync-step-content">

                    <h3>Approve when required</h3>

                    <p>
                        Plans that touch <code>metadata.sensitive: true</code> resources or include pending removals may
                        require approval. Use <strong>Approve</strong> or <strong>Reject</strong> in
                        <strong>Recent runs</strong>, or review under <strong>Operations → Approvals</strong>.
                    </p>

                </div>

            </div>


            <div class="sync-step-item">

                <div class="sync-step-circle">5</div>

                <div class="sync-step-content">

                    <h3>Review results</h3>

                    <p>
                        Inspect <strong>Recent runs</strong> for status, validation, approval state, resources
                        created/updated/deleted, duration, and summary. Open run details for the full plan and apply results.
                    </p>

                </div>

            </div>


            <div class="sync-step-item">

                <div class="sync-step-circle">6</div>

                <div class="sync-step-content">

                    <h3>Resolve pending removals &amp; history</h3>

                    <p>
                        When manifests are deleted from Git, confirm <strong>Pending removals</strong>
                        (delete from platform or keep). Use <strong>Platform as Code → History</strong> for a
                        read-only audit of all past synchronization runs.
                    </p>

                </div>

            </div>

        </div>


        <!-- RIGHT CONTENT -->

        <div class="sync-content">


            <!-- WHAT ARE SYNCHRONIZATIONS -->

            <div class="sync-info-card">

                <div class="sync-info-icon">

                    <img src="{{ '/assets/icons/refresh-cw.svg' | relative_url }}"
                         alt="Synchronizations">

                </div>

                <div>

                    <h3>What are Synchronizations?</h3>

                    <p>
                        Synchronizations compare desired state in Git with live platform resources. For each run Axio
                        discovers YAML/JSON manifests, validates schemas and dependencies, previews a plan, and applies
                        creates, updates, or staged deletions. Successful runs update
                        <a href="{{ '/axio/platform-as-code/resources/' | relative_url }}">Resources</a> inventory and
                        appear in sync history.
                    </p>

                </div>

            </div>


            <!-- REPOSITORIES TABLE -->

            <div class="sync-info-card" style="margin-top: 1rem;">

                <div class="sync-info-icon">
                    <img src="{{ '/assets/icons/clipboard-list.svg' | relative_url }}" alt="Repositories">
                </div>

                <div>
                    <h3>Connected repositories</h3>
                    <p>Each row shows repository, provider, branch, schedule, last sync, and status. Actions:</p>
                    <ul>
                        <li><strong>Auto</strong> — Enable or disable scheduled reconciliation (Administrators)</li>
                        <li><strong>Interval</strong> — Poll frequency when Auto is on</li>
                        <li><strong>Sync now</strong> — Immediate run (Administrators and scoped Members)</li>
                        <li><strong>Remove</strong> — Delete PaC sync configuration for the repo (Administrators)</li>
                    </ul>
                </div>

            </div>


            <!-- WORKFLOW DIAGRAM -->

            <div class="sync-process-card">

                <h3>How Synchronizations Work</h3>

                <div class="sync-process-flow">


                    <div class="sync-process-item">

                        <div class="sync-process-icon">

                            <span class="git-mark">◆</span>

                        </div>

                        <h4>Git Repository</h4>

                        <p>
                            Manifests under<br>
                            the working directory
                        </p>

                    </div>


                    <div class="sync-arrow">→</div>


                    <div class="sync-process-item">

                        <div class="sync-process-icon">

                            <span class="process-symbol">⌕</span>

                        </div>

                        <h4>Discover</h4>

                        <p>
                            Fetch commit and<br>
                            scan manifest files
                        </p>

                    </div>


                    <div class="sync-arrow">→</div>


                    <div class="sync-process-item">

                        <div class="sync-process-icon">

                            <span class="process-symbol">▤</span>

                        </div>

                        <h4>Validate</h4>

                        <p>
                            Schema, dependencies,<br>
                            and policy checks
                        </p>

                    </div>


                    <div class="sync-arrow">→</div>


                    <div class="sync-process-item">

                        <div class="sync-process-icon">

                            <span class="process-symbol">≡</span>

                        </div>

                        <h4>Plan</h4>

                        <p>
                            Preview creates,<br>
                            updates, removals
                        </p>

                    </div>


                    <div class="sync-arrow">→</div>


                    <div class="sync-process-item">

                        <div class="sync-process-icon">

                            <span class="process-symbol">●</span>

                        </div>

                        <h4>Approve</h4>

                        <p>
                            When required for<br>
                            sensitive changes
                        </p>

                    </div>


                    <div class="sync-arrow">→</div>


                    <div class="sync-process-item">

                        <div class="sync-process-icon">

                            <span class="process-symbol">⟳</span>

                        </div>

                        <h4>Reconcile</h4>

                        <p>
                            Apply the plan to<br>
                            the Axio platform
                        </p>

                    </div>


                    <div class="sync-arrow">→</div>


                    <div class="sync-process-item">

                        <div class="sync-process-icon">

                            <span class="process-symbol">▥</span>

                        </div>

                        <h4>Observe</h4>

                        <p>
                            Recent runs,<br>
                            Resources, History
                        </p>

                    </div>

                </div>

            </div>


            <!-- BEST PRACTICES + TIP -->

            <div class="sync-bottom-grid">


                <div class="sync-best-practices">

                    <h3>Best Practices</h3>

                    <ul>

                        <li>Keep manifests focused — one resource per file or logical grouping under <code>platform-config/</code>.</li>

                        <li>Use descriptive commit messages; each sync run records the commit SHA.</li>

                        <li>Enable <strong>Auto</strong> on production repos or run <strong>Sync now</strong> after merging manifest changes.</li>

                        <li>Review <strong>Recent runs</strong> validation and approval columns before assuming apply succeeded.</li>

                        <li>Declare parent resources (Project → Workspace → Environment) before children, or sync all manifests together.</li>

                        <li>Use <code>metadata.sensitive: true</code> deliberately — it triggers approval for Git-driven updates and deletions.</li>

                    </ul>

                </div>


                <div class="sync-tip-card">

                    <div class="sync-tip-header">

                        <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
                             alt="Tip">

                        <h3>Tip</h3>

                    </div>

                    <p>
                        Run <strong>Sync now</strong> after important Git changes or when
                        <a href="{{ '/axio/platform-as-code/resources/' | relative_url }}">Resources</a> show drift.
                        Search repositories and recent runs using the search boxes on this page. For schema reference before
                        editing manifests, use <a href="{{ '/axio/platform-as-code/catalog/' | relative_url }}">Catalog</a>.
                    </p>

                    <hr>

                    <h4>Recent run columns:</h4>

                    <ul>
                        <li><strong>Trigger</strong> — Manual, scheduled, or webhook-driven</li>
                        <li><strong>Approval / Validation</strong> — Plan gate and schema outcome</li>
                        <li><strong>Changed</strong> — Count of resources created, updated, or deleted</li>
                        <li><strong>Summary</strong> — Plan overview; click a row for full details</li>
                    </ul>

                </div>

            </div>

        </div>

    </div>

</div>


<div class="page-navigation">

<a
class="nav-button previous"
href="{{ '/axio/platform-as-code/resources/' | relative_url }}">

← Resources

</a>

<a
class="nav-button next"
href="{{ '/axio/platform-as-code/' | relative_url }}">

Platform as Code →

</a>

</div>
