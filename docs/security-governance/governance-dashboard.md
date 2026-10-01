---
layout: default
title: Governance Dashboard
parent: Security & Governance
nav_order: 5
permalink: /axio/security-governance/governance-dashboard/
---

<div class="governance-dashboard">

<div class="governance-intro">

  <h1>Governance Dashboard</h1>

  <p>

    Open <strong>Security &amp; Governance → Dashboard</strong> for the org-wide

    governance control center: compliance posture, policy violations, exceptions, remediation, analytics, and settings.

    Requires <code>governance:read</code> (org Admin/Owner or users with governance read access).

  </p>

  <div class="governance-note">

    <span class="governance-note-icon">i</span>

    <span>

      Engineers who only fix issues on their stacks should use

      <a href="{{ '/axio/security-governance/my-findings/' | relative_url }}">My findings</a>

      instead of the full dashboard.

    </span>

  </div>

</div>

<section class="governance-section">

  <h2>Page layout</h2>

  <table class="governance-table">

    <thead>

      <tr>

        <th>Area</th>

        <th>What it shows</th>

      </tr>

    </thead>

    <tbody>

      <tr>

        <td><strong>Quick actions</strong></td>

        <td>Review violations (when any exist), Run IaC scan, Manage policies, Policy packs.</td>

      </tr>

      <tr>

        <td><strong>Filters</strong></td>

        <td>Date range (7 / 30 / 90 days), cloud provider (All, AWS, Azure, GCP, OCI, DigitalOcean), framework (All, CIS, NIST, ISO 27001, SOC 2, PCI DSS, HIPAA).</td>

      </tr>

      <tr>

        <td><strong>Hero banner</strong></td>

        <td>Compliance score with posture status (Looking good / Needs attention / At risk), open violations, active policies, critical/high count.</td>

      </tr>

      <tr>

        <td><strong>Severity strip</strong></td>

        <td>Critical, high, medium, and low violation counts with link to the Violations tab.</td>

      </tr>

      <tr>

        <td><strong>Recommended next steps</strong></td>

        <td>Contextual suggestions (e.g. review violations, manage exceptions, run scans).</td>

      </tr>

      <tr>

        <td><strong>Main tabs</strong></td>

        <td>Violations, Exceptions, Remediation, Posture, Analytics, Settings — tab labels show live counts where applicable.</td>

      </tr>

    </tbody>

  </table>

  <p>

    Use the header <strong>⋮</strong> menu to <strong>Export CSV</strong> (KPI snapshot),

    open the <strong>Setup wizard</strong>, or <strong>Export PDF</strong> (browser print).

    The refresh button reloads all dashboard data.

  </p>

</section>

<section class="governance-section">

  <h2>Hero KPIs</h2>

  <p>Click a KPI card to jump to the related tab or filtered view:</p>

  <table class="governance-table">

    <thead>

      <tr>

        <th>KPI</th>

        <th>Meaning</th>

        <th>Click action</th>

      </tr>

    </thead>

    <tbody>

      <tr>

        <td><strong>Compliance score</strong></td>

        <td>Overall posture percentage; status band at 90%+ (healthy), 70–89% (attention), below 70% (at risk).</td>

        <td>Analytics → compliance score trend</td>

      </tr>

      <tr>

        <td><strong>Open violations</strong></td>

        <td>Total open policy violations in scope.</td>

        <td>Violations tab</td>

      </tr>

      <tr>

        <td><strong>Active policies</strong></td>

        <td>Enabled policies contributing to evaluation.</td>

        <td>Analytics → policy distribution</td>

      </tr>

      <tr>

        <td><strong>Critical / high</strong></td>

        <td>Priority violations requiring review.</td>

        <td>Violations tab filtered to critical and high</td>

      </tr>

    </tbody>

  </table>

</section>

<section class="governance-section">

  <h2>Tabs</h2>

  <table class="governance-table">

    <thead>

      <tr>

        <th>Tab</th>

        <th>Purpose</th>

      </tr>

    </thead>

    <tbody>

      <tr>

        <td class="enforce-text">Violations</td>

        <td>Org-wide <strong>Open violations</strong> explorer — drill down by stack, policy, and resource; filter by severity from hero KPIs. Uses admin audience (includes <strong>Evaluate policies</strong> in empty state).</td>

      </tr>

      <tr>

        <td class="advisory-text">Exceptions</td>

        <td>Time-bound <strong>policy waivers</strong> with approval workflow. Requires <code>governance:approve</code> to approve (Compliance Officer preset).</td>

      </tr>

      <tr>

        <td class="failopen-text">Remediation</td>

        <td>Remediation center — track enforcing violations, assign owners, sync with external tickets when change management is connected.</td>

      </tr>

      <tr>

        <td>Posture</td>

        <td>Policy coverage by cloud and stack; <strong>Scheduled compliance</strong> panel for automatic policy re-evaluation interval.</td>

      </tr>

      <tr>

        <td>Analytics</td>

        <td>Evaluation trend, compliance score trend, policy distribution by category, framework coverage, cloud distribution, policy pack usage, findings severity trend.</td>

      </tr>

      <tr>

        <td>Settings</td>

        <td>Policy gate, live-scan defaults, audit webhook, evidence delivery schedules, integrations — grouped by purpose.</td>

      </tr>

    </tbody>

  </table>

