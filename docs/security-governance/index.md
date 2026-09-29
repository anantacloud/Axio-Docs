---
layout: default
title: Security & Governance
nav_order: 6
has_children: true
has_toc: false
permalink: /axio/security-governance/
---

<div class="governance-dashboard">

  <div class="governance-top">

    <div class="governance-intro">

      <h1>Security &amp; Governance</h1>

      <p>
        The <strong>Security &amp; Governance</strong> area centralizes policy posture, compliance,
        security scanning, and risk for your organization. Open
        <strong>Security &amp; Governance → Dashboard</strong> (<code>/governance</code>) for the
        governance control center — violations, exceptions, remediation, posture, analytics, and settings.
      </p>

      <div class="governance-note">
        <span class="governance-note-icon">i</span>
        <span>
          Engineers who only need to fix issues on their stacks should start with
          <a href="{{ '/axio/security-governance/my-findings/' | relative_url }}">My Findings</a>
          under <strong>Security &amp; Governance → My findings</strong>.
        </span>
      </div>
    </div>

  <section class="governance-kpis">

    <div class="governance-kpi-card">
      <span class="kpi-icon blue">♢</span>
      <div>
        <h3>Compliance score</h3>
        <strong class="kpi-value blue-text">—</strong>
        <p>Pass rate from policy and compliance posture</p>
        <p>Healthy · Needs attention · At risk</p>
      </div>
    </div>

    <div class="governance-kpi-card">
      <span class="kpi-icon red">♢</span>
      <div>
        <h3>Open violations</h3>
        <strong class="kpi-value red-text">—</strong>
        <p>Total open policy violations</p>
        <p>Click to open the Violations tab</p>
      </div>
    </div>

    <div class="governance-kpi-card">
      <span class="kpi-icon purple">▣</span>
      <div>
        <h3>Active policies</h3>
        <strong class="kpi-value purple-text">—</strong>
        <p>Enabled policies in scope</p>
        <p>Jump to Analytics → policy distribution</p>
      </div>
    </div>

    <div class="governance-kpi-card">
      <span class="kpi-icon orange">!</span>
      <div>
        <h3>Critical / high</h3>
        <strong class="kpi-value orange-text">—</strong>
        <p>Priority violations requiring review</p>
        <p>Filtered view on the Violations tab</p>
      </div>
    </div>

    <div class="governance-kpi-card">
      <span class="kpi-icon green">⌕</span>
      <div>
        <h3>Findings by severity</h3>
        <strong class="kpi-value green-text">—</strong>
        <p>Critical · High · Medium · Low</p>
        <p>Severity strip below the hero banner</p>
      </div>
    </div>

  </section>

  <section class="governance-section">

    <div class="governance-tabs">
      <span class="active">Violations</span>
      <span>Exceptions</span>
      <span>Remediation</span>
      <span>Posture</span>
      <span>Analytics</span>
      <span>Settings</span>

      <div class="governance-filters">
        <span>▣ &nbsp; 7 / 30 / 90 days</span>
        <span>Cloud: All providers⌄</span>
        <span>Framework: All⌄</span>
      </div>
    </div>

    <p style="margin-top: 1rem;">
      Tab counts reflect live data (e.g. <strong>Violations (n)</strong>, <strong>Exceptions (n)</strong>,
      <strong>Remediation (n)</strong>). Use the menu on the dashboard to <strong>Export CSV</strong>,
      <strong>Export PDF</strong>, or run the <strong>Setup wizard</strong>.
    </p>

  </section>

  <section class="governance-chart-grid">

    <div class="governance-chart-card">
      <h2>Analytics — evaluation trend</h2>

      <p>
        On the <strong>Analytics</strong> tab, view passed, failed, and warning signals over the selected
        date range (7, 30, or 90 days).
      </p>

      <a class="chart-link" href="{{ '/axio/security-governance/' | relative_url }}#analytics">Open Analytics tab <span>→</span></a>
    </div>

    <div class="governance-chart-card">
      <h2>Analytics — cloud &amp; framework</h2>

      <p>
        <strong>Cloud distribution</strong> shows policy coverage by provider (AWS, Azure, GCP, and others).
        <strong>Framework coverage</strong> maps controls to CIS, NIST, ISO 27001, SOC 2, PCI DSS, HIPAA, and related frameworks.
      </p>

      <a class="chart-link" href="{{ '/axio/security-governance/' | relative_url }}#analytics">View coverage charts <span>→</span></a>
    </div>

    <div class="governance-chart-card">
      <h2>Analytics — categories &amp; packs</h2>

      <p>
        <strong>Policy distribution</strong> groups policies by governance category (Security, Operational, Cost, Networking, Identity, Compliance).
        <strong>Policy pack usage</strong> shows the most assigned packs. A <strong>findings trend</strong> chart breaks violations down by severity over time.
      </p>

      <a class="chart-link" href="{{ '/axio/security-governance/policy-packs/' | relative_url }}">Browse policy packs <span>→</span></a>
    </div>

  </section>

  <section class="governance-bottom-grid">

    <div class="governance-panel">
      <h2>Dashboard tabs</h2>

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
            <td>Explore open findings by stack, policy, and resource; filter by severity.</td>
          </tr>
          <tr>
            <td class="advisory-text">Exceptions</td>
            <td>Manage time-bound policy waivers with owner approval workflow.</td>
          </tr>
          <tr>
            <td class="failopen-text">Remediation</td>
            <td>Track open remediation tasks, assign owners, sync with Jira when connected.</td>
          </tr>
          <tr>
            <td>Posture</td>
            <td>Policy coverage by cloud and stack; configure scheduled compliance re-evaluation.</td>
          </tr>
          <tr>
            <td>Analytics</td>
            <td>Trends, framework coverage, cloud distribution, pack usage, severity history.</td>
          </tr>
          <tr>
            <td>Settings</td>
            <td>Policy gate, live scanning defaults, audit webhook, evidence export, integrations.</td>
          </tr>
        </tbody>
      </table>
    </div>

    <div class="governance-panel governance-settings">
      <h2>Related pages</h2>

      <ul class="settings-checklist">
        <li><strong>Security Insights</strong> — IaC scanning, live scan history, CIS dashboard</li>
        <li><strong>My findings</strong> — Engineer-focused view of findings on assigned stacks</li>
        <li><strong>Policy Packs</strong> — Install and assign curated policy bundles</li>
        <li><strong>Policy Library</strong> — Browse, evaluate, and manage individual policies</li>
        <li><strong>Compliance</strong> — Framework assessments and compliance posture</li>
        <li><strong>Risk</strong> — Security risk dashboard</li>
        <li><strong>Reports</strong> — Governance and evidence reports</li>
      </ul>
    </div>

  </section>

  <section class="governance-bottom-grid" style="margin-top: 2rem;">

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

      <div class="policy-gate-note">
        ⓘ &nbsp; The policy gate runs during <strong>PLAN</strong> and <strong>APPLY</strong> for pre-deployment validation.
        Enable <strong>per-environment gates</strong> in Settings to override the org default by environment type (e.g. Production vs Development).
      </div>
    </div>

    <div class="governance-panel governance-settings">
      <h2>Settings checklist</h2>

      <ul class="settings-checklist">
        <li>Set the org-wide policy gate mode and optional per-environment overrides.</li>
        <li>Enable live scanning defaults for new repositories (scanner, severity threshold, runner options).</li>
        <li>Configure the audit webhook for governance-category audit events (JSON POST).</li>
        <li>Schedule compliance evidence export to a delivery webhook under Settings → Evidence delivery.</li>
        <li>Review unified schedules for evidence export, compliance assessments, and related jobs.</li>
        <li>Connect change management (e.g. Jira) under <strong>Administration → Integrations → Change Management</strong>.</li>
      </ul>

      <div class="governance-delivery-note">
        <strong>Evidence delivery:</strong> Scheduled evidence bundles are delivered via <strong>webhook</strong>
        (HTTP POST). Email and S3 delivery may log intent until outbound mail and object-store credentials are
        configured in Administration. Jira and other ITSM links are managed under Integrations.
      </div>
    </div>

  </section>

  <section class="governance-section" style="margin-top: 2rem;">
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
          <td><code>governance:manage</code> or org Admin/Owner</td>
          <td>Full dashboard, settings, pack assignment, governance administration</td>
        </tr>
        <tr>
          <td><code>policy:manage</code></td>
          <td>Manage own policy packs; act on findings within scope</td>
        </tr>
        <tr>
          <td><code>security:manage</code></td>
          <td>Resolve or suppress findings and update remediations</td>
        </tr>
        <tr>
          <td>Viewers</td>
          <td>Read-only access to dashboards and findings</td>
        </tr>
      </tbody>
    </table>
  </section>

</div>
