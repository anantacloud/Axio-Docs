---
layout: default
title: Overview
parent: Organization
nav_order: 1
description: Learn how Organization resources are structured in Axio.
permalink: /axio/organization/overview/
---

<link rel="stylesheet" href="{{ '/assets/css/organization-overview.css' | relative_url }}">

# Organization

<div class="announcement-box">

    <div class="announcement-icon">
        <img src="{{ '/assets/icons/building-2.svg' | relative_url }}"
             alt="Organization">
    </div>

    <div class="announcement-content">

        <h2>Manage all your organizational resources in one place.</h2>

        <p>
            Create and manage
            <strong>Projects</strong>,
            <strong>Workspaces</strong>, and
            <strong>Environments</strong>
            using either the
            <strong>Axio UI</strong>
            or
            <strong>Platform as Code (Git-based)</strong>.
        </p>

    </div>

</div>

---

## What is an organization?

An **organization** is the top-level tenant boundary in Axio. Everything you manage—projects, workspaces, environments, stacks, runners, policies, and users—belongs to a single organization.

| Concept | Description |
|---------|-------------|
| **Organization** | Your tenant: billing, members, governance, and all platform resources |
| **Organization ID** | An 8-character code shown on **Organization → Overview**. Use this at sign-in—not the organization display name or slug |
| **Organization name** | Human-readable display name for the tenant |
| **Members** | Users invited or provisioned with a role and optional scope |


<div class="organization-context-notes">

  <p>After sign-in, the organization context determines which resources, permissions, and settings apply to your session.</p>

  <p>Every new organization is also provisioned with a system <strong>Default Project</strong>, <strong>Default Workspace</strong>, and <strong>Default Environment</strong> for bootstrap    and fallback assignment.</p>

</div>

---

<section class="resource-hierarchy-section">

  <h2>Resource hierarchy</h2>

  <p class="section-description">
    Organization resources form a nested hierarchy. Use this order when creating resources and assigning access.
  </p>

  <div class="hierarchy-layout">

    <div class="hierarchy-visual">
      <div class="hierarchy-tree">
        <div class="tree-level tree-organization">
          <span class="tree-icon">▣</span>
          <strong>Organization</strong>
        </div>

        <div class="tree-level tree-project">
          <span class="tree-branch">└──</span>
          <span class="tree-icon">□</span>
          <strong>Project</strong>
        </div>

        <div class="tree-level tree-workspace">
          <span class="tree-branch">└──</span>
          <span class="tree-icon">◈</span>
          <strong>Workspace</strong>
        </div>

        <div class="tree-level tree-environment">
          <span class="tree-branch">└──</span>
          <span class="tree-icon">◎</span>
          <strong>Environment</strong>
        </div>

        <div class="tree-level tree-stack">
          <span class="tree-branch">└──</span>
          <span class="tree-icon">▤</span>
          <strong>Stack</strong>
          <span class="tree-muted">(provisioned infrastructure)</span>
        </div>

        <div class="tree-level tree-workflow">
          <span class="tree-branch">└──</span>
          <span class="tree-icon">▷</span>
          <strong>Workflow / Deployment</strong>
        </div>
      </div>
    </div>

    <div class="hierarchy-table-wrapper">
      <table class="hierarchy-table">
        <thead>
          <tr>
            <th>Layer</th>
            <th>Role</th>
          </tr>
        </thead>

        <tbody>
          <tr>
            <td><strong>Project</strong></td>
            <td>
              Groups workspaces; project-level configuration,
              lifecycle policy overrides, and access scope
            </td>
          </tr>

          <tr>
            <td><strong>Workspace</strong></td>
            <td>
              Belongs to a project; contains environments;
              links to IaC state and stack provisioning
            </td>
          </tr>

          <tr>
            <td><strong>Environment</strong></td>
            <td>
              Deployment target where workflows run, deployments
              are approved, and governance rules apply
            </td>
          </tr>

          <tr>
            <td><strong>Stack</strong></td>
            <td>
              Infrastructure defined in Git (Terraform, Pulumi, etc.)
              deployed into an environment
            </td>
          </tr>
        </tbody>
      </table>
    </div>

  </div>

  <div class="creation-order">
    <span class="creation-order-icon">💡</span>
    <span>
      <strong>Recommended creation order:</strong>
      Project → Workspace → Environment → Stack
    </span>
  </div>

  <div class="hierarchy-example">

    <div class="example-heading">
      <span class="example-icon">▣</span>
      <strong>Example</strong>
    </div>

    <ol>
      <li>
        <strong>Project:</strong>
        <code>payments-platform</code>
      </li>

      <li>
        <strong>Workspace:</strong>
        <code>payments-infra</code>
        <span>(assigned to the project)</span>
      </li>

      <li>
        <strong>Environment:</strong>
        <code>production</code>
        <span>(owners assigned, self-approval disabled)</span>
      </li>

      <li>
        <strong>Stack:</strong>
        Terraform stack deployed into
        <code>production</code>
      </li>
    </ol>

  </div>

