---
layout: default
title: Identity Provider
parent: Integrations
nav_order: 1
---

# Identity Provider

Axio supports enterprise authentication by integrating with external Identity Providers (IdPs). This enables centralized user authentication, improves security, and simplifies user management across the platform.

<div class="hero-image">

![Identity Provider](/assets/images/integrations/oauth/oauth-hero.png)

</div>

{: .highlight }

> ## Centralized Authentication
>
> Integrating an Identity Provider allows organizations to authenticate users using their existing enterprise identity system while maintaining centralized access control.

---

## Authentication Workflow

```mermaid
flowchart LR

A[User Login]
-->
B[Redirect to Identity Provider]

B
-->
C[Authenticate User]

C
-->
D[Validate Identity]

D
-->
E[Grant Platform Access]
```

---

# Before You Begin

Ensure that:

- An enterprise Identity Provider is available.
- You have administrative access to configure authentication.
- Required client credentials are available.
- User roles have been planned.

{: .note }

> Identity Provider configuration should be performed by platform administrators.

---

### Step 1 — Open Identity Provider Settings

Navigate to:

**Settings → Integrations → Identity Provider**

<div class="doc-image">

![Identity Dashboard](/assets/images/integrations/oauth/idp-dashboard.png)

</div>

---

### Step 2 — Configure Authentication

Provide the required authentication details for your Identity Provider.

Typical configuration includes:

- Client ID
- Client Secret
- Tenant or Organization
- Redirect URI

<div class="doc-image">

![Configure Identity Provider](/assets/images/integrations/oauth/idp-configure.png)

</div>

---

### Step 3 — Validate Configuration

Click **Validate Connection**.

Axio verifies:

- Identity Provider availability
- Authentication configuration
- Client credentials

<div class="doc-image">

![Validation](/assets/images/integrations/oauth/idp-validation.png)

</div>

---

### Step 4 — Enable Authentication

After validation succeeds, enable the Identity Provider for user authentication.

<div class="doc-image">

![Authentication Enabled](/assets/images/integrations/oauth/idp-enabled.png)

</div>

---

## Benefits

<div class="feature-grid">

<div class="feature-card">

<h3>Single Sign-On</h3>

<p>Centralized user authentication</p>

</div>

<div class="feature-card">

<h3>Secure Access</h3>

<p>Reduce credential management overhead</p>

</div>

<div class="feature-card">

<h3>Centralized User Management</h3>

<p>Manage users through the enterprise identity system</p>

</div>

<div class="feature-card">

<h3>Improved Governance</h3>

<p>Consistent authentication across teams</p>

</div>

</div>

---

## Best Practices

- Enable enterprise authentication for all production users.
- Regularly review access permissions.
- Use role-based access after authentication.
- Monitor authentication activity.

{: .warning }

> Restrict administrative access to trusted Identity Provider administrators.
