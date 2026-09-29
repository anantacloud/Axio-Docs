---
layout: default
title: Compliance
parent: Security & Governance
nav_order: 4
permalink: /axio/security-governance/compliance/
---

<div class="compliance-risk-reports">

  <div class="crr-breadcrumb">
    <span>Security &amp; Governance</span>
    <span class="crumb-separator">›</span>
    <strong>Compliance, risk, and reports</strong>
  </div>

  <header class="crr-page-header">
    <h1>Compliance, risk, and reports</h1>
    <p>
      Three related surfaces for posture reporting — each is a separate page in the product:
      <strong>Compliance</strong> (<code>/compliance</code>),
      <strong>Risk</strong> (<code>/security/risk</code>), and
      <strong>Reports</strong> (<code>/governance/reports</code>).
      Use them for frameworks and assessments, quantified scan-based risk, and auditor-ready exports.
    </p>
  </header>

  <section class="crr-section">
    <table class="crr-table">
      <thead>
        <tr>
          <th>Page</th>
          <th>Route</th>
          <th>Nav permission</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><strong>Compliance</strong></td>
          <td><code>/compliance</code></td>
          <td><code>compliance:manage</code></td>
        </tr>
        <tr>
          <td><strong>Risk</strong></td>
          <td><code>/security/risk</code></td>
          <td><code>governance:read</code></td>
        </tr>
        <tr>
          <td><strong>Reports</strong></td>
          <td><code>/governance/reports</code></td>
          <td><code>governance:read</code></td>
        </tr>
      </tbody>
    </table>
  </section>

  <!-- Compliance -->
  <section class="crr-section compliance-section">

    <div class="crr-main-column">
      <div class="crr-section-title">
        <span class="crr-icon compliance-icon">♢</span>
        <h2>Compliance</h2>
      </div>

      <p>
        Compliance maps technical signals — policy results, RBAC, audit logs, approvals, drift, and manual attestation —
        onto <strong>framework controls and assessments</strong>, not just raw scan findings.
      </p>

      <p><strong>Frameworks on the Compliance page</strong> (six built-in assessments):</p>

      <ul>
        <li><strong>CIS</strong> — CIS Benchmarks</li>
        <li><strong>SOC2</strong> — SOC 2 Trust Services Criteria</li>
        <li><strong>ISO27001</strong> — ISO/IEC 27001 (Annex A)</li>
        <li><strong>PCI</strong> — PCI DSS</li>
        <li><strong>HIPAA</strong> — HIPAA Security Rule</li>
        <li><strong>NIST</strong> — NIST 800-53</li>
      </ul>

      <p>
        Policy Library bundles may reference additional frameworks (CIS cloud benchmarks, SOC 2 packs, PCI, HIPAA,
        Zero Trust, AI Governance, and others) for guardrails; the Compliance page assesses the six frameworks above.
      </p>

      <p><strong>Page sections:</strong></p>

      <ul>
        <li><strong>Executive dashboard</strong> — average score, frameworks assessed, continuous coverage, open exceptions, trends, and recommendations.</li>
        <li><strong>Framework cards</strong> — control count, latest score, pass/fail/risk chips; <strong>Assess</strong> or <strong>View</strong>.</li>
        <li><strong>Recent assessments</strong> — score, risk level, pass / fail / manual / waived counts.</li>
        <li><strong>Continuous compliance</strong> — enable per-framework continuous mode; <strong>Run due assessments now</strong>.</li>
        <li><strong>Exceptions (waivers)</strong> — pending and approved waivers with justification and expiry.</li>
      </ul>

      <p>
        Open an assessment to see control-level results (<strong>PASS</strong>, <strong>FAIL</strong>,
        <strong>MANUAL</strong>, <strong>WAIVED</strong>), evidence, re-assess, generate a markdown report, and export
        JSON, CSV, or Markdown for that assessment.
      </p>

      <div class="crr-callout green-callout">
        <span class="callout-icon">i</span>
        <p>
          Compliance is not a substitute for fixing violations. A high framework score with open critical findings
          still needs remediation on the
          <a href="{{ '/axio/security-governance/' | relative_url }}">Governance Dashboard</a> and
          <a href="{{ '/axio/security-governance/my-findings/' | relative_url }}">My findings</a>.
        </p>
      </div>
    </div>

    <aside class="crr-action-card green-card">
      <h3>What you can do</h3>
      <ul class="check-list">
        <li>Review score and control coverage per framework on the dashboard.</li>
        <li>Run <strong>Assess</strong> on a framework card to generate a new assessment.</li>
        <li>Request a waiver from a failing or manual control inside the assessment dialog (owner approval required).</li>
        <li>Enable continuous compliance per framework and run due assessments on demand.</li>
        <li><strong>Export audit</strong> from the page header — compliance audit bundle (JSON or CSV).</li>
        <li>Export individual assessments as JSON, CSV, or Markdown from the assessment dialog.</li>
      </ul>
    </aside>

  </section>

  <!-- Risk -->
  <section class="crr-section risk-section">

    <div class="crr-main-column">
      <div class="crr-section-title">
        <span class="crr-icon risk-icon">▥</span>
        <h2>Risk</h2>
      </div>

      <p>
        Risk is the <strong>security intelligence command center</strong> for scan-based findings: severity mix,
        trends, heatmaps, top risks, and prioritized remediation recommendations.
      </p>

      <p>
        The enterprise risk model scores each open finding 0–100 using weighted dimensions including
        severity, exploitability, internet exposure, asset criticality, business impact, compliance impact,
        identity exposure, lateral movement risk, finding age, KEV listing, EPSS, public exposure, and runtime activity.
      </p>

      <p><strong>Dashboard areas:</strong></p>

      <ul>
        <li>Overall risk score and severity breakdown (critical / high / medium / low).</li>
        <li>Risk trend and category distribution charts.</li>
        <li>Risk heatmap and top open risks table.</li>
        <li>Remediation recommendations with links back to Security Insights and Governance.</li>
      </ul>

      <div class="crr-callout purple-callout">
        <span class="callout-icon">i</span>
        <p>
          This page does <strong>not</strong> run scans. It aggregates security scan findings (IaC misconfigurations,
          secrets, and related intelligence). <strong>Policy Library violations</strong> are tracked separately —
          open policy violations may appear in the executive summary chips but are remediated via Policy Library
          or the Governance Dashboard.
        </p>
      </div>
    </div>

    <aside class="crr-action-column">
      <div class="crr-action-card purple-card">
        <h3>What you can do</h3>
        <ul class="check-list purple-check">
          <li>Read the current overall risk score and severity counts.</li>
          <li>Review category distribution and heatmap to see what contributes most.</li>
          <li>Prioritize top open risks, then jump to Security Insights or My findings to remediate.</li>
        </ul>
      </div>

      <div class="persona-block">
        <h4>Empty state</h4>
        <p>
          When no scan-based risks exist, run IaC scans from
          <a href="{{ '/axio/security-governance/security-insights/' | relative_url }}">Security Insights → IaC scans</a>.
          Policy evaluation failures are handled under
          <a href="{{ '/axio/security-governance/policies/' | relative_url }}">Policy Library → Evaluate</a>.
        </p>
      </div>
    </aside>

  </section>

  <!-- Reports -->
  <section class="crr-section reports-section">

    <div class="crr-main-column">
      <div class="crr-section-title">
        <span class="crr-icon reports-icon">▤</span>
        <h2>Reports</h2>
      </div>

      <p>
        Open <strong>Security &amp; Governance → Reports</strong> for auditor-ready exports. The page shows posture
        KPIs (pass rate, open violations, active exceptions, enabled policies) for a selectable period
        (<strong>7</strong>, <strong>30</strong>, or <strong>90</strong> days).
      </p>

      <p><strong>Tabs:</strong></p>

      <ul>
        <li><strong>Exports</strong> — unified evidence bundle and standalone policy evidence CSV.</li>
        <li><strong>Persona reports</strong> — audience-specific KPI packs with JSON, CSV, or HTML download.</li>
        <li><strong>Report catalog</strong> — every artifact, format, and which export includes it.</li>
      </ul>

      <div class="crr-callout amber-callout">
        <span class="callout-icon">☆</span>
        <p>
          <strong>Entitlement:</strong> the unified <strong>evidence bundle</strong> and
          <strong>persona exports</strong> require the <strong>governance</strong> platform feature
          (Professional / Enterprise). The standalone <strong>policy evidence CSV</strong> is available with
          <code>governance:read</code>, <code>policy:read</code>, or <code>compliance:read</code>.
        </p>
      </div>

      <div class="crr-callout amber-callout warning-callout">
        <span class="callout-icon">!</span>
        <p>
          If evidence bundle download fails, the usual cause is a missing <strong>governance entitlement</strong>
          on the organization plan — not a permissions bug for org Owner.
        </p>
      </div>
    </div>

    <div class="reports-table-column">
      <h3 class="download-heading">What you can download</h3>

      <table class="crr-table">
        <thead>
          <tr>
            <th>Export</th>
            <th>Contents</th>
            <th>Typical audience</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td class="export-red">Policy evidence (CSV)</td>
            <td>Violations, exceptions, remediations, and posture summary for the selected period</td>
            <td>Platform / DevSecOps</td>
          </tr>
          <tr>
            <td class="export-green">Evidence bundle (JSON manifest)</td>
            <td>Policy CSV, compliance JSON snapshot, governance audit CSV, drift evidence (when licensed), all five persona reports, manifest</td>
            <td>Auditors, GRC</td>
          </tr>
          <tr>
            <td class="export-blue">Persona export</td>
            <td>JSON, CSV, or HTML per persona — <strong>Executive</strong>, <strong>CISO</strong>, <strong>Compliance</strong>, <strong>Auditor</strong>, <strong>DevSecOps</strong></td>
            <td>Role-specific reviews</td>
          </tr>
          <tr>
            <td class="export-green">Compliance audit bundle</td>
            <td>Compliance page <strong>Export audit</strong> — JSON or CSV (separate from Governance Reports evidence bundle)</td>
            <td>Compliance officers</td>
          </tr>
        </tbody>
      </table>
    </div>

    <div class="crr-wide-callout blue-callout">
      <span class="callout-icon">i</span>
      <p>
        <strong>Scheduled evidence (Governance Dashboard → Settings)</strong><br>
        Schedule evidence delivery to a webhook (HTTP POST). Email and S3 delivery may log intent until outbound
        mail and object-store credentials are configured in Administration. Change-management tickets for
        remediations are configured under
        <strong>Administration → Integrations → Change Management</strong>.
      </p>
    </div>

  </section>

  <!-- Exceptions & waivers -->
  <section class="crr-section">

    <div class="crr-main-column">
      <div class="crr-section-title">
        <span class="crr-icon compliance-icon">♢</span>
        <h2>Exceptions and waivers</h2>
      </div>

      <p>Two waiver flows exist — do not confuse them:</p>

      <table class="crr-table">
        <thead>
          <tr>
            <th>Surface</th>
            <th>What it waives</th>
            <th>Approval</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td><strong>Compliance → Exceptions</strong></td>
            <td>A failing or manual <strong>framework control</strong></td>
            <td>Organization <strong>owner</strong> (<code>org:delete</code>) approves or rejects</td>
          </tr>
          <tr>
            <td><strong>Governance Dashboard → Exceptions</strong></td>
            <td>An enforcing <strong>policy violation</strong></td>
            <td>Requires <code>governance:approve</code> (Compliance Officer preset)</td>
          </tr>
        </tbody>
      </table>
    </div>

  </section>

  <!-- Audit trail -->
  <section class="crr-section audit-section">

    <div class="crr-main-column">
      <div class="crr-section-title">
        <span class="crr-icon audit-icon">♢</span>
        <h2>Audit trail</h2>
      </div>

      <p>
        Governance actions (gate changes, exception decisions, break-glass, policy publish) are written to
        <strong>Administration → Audit Logs</strong> (<code>/administration/audit-logs</code>).
        The governance audit trail is also included in the Reports evidence bundle.
      </p>

      <div class="audit-role-note">
        Viewing audit logs requires <code>audit:read</code> (typically Admin roles — not granted to the default Member/Viewer presets).
      </div>
    </div>

    <div class="audit-webhook-card">
      <span class="webhook-icon">⌁</span>
      <p>
        Optional <strong>audit webhook</strong> under Governance Dashboard → Settings streams
        governance-category events to a SIEM (JSON POST).
      </p>
    </div>

  </section>

</div>

<div class="page-navigation">

<a
class="nav-button previous"
href="{{ '/axio/security-governance/policies/' | relative_url }}">

← Policies

</a>

<a
class="nav-button next"
href="{{ '/axio/security-governance/' | relative_url }}">

Governance Dashboard →

</a>

</div>