</section>

---

## Organization Resources

<p class="section-description">
An organization consists of the following core resources.
</p>

<div class="resource-grid">

<!-- ===================== PROJECT ====================== -->

<div class="resource-card project">

    <div class="card-title">

        <img class="project-icon" src="{{ '/assets/icons/folder.svg' | relative_url }}"
             alt="Projects">

        <h3>Projects</h3>

    </div>

    <p>
        Group related workspaces and manage project-level configuration and access.
    </p>

    <h4>Features</h4>

    <ul>

        <li>Group related workspaces</li>

        <li>Mark projects as sensitive</li>

        <li>Archive projects when eligible</li>

        <li>Override organization environment lifecycle policies</li>

    </ul>

    <p><strong>In the UI:</strong> Organization → <strong>Projects</strong></p>

    <div class="card-footer">

        <a href="{{ '/axio/organization/project/create-project-ui/' | relative_url }}">

            Explore Projects →

        </a>

    </div>

</div>

<!-- ===================== WORKSPACE ====================== -->

<div class="resource-card workspace">

    <div class="card-title">

        <img class="workspace-icon" src="{{ '/assets/icons/boxes.svg' | relative_url }}"
             alt="Workspaces">

        <h3>Workspaces</h3>

    </div>

    <p>
        Workspaces belong to projects and contain environments for applications, services, and infrastructure.
    </p>

    <h4>Features</h4>

    <ul>

        <li>Contain environments</li>

        <li>Assign or unassign from projects</li>

        <li>Mark workspaces as sensitive</li>

        <li>Archive workspaces when eligible</li>

    </ul>

    <p><strong>In the UI:</strong> Organization → <strong>Workspaces</strong></p>

    <div class="card-footer">

        <a href="{{ '/axio/organization/workspace/create-workspace-ui/' | relative_url }}">

            Explore Workspaces →

        </a>

    </div>

</div>

<!-- ===================== ENVIRONMENT ====================== -->

<div class="resource-card environment">

    <div class="card-title">

        <img class="environment-icon" src="{{ '/assets/icons/globe.svg' | relative_url }}"
             alt="Environments">

        <h3>Environments</h3>

    </div>

    <p>
        Environments are deployment targets where workflows run and deployments are approved.
    </p>

    <h4>Features</h4>

    <ul>

        <li>Assign users or groups as owners</li>

        <li>Run workflows and approve deployments</li>

        <li>Configure self-approval behavior</li>

        <li>Set TTL, destroy protection, and lifecycle rules</li>

    </ul>

    <p><strong>In the UI:</strong> Organization → <strong>Environments</strong></p>

    <div class="card-footer">

        <a href="{{ '/axio/organization/environment/create-environment-ui/' | relative_url }}">

            Explore Environments →

        </a>

    </div>

</div>

</div>

---

## Key concepts

<div class="resource-grid-info">

<div class="resource-card project">

    <div class="card-title">

        <img class="project-icon" src="{{ '/assets/icons/folder.svg' | relative_url }}"
             alt="Sensitive">

        <h3>Sensitive resources</h3>

    </div>

    <p>
        Projects, workspaces, and environments can be marked <strong>Sensitive</strong> for production-critical or compliance-bound resources.
    </p>

    <ul>

        <li>Sensitive resources cannot be deleted</li>

        <li>Sensitive resources cannot be archived</li>

        <li>Destroy deployments for stacks linked to sensitive environments are blocked</li>

    </ul>

