---
layout: default
title: History
parent: Platform as Code
nav_order: 4
has_toc: false
permalink: /axio/platform-as-code/history/
---

# History

<div class="history-page">

    <!-- HEADER -->

    <div class="history-header-row">

        <div class="history-title">

            <h2>GitOps History</h2>

            <p>
                Open <strong>Platform as Code → History</strong> for a read-only audit of every synchronization run —
                validation, approval, reconciliation, and final outcome. Use
                <a href="{{ '/axio/platform-as-code/synchronization/' | relative_url }}">Synchronizations</a>
                for operational tasks such as approving plans, reviewing run details, or cleaning recent run records.
            </p>

        </div>

        <div class="history-prerequisite">

            <div class="history-prerequisite-icon">
                <img src="{{ '/assets/icons/info.svg' | relative_url }}"
                     alt="Info">
            </div>

            <div>

                <h3>Prerequisites</h3>

                <p>
                    At least one synchronization must have run (manual, scheduled, or webhook-triggered).
                    Viewers with <code>pac:read</code> can browse history; Administrators and scoped Members
                    use the same read-only view on this tab.
                </p>

            </div>

        </div>

    </div>

    <div class="important-box" style="margin-bottom: 1.5rem;">
      <div class="important-header">
        <img src="{{ '/assets/icons/triangle-alert.svg' | relative_url }}" alt="Warning">
        <h3>History vs Recent runs</h3>
      </div>
      <p>
        <strong>History</strong> is a compact audit table across synchronization runs. For plan previews,
        Approve/Reject actions, duration, change counts, and run cleanup, use
        <strong>Synchronizations → Recent runs</strong>. Both views draw from the same sync-run records.
      </p>
    </div>


    <!-- MAIN CONTENT -->

    <div class="history-main-grid">


        <!-- LEFT COLUMN -->

        <div class="history-left">


            <!-- WHAT IS HISTORY -->

            <div class="history-info-card">

                <div>

                    <h3>What is History?</h3>

                    <p>
                        GitOps History is an organization-wide audit log of Platform as Code synchronization
                        executions. Each row captures when a run started, which repository and commit were
                        reconciled, how it was triggered, whether validation and approval gates passed, and
                        whether the plan was applied, failed, or rejected.
                    </p>

                </div>

            </div>


            <!-- HISTORY TABLE -->

            <div class="history-info-card" style="margin-top: 1rem;">

                
                <div>
                    <h3>History columns</h3>
                    <ul>
                        <li><strong>Started</strong> — Local date and time the run began</li>
                        <li><strong>Repository</strong> — Connected Git repository name</li>
                        <li><strong>Commit</strong> — Short SHA of the reconciled commit</li>
                        <li><strong>Trigger</strong> — Manual (<strong>Sync now</strong>), scheduled (<strong>Auto</strong>), or webhook</li>
                        <li><strong>Validation</strong> — Schema and dependency check outcome (<code>valid</code>, <code>invalid</code>, <code>partial</code>)</li>
                        <li><strong>Approval</strong> — Whether a plan required or received approval (<code>pending</code>, <code>approved</code>, <code>not_required</code>, etc.)</li>
                        <li><strong>Applied</strong> — <code>Yes</code> when reconciliation completed successfully</li>
                        <li><strong>Failed</strong> — <code>Yes</code> when validation or apply errors occurred</li>
                        <li><strong>Rejected</strong> — <code>Yes</code> when an approver rejected the plan</li>
                        <li><strong>Status</strong> — Overall run state (<code>completed</code>, <code>failed</code>, <code>awaiting approval</code>, <code>running</code>, <code>rejected</code>)</li>
                    </ul>
                </div>

            </div>


            <!-- HOW HISTORY HELPS -->

            <div class="history-help-card">

                <h3>How History Helps</h3>


                <div class="history-help-item">

                    <div class="history-help-icon">✓</div>

                    <div>

                        <h4><strong>Audit trail</strong></h4>

                        <p>
                            Maintain a record of Git-driven platform changes for compliance
                            and post-incident review.
                        </p>

                    </div>

                </div>


                <div class="history-help-item">

                    <div class="history-help-icon">⚒</div>

                    <div>

                        <h4><strong>Troubleshooting</strong></h4>

                        <p>
                            Filter failed or rejected runs, then open the same run under
                            <strong>Synchronizations → Recent runs</strong> for plan details and error messages.
                        </p>

                    </div>

                </div>


                <div class="history-help-item">

                    <div class="history-help-icon">⌁</div>

                    <div>

                        <h4><strong>Trends</strong></h4>

                        <p>
                            Scan validation and approval columns over time to spot recurring
                            schema issues or sensitive-resource approval bottlenecks.
                        </p>

                    </div>

                </div>


                <div class="history-help-item">

                    <div class="history-help-icon">⌑</div>

                    <div>

                        <h4><strong>Traceability</strong></h4>

                        <p>
                            Trace each run back to repository, commit SHA, and trigger type.
                            Commit author and message are included in search even though they are
                            not shown as separate columns.
                        </p>

                    </div>

                </div>

            </div>

        </div>


        <!-- RIGHT COLUMN -->

        <div class="history-right">


            <!-- HISTORY AT A GLANCE -->

            <div class="history-glance-card">

                <h3>History at a Glance</h3>

                <div class="history-glance-flow">


                    <div class="history-glance-item">

                        <div class="history-glance-icon">▷</div>

                        <h4>Triggered</h4>

                        <p>
                            A run starts from <strong>Sync now</strong>,
                            an <strong>Auto</strong> schedule, or a Git webhook.
                        </p>

                    </div>


                    <div class="history-glance-line"></div>


                    <div class="history-glance-item">

                        <div class="history-glance-icon">☷</div>

                        <h4>Discovered &amp; validated</h4>

                        <p>
                            Manifests are fetched from the working directory,
                            parsed, and checked against schemas and policies.
                        </p>

                    </div>


                    <div class="history-glance-line"></div>


                    <div class="history-glance-item">

                        <div class="history-glance-icon">≡</div>

                        <h4>Planned &amp; approved</h4>

                        <p>
                            A sync plan is built; sensitive changes may require
                            approval before apply.
                        </p>

                    </div>


                    <div class="history-glance-line"></div>


                    <div class="history-glance-item">

                        <div class="history-glance-icon">✓</div>

                        <h4>Reconciled</h4>

                        <p>
                            Creates, updates, and staged deletions are applied
                            to platform resources (or the plan is rejected).
                        </p>

                    </div>


                    <div class="history-glance-line"></div>


                    <div class="history-glance-item">

                        <div class="history-glance-icon">▣</div>

                        <h4>Recorded</h4>

                        <p>
                            Outcome, validation, approval, and status appear
                            in GitOps History and Recent runs.
                        </p>

                    </div>


                    <div class="history-glance-line"></div>


                    <div class="history-glance-item">

                        <div class="history-glance-icon">◔</div>

                        <h4>Reviewed</h4>

                        <p>
                            Search and refresh on the History tab, or drill into
                            run details from Synchronizations when action is needed.
                        </p>

                    </div>

                </div>

            </div>


            <!-- TIP -->

            <div class="history-tip-card">

                <div class="history-tip-header">

                    <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
                         alt="Tip">

                    <h3>Tip</h3>

                </div>

                <p>
                    Use the search box to filter by repository, commit SHA, trigger, status, validation,
                    or approval. Click <strong>Refresh</strong> to reload the latest runs. When a run
                    shows <strong>awaiting approval</strong>, switch to
                    <a href="{{ '/axio/platform-as-code/synchronization/' | relative_url }}">Synchronizations</a>
                    to Approve or Reject, or open <strong>Operations → Approvals</strong> for the full request.
                    Administrators can prune old entries with <strong>Clean history</strong> on the
                    Synchronizations tab — that action is not available on History itself.
                </p>

            </div>

        </div>

    </div>

</div>


<div class="page-navigation">

<a
class="nav-button previous"
href="{{ '/axio/platform-as-code/synchronization/' | relative_url }}">

← Synchronizations

</a>

<a
class="nav-button next"
href="{{ '/axio/platform-as-code/' | relative_url }}">

Platform as Code →

</a>

</div>