</section>

<section class="governance-section">

  <h2>Setup wizard</h2>

  <p>

    Open from the header <strong>⋮ → Setup wizard</strong> or Settings when onboarding is incomplete.

    Four steps:

  </p>

  <ol class="settings-checklist">

    <li><strong>Install pack</strong> — install the recommended SOC 2 demo policy pack (<code>soc2-pack</code>) or continue with existing policies.</li>

    <li><strong>Gate mode</strong> — set org-wide <strong>Enforce</strong>, <strong>Advisory</strong>, or <strong>Fail-open</strong> for PLAN/APPLY.</li>

    <li><strong>Evaluate</strong> — run an organization-wide policy evaluation (or skip).</li>

    <li><strong>Done</strong> — mark onboarding complete; review violations or export from Reports.</li>

  </ol>

  <p>

    Manual setup alternative: use

    <a href="{{ '/axio/security-governance/policies/' | relative_url }}">Policy Packs</a> and

    <a href="{{ '/axio/security-governance/policies/' | relative_url }}">Policy Library</a>,

    then return to finish gate mode and evaluation.

  </p>

</section>

<section class="governance-bottom-grid">

  <div class="governance-panel">

    <h2>Policy gate modes</h2>

    <table class="governance-table">

      <thead>

        <tr>

          <th>Mode</th>

          <th>Deploy behavior</th>

        </tr>

      </thead>

      <tbody>

        <tr>

          <td class="enforce-text">Enforce</td>

          <td>Blocks deployment when policies fail or the gate cannot evaluate.</td>

        </tr>

        <tr>

          <td class="advisory-text">Advisory</td>

          <td>Records violations but does not block deployment.</td>

        </tr>

        <tr>

          <td class="failopen-text">Fail-open</td>

          <td>Blocks on enforcing violations; evaluation engine errors allow deploy with warnings.</td>

        </tr>

      </tbody>

    </table>

  </div>

  <div class="governance-panel governance-settings">

    <h2>Settings tab checklist</h2>

    <ul class="settings-checklist">

      <li>Org-wide policy gate mode and optional per-environment overrides.</li>

      <li>Live scanning defaults for new repositories (enabled, scanners, fail-on severity, runner, notify on failure).</li>

      <li>Audit webhook URL for governance-category events (JSON POST).</li>

      <li>Unified schedules — evidence export, compliance assessments, and related jobs.</li>

      <li>Integrations panel for governance-related connectors.</li>

      <li>Related links: IaC runtime images (Administration → IaC Engines), Jira/evidence (Administration → Integrations → Change Management).</li>

    </ul>

    <div class="governance-delivery-note">

      <strong>Evidence delivery:</strong> Scheduled evidence bundles are delivered via <strong>webhook</strong>

      (HTTP POST). Email and S3 delivery may log intent until credentials are configured in Administration.

    </div>

  </div>

</section>

<section class="governance-section">

  <h2>Permissions</h2>

  <table class="governance-table">

    <thead>

      <tr>

        <th>Permission / role</th>

        <th>Typical access</th>

      </tr>

    </thead>

    <tbody>

      <tr>

        <td><code>governance:read</code></td>

        <td>View the dashboard, analytics, and read-only tabs.</td>

      </tr>

      <tr>

        <td><code>governance:manage</code> or org Admin/Owner</td>

        <td>Change settings, gate mode, webhooks, and schedules.</td>

      </tr>

      <tr>

        <td><code>governance:approve</code></td>

        <td>Approve policy exceptions on the Exceptions tab.</td>

      </tr>

      <tr>

        <td><code>security:manage</code>, <code>policy:manage</code></td>

        <td>Act on findings and remediations where permitted.</td>

      </tr>

    </tbody>

  </table>

</section>

</div>

<div class="page-navigation">

<a

class="nav-button previous"

href="{{ '/axio/security-governance/' | relative_url }}">

← Security &amp; Governance

</a>

<a

class="nav-button next"

href="{{ '/axio/security-governance/security-insights/' | relative_url }}">

Security Insights →

</a>

</div>
