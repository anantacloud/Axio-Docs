---
layout: default
title: Compliance
parent: Security & Governance
nav_order: 3
---

<div class="compliance-risk-reports">

  <div class="crr-breadcrumb">
    <span>Security &amp; Governance</span>
    <span class="crumb-separator">›</span>
    <strong>Compliance, risk, and reports</strong>
  </div>

  <header class="crr-page-header">
    <h1>Compliance, risk, and reports</h1>
    <p>These three pages are for posture reporting: frameworks and assessments, quantified risk, and files you hand to auditors.</p>
  </header>

  <!-- Compliance -->
  <section class="crr-section compliance-section">

    <div class="crr-main-column">
      <div class="crr-section-title">
        <span class="crr-icon compliance-icon">♢</span>
        <h2>Compliance</h2>
      </div>

      <div class="crr-meta">
        <span><strong>Route:</strong> <b>/compliance</b></span>
        <span><strong>Who:</strong> OWNER and ADMIN</span>
      </div>

      <p>
        Compliance maps technical policy results onto <strong>frameworks</strong>
        (controls and assessments), not just raw scan findings.
      </p>

      <p>
        Frameworks available in intelligence/compliance views include
        <strong>CIS, NIST CSF, SOC 2, PCI DSS, HIPAA, GDPR, ISO 27001,
        FedRAMP, CMMC, DORA, NIS2, and Kubernetes CIS.</strong>
        The Compliance page lists framework summaries, posture, assessments,
        exceptions, and schedules.
      </p>

      <div class="crr-callout green-callout">
        <span class="callout-icon">i</span>
        <p>
          Compliance is not a substitute for fixing violations. A high framework
          score with open critical findings still needs remediation on
          <a href="./governance-dashboard.md">Dashboard</a> and
          <a href="./security-insights.md#my-findings">My findings</a>.
        </p>
      </div>
    </div>

    <aside class="crr-action-card green-card">
      <h3>What you can do</h3>
      <ul class="check-list">
        <li>Review score and control coverage per framework.</li>
        <li>Create or update an <strong>assessment</strong> (period, scope, notes).</li>
        <li>Record or review exceptions tied to compliance (OWNER is required to approve/reject some waivers).</li>
        <li>Export compliance reports (download from the page actions).</li>
        <li>Use scheduled assessments so evidence does not depend on a manual click.</li>
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

      <div class="crr-meta">
        <span><strong>Route:</strong> <b>/security/risk</b></span>
        <span><strong>Who:</strong> OWNER and ADMIN</span>
      </div>

      <p>
        Risk is the <strong>command center</strong> for severity mix, trends,
        heatmaps, and prioritized remediation. It uses the security intelligence
        risk model (score 0–100 across dimensions such as severity, exploitability,
        internet exposure, asset criticality, compliance impact, identity exposure,
        KEV/EPSS, and finding age).
      </p>

      <div class="crr-callout purple-callout">
        <span class="callout-icon">i</span>
        <p>
          This page does not run scans. It aggregates scan and intelligence data.
          If the page is empty, run scans and enable live scan first.
        </p>
      </div>
    </div>

    <aside class="crr-action-column">
      <div class="crr-action-card purple-card">
        <h3>What you can do</h3>
        <ul class="check-list purple-check">
          <li>Read the current risk score and how it changed over the selected period.</li>
          <li>See which categories or assets contribute most.</li>
          <li>Prioritize remediation (what to fix first), then jump back to findings or Governance Dashboard.</li>
        </ul>
      </div>

      <div class="persona-block">
        <h4>Persona reports available</h4>
        <div class="persona-tags">
          <span>EXECUTIVE</span>
          <span>CISO</span>
          <span>CLOUD_SECURITY</span>
          <span>PLATFORM_ENGINEERING</span>
          <span>KUBERNETES</span>
          <span>DEVSECOPS</span>
          <span>COMPLIANCE</span>
          <span>OPERATIONS</span>
          <span>DEVELOPER</span>
          <span>AUDITOR</span>
        </div>
        <p>Governance Reports expose a subset for download (see Reports below).</p>
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

      <div class="crr-meta">
        <span><strong>Route:</strong> <b>/governance/reports</b></span>
        <span><strong>Who:</strong> OWNER and ADMIN</span>
      </div>

      <div class="crr-callout amber-callout">
        <span class="callout-icon">☆</span>
        <p>
          <strong>Entitlement:</strong> full <strong>evidence bundle</strong> and
          <strong>persona pack</strong> require the <strong>governance</strong>
          feature (Professional / Enterprise). CSV policy export of recent
          evaluations is available more broadly.
        </p>
      </div>

      <div class="crr-callout amber-callout warning-callout">
        <span class="callout-icon">!</span>
        <p>
          If evidence bundle download fails, the usual cause is missing
          <strong>governance entitlement</strong> on the organization plan—not
          a permissions bug for OWNER.
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
            <td class="export-red">Policy report (CSV)</td>
            <td>Evaluations / violations for the last 30 days</td>
            <td>Platform / DevSecOps</td>
          </tr>
          <tr>
            <td class="export-green">Evidence bundle</td>
            <td>Combined pack: policy CSV, compliance JSON, audit CSV, persona files</td>
            <td>Auditors, GRC</td>
          </tr>
          <tr>
            <td class="export-blue">Persona export</td>
            <td>JSON, CSV, or HTML for EXECUTIVE, CISO, COMPLIANCE, AUDITOR, DEVSECOPS</td>
            <td>Role-specific reviews</td>
          </tr>
        </tbody>
      </table>
    </div>

    <div class="crr-wide-callout blue-callout">
      <span class="callout-icon">i</span>
      <p>
        <strong>Scheduled evidence (Dashboard settings)</strong><br>
        You can schedule evidence delivery (webhook live; email and S3 until credentials
        exist) and run a schedule on demand. Configure under
        <strong>Governance Dashboard → Settings</strong>. Change-management tickets for
        remediations are configured under
        <strong>Administration → Integrations → Change Management</strong>.
      </p>
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
        Governance actions (gate changes, exception decisions, break-glass,
        policy publish) are written to
        <strong>Administration → Audit Logs</strong>
        (<code>/administration/audit-logs</code>).
      </p>

      <div class="audit-role-note">
        <strong>VIEWER</strong> has <code>audit:read</code>;
        <strong>MEMBER</strong> does not.
      </div>
    </div>

    <div class="audit-webhook-card">
      <span class="webhook-icon">⌁</span>
      <p>Optional <strong>audit webhook</strong> streams governance-category events to a SIEM.</p>
    </div>

  </section>

</div>
