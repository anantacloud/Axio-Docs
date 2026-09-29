---
layout: default
title: Runner groups
parent: Runner
nav_order: 2
permalink: /axio/administration/runner/group/
---

<link rel="stylesheet" href="{{ '/assets/css/runner-groups.css' | relative_url }}">

<div class="runner-groups-doc">

  <h1>Runner groups</h1>

  <p class="lead">
    Groups are how you organize runners and how stacks/workflows pick a fleet.
    They live under <strong>Administration → Runners → Setup → Step 1.</strong>
  </p>

  <p class="intro">
    Think of a group as a GitHub Actions runner group: runners join the group;
    workloads target the group and labels.
  </p>

  <section>
    <h2>Default group</h2>


<p>
  Every organization has a system <code>Default</code> group.
</p>

<div class="callout callout-info">
  <div class="callout-icon">i</div>

  <ul>
    <li>It cannot be deleted.</li>
    <li>
      You cannot create another group named
      <code>Default</code> (case-insensitive).
    </li>
    <li>
      If you delete a custom group, its runners move to
      <code>Default</code>.
    </li>
  </ul>
</div>


  </section>

  <section>
    <h2>Scope</h2>

<p>When you create or edit a group, choose a scope:</p>

<div class="table-wrap">
  <table>
    <thead>
      <tr>
        <th>UI scope</th>
        <th>Who can use runners in this group</th>
      </tr>
    </thead>

    <tbody>
      <tr>
        <td>Organization</td>
        <td>Entire organization</td>
      </tr>

      <tr>
        <td>Project</td>
        <td>One project</td>
      </tr>

      <tr>
        <td>Workspace</td>
        <td>
          One workspace
          (requires a project that already has workspaces)
        </td>
      </tr>

      <tr>
        <td>Environment</td>
        <td>
          One environment
          (requires a project that already has environments)
        </td>
      </tr>
    </tbody>
  </table>
</div>

<p class="note">
  Workspace scope is stored as project-level scope plus a workspace tag.
  Environment scope requires both a project and an environment.
</p>

<div class="callout callout-success">
  <div class="callout-icon">✓</div>

  <p>
    Narrower scopes keep a GPU or production fleet from being used by
    every stack in the org.
  </p>
</div>


  </section>

  <section>
    <h2>Fields</h2>


<div class="table-wrap">
  <table>
    <thead>
      <tr>
        <th>Field</th>
        <th>Notes</th>
      </tr>
    </thead>

    <tbody>
      <tr>
        <td><strong>Name</strong></td>
        <td>
          Required. <code>Default</code> is reserved.
        </td>
      </tr>

      <tr>
        <td><strong>Description</strong></td>
        <td>Optional</td>
      </tr>

      <tr>
        <td><strong>Scope</strong></td>
        <td>
          Organization / project / workspace / environment
        </td>
      </tr>

      <tr>
        <td><strong>Enabled</strong></td>
        <td>
          Disabled groups cannot receive new registrations.
        </td>
      </tr>

      <tr>
        <td><strong>Max runners</strong></td>
        <td>
          Optional cap for self-hosted runners in this group
          (org-wide sum still respects plan
          <code>maxCustomerRunners</code>).
        </td>
      </tr>
    </tbody>
  </table>
</div>

<div class="callout callout-info">
  <div class="callout-icon">i</div>

  <p>
    The control plane creates an internal default pool on the group
    for isolation and fleet settings. You do not name or manage that
    pool in the Setup UI.
  </p>
</div>


  </section>

  <section class="operation-grid">


<div>
  <h2>Create</h2>

  <ol class="steps">
    <li>
      Open <strong>Runners → Setup.</strong>
    </li>

    <li>
      In Step 1 — Create a runner group, click
      <strong>Create group.</strong>
    </li>

    <li>
      Set name, optional description, and scope.
    </li>

    <li>
      Save. The new group appears in the table and becomes
      selectable in Step 2.
    </li>
  </ol>

  <div class="callout callout-info compact">
    <div class="callout-icon">i</div>

    <p>
      You need
      <code>runner:manage</code>
      or
      <code>runner:customer:manage</code>.
    </p>
  </div>
</div>

<div>
  <h2>Edit</h2>

  <p>
    Use the pencil on a group row. You can change the name
    (except creating a second <code>Default</code>), description,
    scope, and enabled flag.
  </p>
</div>

<div>
  <h2>Delete</h2>

  <ol class="steps">
    <li>
      Open delete on a non-default group.
    </li>

    <li>
      Type <code>DELETE</code> or the exact group name to confirm.
    </li>
  </ol>

  <div class="callout callout-danger compact">
    <div class="callout-icon">!</div>

    <div>
      <strong>Rules:</strong>

      <ul>
        <li>
          The default group cannot be deleted.
        </li>

        <li>
          Runners assigned to the deleted group are moved to
          <code>Default</code>.
        </li>

        <li>
          If the API still reports registered runners blocking delete,
          disconnect or move them first.
        </li>
      </ul>
    </div>
  </div>
</div>


  </section>

  <section class="bottom-grid">


<div>
  <h2>Using a group</h2>

  <ul>
    <li>
      <strong>Registration:</strong>
      Step 2 requires a selected group. The install token is bound
      to that group and its scope.
    </li>

    <li>
      <strong>Workloads:</strong>
      stacks and <code>axio.yaml</code> can set
      <code>strategy: runner-group</code>
      and
      <code>runnerGroup: &lt;name&gt;</code>.
      See
      <a href="{{ '/runners/targeting' | relative_url }}">
        Targeting runners
      </a>.
    </li>

    <li>
      <strong>Inventory:</strong>
      Overview shows the group name on every runner row.
    </li>
  </ul>
</div>

<div>
  <h2>Isolation on the internal pool</h2>

  <p>
    Isolation (process / container / Kubernetes pod) is chosen when
    you generate a registration command, not as a free-form group
    field. It is stored on the group's internal pool and cannot be
    changed later for that pool.
  </p>

  <p>
    Register a new group (or a new internal pool via API) if you need
    a different isolation mode. See
    <a href="{{ '/runners/isolation' | relative_url }}">
      Runner isolation
    </a>.
  </p>
</div>


  </section>

</div>
