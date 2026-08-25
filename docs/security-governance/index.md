---
layout: default
title: Security & Governance
nav_order: 6
has_children: true
has_toc: false
---

<div class="governance-dashboard">

  <div class="governance-top">

    <div class="governance-intro">
      <div class="governance-breadcrumb">
        Security &amp; Governance <span>/</span> <strong>Governance Dashboard</strong>
      </div>

      <h1>Governance Dashboard</h1>

      <div class="governance-meta">
        <span><strong>Route:</strong> <b>/governance</b></span>
        <span><strong>Who:</strong> OWNER and ADMIN (<b>tenant_admin / org_owner</b>)</span>
      </div>

      <p>
        The Governance Dashboard is the control center for <strong>policy posture</strong>
        across the organization. Use it to review open violations, manage policy
        exceptions, track remediation, review posture and analytics, and configure
        governance settings.
      </p>

      <div class="governance-note">
        <span class="governance-note-icon">i</span>
        <span>
          Engineers who only need to fix issues on their stacks should start with
          <a href="./security-insights.md#my-findings">My Findings</a>.
        </span>
      </div>
    </div>


  <section class="governance-kpis">

    <div class="governance-kpi-card">
      <span class="kpi-icon red">♢</span>
      <div>
        <h3>Open Violations</h3>
        <strong class="kpi-value red-text">128</strong>
        <p>23 Critical &nbsp;•&nbsp; 48 High</p>
        <p>57 Medium &nbsp;•&nbsp; 0 Low</p>
      </div>
    </div>

    <div class="governance-kpi-card">
      <span class="kpi-icon orange">!</span>
      <div>
        <h3>Exceptions</h3>
        <strong class="kpi-value orange-text">12</strong>
        <p>6 Active &nbsp;•&nbsp; 4 Expiring soon</p>
        <p>2 Expired</p>
      </div>
    </div>

    <div class="governance-kpi-card">
      <span class="kpi-icon green">⌕</span>
      <div>
        <h3>Remediation</h3>
        <strong class="kpi-value green-text">86</strong>
        <p>42 In progress &nbsp;•&nbsp; 44 To do</p>
        <p>0 Blocked</p>
      </div>
    </div>

    <div class="governance-kpi-card">
      <span class="kpi-icon blue">♢</span>
      <div>
        <h3>Posture</h3>
        <strong class="kpi-value blue-text">78%</strong>
        <p>Pass <strong>186</strong> &nbsp;•&nbsp; Fail 52</p>
        <p>Total <strong>238</strong></p>
      </div>
    </div>

    <div class="governance-kpi-card">
      <span class="kpi-icon purple">↗</span>
      <div>
        <h3>Policy Packs</h3>
        <strong class="kpi-value purple-text">14</strong>
        <p>12 Installed &nbsp;•&nbsp; 2 Outdated</p>
        <p>Coverage <strong>92%</strong></p>
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
        <span>▣ &nbsp; Last 30 days⌄</span>
        <span>Cloud: All⌄</span>
        <span>Framework: All⌄</span>
        <span class="clear-filter">⟳ &nbsp; Clear filters</span>
      </div>
    </div>

  </section>

  <section class="governance-chart-grid">

    <div class="governance-chart-card">
      <h2>Violations by Severity</h2>

      <div class="donut-layout">
        <div class="donut severity-donut">
          <div class="donut-center">
            <strong>128</strong>
            <span>Total</span>
          </div>
        </div>

        <div class="chart-legend">
          <div><i class="dot critical"></i><span>Critical</span><b>23</b><small>(18%)</small></div>
          <div><i class="dot high"></i><span>High</span><b>48</b><small>(38%)</small></div>
          <div><i class="dot medium"></i><span>Medium</span><b>57</b><small>(44%)</small></div>
          <div><i class="dot low"></i><span>Low</span><b>0</b><small>(0%)</small></div>
        </div>
      </div>

      <a class="chart-link" href="#">View all violations <span>→</span></a>
    </div>

    <div class="governance-chart-card">
      <h2>Violations by Cloud</h2>

      <div class="donut-layout">
        <div class="donut cloud-donut">
          <div class="donut-center">
            <strong>128</strong>
            <span>Total</span>
          </div>
        </div>

        <div class="chart-legend">
          <div><i class="dot aws"></i><span>AWS</span><b>62</b><small>(48%)</small></div>
          <div><i class="dot azure"></i><span>Azure</span><b>34</b><small>(27%)</small></div>
          <div><i class="dot gcp"></i><span>GCP</span><b>22</b><small>(17%)</small></div>
          <div><i class="dot others"></i><span>Others</span><b>10</b><small>(8%)</small></div>
        </div>
      </div>

      <a class="chart-link" href="#">View by cloud <span>→</span></a>
    </div>

    <div class="governance-chart-card">
      <h2>Top Policy Categories</h2>

      <div class="category-chart">
        <div><span>Access Control</span><div class="bar"><i style="width:100%"></i></div><b>32</b></div>
        <div><span>Network Security</span><div class="bar"><i style="width:88%"></i></div><b>28</b></div>
        <div><span>Data Protection</span><div class="bar"><i style="width:75%"></i></div><b>24</b></div>
        <div><span>Logging &amp; Monitoring</span><div class="bar"><i style="width:56%"></i></div><b>18</b></div>
        <div><span>Encryption</span><div class="bar"><i style="width:50%"></i></div><b>16</b></div>
      </div>

      <a class="chart-link" href="#">View all categories <span>→</span></a>
    </div>

  </section>

  <section class="governance-bottom-grid">

    <div class="governance-panel">
      <h2>Policy Gate Modes</h2>

      <table class="governance-table">
        <thead>
          <tr>
            <th>Mode</th>
            <th>Deploy Behavior</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td class="enforce-text">Enforce</td>
            <td>Blocks deployment when enforcing violations exist or gate evaluation fails.</td>
          </tr>
          <tr>
            <td class="advisory-text">Advisory</td>
            <td>Records violations but does not block deployment.</td>
          </tr>
          <tr>
            <td class="failopen-text">Fail-open</td>
            <td>Blocks on enforcing violations; evaluation errors become warnings.</td>
          </tr>
        </tbody>
      </table>

      <div class="policy-gate-note">
        ⓘ &nbsp; The policy gate runs during <strong>PLAN / APPLY</strong> for pre-deployment validation.
      </div>
    </div>

    <div class="governance-panel governance-settings">
      <h2>Settings Checklist</h2>

      <ul class="settings-checklist">
        <li>Set the policy gate mode and environment-aware overrides if required.</li>
        <li>Enable live scanning defaults for new repositories.</li>
        <li>Connect the audit webhook for governance-category audit events or configure evidence delivery.</li>
        <li>Review unified schedules for policy compliance, evidence export, and framework assessments.</li>
        <li>Confirm Change Management integrations such as Jira or ServiceNow under Administration → Integrations.</li>
      </ul>

      <div class="governance-delivery-note">
        <strong>Evidence delivery:</strong> Email and S3 delivery log intent until the required mail and object-store
        credentials are configured. <strong>Webhook</strong> delivery sends a live HTTP POST.
      </div>
    </div>

  </section>

</div>
