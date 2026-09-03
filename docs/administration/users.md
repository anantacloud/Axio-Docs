---
layout: default
title: Users & Role Assignment
parent: Role & Access
nav_order: 3
---


<div class="ura-page">


  <header class="ura-title-block">
    <h1>Users &amp; Role Assignment</h1>
    <p>Understand how users are added, how roles are assigned, and how groups simplify access management.</p>
  </header>

  <div class="ura-info-box">
    <span class="ura-info-icon">i</span>
    <p>
      Access in AXIO is always given to a <strong>User</strong> or <strong>Group</strong> at a specific
      scope with a <strong>role</strong>.<br>
      Roles decide what actions are allowed, and <strong>scope</strong> decides where.
    </p>
  </div>

  <!-- 1. USERS & MEMBERSHIP -->
  <section class="ura-section">
    <h2><span class="ura-number">1</span> Users &amp; Membership</h2>
    <p class="ura-intro">
      Users are the people who access AXIO. They become members when added to the organization.
    </p>

    <div class="ura-card-grid four">

      <article class="ura-card">
        <div class="ura-icon">♟+</div>
        <h3>Add Users</h3>
        <p>Invite users to your organization.</p>
      </article>

      <article class="ura-card">
        <div class="ura-icon">✉</div>
        <h3>Invitation &amp; Join</h3>
        <p>Users receive an invitation and join the organization.</p>
      </article>

      <article class="ura-card">
        <div class="ura-icon">♟♟</div>
        <h3>Active Members</h3>
        <p>Joined users appear in the Members list and can be assigned roles.</p>
      </article>

      <article class="ura-card">
        <div class="ura-icon">♟✓</div>
        <h3>User Status</h3>
        <p>Active, Inactive, or Removed users.</p>
      </article>

    </div>
  </section>

  <!-- 2. ROLE ASSIGNMENT -->
  <section class="ura-section">
    <h2><span class="ura-number">2</span> Role Assignment</h2>
    <p class="ura-intro">
      Assign roles to users or groups at any scope. The role defines what they can do within that scope.
    </p>

    <div class="ura-assignment-flow">

      <article class="ura-flow-card">
        <div class="ura-flow-icon">♟</div>
        <h3>Select Principal</h3>
        <p>Choose a <strong>User</strong> or <strong>Group</strong>.</p>
      </article>

      <div class="ura-flow-arrow">→</div>

      <article class="ura-flow-card">
        <div class="ura-flow-icon">▦</div>
        <h3>Select Scope</h3>
        <p>Choose the scope: Organization, Project, Workspace, Environment.</p>
      </article>

      <div class="ura-flow-arrow">→</div>

      <article class="ura-flow-card">
        <div class="ura-flow-icon">⬟</div>
        <h3>Select Role</h3>
        <p>Pick a role: Owner, Admin, Member, Viewer, or Unassigned.</p>
      </article>

      <div class="ura-flow-arrow">→</div>

      <article class="ura-flow-card">
        <div class="ura-flow-icon">✓</div>
        <h3>Apply</h3>
        <p>Save the assignment. Access is granted based on role and scope.</p>
      </article>

    </div>

    <table class="ura-table ura-role-table">
      <thead>
        <tr>
          <th>Role</th>
          <th>Description</th>
          <th>Typical Use</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><span class="ura-table-icon">♛</span><strong>Owner</strong></td>
          <td>Full control over the organization and all settings.</td>
          <td>Used by platform owners.</td>
        </tr>
        <tr>
          <td><span class="ura-table-icon">♜</span><strong>Admin</strong></td>
          <td>Manages users, roles, projects, and platform settings within scope.</td>
          <td>Used by administrators.</td>
        </tr>
        <tr>
          <td><span class="ura-table-icon">♟♟</span><strong>Member</strong></td>
          <td>Can create and manage resources within their scope.</td>
          <td>Used by operators and developers.</td>
        </tr>
        <tr>
          <td><span class="ura-table-icon">●</span><strong>Viewer</strong></td>
          <td>Read-only access to view resources and data.</td>
          <td>Used by auditors and viewers.</td>
        </tr>
        <tr>
          <td><span class="ura-table-icon ura-muted-icon">●</span><strong>Unassigned</strong></td>
          <td>No access to any resources. Access after role assignment.</td>
          <td>Default state for new users.</td>
        </tr>
      </tbody>
    </table>
  </section>

  <!-- 3. GROUPS -->
  <section class="ura-section">
    <h2><span class="ura-number">3</span> Groups</h2>
    <p class="ura-intro">Groups help you manage access for multiple users at the same time.</p>

    <div class="ura-groups-layout">

      <article class="ura-group-card">
        <div class="ura-group-icon">♟♟♟</div>
        <div>
          <h3>Create Groups</h3>
          <p>Create groups like DevOps Team, Security Team, Auditors, etc.</p>
        </div>
      </article>

      <article class="ura-group-card">
        <div class="ura-group-icon">✓</div>
        <div>
          <h3>Assign Roles</h3>
          <p>Assign roles to groups at the required scope. All members inherit the same access.</p>
        </div>
      </article>

      <div class="ura-benefits">
        <div class="ura-benefits-title">
          <span class="ura-check-icon">✓</span>
          Benefits of Groups
        </div>
        <ul>
          <li>Simplify role management for many users.</li>
          <li>Ensure consistent access across teams.</li>
          <li>Easier to onboard and offboard users.</li>
          <li>Reduce errors and improve security.</li>
        </ul>
      </div>

    </div>
  </section>

  <!-- 4. IMPORTANT NOTES -->
  <section class="ura-section">
    <h2><span class="ura-number">4</span> Important Notes</h2>

    <div class="ura-notes">
      <div class="ura-note">
        <span>◎</span>
        <p>Access is always given at a specific scope.</p>
      </div>

      <div class="ura-note">
        <span>⬟</span>
        <p>Roles define what actions are allowed, not where.</p>
      </div>

      <div class="ura-note">
        <span>♟♟</span>
        <p>Groups inherit access from the role assigned to them.</p>
      </div>

      <div class="ura-note">
        <span>🔒</span>
        <p>Removing a role removes access.</p>
      </div>
    </div>
  </section>

  <div class="ura-reminder">
    <span class="ura-info-icon">i</span>
    <p>
      <strong>Remember:</strong>
      Use the least privilege role possible. Review access regularly and remove what is no longer needed.
    </p>
  </div>

</div>

