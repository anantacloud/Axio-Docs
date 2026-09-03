---
layout: default
title: Overview
parent: Role & Access
nav_order: 2
---


<div class="rao-page">

    <header class="rao-title-block">
    <h1>Roles &amp; Access Overview</h1>
    <p>Understand the built-in roles, how access works in AXIO, and the core principles that keep your organization secure and simple.</p>
   </header>

  <div class="rao-info-box">
    <span class="rao-info-icon">i</span>
    <p>
      AXIO uses a role-based access model with scope-based access to ensure users can only
      see and perform actions that are relevant to their role and scope.
    </p>
  </div>


    <div class="rao-role-grid">

      <article class="rao-role-card">
        <div class="rao-role-icon">♛</div>
        <h3>Owner</h3>
        <p>Full control over the organization. Can manage all settings, users, projects, and resources.</p>
        <span class="rao-role-label">Highest privilege</span>
      </article>

      <article class="rao-role-card">
        <div class="rao-role-icon">♜</div>
        <h3>Admin</h3>
        <p>Manages users, roles, projects, and platform settings within their assigned scope.</p>
        <span class="rao-role-label">High privilege</span>
      </article>

      <article class="rao-role-card">
        <div class="rao-role-icon">♟</div>
        <h3>Member</h3>
        <p>Can create and manage resources (e.g., stacks) and operate within their assigned scope.</p>
        <span class="rao-role-label">Standard access</span>
      </article>

      <article class="rao-role-card">
        <div class="rao-role-icon">●</div>
        <h3>Viewer</h3>
        <p>Read-only access. Can view resources and data within their assigned scope.</p>
        <span class="rao-role-label">Read-only access</span>
      </article>

      <article class="rao-role-card rao-unassigned">
        <div class="rao-role-icon">⊘</div>
        <h3>Unassigned</h3>
        <p>No access to any resources. Access is granted only after a role is assigned.</p>
        <span class="rao-role-label">No access</span>
      </article>

    </div>


  <!-- 2. KEY CONCEPTS -->
  <section class="rao-section">
    <h2><span class="rao-number">2</span> Key Concepts</h2>

    <div class="rao-concept-grid">

      <article class="rao-concept-card">
        <div class="rao-concept-icon">◎</div>
        <div>
          <h3>Role</h3>
          <p>Defines what a user can do (permissions). Example: Member can create stacks, Viewer can only view.</p>
        </div>
      </article>

      <article class="rao-concept-card">
        <div class="rao-concept-icon">▦</div>
        <div>
          <h3>Scope</h3>
          <p>Defines where a user can access. Hierarchy: Organization → Project → Workspace → Environment.</p>
        </div>
      </article>

      <article class="rao-concept-card">
        <div class="rao-concept-icon">◆</div>
        <div>
          <h3>Most-Specific Role</h3>
          <p>The most-specific role in the hierarchy (e.g., Environment) always takes precedence.</p>
        </div>
      </article>

      <article class="rao-concept-card">
        <div class="rao-concept-icon">♣</div>
        <div>
          <h3>Group</h3>
          <p>A collection of users who can be assigned roles together to simplify management.</p>
        </div>
      </article>

    </div>
  </section>

  <!-- 3. HOW ACCESS WORKS -->
  <section class="rao-section rao-access-section">
    <h2><span class="rao-number">3</span> How Access Works</h2>

    <div class="rao-flow">

      <article class="rao-flow-item">
        <div class="rao-flow-icon">♟+</div>
        <h3>1. Assign Role</h3>
        <p>A user or group is assigned a role.</p>
      </article>

      <div class="rao-flow-arrow">→</div>

      <article class="rao-flow-item">
        <div class="rao-flow-icon">●</div>
        <h3>2. Define Scope</h3>
        <p>The role is assigned at a specific scope (Org / Project / Workspace / Environment).</p>
      </article>

      <div class="rao-flow-arrow">→</div>

      <article class="rao-flow-item">
        <div class="rao-flow-icon">✓</div>
        <h3>3. Access Granted</h3>
        <p>The user can access resources based on their role and scope.</p>
      </article>

      <div class="rao-flow-arrow">→</div>

      <article class="rao-flow-item">
        <div class="rao-flow-icon">▣</div>
        <h3>4. Enforced Everywhere</h3>
        <p>The same rules are enforced in the UI, API, and all platform operations.</p>
      </article>

    </div>
  </section>

  <!-- CORE PRINCIPLE -->
  <div class="rao-core-box">
    <span class="rao-core-icon">💡</span>
    <div>
      <h3>Core Principle</h3>
      <p>
        Built-in roles (Owner, Admin, Member, Viewer) decide <strong>WHERE</strong> a user can go (scope).
        <br>
        Custom roles decide <strong>WHAT EXTRA</strong> they can do, but they never open new scope.
      </p>
    </div>
  </div>

  <div class="rao-tip-box">
    <span class="rao-info-icon">i</span>
    <p>This guide uses simple language to help everyone understand roles and access clearly.</p>
  </div>

</div>