</div>

<div class="resource-card workspace">

    <div class="card-title">

        <img class="workspace-icon" src="{{ '/assets/icons/boxes.svg' | relative_url }}"
             alt="Archive">

        <h3>Archiving resources</h3>

    </div>

    <p>
        Archive projects, workspaces, or environments when they are no longer active. Archiving is a reversible soft deactivation.
    </p>

    <ul>

        <li>Archived resources are retained for reference and can be unarchived</li>

        <li>Sensitive resources cannot be archived</li>

        <li>System and Git-managed resources have limited archive/delete options in the UI</li>

        <li><strong>Delete</strong> is permanent: projects must have no workspaces; workspaces must have no environments</li>

    </ul>

</div>

<div class="resource-card environment">

    <div class="card-title">

        <img class="environment-icon" src="{{ '/assets/icons/globe.svg' | relative_url }}"
             alt="Self-approval">

        <h3>Self-approval</h3>

    </div>

    <p>
        Each environment controls whether the user who triggered a workflow may also approve it.
    </p>

    <ul>

        <li><strong>Self-approval allowed</strong> — the initiator may approve when they are an owner</li>

        <li><strong>Skip self-approval</strong> — the initiator cannot approve; another owner must approve</li>

        <li>Production environments typically disable self-approval</li>

    </ul>

</div>

</div>

---

<section class="access-roles-section">

  <h2>Access, roles, and permissions</h2>

  <p class="access-intro">
    Who can create and manage organization resources depends on
    <strong>organization membership role</strong> and optional
    <strong>scoped assignments</strong> via
    <strong>Administration → Roles &amp; Access</strong>.
  </p>

  <div class="access-table-wrapper">
    <table class="access-roles-table">
      <thead>
        <tr>
          <th>Role</th>
          <th>Create projects / workspaces</th>
          <th>Delete projects</th>
          <th>Manage org settings &amp; members</th>
        </tr>
      </thead>

      <tbody>
        <tr>
          <td><strong>Owner</strong></td>
          <td>Yes</td>
          <td>Yes</td>
          <td>Yes</td>
        </tr>

        <tr>
          <td><strong>Admin</strong></td>
          <td>Yes</td>
          <td>Yes</td>
          <td>Limited</td>
        </tr>

        <tr>
          <td><strong>Member</strong></td>
          <td>Yes*</td>
          <td>No</td>
          <td>No</td>
        </tr>

        <tr>
          <td><strong>Viewer</strong></td>
          <td>No</td>
          <td>No</td>
          <td>No</td>
        </tr>

        <tr>
          <td><strong>Unassigned</strong></td>
          <td>No</td>
          <td>No</td>
          <td>No</td>
        </tr>
      </tbody>
    </table>
  </div>

  <p class="access-footnote">
    *Members with <strong>project-, workspace-, or environment-scoped</strong>
    access only cannot create new projects.
  </p>

  <p class="access-scope-note">
    Scoped assignments can apply at organization, business unit, project,
    workspace, or environment level.
  </p>

</section>


<section class="organization-settings-section">

  <h2>Organization settings and business units</h2>

  <div class="organization-subsection">

    <h3>Organization settings</h3>

    <p>
      <strong>Organization → Settings</strong> covers tenant-wide governance,
      including environment lifecycle policies (default TTL, max TTL,
      active environment limits), MFA, and other organization-level
      configuration. Project detail pages can override lifecycle defaults
      when permitted.
    </p>

  </div>


  <div class="organization-subsection">

    <h3>Business units (enterprise)</h3>

    <p>
      <strong>Organization → Business Units</strong> provides hierarchy and
      delegated administration for multi-team tenants. Business units
      complement Project → Workspace → Environment for
      <strong>access and delegation</strong>—they do not replace that
      resource hierarchy.
    </p>

    <p>
      When a workspace is unassigned from a project, it moves to the system
      <strong>Default Project</strong> along with its environments.
    </p>

  </div>

