---
layout: default
title: Integrations
nav_order: 6
has_children: true
---

# Integrations

Integrations enable Axio to connect with external platforms, allowing teams to manage infrastructure, source code, authentication, and deployment workflows from a centralized control plane.

<div class="hero-image">

![Integrations Overview](/assets/images/integrations/integrations-overview.png)

</div>

{: .highlight }

> ## Connect Your Platform
>
> Axio integrates with version control systems and identity providers to simplify infrastructure management, secure authentication, and deployment automation.

---

## Supported Integration Areas

<div class="feature-grid">

<div class="feature-card">

<h3>GitHub</h3>

<p>Connect repositories for Infrastructure-as-Code and application source</p>

</div>

<div class="feature-card">

<h3>VCS Connections</h3>

<p>Centralized repository management for projects</p>

</div>

<div class="feature-card">

<h3>Identity Providers</h3>

<p>Configure enterprise authentication providers</p>

</div>

<div class="feature-card">

<h3>Automation</h3>

<p>Enable deployment workflows using connected repositories</p>

</div>

</div>

---

## Integration Workflow

```mermaid
flowchart LR

A[Connect External System]
-->
B[Authenticate]

B
-->
C[Validate Connection]

C
-->
D[Register Integration]

D
-->
E[Use in Projects]
```

---

## Why Use Integrations?

Connecting external systems allows teams to:

- Centralize infrastructure management
- Secure authentication
- Access Infrastructure-as-Code repositories
- Standardize deployment workflows
- Improve collaboration across teams

---

## Available Guides

| Guide | Description |
|--------|-------------|
| GitHub | Connect GitHub repositories |
| OAuth | Configure enterprise authentication |
| VCS Connection | Register and manage repositories |
