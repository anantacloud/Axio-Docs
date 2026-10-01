---
layout: default
title: My Profile
parent: Administration
nav_order: 1
permalink: /axio/administration/profile/
---

<div class="profile-page">

<h1>Administration — My Profile</h1>
<p class="profile-subtitle">Personal account settings for the signed-in user — not organization administration (Users, Groups, Roles, or org-wide MFA policy).</p>

<div class="profile-banner">
<span>ⓘ</span>
Open from the <strong>user account menu</strong> (avatar / name) → <strong>My profile</strong>, or go to <code>/administration/profile</code>.
Legacy <code>/admin/platform/profile</code> redirects here.
Org-wide MFA policy: <code>/administration/mfa</code> (administrators only).
</div>

<h2>What it does</h2>
<p>The signed-in user can manage their own account:</p>

<div class="profile-features">
<div><b>♙</b><h3>Edit profile</h3><p>Update first name, last name, and profile picture URL; email is read-only</p></div>
<div><b>✉</b><h3>Email verification</h3><p>See verification status and resend the verification email</p></div>
<div><b>♢</b><h3>MFA enrollment</h3><p>Enroll with Google or Microsoft Authenticator (TOTP), view status, and regenerate recovery codes</p></div>
<div><b>▣</b><h3>Active sessions</h3><p>Review signed-in devices; revoke one session, sign out other devices, or sign out everywhere</p></div>
<div><b>⌁</b><h3>Activity &amp; insights</h3><p>Charts for sign-in trends, security posture, sessions, and API-key activity; recent sign-in list</p></div>
<div><b>⚿</b><h3>Security recommendations</h3><p>Personal recommendations (verify email, enable MFA, regenerate recovery codes)</p></div>
</div>

<h2>How to access</h2>
<p>
  <strong>My Profile</strong> lives under the <code>/administration/profile</code> URL but is categorized as <strong>Account</strong> in navigation —
  it is opened from the top-bar <strong>user account menu</strong>, not from the Administration sidebar.
  Any authenticated organization member can open the page.
</p>

<h2>Prerequisites &amp; permissions</h2>
<div class="profile-table">
<div class="profile-head"><b>Requirement</b><b>Detail</b></div>
<div><strong>Sign-in</strong><span>Must be authenticated; unauthenticated users are redirected to login with a <code>next</code> return URL</span></div>
<div><strong>Organization context</strong><span>MFA status and audit activity are scoped to the <strong>current organization</strong></span></div>
<div><strong>Route gate</strong><span>No special admin permission is required on the route itself — unlike pages such as Users or org-wide MFA policy</span></div>
</div>

<p class="profile-subtitle">
  Password changes are not performed on this page — use your identity provider or contact an organization administrator.
  <strong>Notification preferences</strong> are managed separately at <code>/notifications</code>.
</p>

<h2>Sections</h2>
<div class="profile-table">
<div class="profile-head"><b>Section</b><b>Content</b></div>
<div><strong>Overview</strong><span>Signed-in account summary (name, email, org role, org name), operational alerts, clickable KPIs, and <strong>Refresh</strong></span></div>
<div><strong>♙　Personal Information</strong><span>First name, last name, profile picture URL — <code>PATCH /users/me</code></span></div>
<div><strong>♢　Account Security</strong><span>Email verification status; <strong>Resend verification email</strong> — <code>POST /auth/resend-verification</code></span></div>
<div><strong>▣　Multi-Factor Authentication</strong><span>TOTP enrollment (Google / Microsoft Authenticator), recovery codes — <code>/users/me/mfa</code></span></div>
<div><strong>▣　Active sessions</strong><span>List sessions; revoke one; sign out other devices or everywhere — <code>/users/me/sessions</code></span></div>
<div><strong>⌁　Activity &amp; insights</strong><span>Account activity trend (7d / 30d / 90d), security posture, sessions &amp; API activity, API key activity, top actions; <strong>Recent sign-ins</strong> from org audit logs</span></div>
<div><strong>Security recommendations</strong><span>Actionable personal security items when applicable</span></div>
</div>

<div class="profile-panel">
<div class="panel-title">Overview — <strong>Signed-in account</strong><em>Refresh</em><span>⌃</span></div>
<p class="profile-subtitle">Shows avatar, full name, email, organization role chip, organization name, email-verified and MFA-enabled chips.</p>
<div class="profile-table">
<div class="profile-head"><b>KPI (clickable)</b><b>Scrolls to</b></div>
<div><strong>Last Login</strong><span>Activity &amp; insights / recent sign-ins</span></div>
<div><strong>MFA Status</strong><span>Multi-Factor Authentication section</span></div>
<div><strong>Recovery Codes</strong><span>Multi-Factor Authentication section</span></div>
<div><strong>Active Sessions</strong><span>Active sessions table (brief highlight)</span></div>
</div>
<p class="profile-subtitle">Operational alerts appear when email is unverified, MFA is disabled, or recovery codes are running low.</p>
</div>

<div class="profile-panel">
<div class="panel-title">♙　<strong>Personal Information</strong><em>Save changes</em><span>⌃</span></div>
<div class="profile-form">
<label>Email address<div><input value="(read-only — from sign-in account)" readonly></div></label>
<label>First name<input placeholder="First name" readonly></label>
<label>Last name<input placeholder="Last name" readonly></label>
<label>Profile picture URL<div class="avatar-row"><i>—</i><input placeholder="https://example.com/avatar.png" readonly></div><small>Optional image URL used for your avatar. A live preview appears above the form.</small></label>
</div>
<div class="actions"><button class="primary">Save changes</button></div>
</div>

