---
layout: default
nav_order: 1
parent: Operations
title: Approvals
---

# Approvals

Approvals introduce a manual checkpoint into your deployment workflows. When enabled, specific actions require explicit approval from authorized users before Axio proceeds with the operation.

<div class="operations-callout operations-callout-info">
  <div class="operations-callout-icon">ⓘ</div>
  <div>
    <strong>Why approvals?</strong>
    <p>They help teams enforce change control, meet compliance requirements, and reduce the risk of unintended or unauthorized changes in production environments.</p>
  </div>
</div>

## How it works

When a workflow reaches an approval step, Axio pauses the execution and creates a pending request. Authorized users receive a notification and can review the details before approving or rejecting the request.

<div class="approval-flow">
  <div class="approval-flow-step">
    <strong>Workflow reaches<br>approval step</strong>
  </div>
  <span class="approval-flow-arrow">→</span>

  <div class="approval-flow-step approval-flow-step-yellow">
    <strong>Request created &amp;<br>notified</strong>
  </div>
  <span class="approval-flow-arrow">→</span>

  <div class="approval-flow-step approval-flow-step-purple">
    <strong>User reviews<br>the request</strong>
  </div>
  <span class="approval-flow-arrow">→</span>

  <div class="approval-flow-step approval-flow-step-green">
    <strong>Approved /<br>Rejected</strong>
  </div>
  <span class="approval-flow-arrow">→</span>

  <div class="approval-flow-step approval-flow-step-blue">
    <strong>Workflow<br>continues</strong>
  </div>
</div>

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
      <td>The request is waiting for action from an approver.</td>
    </tr>
    <tr>
      <td><span class="approval-status approval-status-approved">Approved</span></td>
      <td>The request was approved and the workflow can continue.</td>
    </tr>
    <tr>
      <td><span class="approval-status approval-status-rejected">Rejected</span></td>
      <td>The request was rejected and the workflow stops.</td>
    </tr>
  </tbody>
</table>

## Who can approve?

Approval permissions are managed using Axio roles and groups.

- Approvers must have the required permission for the stack or environment.
- Multiple approvers can be required, either sequentially or in parallel.
- You can configure approver groups instead of individual users.

<div class="tip-box">

    <div class="tip-header">

        <img src="{{ '/assets/icons/lightbulb.svg' | relative_url }}"
             alt="Tip">

        <h3>Approvals</h3>

    </div>

    <p>
        When a workflow requires approval, you must assign at least one user or group as an **Environment Owner**. At least one user or group must always            be assigned as an Environment Owner. If Skip self-approval is enabled, the workflow triggerer cannot approve their own deployment.
    </p>

</div>

