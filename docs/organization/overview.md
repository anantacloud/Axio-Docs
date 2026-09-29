---
layout: default
title: Overview
parent: Organization
nav_order: 1
description: Learn how Organization resources are structured in Axio.
permalink: /axio/organization/overview/
---

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

After sign-in, the organization context determines which resources, permissions, and settings apply to your session.

Every new organization is also provisioned with a system **Default Project**, **Default Workspace**, and **Default Environment** for bootstrap and fallback assignment.

---

## Resource hierarchy

Organization resources form a nested hierarchy. Use this order when creating resources and assigning access.

```
Organization
└── Project
    └── Workspace
        └── Environment
            └── Stack (provisioned infrastructure)
                └── Workflow / Deployment
```

**Recommended creation order:** Project → Workspace → Environment → Stack

| Layer | Role |
|-------|------|
| **Project** | Groups workspaces; project-level configuration, lifecycle policy overrides, and access scope |
| **Workspace** | Belongs to a project; contains environments; links to IaC state and stack provisioning |
| **Environment** | Deployment target where workflows run, deployments are approved, and governance rules apply |
| **Stack** | Infrastructure defined in Git (Terraform, Pulumi, etc.) deployed into an environment |

### Example

1. **Project:** `payments-platform`
2. **Workspace:** `payments-infra` (assigned to the project)
3. **Environment:** `production` (owners assigned, self-approval disabled)
4. **Stack:** Terraform stack deployed into `production`

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

## Access, roles, and permissions

Who can create and manage organization resources depends on **organization membership role** and optional **scoped assignments** via **Administration → Roles & Access**.

| Role | Create projects / workspaces | Delete projects | Manage org settings & members |
|------|:----------------------------:|:---------------:|:-----------------------------:|
| **Owner** | Yes | Yes | Yes |
| **Admin** | Yes | Yes | Limited |
| **Member** | Yes* | No | No |
| **Viewer** | No | No | No |
| **Unassigned** | No | No | No |

\*Members with **project-, workspace-, or environment-scoped** access only cannot create new projects.

Scoped assignments can apply at organization, business unit, project, workspace, or environment level.

---

## Organization settings and business units

### Organization settings

**Organization → Settings** covers tenant-wide governance, including environment lifecycle policies (default TTL, max TTL, active environment limits), MFA, and other organization-level configuration. Project detail pages can override lifecycle defaults when permitted.

### Business units (enterprise)

**Organization → Business Units** provides hierarchy and delegated administration for multi-team tenants. Business units complement Project → Workspace → Environment for **access and delegation**—they do not replace that resource hierarchy.

When a workspace is unassigned from a project, it moves to the system **Default Project** along with its environments.

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

```yaml
apiVersion: platform.axio.io/v1
kind: Project
metadata:
  name: payments-platform
spec:
  displayName: Payments Platform
  description: Core payments infrastructure
```

    <p><strong>Workflow:</strong> validate → plan → apply / reconcile → monitor drift</p>

    <div class="card-footer">

        <a href="{{ '/axio/organization/project/create-project-platform-as-code/' | relative_url }}">

            Create Project using Platform as Code →

        </a>

    </div>

</div>

</div>

### UI vs Platform as Code

| Criterion | Prefer UI | Prefer Platform as Code |
|-----------|-----------|-------------------------|
| Team maturity | Small team, early exploration | Established GitOps practice |
| Change review | Ad hoc | Pull-request review required |
| Audit & reproducibility | Lower priority | High priority |
| Automation | Manual setup | CI/CD-driven provisioning |
| Mixed mode | Bootstrap in UI, steady state in Git | — |

Both paths manage the same underlying resources—choose based on process, not capability.

---

## What comes next

Organization hierarchy is the foundation of your Axio estate. After projects, workspaces, and environments are in place:

| Step | Area | What you do |
|------|------|-------------|
| **1** | **Organization** (this page) | Structure your estate: projects, workspaces, environments |
| **2** | **Stacks** | Connect cloud and source control; provision infrastructure with your IaC engine |
| **3** | **Operations** | Monitor runs, approvals, drift, and cost |

Environments connect to **deployment governance**: approval policies, workflow execution, TTL and destroy rules, and linked stacks.

---

## Getting started checklist

- [ ] Obtain your **Organization ID** from **Organization → Overview**
- [ ] Sign in and confirm your role (Owner, Admin, Member, or Viewer)
- [ ] Create a **project**
- [ ] Create a **workspace** and assign it to the project
- [ ] Create an **environment**, assign **owners**, and set **self-approval**
- [ ] (Optional) Configure **Organization → Settings** lifecycle policies
- [ ] Proceed to **Stacks** to connect a repository and run your first deployment
- [ ] (Optional) Adopt **Platform as Code** for Git-managed configuration

---

## Glossary

| Term | Definition |
|------|------------|
| **Organization ID** | 8-character login identifier for your tenant |
| **Project** | Top-level grouping of workspaces within an organization |
| **Workspace** | Container for environments; tied to IaC/state context |
| **Environment** | Deployment target with owners, approvals, and lifecycle rules |
| **Sensitive** | Protection flag preventing delete, archive, and destroy |
| **Archive** | Soft deactivation of a resource no longer in use |
| **Self-approval** | Whether a workflow initiator may approve their own deployment |
| **Platform as Code (PaC)** | Git-based declarative management of Axio platform resources |
| **axio.yaml** | Stack blueprint in an IaC repo—not platform configuration |
| **Business unit** | Enterprise hierarchy unit for delegated administration |
| **Default Project** | System-provisioned project used for bootstrap and unassigned workspaces |

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
