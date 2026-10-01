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
    Groups organize self-hosted runners and define which part of the organization may use them.
    Workloads target a group by <strong>name</strong> (for example <code>Default</code>) plus optional labels.
  </p>

  <p class="intro">
    Open <strong>Administration → Runners</strong> at <code>/admin/runners</code>, select the <strong>Setup</strong> tab,
    then <strong>Step 1 — Create a runner group</strong>. Step 2 registers agents into the selected group.
    Think of a group like a GitHub Actions runner group: runners join the group; stacks and workflows target the group and labels.
  </p>

  <div class="callout callout-info">
    <div class="callout-icon">i</div>
    <p>
      Legacy routes such as <code>/administration/execution/runner-registration</code> redirect to <code>/admin/runners</code>.
      Provider-hosted fleet groups are managed separately on the <strong>Hosted fleet</strong> tab (platform provider orgs).
    </p>
  </div>

  <section>
    <h2>Default group</h2>

    <p>
      Every organization gets a system <code>Default</code> group automatically the first time groups are listed
      (<code>GET /organizations/:orgId/runner-groups</code>).
    </p>

    <div class="callout callout-info">
      <div class="callout-icon">i</div>
      <ul>
        <li>It cannot be deleted.</li>
        <li>
          You cannot create another group named <code>Default</code> (case-insensitive).
        </li>
        <li>
          If you delete a custom group, its runners, registration tokens, and pools are moved to <code>Default</code>.
        </li>
        <li>
          The default group is marked with a <em>default</em> chip in the table and shown as <code>(default)</code> in the Step 2 picker.
        </li>
      </ul>
    </div>
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
            <td>Open Runners admin (nav)</td>
            <td><code>runner:manage</code>, <code>runner:customer:manage</code>, or <code>runner:customer:register</code></td>
          </tr>
          <tr>
            <td>List / view groups</td>
            <td><code>runner:read</code> (or broader runner permissions via the UI)</td>
          </tr>
          <tr>
            <td>Create, edit, delete groups (API)</td>
            <td><code>runner:manage</code></td>
          </tr>
          <tr>
            <td>Register runners (Step 2)</td>
            <td><code>runner:customer:register</code>, <code>runner:customer:manage</code>, or <code>runner:manage</code></td>
          </tr>
        </tbody>
      </table>
    </div>

    <p class="note">
      The Setup UI shows create/edit/delete controls when the user has <code>runner:manage</code> or
      <code>runner:customer:manage</code>, but group mutations on the API require <code>runner:manage</code>.
      Read-only users see the group table without action buttons.
    </p>
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
            <td>One selected project</td>
          </tr>
          <tr>
            <td>Workspace</td>
            <td>
              One workspace within a project
              (project must already have workspaces)
            </td>
          </tr>
          <tr>
            <td>Environment</td>
            <td>
              One environment within a workspace
              (project → workspace → environment)
            </td>
          </tr>
        </tbody>
      </table>
    </div>

    <p class="note">
      Workspace scope is stored as <code>scopeType: PROJECT</code> plus a system tag
      <code>axio:workspace:&lt;workspaceId&gt;</code>.
      Environment scope uses <code>scopeType: ENVIRONMENT</code> with both <code>projectId</code> and <code>environmentId</code>.
      Registration in Step 2 must match the group scope; mismatches are rejected.
    </p>

    <div class="callout callout-success">
      <div class="callout-icon">✓</div>
      <p>
        Narrower scopes keep a GPU or production fleet from being used by every stack in the org.
      </p>
    </div>
  </section>

  <section>
    <h2>Group table</h2>

    <p>The Step 1 table includes search (case-insensitive name filter) and these columns:</p>

    <div class="table-wrap">
      <table>
        <thead>
          <tr>
            <th>Column</th>
            <th>Meaning</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td><strong>Name</strong></td>
            <td>Group name; default group shows a <em>default</em> chip</td>
          </tr>
          <tr>
            <td><strong>Scope</strong></td>
            <td>Organization, Project, Workspace, or Environment</td>
          </tr>
          <tr>
            <td><strong>Status</strong></td>
            <td><em>Enabled</em> or <em>Disabled</em></td>
          </tr>
          <tr>
            <td><strong>Runners</strong></td>
            <td>Count of registered runners in the group</td>
          </tr>
          <tr>
            <td><strong>Actions</strong></td>
            <td>Edit (pencil) and delete (non-default groups only)</td>
          </tr>
        </tbody>
      </table>
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
              Required. <code>Default</code> is reserved. Names must be unique within the organization.
            </td>
          </tr>
          <tr>
            <td><strong>Description</strong></td>
            <td>Optional</td>
          </tr>
          <tr>
            <td><strong>Scope</strong></td>
            <td>
              Organization / project / workspace / environment, with cascading project → workspace → environment pickers
            </td>
          </tr>
          <tr>
            <td><strong>Enabled</strong></td>
            <td>
              Shown in the table. Disabled groups cannot receive new registrations (Step 2 blocks token generation).
              Only enabled groups appear in stack/workflow runner-group pickers.
              Toggle via API (<code>enabled</code> on create/update); not exposed in the Setup group form today.
            </td>
          </tr>
          <tr>
            <td><strong>Max runners</strong> (API)</td>
            <td>
              Returned on group objects (<code>maxRunners</code>, default 50) for capacity alignment with internal pools.
              Not editable in the Setup UI. Org-wide registration still respects plan limits such as
              <code>maxCustomerRunners</code> and <code>maxGroups</code>.
            </td>
          </tr>
        </tbody>
      </table>
    </div>

    <div class="callout callout-info">
      <div class="callout-icon">i</div>
      <p>
        The control plane creates an internal default pool per group for isolation and fleet settings.
        You do not name or manage that pool in the Setup UI. Additional internal pools may be created automatically
        when you register runners with a specific isolation mode (see below).
      </p>
    </div>
  </section>

  <section class="operation-grid">

    <div>
      <h2>Create</h2>

      <ol class="steps">
        <li>
          Open <strong>Runners → Setup</strong> (<code>/admin/runners?tab=setup</code>).
        </li>
        <li>
          In Step 1, click <strong>Create group</strong>.
        </li>
        <li>
          Set name, optional description, and scope (plus project / workspace / environment when required).
        </li>
        <li>
          Save. The new group appears in the table and becomes selectable in Step 2.
        </li>
      </ol>

      <div class="callout callout-info compact">
        <div class="callout-icon">i</div>
        <p>
          Requires <code>runner:manage</code> on the API
          (<code>POST /organizations/:orgId/runner-groups</code>).
          Subject to organization group quota (<code>maxGroups</code>) when configured.
        </p>
      </div>
    </div>

    <div>
      <h2>Edit</h2>

      <p>
        Use the pencil icon on a group row. In the Setup UI you can change the name
        (except creating a second <code>Default</code>), description, and scope.
        Saving calls <code>PATCH /organizations/:orgId/runner-groups/:groupId</code>.
      </p>
      <p class="note">
        Changing scope may trigger the control plane to ensure the group’s internal default pool matches the new scope.
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
            <li>The default group cannot be deleted.</li>
            <li>
              Registered runners in the deleted group are moved to <code>Default</code> along with their pools and tokens.
            </li>
            <li>
              Empty groups have their internal pools removed; the group record is then deleted.
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
          <strong>Registration (Step 2):</strong>
          Select a runner group before generating an install command. The registration token is bound to that group,
          its scope, and the chosen platform/isolation. Disabled groups cannot be used.
        </li>
        <li>
          <strong>Workloads:</strong>
          Stacks and <code>axio.yaml</code> can set
          <code>runner.strategy: runner-group</code> and
          <code>runner.runnerGroup: &lt;name&gt;</code>
          (match the group <strong>name</strong>, not the internal id).
          Combine with <code>runnerLabels</code> to narrow to labeled runners within the group.
        </li>
        <li>
          <strong>Inventory:</strong>
          The <strong>Overview</strong> tab shows the group name on each runner row.
        </li>
        <li>
          <strong>Reassign runners:</strong>
          Use runner edit actions or API assign/remove endpoints to move runners between groups
          (scope must remain compatible).
        </li>
      </ul>
    </div>

    <div>
      <h2>Isolation and internal pools</h2>

      <p>
        Isolation (process / container / Kubernetes pod) is chosen in Step 2 when you register a runner
        (platform-dependent — for example Linux/Windows support process or container; Docker requires container;
        Kubernetes requires pod isolation).
      </p>

      <p>
        The control plane selects or creates an internal pool for that isolation mode on the group.
        Pool isolation cannot be changed after creation; register against a different isolation choice
        (which may create another internal pool) if you need a separate execution mode.
      </p>

      <p class="note">
        See repository docs <code>docs/RUNNER.md</code> and <code>docs/RUNNER_FLEET.md</code> for fleet and execution details.
      </p>
    </div>

  </section>

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
            <td><code>GET /organizations/:orgId/runner-groups</code></td>
            <td>List groups; optional <code>?search=</code>. Ensures <code>Default</code> exists.</td>
          </tr>
          <tr>
            <td><code>POST /organizations/:orgId/runner-groups</code></td>
            <td>Create group (<code>runner:manage</code>)</td>
          </tr>
          <tr>
            <td><code>PATCH /organizations/:orgId/runner-groups/:groupId</code></td>
            <td>Update name, description, scope, tags, <code>enabled</code> (<code>runner:manage</code>)</td>
          </tr>
          <tr>
            <td><code>DELETE /organizations/:orgId/runner-groups/:groupId</code></td>
            <td>Delete group; runners/tokens/pools moved to <code>Default</code> (<code>runner:manage</code>)</td>
          </tr>
          <tr>
            <td><code>POST /organizations/:orgId/runner-groups/:groupId/runners</code></td>
            <td>Assign existing runners to a group (<code>runner:manage</code>)</td>
          </tr>
          <tr>
            <td><code>DELETE /organizations/:orgId/runner-groups/:groupId/runners/:runnerId</code></td>
            <td>Remove runner from group (moves to <code>Default</code>)</td>
          </tr>
        </tbody>
      </table>
    </div>
  </section>

  <div class="callout callout-info">
    <div class="callout-icon">i</div>
    <p>
      <strong>Example axio.yaml</strong> — target the system default group:
    </p>
    <pre><code>runner:
  strategy: runner-group
  runnerGroup: Default</code></pre>
  </div>

</div>
