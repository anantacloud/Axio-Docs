---
layout: default
nav_order: 2
parent: Operations
title: Drift Detection
---

# Drift Detection

Drift Detection helps you ensure that your live infrastructure matches what you declared in code. Axio continuously compares the actual deployed state with the desired state defined in your workflow.

<div class="operations-callout operations-callout-info">
  <div class="operations-callout-icon">ⓘ</div>
  <div>
    <strong>Why drift detection?</strong>
    <p>
      Infrastructure can change outside of your workflows — manual updates,
      emergency fixes, or external tools. Drift detection identifies these
      differences so you can fix them early and keep environments reliable.
    </p>
  </div>
</div>

## How it works

Axio compares your desired state with the actual state using your configured IaC engine.

<div class="drift-flow">
  <div class="drift-flow-step drift-flow-blue">
    <div class="drift-flow-icon">&lt;/&gt;</div>
    <strong>1. Desired State</strong>
    <span>Defined in code<br>(Terraform, OpenTofu, Pulumi)</span>
  </div>

  <span class="drift-flow-arrow">→</span>

  <div class="drift-flow-step drift-flow-green">
    <div class="drift-flow-icon">☁</div>
    <strong>2. Actual State</strong>
    <span>Live infrastructure<br>in your cloud</span>
  </div>

  <span class="drift-flow-arrow">→</span>

  <div class="drift-flow-step drift-flow-purple">
    <div class="drift-flow-icon">⌕</div>
    <strong>3. Drift Detection</strong>
    <span>Axio compares<br>the two states</span>
  </div>

  <span class="drift-flow-arrow">→</span>

  <div class="drift-result">
    <div class="drift-result-row drift-result-ok">
      <span class="drift-result-icon">✓</span>
      <span><strong>No Drift</strong><small>Everything is in sync</small></span>
    </div>
    <div class="drift-result-row drift-result-alert">
      <span class="drift-result-icon">!</span>
      <span><strong>Drift Detected</strong><small>Differences found</small></span>
    </div>
  </div>
</div>


# Drift Detection Dashboard

The Drift Detection page provides two views for monitoring infrastructure drift.

## Watched

The **Watched** tab shows workspaces and stacks that are currently being monitored for drift.

| Field | Description |
|---|---|
| **Stack** | Name of the stack being monitored |
| **Workspace** | Workspace containing the stack |
| **Engine** | IaC engine used by the stack, such as Terraform |
| **Level** | Scope at which drift detection is configured |
| **Status** | Result of the latest drift check |
| **Last checked** | Time when the stack was last checked |
| **Schedule** | Frequency at which the stack is checked |
| **Actions** | Available actions for the watched stack |

## All Sources

The **All Sources** tab shows the available infrastructure sources that can be selected for drift monitoring.

---

<div class="drift-two-column">

<div class="drift-section">

<h2>Watch a Stack</h2>

<p>Use <strong>Watch stack</strong> to add a stack to Drift Detection.</p>

<p>Once a stack is being watched, Axio periodically runs a drift check according to its configured schedule.</p>

<p>A watched stack appears in the <strong>Watched</strong> tab with its current status and last check time.</p>

<div class="drift-info-card">

<strong>Watch a stack</strong>

<p>Add a stack to Drift Detection to automatically check it according to the configured schedule.</p>

</div>

</div>

<div class="drift-section">

<h2>Drift Check Status</h2>

<p>Each watched stack displays the result of its most recent check.</p>

<div class="drift-status-card drift-success">

<strong>✓ Check Passed</strong>

<p>The latest drift check completed successfully and the infrastructure is consistent with the declared configuration.</p>

</div>

<div class="drift-status-card drift-failed">

<strong>× Check Failed</strong>

<p>A drift check failed or could not complete successfully.</p>

<p>When checks fail, open the affected workspace and run a new check.</p>

</div>

</div>

</div>

<div class="drift-note">

<strong>Note:</strong> A failed check can mean that the IaC plan or preview could not complete successfully on the assigned runner. Investigate the workspace and runner configuration before treating the result as confirmed infrastructure drift.

</div>

---

<div class="drift-two-column">

<div class="drift-section">

<h2>Check Schedule</h2>

<p>Drift Detection can run checks at a configured interval.</p>

<div class="drift-schedule-grid">

<div class="drift-schedule-card">

<strong>Every 15 minutes</strong>

<span>Frequent drift monitoring</span>

</div>

<div class="drift-schedule-card">

<strong>Every hour</strong>

<span>Hourly drift monitoring</span>

</div>

</div>

<p>The <strong>Schedule</strong> column shows the configured frequency for each watched stack.</p>

</div>

<div class="drift-section">

<h2>Manage Watched Stacks</h2>

<p>The <strong>Actions</strong> column provides controls for managing a watched stack.</p>

<p>Depending on the available actions, you can:</p>

<ul>
  <li>Run a new drift check</li>
  <li>Remove the stack from Drift Detection</li>
</ul>

<p>Removing a stack from the watched list stops scheduled drift checks for that stack.</p>

</div>

</div>

---

<h2>Troubleshooting Failed Checks</h2>

<p>If a drift check shows <strong>Check failed</strong>:</p>

<div class="drift-steps">

<ol>
  <li>Open the affected workspace.</li>
  <li>Review the stack configuration.</li>
  <li>Check whether the IaC plan or preview can complete successfully.</li>
  <li>Verify that the assigned runner is available and has the required IaC engine.</li>
  <li>Run a new drift check.</li>
  <li>Review the updated status.</li>
</ol>

</div>

<div class="drift-warning">

<strong>Important</strong>

<p>A failed drift check does not necessarily mean that infrastructure has drifted. The check itself may have failed because the IaC plan or preview could not complete.</p>

</div>

---

<div class="drift-analytics">

<div>

<h2>Trends &amp; Analytics</h2>

<p>Use <strong>Show trends &amp; analytics</strong> to review drift-related trends and analytics for monitored infrastructure.</p>

<p>This can help identify recurring check failures and understand drift detection activity over time.</p>

</div>

<div class="drift-analytics-button">
Show trends &amp; analytics →
</div>

</div>