---
layout: default
title: Groups
parent: Administration
nav_order: 4
---

<div class="admin-groups-page">

  <h1>Administration — Groups</h1>
  <p class="admin-groups-lead">Local teams plus directory-synced groups.</p>

  <div class="admin-groups-info">
    <span class="info-dot">i</span>
    <span>Overview: <code>ADMINISTRATION.md</code></span>
    <span class="info-separator">•</span>
    <span>Users: <code>ADMINISTRATION_USERS.md</code></span>
    <span class="info-separator">•</span>
    <span>Assigning custom roles to groups: <code>ADMINISTRATION_ROLES_ACCESS.md</code></span>
  </div>

  <div class="groups-tabs">
    <button class="groups-tab active" type="button">
      <span class="tab-icon">♙</span>
      Internal groups
    </button>
    <button class="groups-tab" type="button">
      <span class="tab-icon cloud">☁</span>
      Synced groups
    </button>
  </div>

  <section class="groups-workspace">
    <div class="groups-toolbar">
      <p>Create and manage local groups and their members.</p>
      <div class="groups-actions">
        <label class="groups-search">
          <span>⌕</span>
          <input type="text" placeholder="Search groups..." aria-label="Search groups">
        </label>
        <button class="groups-filter" type="button">▽ &nbsp; Filters</button>
        <button class="create-group" type="button">＋ Create group</button>
      </div>
    </div>

    <div class="group-grid">

      <article class="group-card green">
        <div class="group-card-top">
          <div class="group-symbol">♧</div>
          <div class="group-heading">
            <h2>Platform Team</h2>
            <span>8 members</span>
          </div>
          <button class="more-btn" type="button" aria-label="Platform Team actions">•••</button>
        </div>
        <p>Team responsible for platform operations and governance.</p>
        <div class="avatars">
          <span>SK</span><span>AR</span><span>NT</span><span>PM</span><span class="more-avatar">+4</span>
        </div>
        <small>Created on Apr 12, 2024</small>
      </article>

      <article class="group-card blue">
        <div class="group-card-top">
          <div class="group-symbol">♧</div>
          <div class="group-heading">
            <h2>Developers</h2>
            <span>15 members</span>
          </div>
          <button class="more-btn" type="button" aria-label="Developers actions">•••</button>
        </div>
        <p>Application developers and engineers building our products.</p>
        <div class="avatars">
          <span>RS</span><span>VD</span><span>AK</span><span>DP</span><span class="more-avatar">+11</span>
        </div>
        <small>Created on May 20, 2024</small>
      </article>

      <article class="group-card orange">
        <div class="group-card-top">
          <div class="group-symbol">♧</div>
          <div class="group-heading">
            <h2>DevOps</h2>
            <span>6 members</span>
          </div>
          <button class="more-btn" type="button" aria-label="DevOps actions">•••</button>
        </div>
        <p>Infrastructure, CI/CD and release management team.</p>
        <div class="avatars">
          <span>NP</span><span>MG</span><span>PS</span><span class="more-avatar">+3</span>
        </div>
        <small>Created on Jun 5, 2024</small>
      </article>

    </div>

    <div class="groups-pagination">
      <span>Showing 1 to 3 of 3 groups</span>
      <div>
        <button type="button" disabled>‹ &nbsp; Previous</button>
        <button class="current-page" type="button">1</button>
        <button type="button" disabled>Next &nbsp; ›</button>
      </div>
    </div>
  </section>

  <div class="groups-bottom">

    <section class="groups-panel about-groups">
      <h2><span class="panel-icon green-icon">✓</span> About groups</h2>
      <ul>
        <li>Groups help you organize users and simplify access management.</li>
        <li>Assign custom roles to groups from <code>Roles &amp; Access → Role Assignments</code>.</li>
        <li>Changes to group membership reflect in access where group is assigned.</li>
      </ul>
      <div class="panel-note green-note">
        <span>ⓘ</span>
        Groups are not listed under Organization navigation.
      </div>
    </section>

    <section class="groups-panel about-tabs">
      <h2><span class="panel-icon orange-icon">i</span> About the tabs</h2>

      <div class="tab-explanation">
        <div class="explain-icon internal-icon">♧</div>
        <div>
          <strong>Internal groups:</strong>
          Create, rename, delete local groups and manage their members.
        </div>
      </div>

      <div class="tab-explanation synced-explanation">
        <div class="explain-icon synced-icon">☁</div>
        <div>
          <strong>Synced groups:</strong>
          Read-only groups from your identity provider via SCIM / directory sync.
        </div>
      </div>
    </section>

  </div>

</div>

