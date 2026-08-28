---
layout: default
title: Audit Logs
parent: Administration
nav_order: 9
---

<div class="audit-page">

  <header class="audit-hero">
    <h1>Administration — Audit Logs</h1>
    <p>Searchable, exportable record of platform activity.</p>
  </header>

  <div class="audit-info">
    <span class="audit-info-icon">i</span>
    <span>Overview: <code>ADMINISTRATION.md</code></span>
    <b>•</b>
    <span>Role-focused subset: Roles &amp; Access → Audit</span>
    <b>•</b>
    <span>Personal recent events: <code>My Profile</code></span>
  </div>

  <section class="audit-kpis">
    <div class="audit-kpi">
      <div class="audit-kpi-icon blue">▣</div>
      <div><span>Total events</span><strong>128,540</strong><small>All time</small></div>
    </div>
    <div class="audit-kpi">
      <div class="audit-kpi-icon green">□</div>
      <div><span>Today's events</span><strong>1,248</strong><small class="positive">↑ 18% vs yesterday</small></div>
    </div>
    <div class="audit-kpi">
      <div class="audit-kpi-icon red">!</div>
      <div><span>Failed events</span><strong>342</strong><small class="negative">0.27% of total</small></div>
    </div>
    <div class="audit-kpi">
      <div class="audit-kpi-icon orange">◇</div>
      <div><span>Security events</span><strong>678</strong><small class="orange-text">0.53% of total</small></div>
    </div>
    <div class="audit-kpi">
      <div class="audit-kpi-icon purple">♙</div>
      <div><span>Authentication</span><strong>5,234</strong><small class="purple-text">4.07% of total</small></div>
    </div>
    <div class="audit-kpi">
      <div class="audit-kpi-icon blue">⚙</div>
      <div><span>Configuration changes</span><strong>2,891</strong><small class="purple-text">2.25% of total</small></div>
    </div>
  </section>

  <section class="audit-analytics">
    <h2>Analytics <small>(Last 30 days)</small></h2>

    <div class="audit-chart-grid">

      <div class="audit-chart">
        <h3>Events over time</h3>
        <div class="line-chart">
          <div class="line-grid"></div>
          <svg viewBox="0 0 360 145" preserveAspectRatio="none" aria-hidden="true">
            <polyline points="5,112 22,67 39,88 56,76 73,107 90,55 107,72 124,43 141,60 158,95 175,116 192,91 209,50 226,73 243,81 260,108 277,72 294,86 311,43 328,69 345,56 355,72"
              fill="none" stroke="#6b35ef" stroke-width="3"/>
          </svg>
          <div class="chart-axis x"><span>May 20</span><span>May 27</span><span>Jun 3</span><span>Jun 10</span><span>Jun 17</span></div>
        </div>
      </div>

      <div class="audit-chart">
        <h3>By category</h3>
        <div class="donut-row">
          <div class="donut category-donut"></div>
          <div class="legend">
            <span><i class="dot d1"></i>Authentication <b>28.5%</b></span>
            <span><i class="dot d2"></i>Authorization <b>16.2%</b></span>
            <span><i class="dot d3"></i>Stacks <b>12.7%</b></span>
            <span><i class="dot d4"></i>Deployments <b>10.3%</b></span>
            <span><i class="dot d5"></i>Policies <b>8.6%</b></span>
            <span><i class="dot d6"></i>Others <b>23.7%</b></span>
          </div>
        </div>
      </div>

      <div class="audit-chart">
        <h3>By status</h3>
        <div class="donut-row">
          <div class="donut status-donut"></div>
          <div class="legend">
            <span><i class="dot success"></i>Success <b>93.1%</b></span>
            <span><i class="dot failure"></i>Failure <b>5.2%</b></span>
            <span><i class="dot warning"></i>Warning <b>1.2%</b></span>
            <span><i class="dot info"></i>Info <b>0.5%</b></span>
          </div>
        </div>
      </div>

      <div class="audit-chart">
        <h3>By action</h3>
        <div class="bar-chart">
          <div><i style="height:92%"></i><span>Create</span></div>
          <div><i style="height:72%"></i><span>Update</span></div>
          <div><i style="height:50%"></i><span>Delete</span></div>
          <div><i style="height:35%"></i><span>Login</span></div>
          <div><i style="height:24%"></i><span>Approve</span></div>
          <div><i style="height:15%"></i><span>Others</span></div>
        </div>
      </div>

    </div>
  </section>

  <section class="audit-workspace">

    <div class="audit-toolbar">
      <div class="audit-search">⌕ <span>Search events...</span></div>
      <button>Category⌄</button>
      <button>▣ &nbsp; Last 30 days⌄</button>
      <button>Action⌄</button>
      <button>Status⌄</button>
      <button>Severity⌄</button>
      <button>Resource type⌄</button>
      <button>⚱ &nbsp; More filters</button>
    </div>

    <div class="audit-filter-row">
      <span class="filter-count">ⓘ Filters applied: 2</span>
      <span>Status: All ×</span>
      <span>Severity: All ×</span>
      <button class="reset">Resort ↻</button>
    </div>

    <div class="audit-export">
      <button>⇩ &nbsp; Export CSV</button>
      <button>⇩ &nbsp; Export JSON</button>
    </div>

    <div class="audit-table-wrap">
      <table class="audit-table">
        <thead>
          <tr>
            <th>Time</th><th>Category</th><th>Action</th><th>Status</th>
            <th>Severity</th><th>User</th><th>Resource</th><th>Source</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Jun 18, 2025 10:24:31 AM</td>
            <td class="link">Authentication</td>
            <td>Login</td>
            <td><span class="badge success">✓ Success</span></td>
            <td><span class="severity info">INFO</span></td>
            <td>sarah.kapoor@acme.com</td>
            <td>User</td><td>Web UI</td>
          </tr>
          <tr>
            <td>Jun 18, 2025 10:23:11 AM</td>
            <td class="link">Stacks</td>
            <td>Update</td>
            <td><span class="badge success">✓ Success</span></td>
            <td><span class="severity info">INFO</span></td>
            <td>amit.rawat@acme.com</td>
            <td>aws-prod-vpc</td><td>Web UI</td>
          </tr>
          <tr>
            <td>Jun 18, 2025 10:21:02 AM</td>
            <td class="deploy">Deployments</td>
            <td>Create</td>
            <td><span class="badge success">✓ Success</span></td>
            <td><span class="severity info">INFO</span></td>
            <td>neha.tiwari@acme.com</td>
            <td>deploy-9f7ab2</td><td>Runner</td>
          </tr>
          <tr>
            <td>Jun 18, 2025 10:18:45 AM</td>
            <td class="policy">Policies</td>
            <td>Delete</td>
            <td><span class="badge failure">× Failure</span></td>
            <td><span class="severity high">HIGH</span></td>
            <td>raj.sharma@acme.com</td>
            <td>policy-allow-ssh</td><td>Web UI</td>
          </tr>
          <tr>
            <td>Jun 18, 2025 10:17:33 AM</td>
            <td class="authz">Authorization</td>
            <td>Access Denied</td>
            <td><span class="badge failure">× Failure</span></td>
            <td><span class="severity critical">CRITICAL</span></td>
            <td>john.doe@acme.com</td>
            <td>project-alpha</td><td>API</td>
          </tr>
        </tbody>
      </table>
    </div>

  </section>

</div>

