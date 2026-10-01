---
layout: default
title: My Findings
parent: Security & Governance
nav_order: 2
permalink: /axio/security-governance/my-findings/  
---

<div class="security-insights-page">

  <div class="security-page-header">
    <h1>My findings</h1>

    <div class="security-admin-note">
      <span class="security-note-icon">i</span>
      <span>
        Open <strong>Security &amp; Governance → My findings</strong>.
      </span>
    </div>

    <p class="security-lead">
      My findings is the <strong>engineer work queue</strong> for open misconfigurations and policy failures
      on repositories and stacks you can access. Run IaC scans from
      <a href="{{ '/axio/security-governance/security-insights/' | relative_url }}">Security Insights</a>,
      fix the infrastructure code, and track violations here until they clear.
      For org-wide posture, exceptions, and analytics, admins use the
      <a href="{{ '/axio/security-governance/' | relative_url }}">Governance Dashboard</a> instead.
    </p>
  </div>

  <section class="security-section">
    <h2>Who should use this page</h2>

    <table class="security-table">
      <thead>
        <tr>
          <th>Audience</th>
          <th>Use My findings when…</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><strong>Engineers / members</strong></td>
          <td>You need to see and fix violations on stacks and repos in your day-to-day work.</td>
        </tr>
        <tr>
          <td><strong>Admins / governance owners</strong></td>
          <td>You want a focused violation list without leaving the security area; use Governance Dashboard for org-wide remediation and settings.</td>
        </tr>
        <tr>
          <td><strong>Viewers</strong></td>
          <td>You need read-only visibility into open violations in scope.</td>
        </tr>
      </tbody>
    </table>

    <div class="security-info-note">
      <span>i</span>
      <p>
        Non-admins see an info banner: organization-wide policy packs, scan defaults, and compliance
        settings are managed by your administrator. You can still scan Git repositories and platform
        resources you have access to from Security Insights.
      </p>
    </div>
  </section>

  <section class="security-section">
    <h2>Open violations explorer</h2>

    <p>
      The <strong>Open violations</strong> panel uses the same violation explorer as the Governance Dashboard,
      tuned for engineers. IaC scan findings appear here after you run a repository or platform scan;
      policy evaluation results appear when assigned policies fail.
    </p>

    <h3>Filters and summaries</h3>

    <table class="security-table">
      <thead>
        <tr>
          <th>Control</th>
          <th>What it does</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><strong>Filter by stack</strong></td>
          <td>Chip filters for stacks with open violations (up to eight shown). Click again to clear, or use <strong>Clear filter</strong>.</td>
        </tr>
        <tr>
          <td><strong>Policy summary chips</strong></td>
          <td>Top policies by violation count — quick context before drilling into rows.</td>
        </tr>
        <tr>
          <td><strong>Time window</strong></td>
          <td>Violations from the last <strong>30 days</strong> (default query period).</td>
        </tr>
        <tr>
          <td><strong>Pagination</strong></td>
          <td>Page through results; change page size (10, 20, 50, or 100 rows).</td>
        </tr>
      </tbody>
    </table>

    <h3>Violation table columns</h3>

    <table class="security-table">
      <thead>
        <tr>
          <th>Column</th>
          <th>Meaning</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><strong>Policy</strong></td>
          <td>Policy name and violation message.</td>
        </tr>
        <tr>
          <td><strong>Resource</strong></td>
          <td>Resource address in IaC (monospace).</td>
        </tr>
        <tr>
          <td><strong>Severity</strong></td>
          <td>Critical, high, medium, or low.</td>
        </tr>
        <tr>
          <td><strong>Trigger</strong></td>
          <td>What produced the evaluation (e.g. scan, deployment gate, policy evaluation).</td>
        </tr>
        <tr>
          <td><strong>Status</strong></td>
          <td>Remediation status: <strong>OPEN</strong>, <strong>IN PROGRESS</strong>, or <strong>RESOLVED</strong>.</td>
        </tr>
      </tbody>
    </table>

  </section>

  <section class="security-section">
    <h2>Empty state</h2>

    <p>
      When there are no open violations for the selected period, the page shows
      <strong>No open violations</strong> with guidance to keep posture current.
    </p>

    <div class="security-action-grid">

      <div class="security-action-card">
        <span class="security-action-icon green">⌕</span>
        <h4>Run IaC scan</h4>
        <p>Primary action — opens Security Insights on the IaC scans tab to scan Git repos or platform resources.</p>
      </div>

    </div>

    <p>
      On the Governance Dashboard, admins see an additional <strong>Evaluate policies</strong> action in the
      empty state; My findings does not show that secondary action (engineers scan IaC instead).
    </p>
  </section>

  <section class="security-section security-findings-section">
    <h2>Typical workflow</h2>

    <ol class="security-numbered-list">
      <li>Open <strong>My findings</strong> and review open violations, optionally filtering by stack.</li>
      <li>Identify the policy and resource address; open the corresponding repo or stack in your editor.</li>
      <li>Fix the IaC misconfiguration or policy failure in source code.</li>
      <li>Re-scan from <strong>Security Insights → IaC scans</strong> (Git live scan, Scan now, or platform on-demand scan).</li>
      <li>Retry deployment if a gate blocked <strong>PLAN</strong> or <strong>APPLY</strong>.</li>
      <li>Confirm the violation moves to <strong>RESOLVED</strong> or drops off the list after the next evaluation.</li>
    </ol>

    <div class="security-two-column">

      <div class="security-capability-card allowed">
        <h3>What you can do</h3>
        <ul>
          <li>Filter and inspect violations on stacks and repos in your work queue.</li>
          <li>Jump to Security Insights to run new scans.</li>
          <li>Open the remediation center for tracking (shared with Governance Dashboard).</li>
        </ul>
      </div>

      <div class="security-capability-card restricted">
        <h3>What you cannot do here</h3>
        <ul>
          <li>Install org-wide policy packs or assign compliance frameworks.</li>
          <li>Change policy gate mode or live-scan defaults.</li>
          <li>Create or approve organization-wide policy exceptions.</li>
          <li>Run org-wide platform scans (reserved for org owner on Security Insights).</li>
        </ul>
      </div>

    </div>
  </section>

  <section class="security-section">
    <h2>My findings vs Governance Dashboard</h2>

    <table class="security-table">
      <thead>
        <tr>
          <th>My findings</th>
          <th>Governance Dashboard</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>Engineer-focused work queue at <code>/security/findings</code></td>
          <td>Org control center at <code>/governance</code></td>
        </tr>
        <tr>
          <td>Open violations table and scan shortcut</td>
          <td>Violations, exceptions, remediation, posture, analytics, settings</td>
        </tr>
        <tr>
          <td>Linked from Security Insights KPIs (non-admin)</td>
          <td>Linked from Security Insights KPIs (admin) and connectors</td>
        </tr>
        <tr>
          <td>No policy pack or gate configuration</td>
          <td>Gate mode, live-scan defaults, evidence export, integrations</td>
        </tr>
      </tbody>
    </table>

    <div class="security-warning">
      <span>⚠</span>
      <p>
        Admins see a footer link to the Governance Dashboard for org-wide remediation, exceptions,
        and posture analytics. Do not disable deploy gates globally to clear a single stack unless
        leadership explicitly approves it.
      </p>
    </div>
  </section>

  <section class="security-section">
    <h2>How findings get here</h2>

    <ol class="security-numbered-list">
      <li><strong>IaC scans</strong> (Security Insights) — Terraform, OpenTofu, Pulumi, CloudFormation, and secrets-in-code checks produce misconfiguration findings.</li>
      <li><strong>Live scan</strong> — continuous evaluation on connected Git repositories surfaces new issues automatically.</li>
      <li><strong>Policy evaluation</strong> — assigned policy packs add guardrails; failures become violations.</li>
      <li><strong>Deploy gates</strong> — enforcing policies during <strong>PLAN/APPLY</strong> record violations when deployments are blocked or warned.</li>
    </ol>

    <div class="security-info-note">
      <span>i</span>
      <p>
        Built-in misconfiguration and secrets checks always run during scans; policy packs are optional
        but add organizational rules on top. Violations from scans and policy evaluation appear together
        in the Open violations table.
      </p>
    </div>
  </section>

  <section class="security-section">
    <h2>Permissions</h2>

    <table class="security-table">
      <thead>
        <tr>
          <th>Permission / role</th>
          <th>Typical access on My findings</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><code>security:read</code></td>
          <td>View My findings and the violations table (required for nav access).</td>
        </tr>
        <tr>
          <td><code>security:manage</code>, <code>policy:manage</code>, or <code>governance:manage</code></td>
          <td>Act on findings — resolve, suppress, or update remediations (viewers stay read-only).</td>
        </tr>
        <tr>
          <td><code>governance:manage</code> or org Admin/Owner</td>
          <td>Same violation explorer with admin empty-state actions; full org tools on Governance Dashboard.</td>
        </tr>
        <tr>
          <td>Viewers</td>
          <td>Read-only access to violations in scope.</td>
        </tr>
      </tbody>
    </table>
  </section>

</div>

<div class="page-navigation">

<a
class="nav-button previous"
href="{{ '/axio/security-governance/security-insights/' | relative_url }}">

← Security Insights

</a>

<a
class="nav-button next"
href="{{ '/axio/security-governance/' | relative_url }}">

Governance Dashboard →

</a>

</div>

