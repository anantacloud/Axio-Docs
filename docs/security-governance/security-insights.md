---
layout: default
title: Security Insights
parent: Security & Governance
nav_order: 1
---

<div class="security-insights-page">

  <div class="security-page-header">
    <h1>Security Insights and findings</h1>

    <div class="security-meta">
      <span><strong>Routes:</strong> <b>/security/insights</b> &nbsp; <b>/security/findings</b></span>
      <span><strong>Who:</strong> All signed-in org members with <b>security:read</b>.</span>
    </div>

    <div class="security-admin-note">
      <span class="security-note-icon">i</span>
      <span>Admins see extra connectors and org-wide actions.</span>
    </div>

    <p class="security-lead">
      Security Insights is the <strong>operations</strong> view: scans, vulnerabilities,
      SBOMs, executive risk snapshot, and live IaC scan status.
      Governance Dashboard is the <strong>policy posture</strong> view. Use both;
      they are not duplicates.
    </p>
  </div>

  <section class="security-section">
    <h2>Security Insights</h2>

    <h3>Overview tab</h3>

    <p>
      Shows organization security score/grade, executive snapshot, attack-surface
      summary, open remediations, recent timeline events, and recommendations.
    </p>

    <p class="security-label">Typical actions:</p>

    <div class="security-action-grid">

      <div class="security-action-card">
        <span class="security-action-icon green">♢</span>
        <h4>Read the score</h4>
        <p>Read the score and severity mix before a leadership review.</p>
      </div>

      <div class="security-action-card">
        <span class="security-action-icon purple">✣</span>
        <h4>Follow recommendations</h4>
        <p>Follow recommendations (enable live scan, install a pack, close critical findings).</p>
      </div>

      <div class="security-action-card">
        <span class="security-action-icon blue">↗</span>
        <h4>Jump to key areas</h4>
        <p>Jump to Governance Dashboard, Policy Library, or Policy Packs via the connector cards.</p>
      </div>

      <div class="security-action-card">
        <span class="security-action-icon orange">♧</span>
        <h4>Stay updated</h4>
        <p>Review timeline events and stay informed about security changes.</p>
      </div>

    </div>
  </section>

  <section class="security-section">
    <h3>Scans tab</h3>

    <p>Embedded security operations: <strong>Scans</strong>, <strong>CVE Database</strong>, and <strong>SBOM</strong>.</p>

    <table class="security-table">
      <thead>
        <tr>
          <th>Surface</th>
          <th>What you can do</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><strong>Scans</strong></td>
          <td>Start or review IaC / image / config scans; inspect findings.</td>
        </tr>
        <tr>
          <td><strong>CVE Database</strong></td>
          <td>Browse known CVEs; sync live data from OSV (<strong>SEED</strong> vs <strong>OSV</strong> source).</td>
        </tr>
        <tr>
          <td><strong>SBOM</strong></td>
          <td>Inspect software bills of materials and component inventory.</td>
        </tr>
      </tbody>
    </table>

    <div class="security-live-card">
      <div class="security-live-title">
        <span>✓</span>
        <strong>Live scan per Git repository</strong>
      </div>

      <ul>
        <li>Enable <strong>live scan</strong> on connected repos so new IaC is evaluated without a manual click every time.</li>
        <li>Open <code>/security/insights?tab=scans</code> (also used after Governance live-scan bookmarks).</li>
        <li>Org default for new repos is set under <strong>Governance Dashboard → Settings</strong>.</li>
      </ul>
    </div>

    <p>
      Scan engines in the product include IaC-oriented checks
      (Terraform, OpenTofu, Pulumi, CloudFormation, secrets-in-code).
      Results become findings and, when policies are assigned, policy violations.
    </p>
  </section>

  <section class="security-section">
    <h3>Quick actions</h3>

    <p>From the Insights hero/quick-actions:</p>

    <div class="security-quick-grid">

      <div class="security-quick-card">
        <span class="quick-icon green">⌕</span>
        <h4>Run a scan</h4>
        <p>Open the Scans tab and run an IaC scan.</p>
      </div>

      <div class="security-quick-card">
        <span class="quick-icon purple">☷</span>
        <h4>My findings</h4>
        <p>Open My findings for a personal work queue.</p>
      </div>

      <div class="security-quick-card">
        <span class="quick-icon blue">▱</span>
        <h4>Policy Packs</h4>
        <p>Admins: open Policy Packs.</p>
      </div>

      <div class="security-quick-card">
        <span class="quick-icon orange">▤</span>
        <h4>Policy Library</h4>
        <p>Admins: open Policy Library.</p>
      </div>

      <div class="security-quick-card">
        <span class="quick-icon teal">⚙</span>
        <h4>Settings &amp; eval</h4>
        <p>Admins: open live-scan settings or policy evaluation.</p>
      </div>

    </div>
  </section>

  <section class="security-section security-findings-section">
    <h2>My findings</h2>

    <div class="security-route-badge">
      <strong>Route:</strong> /security/findings
    </div>

    <p>
      This is the engineer work queue: <strong>open misconfigurations and policy failures
      on repositories and stacks you can access</strong>. It is scoped by resource visibility,
      not the full org (unless you are OWNER/ADMIN).
    </p>

    <div class="security-two-column">

      <div class="security-capability-card allowed">
        <h3>What you can do</h3>
        <ul>
          <li>Filter and inspect violations that belong to your stacks/repos.</li>
          <li>Open a finding, fix the IaC, and re-scan.</li>
          <li>Start a new scan via <strong>Security Insights → Scans</strong>.</li>
        </ul>
      </div>

      <div class="security-capability-card restricted">
        <h3>What you cannot do here</h3>
        <ul>
          <li>Install org-wide policy packs or change compliance frameworks.</li>
          <li>Change gate mode or live-scan defaults.</li>
          <li>Approve exceptions for the whole organization.</li>
        </ul>
      </div>

    </div>

    <div class="security-warning">
      <span>⚠</span>
      <p>Non-admins see a banner that organization-wide packs and compliance are managed by an administrator.</p>
    </div>
  </section>

  <section class="security-section">
    <h2>How scans relate to deploy gates</h2>

    <ol class="security-numbered-list">
      <li>A scan or policy evaluation produces <strong>findings / violations</strong>.</li>
      <li>If the policy is <strong>enforcing</strong> and the org (or environment) gate is <strong class="red-text">Enforce</strong>, <strong>PLAN/APPLY</strong> can <strong>block</strong>.</li>
      <li><strong>Advisory mode</strong> still records the same issues so you can fix them without stopping the pipeline.</li>
    </ol>

    <div class="security-info-note">
      <span>i</span>
      <p>
        Fix the code, re-scan, then retry the deployment. Do not disable the gate globally
        to unblock one stack unless that is an explicit leadership decision.
      </p>
    </div>
  </section>

  <section class="security-section security-cve-section">
    <h2>CVE sync</h2>

    <p>
      Admins with <strong class="green-text">security:manage</strong> (or equivalent governance manage)
      can sync CVEs from OSV. The CVE table labels the <strong>data source</strong> so seed/demo rows
      are distinguishable from live feed rows.
    </p>
  </section>

</div>
