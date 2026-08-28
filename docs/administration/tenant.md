---
layout: default
title: Tenant
parent: Administration
nav_order: 2
---

<link rel="stylesheet" href="{{ '/assets/css/administration-tenant.css' | relative_url }}">

<div class="tenant-page">

  <div class="tenant-hero">
    <h1>Administration — Tenant</h1>
    <p>Organization identity and a high-level tenant dashboard.</p>
  </div>

  <div class="tenant-info-banner">
    <span class="tenant-info-icon">ⓘ</span>
    <span>
      Overview:
      <code>ADMINISTRATION.md</code>
      <b>•</b>
      Hierarchy (projects, workspaces, environments, business units) lives under
      <strong>Organization</strong>, not here.
    </span>
  </div>

  <section class="tenant-section">
    <h2>Organization identity</h2>

    <div class="tenant-identity-card">
      <div class="tenant-identity-top">
        <div class="tenant-org-brand">
          <div class="tenant-avatar">AC</div>
          <div>
            <div class="tenant-org-name">
              Acme Corporation
              <span class="tenant-status">Platform Provider</span>
            </div>
            <p>The central organization managing cloud infrastructure and governance.</p>
            <small>Created on Apr 12, 2023 &nbsp;•&nbsp; Owner: Sarah Kapoor</small>
          </div>
        </div>

        <button class="tenant-outline-button">✎ &nbsp; Edit organization</button>
      </div>

      <div class="tenant-fields">
        <div class="tenant-field">
          <label>Organization ID (8-character code)</label>
          <div class="tenant-copy-field">
            <code>ACME7X9Q</code>
            <button>▣ &nbsp; Copy</button>
          </div>
          <small>Use this ID at sign-in to access this organization.</small>
        </div>

        <div class="tenant-field">
          <label>Organization slug</label>
          <div class="tenant-copy-field">
            <code>acme-corp</code>
            <button>▣ &nbsp; Copy</button>
          </div>
          <small>Used in URLs and invitations.</small>
        </div>
      </div>

      <div class="tenant-description">
        <label>Description</label>
        <p>Global platform team building and operating cloud infrastructure.</p>
      </div>
    </div>
  </section>

  <section class="tenant-section">
    <h2>Overview</h2>

    <div class="tenant-kpi-grid">
      <div class="tenant-kpi-card">
        <div class="tenant-kpi-icon purple">♙</div>
        <span>Members</span>
        <strong>128</strong>
        <small class="tenant-positive">↑ 12% <em>vs last 30 days</em></small>
      </div>

      <div class="tenant-kpi-card">
        <div class="tenant-kpi-icon green">◇</div>
        <span>Projects</span>
        <strong>42</strong>
        <small class="tenant-positive">↑ 8% <em>vs last 30 days</em></small>
      </div>

      <div class="tenant-kpi-card">
        <div class="tenant-kpi-icon blue">♙</div>
        <span>Teams</span>
        <strong>16</strong>
        <small class="tenant-positive">↑ 6% <em>vs last 30 days</em></small>
      </div>

      <div class="tenant-kpi-card">
        <div class="tenant-kpi-icon amber">⌁</div>
        <span>Deployment success</span>
        <strong>98.6%</strong>
        <small class="tenant-positive">↑ 2.1% <em>vs last 30 days</em></small>
      </div>
    </div>
  </section>

  <section class="tenant-section">
    <h2>Analytics</h2>

    <div class="tenant-analytics-grid">
      <div class="tenant-chart-card">
        <div class="tenant-chart-header">
          <strong>Deployment success (last 30 days)</strong>
          <button class="tenant-select">Last 30 days⌄</button>
        </div>

        <div class="tenant-line-chart">
          <div class="chart-y-labels">
            <span>100%</span>
            <span>95%</span>
            <span>90%</span>
            <span>85%</span>
          </div>
          <div class="chart-area">
            <div class="chart-gridline g1"></div>
            <div class="chart-gridline g2"></div>
            <div class="chart-gridline g3"></div>
            <div class="chart-gridline g4"></div>
            <svg viewBox="0 0 500 150" preserveAspectRatio="none" aria-hidden="true">
              <path class="chart-fill"
                d="M0,75 L20,62 L40,70 L60,58 L80,64 L100,42 L120,50 L140,60 L160,48 L180,40 L200,47 L220,43 L240,52 L260,44 L280,51 L300,37 L320,46 L340,34 L360,43 L380,30 L400,36 L420,25 L440,33 L460,22 L480,17 L500,10 L500,150 L0,150 Z"/>
              <polyline class="chart-line"
                points="0,75 20,62 40,70 60,58 80,64 100,42 120,50 140,60 160,48 180,40 200,47 220,43 240,52 260,44 280,51 300,37 320,46 340,34 360,43 380,30 400,36 420,25 440,33 460,22 480,17 500,10"/>
            </svg>
            <div class="chart-x-labels">
              <span>Apr 18</span>
              <span>Apr 25</span>
              <span>May 2</span>
              <span>May 9</span>
              <span>May 16</span>
            </div>
          </div>
        </div>
      </div>

      <div class="tenant-chart-card tenant-donut-card">
        <strong>Projects by status</strong>
        <div class="tenant-donut-content">
          <div class="tenant-donut">
            <div>
              <strong>42</strong>
              <span>Total</span>
            </div>
          </div>
          <div class="tenant-legend">
            <div><i class="dot active"></i>Active <b>28 (66.7%)</b></div>
            <div><i class="dot planning"></i>Planning <b>8 (19.0%)</b></div>
            <div><i class="dot hold"></i>On Hold <b>4 (9.5%)</b></div>
            <div><i class="dot archived"></i>Archived <b>2 (4.8%)</b></div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section class="tenant-section">
    <h2>Quick links</h2>

    <div class="tenant-links-grid">
      <a href="#" class="tenant-link-card">
        <span class="link-icon">⚙</span>
        <span><b>Organization Settings</b><small>Manage org details, settings and preferences</small></span>
        <strong>→</strong>
      </a>
      <a href="#" class="tenant-link-card">
        <span class="link-icon">♙</span>
        <span><b>Users</b><small>Invite and manage members</small></span>
        <strong>→</strong>
      </a>
      <a href="#" class="tenant-link-card">
        <span class="link-icon">♧</span>
        <span><b>Teams</b><small>Manage teams and team memberships</small></span>
        <strong>→</strong>
      </a>
      <a href="#" class="tenant-link-card">
        <span class="link-icon">♢</span>
        <span><b>Roles &amp; Permissions</b><small>Configure roles and access permissions</small></span>
        <strong>→</strong>
      </a>
      <a href="#" class="tenant-link-card">
        <span class="link-icon">⌑</span>
        <span><b>SSO Configuration</b><small>Manage SAML / OIDC single sign-on</small></span>
        <strong>→</strong>
      </a>
      <a href="#" class="tenant-link-card">
        <span class="link-icon">♢</span>
        <span><b>MFA Policy</b><small>Configure multi-factor authentication policy</small></span>
        <strong>→</strong>
      </a>
      <a href="#" class="tenant-link-card">
        <span class="link-icon">▤</span>
        <span><b>Audit Logs</b><small>View organization audit and activity logs</small></span>
        <strong>→</strong>
      </a>
      <a href="#" class="tenant-link-card">
        <span class="link-icon">✣</span>
        <span><b>Integrations</b><small>Manage connected services and integrations</small></span>
        <strong>→</strong>
      </a>
      <a href="#" class="tenant-link-card">
        <span class="link-icon">▣</span>
        <span><b>Billing &amp; Plans</b><small>View billing, usage and subscription plans</small></span>
        <strong>→</strong>
      </a>
    </div>
  </section>

  <div class="tenant-warning">
    <strong>♧ &nbsp; Safeguards</strong>
    <ul>
      <li>Only <code>org:update</code> may PATCH the organization (OWNER in the default matrix).</li>
      <li>Organization delete is <code>org:delete</code> (OWNER) and is not the primary action on this page.</li>
      <li>An organization must always have at least one OWNER.</li>
    </ul>
  </div>

  <div class="tenant-signin-note">
    <span>ⓘ</span>
    <span>Sign-in uses the Organization ID from this page, not the slug. See the root <code>README.md</code>.</span>
  </div>

</div>
