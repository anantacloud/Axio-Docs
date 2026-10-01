---
layout: default
title: Security Insights
parent: Security & Governance
nav_order: 2
permalink: /axio/security-governance/security-insights/
---

<div class="security-insights-page">

  <div class="security-page-header">
    <h1>Security Insights</h1>

    <div class="security-admin-note">
      <span class="security-note-icon">i</span>
      <span>
        Open <strong>Security &amp; Governance → Security Insights</strong> (<code>/security/insights</code>).
        Admins see extra connectors, repository setup, and org-wide scan defaults.
      </span>
    </div>

    <p class="security-lead">
      Security Insights is the <strong>operations</strong> view for IaC security: live and on-demand scans,
      misconfiguration findings, severity trends, and remediation guidance.
      The <a href="{{ '/axio/security-governance/' | relative_url }}">Governance Dashboard</a> is the
      <strong>policy posture</strong> view — violations, exceptions, compliance, and settings.
      Use both; they are not duplicates.
    </p>
  </div>

  <section class="security-section">
    <h2>Page layout</h2>

    <p>
      Above the main tabs, the page shows quick actions, related links, scan readiness, hero KPIs,
      and a three-step <strong>How Security Insights works</strong> guide. KPI cards are clickable and
      jump to scan history, findings, or repository scanning.
    </p>

    <table class="security-table">
      <thead>
        <tr>
          <th>Area</th>
          <th>What it shows</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><strong>Hero KPIs</strong></td>
          <td>IaC scans run, open findings, critical/high count, repos with live scan enabled.</td>
        </tr>
        <tr>
          <td><strong>Quick actions</strong></td>
          <td>Scan Git repository (or set up repo scanning), scan stack or workspace; admins also connect repositories and open scan defaults.</td>
        </tr>
        <tr>
          <td><strong>Related / Where findings go next</strong></td>
          <td>My findings; Policy packs (when you have <code>policy:manage</code>); admins also see Governance dashboard, Policy library, Live scan settings, and Policy evaluation.</td>
        </tr>
        <tr>
          <td><strong>Scan readiness</strong></td>
          <td>Connected repo count, enabled policy count, and whether built-in scanners or policy packs are active.</td>
        </tr>
      </tbody>
    </table>

    <div class="security-info-note">
      <span>i</span>
      <p>
        Non-admins see an info banner: repository connections, live-scan defaults, and policy pack
        installation are administrator-managed. You can still scan Git repos and platform resources
        you can access — built-in misconfiguration and secrets checks always run.
      </p>
    </div>
  </section>

  <section class="security-section">
    <h2>Overview tab</h2>

    <p>
      The <strong>Overview</strong> tab summarizes IaC security posture from repository and platform scans:
      security score/grade, severity breakdown, findings trend, findings by category and cloud,
      remediation progress, attack-surface summary, security activity timeline, and recommendations.
    </p>

    <p class="security-label">Typical actions:</p>

    <div class="security-action-grid">

      <div class="security-action-card">
        <span class="security-action-icon green">♢</span>
        <h4>Read the score</h4>
        <p>Review the grade and severity mix before a leadership or sprint review.</p>
      </div>

      <div class="security-action-card">
        <span class="security-action-icon purple">✣</span>
        <h4>Follow recommendations</h4>
        <p>Enable live scan on repos, install a policy pack, or close critical findings.</p>
      </div>

      <div class="security-action-card">
        <span class="security-action-icon blue">↗</span>
        <h4>Jump to related areas</h4>
        <p>Use connector links to open Governance Dashboard, Policy Library, Policy Packs, or My findings.</p>
      </div>

      <div class="security-action-card">
        <span class="security-action-icon orange">♧</span>
        <h4>Stay updated</h4>
        <p>Review timeline events and track remediation progress over time.</p>
      </div>

    </div>

    <p>
      When you click <strong>Open findings</strong> or <strong>Critical/high</strong> on the hero KPIs,
      admins are routed to <strong>Governance Dashboard → Violations</strong>; other users go to
      <a href="{{ '/axio/security-governance/my-findings/' | relative_url }}">My findings</a>.
    </p>
  </section>

  <section class="security-section">
    <h2>IaC scans tab</h2>

    <p>
      The <strong>IaC scans</strong> tab is dedicated to infrastructure-as-code scanning — not CVE browsing
      or SBOM generation. It covers two scan sources:
    </p>

    <ul>
      <li><strong>Git repository</strong> — scan synced GitHub/GitLab code (one-time or continuous via live scan).</li>
      <li><strong>Platform resource</strong> — scan IaC from a project, stack, IaC workspace, or environment you can access, or paste content directly.</li>
    </ul>

    <table class="security-table">
      <thead>
        <tr>
          <th>Surface</th>
          <th>What you can do</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><strong>Live IaC scan (repositories)</strong></td>
          <td>Enable or disable live scan per connected repo; run <strong>Scan now</strong> on synced code.</td>
        </tr>
        <tr>
          <td><strong>Live IaC CIS dashboard</strong></td>
          <td>Review CIS-oriented posture from live repository scans.</td>
        </tr>
        <tr>
          <td><strong>Live IaC scan history</strong></td>
          <td>Inspect past live-scan runs and outcomes per repository.</td>
        </tr>
        <tr>
          <td><strong>Platform on-demand scans</strong></td>
          <td>Run and review scans against platform resources; open a row for finding detail.</td>
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
        <li>The org default for new repos is set under <strong>Governance Dashboard → Settings</strong> (live-scan defaults).</li>
        <li>Admins connect repos under <strong>Administration → Integrations → Source Control</strong>.</li>
      </ul>
    </div>

    <p><strong>On-demand scan engines</strong> include:</p>

    <ul>
      <li>Terraform, OpenTofu, Pulumi, CloudFormation</li>
      <li>Secrets in IaC (hardcoded credentials, API keys, tokens)</li>
    </ul>

    <p>
      Policy packs are optional for scanning — built-in misconfiguration and secrets checks always run.
      When policies are assigned, scan and evaluation results also appear as policy violations on the
      Governance Dashboard.
    </p>

    <div class="security-info-note">
      <span>i</span>
      <p>
        <strong>Organization-wide platform scans</strong> are reserved for the org owner.
        Other users scan projects, stacks, workspaces, and environments within their access scope.
      </p>
    </div>
  </section>

  <section class="security-section">
    <h2>Quick actions</h2>

    <p>From the quick-actions bar at the top of Security Insights:</p>

    <div class="security-quick-grid">

      <div class="security-quick-card">
        <span class="quick-icon green">⌕</span>
        <h4>Scan Git repository</h4>
        <p>Opens the IaC scans tab focused on connected repositories (or setup when none are linked).</p>
      </div>

      <div class="security-quick-card">
        <span class="quick-icon purple">☷</span>
        <h4>Scan stack or workspace</h4>
        <p>Opens the on-demand scan dialog for a platform resource you can access.</p>
      </div>

      <div class="security-quick-card">
        <span class="quick-icon blue">▱</span>
        <h4>Connect repository</h4>
        <p>Admins: link GitHub/GitLab under Administration → Source Control.</p>
      </div>

      <div class="security-quick-card">
        <span class="quick-icon orange">▤</span>
        <h4>Scan defaults</h4>
        <p>Admins: open Governance → Settings for live-scan defaults on new repositories.</p>
      </div>

    </div>
  </section>

  <section class="security-section security-findings-section">
    <h2>My findings</h2>

    <p>
      <strong>My findings</strong> is a separate page at <code>/security/findings</code>
      (<strong>Security &amp; Governance → My findings</strong>). It is the engineer work queue:
      <strong>open misconfigurations and policy failures on repositories and stacks you can access</strong>.
      Visibility follows resource access, not the full organization (unless you are org Admin/Owner).
    </p>

    <div class="security-two-column">

      <div class="security-capability-card allowed">
        <h3>What you can do</h3>
        <ul>
          <li>Filter and inspect violations on your stacks and repos.</li>
          <li>Open a finding, fix the IaC, and re-scan from Security Insights.</li>
          <li>Use <strong>Scan Git repository</strong> on My findings to jump to <code>/security/insights?tab=scans&amp;focus=repos</code>.</li>
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
      <p>Non-admins see a banner that organization-wide policy packs, scan defaults, and compliance settings are managed by an administrator. Admins are pointed to the Governance Dashboard for org-wide remediation.</p>
    </div>
  </section>

  <section class="security-section">
    <h2>How scans relate to deploy gates</h2>

    <ol class="security-numbered-list">
      <li>A scan or policy evaluation produces <strong>findings / violations</strong>.</li>
      <li>If the policy is <strong>enforcing</strong> and the org (or environment) gate is <strong class="red-text">Enforce</strong>, <strong>PLAN/APPLY</strong> can <strong>block</strong>.</li>
      <li><strong>Advisory</strong> mode records violations without blocking deployment.</li>
      <li><strong>Fail-open</strong> blocks on enforcing violations but allows deploy when the evaluation engine errors (with warnings).</li>
    </ol>

    <div class="security-info-note">
      <span>i</span>
      <p>
        Fix the code, re-scan, then retry the deployment. Do not disable the gate globally
        to unblock one stack unless that is an explicit leadership decision.
        Per-environment gate overrides are configured under Governance → Settings.
      </p>
    </div>
  </section>

  <section class="security-section">
    <h2>Permissions</h2>

    <table class="security-table">
      <thead>
        <tr>
          <th>Permission / role</th>
          <th>Typical access on Security Insights</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><code>security:read</code></td>
          <td>View Security Insights dashboards, scan history, and findings in scope.</td>
        </tr>
        <tr>
          <td><code>governance:manage</code> or org Admin/Owner</td>
          <td>Connect repos, scan defaults, full connector set, org-wide remediation via Governance Dashboard.</td>
        </tr>
        <tr>
          <td><code>policy:manage</code></td>
          <td>Policy packs connector; act on findings within scope.</td>
        </tr>
        <tr>
          <td><code>security:manage</code></td>
          <td>Resolve or suppress findings and update remediations.</td>
        </tr>
        <tr>
          <td>Viewers</td>
          <td>Read-only access to dashboards and findings.</td>
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
href="{{ '/axio/security-governance/my-findings/' | relative_url }}">

My findings →

</a>

</div>
