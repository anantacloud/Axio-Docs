---
layout: default
title: Audit Logs
parent: Administration
nav_order: 9
permalink: /axio/administration/audit-logs/
---

<div class="audit-page">

  <header class="audit-hero">
    <h1>Administration — Audit Logs</h1>
    <p>Searchable, exportable enterprise audit trail for authentication, deployments, drift, governance, RBAC, and administration.</p>
  </header>

  <div class="audit-info">
    <span class="audit-info-icon">i</span>
    <span>Open <strong>Administration → Audit Logs</strong> at <code>/administration/audit-logs</code></span>
    <b>•</b>
    <span>Legacy <code>?section=audit</code> under Roles &amp; Access redirects here</span>
    <b>•</b>
    <span>Personal recent sign-ins: <a href="{{ '/axio/administration/profile/' | relative_url }}">My Profile</a> → Activity &amp; insights</span>
  </div>

  <section>
    <h2>Permissions</h2>
    <div class="table-wrap">
      <table>
        <thead>
          <tr><th>Action</th><th>Permission</th></tr>
        </thead>
        <tbody>
          <tr><td>View audit logs, dashboard, analytics, export</td><td><code>audit:read</code></td></tr>
          <tr><td>Edit retention &amp; archive policy</td><td><code>org:update</code></td></tr>
        </tbody>
      </table>
    </div>
    <p class="note">Legacy paths <code>/audit</code>, <code>/operations/activity</code>, and <code>/operations/events</code> redirect to this page.</p>
  </section>

  <section class="audit-toolbar-actions">
    <h2>Page actions</h2>
    <ul>
      <li><strong>Refresh</strong> — reload dashboard, analytics, and the filtered event list</li>
      <li><strong>Export</strong> — dialog to download <strong>CSV</strong> or <strong>JSON</strong> for a chosen date range</li>
      <li><strong>Retention &amp; archive</strong> — hot retention days, optional cold archive, manual retention run, browse archived events</li>
      <li><strong>Saved filters</strong> — shown but disabled (<em>coming soon</em>)</li>
    </ul>
  </section>

  <section class="audit-kpis">
    <h2>Dashboard KPIs</h2>
    <p>Six clickable cards filter the event log and scroll to the table:</p>

    <div class="audit-kpi">
      <div class="audit-kpi-icon blue">▣</div>
      <div><span>Total events</span><strong>—</strong><small>All time (clears KPI filters)</small></div>
    </div>
    <div class="audit-kpi">
      <div class="audit-kpi-icon green">□</div>
      <div><span>Events today</span><strong>—</strong><small>Custom date range: today only</small></div>
    </div>
    <div class="audit-kpi">
      <div class="audit-kpi-icon red">!</div>
      <div><span>Failed operations</span><strong>—</strong><small>Status = FAILURE</small></div>
    </div>
    <div class="audit-kpi">
      <div class="audit-kpi-icon orange">◇</div>
      <div><span>Security events</span><strong>—</strong><small>Security KPI preset</small></div>
    </div>
    <div class="audit-kpi">
      <div class="audit-kpi-icon purple">♙</div>
      <div><span>Authentication</span><strong>—</strong><small>Authentication KPI preset</small></div>
    </div>
    <div class="audit-kpi">
      <div class="audit-kpi-icon blue">⚙</div>
      <div><span>Configuration changes</span><strong>—</strong><small>Configuration KPI preset</small></div>
    </div>

    <p class="note">Counts come from <code>GET /organizations/:orgId/audit-logs/dashboard</code>. Click again to toggle off a KPI filter (except Total events).</p>
  </section>

  <section class="audit-analytics">
    <h2>Analytics <small>(Last 30 days)</small></h2>
    <p>Loaded from <code>GET /organizations/:orgId/audit-logs/analytics?days=30</code>:</p>

    <div class="audit-chart-grid">

      <div class="audit-chart">
        <h3>Audit event volume</h3>
        <p>Daily timeline: <strong>Total events</strong> and <strong>Failed events</strong>.</p>
      </div>

      <div class="audit-chart">
        <h3>Event status</h3>
        <p>Distribution of <strong>Success</strong> vs <strong>Failure</strong> (not separate Warning/Info status buckets).</p>
      </div>

      <div class="audit-chart">
        <h3>Top categories</h3>
        <p>Most active audit categories (Authentication, Authorization, Stacks, Deployments, Policies, RBAC, etc.).</p>
      </div>

      <div class="audit-chart">
        <h3>Top actions</h3>
        <p>Most frequent actions (Create, Update, Delete, Login, …).</p>
      </div>

    </div>
  </section>

  <section class="audit-workspace">

    <h2>Audit event log</h2>

    <div class="audit-toolbar">
      <p><strong>Default filters shown:</strong> Search, Category, Date range (<em>Last 30 days</em>).</p>
      <p><strong>More filters</strong> toggles optional filters: Action, Status, Severity, Resource type, Resource name, Source module, Repository.</p>
      <p>Filter visibility is persisted in browser storage. Use <strong>Clear all</strong> when filters are active.</p>
    </div>

    <div class="table-wrap">
      <table>
        <thead>
          <tr><th>Filter</th><th>Values</th></tr>
        </thead>
        <tbody>
          <tr><td>Search</td><td>Events, users, resources, correlation IDs</td></tr>
          <tr><td>Category</td><td>Dynamic list from API + built-in categories (Authentication, Stacks, Deployments, RBAC, …)</td></tr>
          <tr><td>Date range</td><td>7 / 30 / 60 / 90 / 180 / 365 days, current month, previous month, custom from/to</td></tr>
          <tr><td>Action</td><td>CREATE, UPDATE, DELETE, LOGIN, LOGOUT, ACCESS, INVITE, REVOKE, SECURITY_VIOLATION</td></tr>
          <tr><td>Status</td><td>SUCCESS, FAILURE</td></tr>
          <tr><td>Severity</td><td>CRITICAL, HIGH, MEDIUM, LOW, INFO</td></tr>
          <tr><td>Resource type / name</td><td>Free text</td></tr>
          <tr><td>Source module</td><td>Free text (audit source field)</td></tr>
          <tr><td>Repository</td><td>Free text (Git-related events)</td></tr>
        </tbody>
      </table>
    </div>

    <div class="audit-export">
      <p><strong>Export</strong> opens a dialog — choose CSV or JSON and the same date presets as search (not separate always-visible export buttons).</p>
    </div>

    <h3>Table columns</h3>
    <p>Sortable, configurable via column settings (persisted in browser storage). Defaults:</p>
    <ul>
      <li>Timestamp, User, Resource Type, Resource Name, Action, Category, Status, Severity, Source Module, IP Address</li>
    </ul>
    <p>Optional columns: Organization, Correlation ID.</p>

    <div class="audit-table-wrap">
      <p>Click a row to open <strong>Audit Event Details</strong> with:</p>
      <ul>
        <li><strong>General</strong> — event ID, timestamp, user, resource, action, status, severity, source; repository/branch/commit when present</li>
        <li><strong>Technical</strong> — API endpoint, HTTP method, client IP, correlation ID, user agent</li>
        <li><strong>Changes</strong> — JSON diff when recorded</li>
      </ul>
    </div>

    <p class="note">Server-side pagination with adjustable page size. Default sort: <code>createdAt</code> descending.</p>

  </section>

  <section>
    <h2>Retention &amp; archive</h2>
    <p>From <strong>Retention &amp; archive</strong>:</p>
    <ul>
      <li>Configure hot retention (30–3650 days; presets 30 / 60 / 90 / 180 / 365 or custom)</li>
      <li>Enable cold archive and optional archive retention limit</li>
      <li>Run retention manually (archives and/or deletes from hot storage per policy)</li>
      <li>Browse archived audit records with search and pagination</li>
    </ul>
    <p class="note">Editing retention requires <code>org:update</code> (typically organization Owner).</p>
  </section>

  <section>
    <h2>API reference</h2>
    <div class="table-wrap">
      <table>
        <thead>
          <tr><th>Endpoint</th><th>Purpose</th></tr>
        </thead>
        <tbody>
          <tr><td><code>GET /organizations/:orgId/audit-logs</code></td><td>Search / list events (query filters)</td></tr>
          <tr><td><code>GET /organizations/:orgId/audit-logs/:id</code></td><td>Event detail</td></tr>
          <tr><td><code>GET /organizations/:orgId/audit-logs/dashboard</code></td><td>KPI counts</td></tr>
          <tr><td><code>GET /organizations/:orgId/audit-logs/analytics?days=30</code></td><td>Charts data</td></tr>
          <tr><td><code>GET /organizations/:orgId/audit-logs/categories</code></td><td>Category list</td></tr>
          <tr><td><code>GET /organizations/:orgId/audit-logs/export</code></td><td>CSV export</td></tr>
          <tr><td><code>GET /organizations/:orgId/audit-logs/export/json</code></td><td>JSON export</td></tr>
          <tr><td><code>GET /organizations/:orgId/audit-logs/retention-policy</code></td><td>Read retention settings</td></tr>
          <tr><td><code>PUT /organizations/:orgId/audit-logs/retention-policy</code></td><td>Update retention (<code>org:update</code>)</td></tr>
          <tr><td><code>POST /organizations/:orgId/audit-logs/retention-policy/run</code></td><td>Run retention job</td></tr>
          <tr><td><code>GET /organizations/:orgId/audit-logs/archives</code></td><td>Search archived events</td></tr>
        </tbody>
      </table>
    </div>
  </section>

  <section>
    <h2>Related surfaces</h2>
    <ul>
      <li><strong>My Profile</strong> — personal sign-in activity and charts from a subset of org audit logs (current organization, limited page size)</li>
      <li><strong>Security &amp; Governance</strong> — compliance and break-glass workflows reference this audit trail</li>
      <li><strong>Roles &amp; Access</strong> — no embedded audit tab; use this page for full RBAC-related events (filter Category = RBAC or search)</li>
    </ul>
  </section>

</div>
