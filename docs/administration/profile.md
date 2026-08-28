---
layout: default
title: My Profile
parent: Administration
nav_order: 1
---

<div class="profile-page">

<h1>Administration — My Profile</h1>
<p class="profile-subtitle">Personal account settings for the signed-in user — not organization administration.</p>

<div class="profile-banner">
<span>ⓘ</span>
Overview: <code>ADMINISTRATION.md</code>　•　Org-wide MFA policy: <code>ADMINISTRATION_MFA.md</code>　•　Login chrome: <code>LOGIN_EXPERIENCE.md</code>
</div>

<h2>What it does</h2>
<p>The signed-in user can:</p>

<div class="profile-features">
<div><b>♙</b><h3>Edit profile</h3><p>Edit first name, last name, and avatar URL</p></div>
<div><b>✉</b><h3>Email status</h3><p>See email verification status and resend verification</p></div>
<div><b>♢</b><h3>MFA</h3><p>Enroll, manage, and recover their own MFA</p></div>
<div><b>▣</b><h3>Active sessions</h3><p>Review and revoke active sessions (this device or all other devices)</p></div>
<div><b>⌁</b><h3>Security insights</h3><p>See personal security recommendations, sign-in activity, and API-key posture</p></div>
<div><b>⚿</b><h3>API keys</h3><p>API-key posture link under Integrations</p></div>
</div>

<div class="profile-route">✓　<code>/settings</code> and <code>/admin/platform/profile</code> also land on this page.</div>

<h2>Sections</h2>
<div class="profile-table">
<div class="profile-head"><b>Section</b><b>Content</b></div>
<div><strong>♙　Personal Information</strong><span>Name and avatar <code>PATCH /users/me</code></span></div>
<div><strong>♢　Account Security</strong><span>Email verification; link to API keys under Integrations</span></div>
<div><strong>▣　Multi-Factor Authentication</strong><span>TOTP / SMS / email enrollment for this user <code>/users/me/mfa</code></span></div>
<div><strong>▣　Active sessions</strong><span>List, revoke one, revoke all others</span></div>
<div><strong>⌁　Activity</strong><span>Recent audit events for the current organization</span></div>
</div>

<div class="profile-panel">
<div class="panel-title">♙　<strong>Personal Information</strong><em>Saved</em><span>⌃</span></div>
<div class="profile-form">
<label>Avatar URL<div class="avatar-row"><i>SK</i><input value="https://avatar.example.com/sk.png" readonly></div><small>Recommended: Square image, at least 200x200px.</small></label>
<label>First name<input value="Sarah" readonly></label>
<label>Last name<input value="Kapoor" readonly></label>
</div>
<div class="actions"><button>Cancel</button><button class="primary">Save changes</button></div>
</div>

<div class="profile-panel compact"><div class="panel-title">♢　<strong>Account Security</strong><em>Email verified</em><span>⌄</span></div></div>
<div class="profile-panel compact"><div class="panel-title">▣　<strong>Multi-Factor Authentication</strong><em>Enabled (TOTP)</em><span>⌄</span></div></div>

<div class="profile-panel">
<div class="panel-title">▣　<strong>Active sessions</strong><em class="purple">3 active sessions</em><span>⌃</span></div>
<div class="sessions">
<div class="session-head"><b>Device</b><b>Location / IP</b><b>Last active</b><b>Status</b><b>Actions</b></div>
<div><strong>▣　Chrome on Windows</strong><small>This device</small><span>Gurugram, India<br>103.21.*.*</span><span>Just now</span><i class="profile-status-active">Active</i><span>—</span></div>
<div><strong>▯　Safari on iPhone</strong><small>iPhone 15 Pro</small><span>Bengaluru, India<br>106.51.*.*</span><span>2 hours ago</span><i class="profile-status-active">Active</i><button class="revoke">Revoke</button></div>
<div><strong>▱　Chrome on Mac</strong><small>MacBook Pro</small><span>Mumbai, India<br>122.17.*.*</span><span>1 day ago</span><i class="profile-status-active">Active</i><button class="revoke">Revoke</button></div>
</div>
<div class="session-actions"><button class="revoke">Revoke all other devices</button><button>⟳ Refresh</button></div>
</div>

<div class="profile-panel compact"><div class="panel-title">⌁　<strong>Activity</strong><small>Recent audit events for the current organization</small><span>⌄</span></div></div>

</div>