<div class="profile-panel compact"><div class="panel-title">♢　<strong>Account Security</strong><em>Verified / Not verified</em><span>⌄</span></div></div>
<p class="profile-subtitle">
  When email is not verified, the page explains that you can use the sign-up verification link or complete email verification through MFA enrollment.
  A note links to <strong>Notification preferences</strong> (<code>/notifications</code>) for alert settings — not API key management.
</p>

<div class="profile-panel compact"><div class="panel-title">▣　<strong>Multi-Factor Authentication</strong><em>Enabled / Disabled</em><span>⌄</span></div></div>
<p class="profile-subtitle">
  Enrollment supports <strong>Google Authenticator</strong> and <strong>Microsoft Authenticator</strong> (TOTP): QR code or manual setup key, verification code, then one-time recovery codes.
  When MFA is enabled, you can regenerate recovery codes with your current MFA code.
  If the organization enforces MFA (<code>/administration/mfa</code>), an info banner explains that administrators manage policy.
  When MFA is enabled without org enforcement, users may see guidance to contact an administrator to disable MFA.
</p>

<div class="profile-panel">
<div class="panel-title">▣　<strong>Active sessions</strong><em class="purple">N active sessions</em><span>⌃</span></div>
<div class="sessions">
<div class="session-head"><b>Device</b><b>Location</b><b>IP address</b><b>Last seen</b><b>Signed in</b><b>Actions</b></div>
<div><strong>Browser on OS</strong><small>This device</small><span>City, Country</span><span>—</span><span>—</span><span>—</span><span>—</span></div>
<div><strong>Other device</strong><small>—</small><span>City, Country</span><span>—</span><span>—</span><span>—</span><button class="revoke">Revoke</button></div>
</div>
<div class="session-actions"><button class="revoke">Sign out other devices</button><button class="revoke">Sign out everywhere</button></div>
<p class="profile-subtitle">
  <strong>Sign out other devices</strong> keeps the current browser signed in.
  <strong>Sign out everywhere</strong> revokes all sessions including this one and returns you to the sign-in page.
  The current session shows a <em>This device</em> chip instead of a Revoke button.
  Sessions are paginated (10 per page). Loading refreshes the current session heartbeat via <code>POST /users/me/sessions/heartbeat</code>.
</p>
</div>

<div class="profile-panel compact"><div class="panel-title">⌁　<strong>Activity &amp; insights</strong><small>Personal sign-in trends, security posture, and platform activity</small><span>⌄</span></div></div>
<div class="profile-table">
<div class="profile-head"><b>Chart</b><b>Description</b></div>
<div><strong>Account activity</strong><span>All events, sign-ins, and security events over 7 / 30 / 90 days (from org audit logs for the current organization)</span></div>
<div><strong>Security posture</strong><span>Email, MFA, and recovery-code status distribution</span></div>
<div><strong>Sessions &amp; API activity</strong><span>Authentication sessions and API token usage trend</span></div>
<div><strong>API key activity</strong><span>Active, rotated, and expired keys (org dashboard summary — keys are not created on this page)</span></div>
<div><strong>Top actions</strong><span>Most frequent account-related audit events</span></div>
<div><strong>Recent sign-ins</strong><span>Latest authentication events derived from audit logs</span></div>
</div>

<h2>API reference (personal scope)</h2>
<div class="profile-table">
<div class="profile-head"><b>Endpoint</b><b>Purpose</b></div>
<div><code>PATCH /users/me</code><span>Update first name, last name, avatar URL</span></div>
<div><code>POST /auth/resend-verification</code><span>Resend email verification message</span></div>
<div><code>GET /users/me/mfa?organizationId=…</code><span>MFA status for current org context</span></div>
<div><code>POST /users/me/mfa/totp/enroll</code><span>Start TOTP enrollment (Google or Microsoft)</span></div>
<div><code>POST /users/me/mfa/totp/verify</code><span>Verify code and enable MFA; returns recovery codes</span></div>
<div><code>POST /users/me/mfa/recovery-codes/regenerate</code><span>Regenerate recovery codes (requires current MFA code)</span></div>
<div><code>GET /users/me/sessions</code><span>List active sessions</span></div>
<div><code>DELETE /users/me/sessions/:id</code><span>Revoke one session</span></div>
<div><code>POST /users/me/sessions/revoke-all</code><span>Sign out other devices (<code>keepCurrent: true</code>) or everywhere (<code>false</code>)</span></div>
<div><code>GET /organizations/:orgId/audit-logs</code><span>Audit events powering activity charts and recent sign-ins</span></div>
</div>

<h2>Related administration pages</h2>
<div class="profile-table">
<div class="profile-head"><b>Page</b><b>Relationship</b></div>
<div><strong>Administration → MFA</strong> (<code>/administration/mfa</code>)<span>Org-wide MFA policy — which methods are allowed and whether MFA is required (<code>identity:manage</code>)</span></div>
<div><strong>Administration → Users</strong> (<code>/administration/users</code>)<span>Administrators manage other users' accounts, roles, and groups</span></div>
<div><strong>Notifications</strong> (<code>/notifications</code>)<span>Personal notification preferences linked from Account Security</span></div>
</div>

</div>
