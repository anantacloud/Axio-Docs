---
layout: default
nav_order: 1
parent: Operations
title: Approvals
permalink: /axio/operations/approval/
---

# Approvals

Open **Operations → Approvals** for your decision inbox. Axio routes pending items here when a **workflow gate** pauses a stack deployment, when a **Platform as Code** synchronization plan requires sign-off, or when a **policy**-driven approval is raised.

<div class="operations-callout operations-callout-info">
  <div class="operations-callout-icon">ⓘ</div>
  <div>
    <strong>Why approvals?</strong>
    <p>
      They enforce change control, meet compliance requirements, and reduce the risk of unintended
      production changes — whether from a deployment workflow or a Git-driven platform sync.
    </p>
  </div>
</div>

## Request types

Pending items are grouped into three categories in the inbox:

<table class="approval-lifecycle-table">
  <thead>
    <tr>
      <th>Type</th>
      <th>When it appears</th>
      <th>Typical scope</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Platform as Code</strong></td>
      <td>A Git synchronization plan touches <code>metadata.sensitive: true</code> resources or includes staged removals</td>
      <td>Git synchronization</td>
    </tr>
    <tr>
      <td><strong>Workflow</strong></td>
      <td>A stack deployment reaches an approval stage in its workflow</td>
      <td>Environment or project (e.g. Production)</td>
    </tr>
    <tr>
      <td><strong>Policy</strong></td>
      <td>Other governance or policy-driven approval requests</td>
      <td>Varies by policy</td>
    </tr>
  </tbody>
</table>

## Using the Approvals page

The page has two tabs:

- **Inbox** — Pending requests that need a decision. Use **Assigned to me** to show only items awaiting your action.
- **History** — Completed requests (requires <code>approval:manage</code>). Administrators can remove entries from history.

Each row shows **Request type**, **Name**, **Scope**, **Status**, **Requested by**, **Approved by**, and **Waiting** (age or expiry). Click a row or **Review** to open the detail dialog, add an optional comment, and **Approve** or **Reject**.

Search filters by title, environment, or requester. Pending counts also appear as category chips at the top of the inbox.

## How workflow approvals work

When a stack deployment workflow reaches an approval stage, execution pauses until an authorized approver decides.

<div class="approval-flow">
  <div class="approval-flow-step">
    <strong>Workflow reaches<br>approval stage</strong>
  </div>
  <span class="approval-flow-arrow">→</span>

  <div class="approval-flow-step approval-flow-step-yellow">
    <strong>Request created &amp;<br>notified</strong>
  </div>
  <span class="approval-flow-arrow">→</span>

  <div class="approval-flow-step approval-flow-step-purple">
    <strong>Approver reviews<br>the request</strong>
  </div>
  <span class="approval-flow-arrow">→</span>

  <div class="approval-flow-step approval-flow-step-green">
    <strong>Approved /<br>Rejected</strong>
  </div>
  <span class="approval-flow-arrow">→</span>

  <div class="approval-flow-step approval-flow-step-blue">
    <strong>Workflow<br>continues or stops</strong>
  </div>
</div>

If approved, the workflow resumes. If rejected, the deployment run does not proceed.

## How Platform as Code approvals work

When a synchronization plan requires approval, the sync run stays in **awaiting approval** until decided. Approving applies the Git reconciliation plan; rejecting leaves platform resources unchanged. You can also approve or reject from **Platform as Code → Synchronizations → Recent runs**, which links to the same requests shown here.

## Approval request lifecycle

Requests can be in one of the following states.

<table class="approval-lifecycle-table">
  <thead>
    <tr>
      <th>State</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><span class="approval-status approval-status-pending">Pending</span></td>
      <td>Waiting for an approver decision. May show time remaining until expiry.</td>
    </tr>
    <tr>
      <td><span class="approval-status approval-status-approved">Approved</span></td>
      <td>Approved manually; the workflow or sync plan can proceed.</td>
    </tr>
    <tr>
      <td><span class="approval-status approval-status-rejected">Rejected</span></td>
      <td>Rejected by an approver; the workflow stops or the sync plan is not applied.</td>
    </tr>
    <tr>
      <td><strong>Auto approved</strong></td>
      <td>Approved automatically by policy (no manual action required).</td>
    </tr>
    <tr>
      <td><strong>Emergency approved</strong></td>
      <td>Approved through an emergency break-glass path when enabled.</td>
    </tr>
    <tr>
      <td><strong>Expired</strong></td>
      <td>The approval window elapsed; outcome depends on policy expiry action.</td>
    </tr>
    <tr>
      <td><strong>Canceled</strong></td>
      <td>The underlying run or request was canceled before a decision.</td>
    </tr>
  </tbody>
</table>

Multi-level policies show a stepper in the request detail dialog. Each level may require one or more approvers before the request advances.

## Who can approve?

Permissions and assignment depend on the request type.

### Permissions

Users with either of these organization permissions can access **Operations → Approvals** and decide most requests:

- <code>governance:approve</code>
- <code>approval:manage</code> (also required to view the **History** tab and remove completed entries)

### Workflow deployment gates

For **Workflow** requests (stack deployments):

- Users with <code>governance:approve</code> or <code>approval:manage</code> can decide.
- **Environment owners** — users or groups assigned under **Organization → Environments → Assign owner** — can run workflows in that environment and approve deployment gates when they are eligible approvers.
- **Multi-level** policies may require sequential or parallel sign-off across configured approver lists.

### Platform as Code sync plans

For **Platform as Code** requests:

- Users with <code>pac:manage</code>, <code>approval:manage</code>, or <code>governance:approve</code> can decide.
- Scoped members with <code>pac:read</code> and <code>iac:manage</code> may approve sync plans that affect only resources in their scope.

### Policy and other requests

When an approval policy defines explicit approver lists (users or groups), only assigned approvers — or users with <code>approval:manage</code> / <code>governance:approve</code> — can decide.

<div class="tip-box">

    <div class="tip-header">

        <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
             alt="Tip">

        <h3>Tip — Environment owners &amp; skip self-approval</h3>

    </div>

    <p>
        For <strong>workflow</strong> approvals, assign at least one user or group as an
        <strong>Environment owner</strong> on the target environment. Owners can run workflows there
        and approve deployment gates when required.
    </p>

    <p>
        Enable <strong>Skip self-approval for workflows</strong> (on by default) so the user who
        triggered a deployment cannot approve their own run — even if they are listed as an owner.
        Another owner must approve those requests.
    </p>

    <p>
        Platform as Code sync approvals follow Git sensitivity and PaC permissions instead of
        environment-owner assignment. Use
        <a href="{{ '/axio/platform-as-code/synchronization/' | relative_url }}">Synchronizations</a>
        to monitor runs after you decide.
    </p>

</div>

## Notifications

Approval policies can notify approvers through **in-app**, **email**, **Slack**, or **Microsoft Teams** channels (when configured). The request detail dialog shows prior decisions, optional comments, and notification history for the request.
