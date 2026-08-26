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
        Group related workspaces and manage project-level configuration and access.
    </p>

    <h4>Features</h4>

    <ul>

        <li>Group related workspaces</li>

        <li>Mark projects as sensitive</li>

        <li>Archive projects when eligible</li>

    </ul>

    <div class="card-footer">

        <a href="/docs/organization/create-project-ui/">

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

    </ul>

    <div class="card-footer">

        <a href="/docs/organization/create-workspace-ui/">

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

    </ul>

    <div class="card-footer">

        <a href="/docs/organization/create-environment-ui/">

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
        Create and manage Projects, Workspaces, and Environments directly from the Axio web interface.
    </p>

    <ul>

        <li>Create Projects, Workspaces, and Environments</li>

        <li>Manage resource hierarchy and assignments</li>

        <li>Configure owners, sensitivity, and archiving</li>

    </ul>

</div>

<!-- ================= PLATFORM AS CODE ================= -->

<div class="method-card git">

    <div class="card-title">

        <img class="git-icon" src="{{ '/assets/icons/git-branch.svg' | relative_url }}"
             alt="Git">

        <h3 class="git-title">Platform as Code (Git-Based)</h3>

    </div>

    <p>
       Define Projects, Workspaces, and Environments using YAML or JSON files stored in Git.
    </p>

    <ul>

        <li>Define organization resources as code</li>

        <li>Track changes with Git</li>

        <li>Automate resource configuration</li>

        <li>Manage resources consistently</li>

    </ul>

</div>

</div>


<div class="page-navigation">

<a
class="nav-button previous"
href="{{ 'index' | relative_url }}">

← Welcome to Axio

</a>

<a
class="nav-button next"
href="{{ '/docs/organization/create-project-ui/' | relative_url }}">

Create Project using UI →

</a>

</div>
