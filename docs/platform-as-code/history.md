---
layout: default
title: History
parent: Platform as Code
nav_order: 4
---

<div class="announcement-box">
    <div class="announcement-content">

        <div>
            <h2>History</h2>

            <p>
                Review the activity and outcomes of Platform as Code
                synchronization and resource changes.
            </p>

        </div>

    </div>
</div>

<div class="prerequisite-header">

    <img src="{{ '/assets/icons/info.svg' | relative_url }}"
         alt="Info">

    <h3>What is History?</h3>

</div>

<p>
    History provides an audit-style view of Platform as Code activity. Use it
    to understand what changed, which Git commit introduced the change, and
    whether the synchronization completed successfully.
</p>

<div class="step-left">

    <div class="step-item">

        <div class="step-circle-ui">1</div>

        <div class="step-content">

            <h3>Open History</h3>

            <p>
                Navigate to <strong>Platform as Code → History</strong> to
                review previous synchronization and resource activity.
            </p>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">2</div>

        <div class="step-content">

            <h3>Identify the Change</h3>

            <p>
                Use the available activity details to identify the affected
                resource, repository, manifest, or Git commit.
            </p>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">3</div>

        <div class="step-content">

            <h3>Review the Outcome</h3>

            <p>
                Check whether the operation succeeded, failed, requires
                approval, or resulted in another synchronization state.
            </p>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">4</div>

        <div class="step-content">

            <h3>Troubleshoot Failed Changes</h3>

            <p>
                When a synchronization fails, use the history details together
                with the corresponding Git commit and manifest to identify the
                cause.
            </p>

        </div>

    </div>

    <div class="step-item">

        <div class="step-circle-ui">5</div>

        <div class="step-content">

            <h3>Trace GitOps Activity</h3>

            <p>
                Use History together with Resources and Synchronizations to
                trace how a Git change moved through the Platform as Code
                workflow.
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
    When troubleshooting a resource, start with the resource status, then check
    the associated synchronization and use History to trace the Git commit
    responsible for the change.
</p>

<a class="nav-button previous"
   href="{{ '/docs/platform-as-code/synchronizations/' | relative_url }}">
    ← Synchronizations
</a>

<a class="nav-button next"
   href="{{ '/docs/platform-as-code/' | relative_url }}">
    Platform as Code →
</a>