</section>

---

## Ways to Create Resources

<p class="section-description">

Choose the workflow that best matches your team's development process.

</p>

<div class="method-grid">

<!-- ================= UI ================= -->

<div class="method-card ui">

    <div class="card-title">

        <img class="ui-icon" src="{{ '/assets/icons/monitor.svg' | relative_url }}"
             alt="UI">

        <h3 class="ui-title">From the UI</h3>

    </div>

    <p>
        Create and manage Projects, Workspaces, and Environments directly from the Axio web interface.
    </p>

    <p><strong>Best for:</strong> quick setup, exploration, and one-off changes without a Git workflow.</p>

    <ul>

        <li>Create Projects, Workspaces, and Environments</li>

        <li>Manage resource hierarchy and assignments</li>

        <li>Configure owners, sensitivity, archiving, and lifecycle options</li>

    </ul>

    <p><strong>Getting started:</strong></p>

    <ol>
        <li>Sign in with your <strong>Organization ID</strong> and credentials</li>
        <li>Create a <strong>Project</strong> under Organization → Projects</li>
        <li>Create a <strong>Workspace</strong> and assign it to the project</li>
        <li>Create an <strong>Environment</strong>, assign owners, and set self-approval</li>
    </ol>

    <div class="card-footer">

        <a href="{{ '/axio/organization/project/create-project-ui/' | relative_url }}">

            Create Project using UI →

        </a>

    </div>

</div>

<!-- ================= PLATFORM AS CODE ================= -->

<div class="method-card git">

    <div class="card-title">

        <img class="git-icon" src="{{ '/assets/icons/git-branch.svg' | relative_url }}"
             alt="Git">

        <h3 class="git-title">Platform as Code (Git-Based)</h3>

    </div>

    <p>
       Define Projects, Workspaces, and Environments using YAML or JSON files stored in Git. Git is the source of truth; Axio reconciles desired state with the live platform.
    </p>

    <p><strong>Best for:</strong> GitOps, pull-request review, audit trails, and CI/CD-driven provisioning.</p>

    <ul>

        <li>Define organization resources as code</li>

        <li>Track changes with Git</li>

        <li>Automate resource configuration</li>

        <li>Manage resources consistently at scale</li>

    </ul>

    <p>
        <strong>Important:</strong> Platform as Code manages the <strong>Axio platform</strong> (projects, environments, policies, runners, etc.). It is <strong>not</strong> the same as <code>axio.yaml</code> stack blueprint files in IaC repositories, which describe stack provisioning.
    </p>

    <p><strong>Example manifest:</strong></p>

      <div class="yaml-example-box">

  <div class="yaml-example-title">
    <span class="yaml-example-icon">▣</span>
    <strong>Example</strong>
  </div>

  <pre class="yaml-code"><code><span class="yaml-key">apiVersion:</span> <span class="yaml-value">platform.axio.io/v1</span>
<span class="yaml-key">kind:</span> <span class="yaml-value">Project</span>
<span class="yaml-key">metadata:</span>
  <span class="yaml-key">name:</span> <span class="yaml-value">payments-platform</span>
<span class="yaml-key">spec:</span>
  <span class="yaml-key">displayName:</span> <span class="yaml-value">Payments Platform</span>
  <span class="yaml-key">description:</span> <span class="yaml-value">Core payments infrastructure</span></code></pre>

</div>

    <p><strong>Workflow:</strong> validate → plan → apply / reconcile → monitor drift</p>

    <div class="card-footer">

        <a href="{{ '/axio/organization/project/create-project-platform-as-code/' | relative_url }}">

            Create Project using Platform as Code →

        </a>

    </div>

</div>

</div>


<div class="page-navigation">

<a
class="nav-button previous"
href="{{ '/axio/' | relative_url }}">

← Welcome to Axio

</a>

<a
class="nav-button next"
href="{{ '/axio/organization/project/create-project-ui/' | relative_url }}">

Create Project using UI →

</a>

</div>
