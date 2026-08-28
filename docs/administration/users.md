---
layout: default
title: Users
parent: Administration
nav_order: 3
---

<div class="admin-users-page">

  <h1>Administration — Users</h1>
  <p class="admin-users-subtitle">Internal membership and directory-synced accounts.</p>

  <div class="admin-users-info">
    <span class="admin-users-info-icon">ⓘ</span>
    <span>
      Overview: <code>ADMINISTRATION.md</code>
      <b>•</b>
      Custom roles: <code>ADMINISTRATION_ROLES_ACCESS.md</code>
      <b>•</b>
      SSO/SCIM: <code>ADMINISTRATION_INTEGRATIONS.md</code>
      <b>•</b>
      Membership matrix: <code>ORGANIZATION_ROLES.md</code>
    </span>
  </div>

  <div class="admin-users-tabs">
    <div class="admin-users-tab active">
      <span>♧</span> Internal users
    </div>
    <div class="admin-users-tab">
      <span>☁</span> Synced users
    </div>
  </div>

  <section class="admin-users-panel">
    <div class="admin-users-toolbar">
      <p>Manage organization members, roles, status, and optional group membership.</p>

      <div class="admin-users-actions">
        <div class="admin-users-search">
          <span>⌕</span>
          <span>Search users...</span>
        </div>
        <button class="admin-users-filter">▽ &nbsp; Filters</button>
        <button class="admin-users-invite">♙ &nbsp; Invite user</button>
      </div>
    </div>

    <div class="admin-users-table-wrap">
      <table class="admin-users-table">
        <thead>
          <tr>
            <th>User</th>
            <th>Email</th>
            <th>Role <span class="admin-users-help">ⓘ</span></th>
            <th>Groups</th>
            <th>Status</th>
            <th>Last active</th>
            <th>Actions</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>
              <div class="admin-user-name">
                <span class="admin-avatar purple">SK</span>
                <strong>Sarah Kapoor</strong>
                <span class="admin-you">You</span>
              </div>
            </td>
            <td>sarah.kapoor@acme.com</td>
            <td><span class="admin-role owner">OWNER</span></td>
            <td>Platform Team, Admins</td>
            <td><span class="admin-status"><i></i> Active</span></td>
            <td>Just now</td>
            <td><span class="admin-action">♢</span><span class="admin-action">⋮</span></td>
          </tr>
          <tr>
            <td>
              <div class="admin-user-name">
                <span class="admin-avatar blue">AR</span>
                <strong>Amit Rawat</strong>
              </div>
            </td>
            <td>amit.rawat@acme.com</td>
            <td><span class="admin-role admin">ADMIN</span></td>
            <td>Platform Team</td>
            <td><span class="admin-status"><i></i> Active</span></td>
            <td>2 hours ago</td>
            <td><span class="admin-action">♢</span><span class="admin-action">⋮</span></td>
          </tr>
          <tr>
            <td>
              <div class="admin-user-name">
                <span class="admin-avatar green">NT</span>
                <strong>Neha Tiwari</strong>
              </div>
            </td>
            <td>neha.tiwari@acme.com</td>
            <td><span class="admin-role member">MEMBER</span></td>
            <td>Developers</td>
            <td><span class="admin-status"><i></i> Active</span></td>
            <td>1 day ago</td>
            <td><span class="admin-action">♢</span><span class="admin-action">⋮</span></td>
          </tr>
        </tbody>
      </table>
    </div>

    <div class="admin-users-pagination">
      <span>Showing 1 to 3 of 3 users</span>
      <div>
        <button disabled>‹ &nbsp; Previous</button>
        <button class="current">1</button>
        <button>Next &nbsp; ›</button>
      </div>
    </div>
  </section>

  <section class="admin-quick-actions">
    <h2><span class="admin-lightning">ϟ</span> Quick actions</h2>
    <div class="admin-quick-grid">
      <div class="admin-quick-card">
        <span class="admin-quick-icon purple-bg">♙</span>
        <div><strong>Invite user</strong><p>Send an invitation<br>to join this organization</p></div>
        <span class="arrow">›</span>
      </div>
      <div class="admin-quick-card">
        <span class="admin-quick-icon blue-bg">♧</span>
        <div><strong>Manage groups</strong><p>Add or remove users<br>from groups</p></div>
        <span class="arrow">›</span>
      </div>
      <div class="admin-quick-card">
        <span class="admin-quick-icon green-bg">♢</span>
        <div><strong>Assign custom role</strong><p>Grant scoped access<br>using custom roles</p></div>
        <span class="arrow">›</span>
      </div>
      <div class="admin-quick-card">
        <span class="admin-quick-icon orange-bg">▤</span>
        <div><strong>View audit logs</strong><p>See recent membership<br>changes</p></div>
        <span class="arrow">›</span>
      </div>
    </div>
  </section>

  <div class="admin-bottom-grid">

    <section class="admin-note membership">
      <h2><span>♢</span> Membership rules</h2>
      <ul>
        <li>You cannot invite someone directly as OWNER (ownership is transferred explicitly).</li>
        <li>Last OWNER cannot be demoted, removed, or disabled.</li>
        <li>You cannot disable or remove your own account.</li>
      </ul>
      <div class="admin-note-callout">
        <span>ⓘ</span>
        <span>
          Baseline OWNER / MEMBER / VIEWER is managed here.<br>
          Additive custom RBAC is managed on <code>Roles &amp; Access → Role Assignments</code>.
        </span>
      </div>
    </section>

    <section class="admin-note about">
      <h2><span>●</span> About the tabs</h2>

      <div class="admin-about-row">
        <span class="admin-about-icon purple-bg">♙</span>
        <p><strong>Internal users:</strong> Organization members you invite and manage.<br>
        You can edit roles, groups, status, and remove members.</p>
      </div>

      <div class="admin-about-divider"></div>

      <div class="admin-about-row">
        <span class="admin-about-icon blue-bg">☁</span>
        <p><strong>Synced users:</strong> Read-only directory identities from SSO/SCIM.<br>
        Manage them in your identity provider.</p>
      </div>
    </section>

  </div>
</div>

