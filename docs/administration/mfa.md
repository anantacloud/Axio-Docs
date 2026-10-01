---
layout: default
title: MFA
parent: Administration
nav_order: 6
permalink: /axio/administration/mfa/
---

<div class="admin-mfa-page">

  <div class="mfa-hero">
    <div>
      <h1>Administration — MFA</h1>
      <p class="mfa-lead">Organization-wide multi-factor authentication policy — enforcement, permitted authenticator app, and enrollment coverage.</p>

      <div class="mfa-info-banner">
        <span class="mfa-info-icon">i</span>
        <span>Open <strong>Administration → MFA</strong> at <code>/administration/mfa</code></span>
        <span class="mfa-dot">•</span>
        <span>Personal enrollment: <a href="{{ '/axio/administration/profile/' | relative_url }}">My Profile</a></span>
        <span class="mfa-dot">•</span>
        <span>Per-user MFA actions: <strong>Roles &amp; Access → Users</strong></span>
      </div>
    </div>
  </div>

  <section>
    <h2>What it does</h2>
    <p>Administrators with <code>identity:manage</code> configure:</p>
    <ul>
      <li>Whether MFA is <strong>required for all organization members</strong></li>
      <li>Which <strong>single authenticator app</strong> members may use (Google or Microsoft Authenticator — TOTP)</li>
      <li>Enrollment coverage KPIs for <strong>internal users</strong></li>
      <li>Operational alerts when enforcement or enrollment needs attention</li>
    </ul>
    <p class="note">This page is org policy — not where users enroll their own MFA (see <strong>My Profile</strong>).</p>
  </section>

  <section>
    <h2>Permissions</h2>
    <div class="table-wrap">
      <table>
        <thead>
          <tr>
            <th>Action</th>
            <th>Permission</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Open MFA policy page</td>
            <td><code>identity:manage</code></td>
          </tr>
          <tr>
            <td>View / update org MFA policy (API)</td>
            <td><code>identity:manage</code></td>
          </tr>
          <tr>
            <td>Reset / disable / force re-enroll user MFA</td>
            <td><code>org:members:manage</code> (from Users — separate from this page)</td>
          </tr>
        </tbody>
      </table>
    </div>
  </section>

  <section class="mfa-summary-grid">

    <section class="mfa-summary-card">
      <div class="summary-icon purple">♢</div>
      <div>
        <h2>MFA policy overview</h2>
        <p>Banner at the top of the page shows:</p>
        <ul>
          <li>Enrolled count vs internal user total, permitted methods, last updated timestamp</li>
          <li>Chips: <em>Enforcement required / optional</em>, <em>N% enrolled</em>, selected authenticator name</li>
          <li>Clickable KPIs: <strong>Members</strong>, <strong>MFA enrolled</strong>, <strong>Pending enrollment</strong>, <strong>Coverage</strong></li>
          <li><strong>Refresh</strong> reloads policy and internal user MFA summaries</li>
        </ul>
      </div>
    </section>

    <section class="mfa-summary-card adoption-card">
      <div class="summary-icon green">♙</div>
      <div class="adoption-copy">
        <h2>MFA adoption</h2>
        <p>Calculated from <strong>internal users</strong> returned by the admin user directory (<code>GET /admin/users</code>), not synced IdP-only accounts.</p>
        <p><strong>Pending enrollment</strong> includes users with <code>enrollmentRequired</code> or policy-enforced users without MFA enabled.</p>
        <p>Coverage = enrolled ÷ total internal users (rounded percentage).</p>
      </div>
    </section>

  </section>

  <section>
    <h2>Require MFA for all members</h2>

    <div class="mfa-toggle-row">
      <p>Toggle: <strong>Require MFA for all members</strong> (<code>enforced</code> on the org policy).</p>
    </div>

    <ul>
      <li>When <strong>enabled</strong>, every member must enroll MFA before accessing Axio. Members without MFA are prompted at next sign-in.</li>
      <li>Existing sessions may continue until expiry.</li>
      <li>When <strong>disabled</strong>, MFA becomes optional at the organization level. Turning enforcement off also clears MFA enrollments for all organization members (MFA records are removed server-side).</li>
    </ul>

    <div class="callout callout-warning">
      <div class="callout-icon">!</div>
      <p>
        Disabling enforcement is destructive: member MFA enrollments for this organization are reset.
        Plan communications before toggling enforcement off in production.
      </p>
    </div>

    <p class="mfa-help">
      The enforcement toggle is staged in the UI — click <strong>Save policy</strong> in the sticky bar to apply.
      You cannot save enforcement while zero authenticator methods are permitted.
    </p>
  </section>

  <section class="mfa-methods">
    <h2>Organization authenticator app</h2>
    <p class="section-subtitle">Select the <strong>single</strong> authenticator app members use during MFA enrollment. This is a radio choice — not multiple independent toggles.</p>

    <div class="mfa-method-grid">

      <article class="mfa-method-card">
        <div class="method-icon google">✣</div>
        <div class="method-content">
          <h3>Google Authenticator (TOTP)</h3>
          <span class="recommended">Recommended</span>
          <p>Time-based one-time passwords using Google Authenticator or compatible apps.</p>
          <div class="method-status">
            <strong>Selected for enrollment</strong> when chosen (radio checked)
          </div>
        </div>
      </article>

      <article class="mfa-method-card">
        <div class="method-icon microsoft">●</div>
        <div class="method-content">
          <h3>Microsoft Authenticator (TOTP)</h3>
          <span class="recommended">Recommended</span>
          <p>Enterprise-friendly authenticator support via Microsoft Authenticator.</p>
          <div class="method-status">
            <strong>Selected for enrollment</strong> when chosen (radio checked)
          </div>
        </div>
      </article>

    </div>

    <div class="callout callout-info">
      <div class="callout-icon">i</div>
      <p>
        <strong>SMS</strong> and <strong>Email</strong> OTP methods are not configurable on this page today.
        The API persists <code>allowSms: false</code> and <code>allowEmail: false</code>.
        Only TOTP authenticator apps are supported for org policy and personal enrollment.
      </p>
    </div>

    <p class="note">Changing the authenticator app saves <strong>immediately</strong> when you select a card (unlike the enforcement toggle).</p>
  </section>

  <section>
    <h2>Member MFA management</h2>
    <p>
      The side panel links to <strong>Manage user MFA</strong> →
      <code>/administration/roles-access?section=users</code>.
      From there, administrators with <code>org:members:manage</code> can reset MFA, force re-enrollment,
      disable MFA, or invalidate recovery codes for individual users (audit reason required).
    </p>
  </section>

  <section>
    <h2>Operational alerts</h2>
    <p>The overview banner may surface:</p>
    <ul>
      <li><strong>Error:</strong> Enforcement enabled but no permitted methods selected</li>
      <li><strong>Warning:</strong> Members still need to enroll under enforced policy</li>
      <li><strong>Info:</strong> Optional MFA with less than 100% coverage — suggests considering enforcement</li>
    </ul>
  </section>

  <div class="mfa-links-grid">

    <section class="mfa-link-card blue-card">
      <div class="link-icon">i</div>
      <div>
        <h2>Prefer directory / SSO MFA?</h2>
        <p>
          Enforce MFA at your identity provider and configure SSO under
          <code>/admin/integrations/identity-providers</code>.
          Axio org MFA policy applies to native Axio sign-in and enrollment flows.
        </p>
      </div>
    </section>

    <section class="mfa-link-card purple-card">
      <div class="link-icon">♙</div>
      <div>
        <h2>Personal enrollment</h2>
        <p>
          Each user enrolls MFA on
          <a href="{{ '/axio/administration/profile/' | relative_url }}">My Profile</a>
          using the authenticator app selected on this page.
        </p>
      </div>
    </section>

  </div>

  <section>
    <h2>API reference</h2>
    <div class="table-wrap">
      <table>
        <thead>
          <tr>
            <th>Endpoint</th>
            <th>Purpose</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td><code>GET /admin/mfa/policy?organizationId=…</code> (v2)</td>
            <td>Read org MFA policy (<code>identity:manage</code>)</td>
          </tr>
          <tr>
            <td><code>PATCH /admin/mfa/policy?organizationId=…</code> (v2)</td>
            <td>Update <code>enforced</code>, <code>allowTotpGoogle</code>, <code>allowTotpMicrosoft</code></td>
          </tr>
          <tr>
            <td><code>GET /admin/mfa/users/:userId?organizationId=…</code></td>
            <td>User MFA status for admin review (<code>org:members:manage</code>)</td>
          </tr>
          <tr>
            <td><code>POST /admin/mfa/users/:userId/reset</code></td>
            <td>Admin MFA reset (reason required)</td>
          </tr>
          <tr>
            <td><code>POST /admin/mfa/users/:userId/force-re-enroll</code></td>
            <td>Force user to enroll again</td>
          </tr>
          <tr>
            <td><code>POST /admin/mfa/users/:userId/disable</code></td>
            <td>Disable user MFA</td>
          </tr>
          <tr>
            <td><code>POST /admin/mfa/users/:userId/recovery-codes/regenerate</code></td>
            <td>Invalidate recovery codes</td>
          </tr>
        </tbody>
      </table>
    </div>
  </section>

  <section>
    <h2>Default policy</h2>
    <p>When no policy record exists yet:</p>
    <ul>
      <li><code>enforced: false</code></li>
      <li><code>allowTotpGoogle: true</code></li>
      <li><code>allowTotpMicrosoft: false</code></li>
      <li>SMS and Email: disabled</li>
    </ul>
  </section>

</div>
