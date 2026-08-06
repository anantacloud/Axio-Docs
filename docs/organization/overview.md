---
layout: default
title: Overview
parent: Organization
nav_order: 1
description: Learn how Organization resources are structured in Axio.
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
        Logical grouping of Workspaces and Environments.
    </p>

    <h4>Features</h4>

    <ul>

        <li>Group related workloads</li>

        <li>Manage project-level access</li>

        <li>Configure project settings</li>

    </ul>

    <div class="card-footer">

        <a href="../projects/">

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

        Isolated areas for applications,
        services and infrastructure.

    </p>

    <h4>Features</h4>

    <ul>

        <li>Contains environments</li>

        <li>Team isolation</li>

        <li>Independent configuration</li>

    </ul>

    <div class="card-footer">

        <a href="../workspaces/">

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

        Deployment targets like
        Development,
        Staging,
        and Production.

    </p>

    <h4>Features</h4>

    <ul>

        <li>Multiple environment types</li>

        <li>Deployment configuration</li>

        <li>Environment-specific settings</li>

    </ul>

    <div class="card-footer">

        <a href="../environments/">

            Explore Environments →

        </a>

    </div>

</div>

</div>

## Ways to Create Resources

<p class="section-description">

Choose the workflow that best matches your team's development process.

</p>

<div class="method-grid">

<!-- ================= UI ================= -->

<div class="method-card ui">

    <div class="card-title">

        <img  class="ui-icon" src="{{ '/assets/icons/monitor.svg' | relative_url }}"
             alt="UI">

        <h3 class="ui-title">From the UI</h3>

    </div>

    <p>

        Create resources directly
        from the Axio web interface.

    </p>

    <ul>

        <li>Quick setup</li>

        <li>Manual administration</li>

        <li>Learning the platform</li>

    </ul>

    <div class="card-footer">

        <a href="../projects/create-from-ui/">

            Create Resources from UI →

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

        Define Projects, Workspaces,
        and Environments using YAML
        or JSON files stored in Git.

    </p>

    <ul>

        <li>GitOps workflows</li>

        <li>Version control</li>

        <li>Automation</li>

        <li>Audit & Compliance</li>

    </ul>

    <div class="card-footer">

        <a href="../platform-as-code/repository-setup/">

            Platform as Code Guide →

        </a>

    </div>

</div>

</div>
