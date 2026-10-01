---
layout: default
title: Break Glass
parent: Security & Governance
nav_order: 6
permalink: /axio/security-governance/break-glass/
---

<div class="compliance-risk-reports">

  <header class="crr-page-header">
    <h1>Break glass</h1>
    <p>
      Break glass provides <strong>TTL-bound emergency role grants</strong> at project, workspace, or environment scope.
      Sessions are logged immutably in the audit trail. This is separate from policy exceptions and compliance waivers.
    </p>
  </header>

  <section class="crr-section">
    <h2>Where to find it</h2>


<table class="crr-table">
  <thead>
    <tr>
      <th>Surface</th>
      <th>Route / path</th>
      <th>Primary use</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Break glass page</strong></td>
      <td><code>/governance/break-glass</code></td>
      <td>View active and historical break glass sessions (Platform Administrators).</td>
    </tr>
    <tr>
      <td><strong>Administration → Roles &amp; Access</strong></td>
      <td><strong>Break Glass</strong> tab</td>
      <td>Create, terminate, and delete sessions; full management UI.</td>
    </tr>
  </tbody>
</table>

<div class="crr-callout amber-callout">
  <span class="callout-icon">!</span>
  <p>
    Break glass is <strong>restricted to Platform Administrators</strong>. The standalone page shows a read-only
    session table when you have access; session creation and termination are managed from Roles &amp; Access.
  </p>
</div>


  </section>

  <section class="crr-section compliance-section">
    <div class="crr-main-column">
      <div class="crr-section-title">
        <span class="crr-icon compliance-icon">♢</span>
        <h2>What break glass does</h2>
      </div>


  <p>
    During an incident, a Platform Administrator can grant a temporary role to a user, team, or synced group
    at a scoped resource so they can perform emergency work without a permanent role change.
  </p>

  <ul>
    <li>Each session has a <strong>time-to-live (TTL)</strong> — 15 minutes to 24 hours.</li>
    <li>An <strong>incident number</strong> and <strong>justification</strong> are required when activating.</li>
    <li>Sessions <strong>expire automatically</strong> when TTL elapses.</li>
    <li>All actions are written to <strong>Administration → Audit Logs</strong>.</li>
  </ul>
</div>

<aside class="crr-action-card green-card">
  <h3>Supported scopes</h3>
  <ul class="check-list">
    <li><strong>Project</strong></li>
    <li><strong>Workspace</strong></li>
    <li><strong>Environment</strong></li>
  </ul>
  <p style="margin-top: 1rem;">
    Grant targets: individual user, team, or synced SCIM group. Assign a role from the org role catalog
    (Compliance Officer is excluded from break glass role pickers).
  </p>
</aside>


  </section>

  <section class="crr-section">
    <h2>Session table columns</h2>


<p>On <code>/governance/break-glass</code> and the Roles &amp; Access tab, sessions show:</p>

<table class="crr-table">
  <thead>
    <tr>
      <th>Column</th>
      <th>Meaning</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Scope</strong></td>
      <td>Project, workspace, or environment.</td>
    </tr>
    <tr>
      <td><strong>Resource</strong></td>
      <td>Scoped resource identifier.</td>
    </tr>
    <tr>
      <td><strong>Grant</strong></td>
      <td>User email (or principal) receiving the temporary role.</td>
    </tr>
    <tr>
      <td><strong>Role</strong></td>
      <td>Role granted for the session.</td>
    </tr>
    <tr>
      <td><strong>Incident</strong></td>
      <td>Incident or ticket reference number.</td>
    </tr>
    <tr>
      <td><strong>Started / Expires</strong></td>
      <td>Session window.</td>
    </tr>
    <tr>
      <td><strong>Remaining</strong></td>
      <td>Minutes left before automatic expiry.</td>
    </tr>
    <tr>
      <td><strong>Assigned by</strong></td>
      <td>Administrator who activated the session.</td>
    </tr>
    <tr>
      <td><strong>Status</strong></td>
      <td><strong>ACTIVE</strong> or expired/terminated state.</td>
    </tr>
  </tbody>
</table>


  </section>

  <section class="crr-section">
    <h2>Typical workflow</h2>

<ol class="security-numbered-list">
  <li>Confirm the incident requires temporary elevated access (not a permanent role change).</li>
  <li>Open <strong>Administration → Roles &amp; Access → Break Glass</strong>.</li>
  <li>Select scope (project, workspace, or environment), target user/team/group, role, TTL, incident number, and justification.</li>
  <li>Activate the session; the grantee receives temporary permissions until expiry.</li>
  <li>Monitor active sessions on the Break Glass tab or <code>/governance/break-glass</code>.</li>
  <li><strong>Terminate</strong> early when the incident is resolved, or let TTL expire.</li>
  <li>Review audit logs for the full session history.</li>
</ol>


  </section>

  <section class="crr-section">
    <h2>Break glass vs other waivers</h2>


<table class="crr-table">
  <thead>
    <tr>
      <th>Mechanism</th>
      <th>What it grants</th>
      <th>Where</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Break glass</strong></td>
      <td>Temporary <strong>role</strong> at project/workspace/environment scope</td>
      <td>Roles &amp; Access → Break Glass</td>
    </tr>
    <tr>
      <td><strong>Policy exceptions</strong></td>
      <td>Time-bound waiver for an enforcing <strong>policy violation</strong></td>
      <td>
        <a href="{{ '/axio/security-governance/governance-dashboard/' | relative_url }}">
          Governance Dashboard → Exceptions
        </a>
      </td>
    </tr>
    <tr>
      <td><strong>Compliance waivers</strong></td>
      <td>Approval to mark a <strong>framework control</strong> as waived</td>
      <td>
        <a href="{{ '/axio/security-governance/compliance/' | relative_url }}">
          Compliance → Exceptions
        </a>
      </td>
    </tr>
  </tbody>
</table>


  </section>

  <section class="crr-section audit-section">
    <div class="crr-main-column">
      <div class="crr-section-title">
        <span class="crr-icon audit-icon">♢</span>
        <h2>Audit and governance</h2>
      </div>

  <p>
    Break glass activation, termination, and expiry events appear in
    <strong>Administration → Audit Logs</strong> (<code>/administration/audit-logs</code>).
    Viewing audit logs requires <code>audit:read</code>.
  </p>

  <p>
    Active break glass session counts may also surface as alerts on the Roles &amp; Access hub when sessions are in progress.
  </p>
</div>

<div class="audit-webhook-card">
  <span class="webhook-icon">⌁</span>
  <p>
    For day-to-day policy posture, use the
    <a href="{{ '/axio/security-governance/governance-dashboard/' | relative_url }}">
      Governance Dashboard
    </a>.
    Break glass is for audited emergency access only — not a substitute for fixing policy violations.
  </p>
</div>


  </section>

</div>
