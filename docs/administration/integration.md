---
layout: default
title: Integrations
parent: Administration
nav_order: 8
permalink: /axio/administration/integrations/
---

<div class="integrations-page">

  <header class="integrations-hero">
    <h1>Administration — Integrations</h1>
    <p class="page-subtitle">
      Configure external platform connections — identity providers, API credentials, AI providers, source control, ChatOps, communication, and platform payment services.
    </p>
  </header>

  <div class="info-banner">
    <span class="info-icon">ⓘ</span>
    <span>
      Open <strong>Administration → Integrations</strong> at <code>/admin/integrations</code>
      <span class="separator">•</span>
      Legacy <code>/administration/integrations</code> redirects here
      <span class="separator">•</span>
      After AI credentials are saved, configure routing on
      <a href="{{ '/axio/ai/model-platform/' | relative_url }}">Model Platform</a>
    </span>
  </div>

  <section>
    <h2>Permissions</h2>
    <p>The hub requires at least one <strong>Integrations hub</strong> permission. Individual category cards appear only when you hold that category’s manage permission.</p>
    <div class="table-wrap">
      <table>
        <thead>
          <tr><th>Scope</th><th>Permission(s)</th></tr>
        </thead>
        <tbody>
          <tr>
            <td>Open Integrations hub (any category page under <code>/admin/integrations</code>)</td>
            <td>Any of: <code>enterprise:manage</code>, <code>identity:manage</code>, <code>api_key:manage</code>, <code>ai_gateway:manage</code>, <code>vcs:manage</code>, <code>git:manage</code>, <code>chatops:manage</code>, <code>communication:manage</code>, <code>cloud:manage</code></td>
          </tr>
        </tbody>
      </table>
    </div>
    <p class="note">Org API keys are not an Integrations hub category. The <code>api_key:manage</code> permission unlocks hub access and is used elsewhere (for example platform administration). Integration changes are recorded in <a href="{{ '/axio/administration/audit-logs/' | relative_url }}">Audit Logs</a>.</p>
  </section>

  <section class="integration-hub">
    <div class="hub-intro">
      <div class="hub-icon">♧</div>
      <div>
        <h2>Integration hub</h2>
        <p>Central place to connect and manage integrations. Category cards show live health, configured count, and last sync where applicable — not fixed totals.</p>
      </div>
    </div>

    <div class="hub-actions">
      <h3>Quick actions</h3>
      <ul>
        <li><strong>Add Integration</strong> — menu of categories you can manage; navigates to the category page</li>
        <li><strong>Import Configuration</strong> — upload JSON (<code>integrations-config-&lt;orgId&gt;.json</code>); currently creates missing secret providers only</li>
        <li><strong>Export Configuration</strong> — download JSON metadata for source control, secret providers, cloud, identity, AI, and ChatOps (no secret values)</li>
        <li><strong>Test All Connections</strong> — validates source-control connections, cloud connections, and enabled ChatOps integrations; results open in a dialog</li>
      </ul>
      <p class="note">Import shows a summary dialog (created / skipped). Credential-backed integrations must still be configured on their category pages after import.</p>
    </div>
  </section>

  <section>
    <h2 class="section-title">Integration categories</h2>
    <p class="section-description">Cards you see depend on your permissions and organization type. Each card shows a health chip (<em>Healthy</em>, <em>Warning</em>, <em>Error</em>, or <em>Not Configured</em>), <em>N configured</em>, and <em>Last sync</em>. Click <strong>Manage</strong> or <strong>Configure</strong> to open the category.</p>

    <div class="integration-grid">

      <div class="integration-card">
        <div class="card-icon purple">⌘</div>
        <div class="card-content">
          <h3>Source Control <span>›</span></h3>
          <p>GitHub, GitLab, Bitbucket, Azure DevOps — repository browsing, stack provisioning, webhooks, GitOps.</p>
          <small><code>git:manage</code> or <code>vcs:manage</code> · <code>/admin/integrations/source-control</code></small>
        </div>
      </div>

      <div class="integration-card">
        <div class="card-icon green">♙</div>
        <div class="card-content">
          <h3>Secret Management <span>›</span></h3>
          <p>Platform Secrets, AWS Secrets Manager, Azure Key Vault, Google Secret Manager, Oracle Cloud Vault, HashiCorp Vault.</p>
          <small><code>enterprise:manage</code> · <code>/admin/integrations/secret-providers</code></small>
        </div>
      </div>

      <div class="integration-card">
        <div class="card-icon blue">☁</div>
        <div class="card-content">
          <h3>Cloud Providers <span>›</span></h3>
          <p>AWS, Azure, GCP, OCI, DigitalOcean — discovery, provisioning, and cloud account sync.</p>
          <small><code>cloud:manage</code> · <code>/admin/integrations/cloud-providers</code></small>
        </div>
      </div>

      <div class="integration-card">
        <div class="card-icon orange">♙</div>
        <div class="card-content">
          <h3>Authentication Providers <span>›</span></h3>
          <p>Microsoft Entra ID, LDAP, Okta, Google Workspace, GitHub, GitLab, generic OIDC, generic SAML 2.0.</p>
          <small><code>identity:manage</code> or <code>enterprise:manage</code> · <code>/admin/integrations/identity-providers</code></small>
        </div>
      </div>

      <div class="integration-card">
        <div class="card-icon purple">◈</div>
        <div class="card-content">
          <h3>AI Providers <span>›</span></h3>
          <p>OpenAI, Google Gemini, AWS Bedrock, Ollama, Vertex AI, Azure AI Foundry — credentials via platform secret references.</p>
          <small><code>ai_gateway:manage</code> · <code>/admin/integrations/ai-providers</code></small>
        </div>
      </div>

      <div class="integration-card">
        <div class="card-icon green">□</div>
        <div class="card-content">
          <h3>ChatOps <span>›</span></h3>
          <p>Slack, Microsoft Teams, Google Chat, generic webhooks — infrastructure card delivery.</p>
          <small><code>chatops:manage</code> · <code>/admin/integrations/chatops</code></small>
        </div>
      </div>

      <div class="integration-card">
        <div class="card-icon pink">⌁</div>
        <div class="card-content">
          <h3>Infracost <span>›</span></h3>
          <p>Infracost CLI token for cost estimation and pipeline runs (built-in pricing remains available).</p>
          <small><code>cost:manage</code> · <code>/admin/integrations/infracost</code></small>
        </div>
      </div>

      <div class="integration-card">
        <div class="card-icon orange">▣</div>
        <div class="card-content">
          <h3>Change Management <span>›</span></h3>
          <p>Jira — governance remediation tickets and ITSM sync.</p>
          <small><code>governance:manage</code> · <code>/admin/integrations/change-management</code></small>
        </div>
      </div>

      <div class="integration-card">
        <div class="card-icon cyan">◇</div>
        <div class="card-content">
          <h3>Container Registry <span>›</span></h3>
          <p>Generic, ECR, ACR, GCR (Artifact Registry), GHCR, Docker Hub — private IaC runtime images.</p>
          <small><code>execution:manage</code> or <code>runner:manage</code> · <code>/admin/integrations/container-registries</code></small>
        </div>
      </div>

      <div class="integration-card">
        <div class="card-icon blue">✉</div>
        <div class="card-content">
          <h3>Communication <span>›</span></h3>
          <p>SMTP, SendGrid (email), AWS SNS (SMS) — verification, MFA delivery, and notifications.</p>
          <small><code>communication:manage</code> · <code>/admin/integrations/communication</code></small>
        </div>
      </div>

      <div class="integration-card">
        <div class="card-icon purple">▣</div>
        <div class="card-content">
          <h3>Payments <span>›</span></h3>
          <p>Platform-wide payment processing for billing and subscription checkout.</p>
          <small>Platform provider org only · <code>subscription:manage</code> or <code>enterprise:manage</code> · <code>/admin/integrations/payments</code></small>
        </div>
      </div>

    </div>
  </section>

  <section class="audit-analytics">
    <h2>Health &amp; Analytics</h2>
    <p>Below the category grid, the hub shows <strong>Integration Summary</strong> KPIs (clickable filters that scroll to categories), distribution charts, and recommendations.</p>

    <div class="audit-kpis">
      <div class="audit-kpi">
        <div class="audit-kpi-icon green">▣</div>
        <div><span>Connected</span><strong>—</strong><small>Categories with at least one configured integration</small></div>
      </div>
      <div class="audit-kpi">
        <div class="audit-kpi-icon blue">▣</div>
        <div><span>Categories</span><strong>—</strong><small>Visible categories for your permissions</small></div>
      </div>
      <div class="audit-kpi">
        <div class="audit-kpi-icon blue">☁</div>
        <div><span>Cloud Providers</span><strong>—</strong><small>Configured cloud connections</small></div>
      </div>
      <div class="audit-kpi">
        <div class="audit-kpi-icon purple">⌘</div>
        <div><span>Source Control</span><strong>—</strong><small>Configured Git connections</small></div>
      </div>
      <div class="audit-kpi">
        <div class="audit-kpi-icon green">✓</div>
        <div><span>Healthy</span><strong>—</strong><small>Categories in healthy state with config</small></div>
      </div>
      <div class="audit-kpi">
        <div class="audit-kpi-icon orange">!</div>
        <div><span>Pending Auth</span><strong>—</strong><small>Categories needing authentication or setup</small></div>
      </div>
    </div>

    <div class="audit-chart-grid">
      <div class="audit-chart">
        <h3>Integration Categories</h3>
        <p>Configured count per visible category.</p>
      </div>
      <div class="audit-chart">
        <h3>Connected Platforms</h3>
        <p>Cloud and source-control provider distribution from the organization dashboard.</p>
      </div>
    </div>

    <p class="note">Recommendations (for example “Connect your cloud provider”) appear when the org dashboard detects gaps. Click a KPI again to clear that filter.</p>
  </section>

  <section>
    <h2>Authentication Providers — SCIM</h2>
    <div class="scim-banner">
      <span class="info-icon">ⓘ</span>
      <span>
        On <strong>Authentication Providers</strong>, the <strong>SCIM provisioning</strong> section supports Microsoft Entra ID, Okta, Google Workspace, and a <strong>Generic SCIM Client</strong>.
        Entra can also use directory sync when Entra SSO is enabled. LDAP, generic OIDC/SAML, GitHub, and GitLab support SSO but not the same SCIM flow unless noted on the provider card.
      </span>
    </div>
  </section>

  <section>
    <h2>Export &amp; import format</h2>
    <p>Export produces <code>version: 1</code> JSON with organization ID, timestamp, and non-secret metadata:</p>
    <ul>
      <li>Source control — id, provider, auth type, name, account, status</li>
      <li>Secret providers — name, type, config shape (values not included)</li>
      <li>Cloud — id, provider, name, auth method, status, regions, sync mode</li>
      <li>Identity — id, name, type, domain, enabled</li>
      <li>AI providers — id, kind, name, slug, enabled, health status</li>
      <li>ChatOps — id, provider, name, events, enabled</li>
    </ul>
    <p>Import validates version and organization ID, then creates secret providers that do not already exist (matched by name and type). Other categories are not auto-created from import.</p>
  </section>

  <section>
    <h2>Legacy routes</h2>
    <div class="table-wrap">
      <table>
        <thead>
          <tr><th>Legacy path</th><th>Redirects to</th></tr>
        </thead>
        <tbody>
          <tr><td><code>/administration/integrations</code></td><td><code>/admin/integrations</code></td></tr>
          <tr><td><code>/vcs</code>, <code>/git</code></td><td><code>/admin/integrations/source-control</code></td></tr>
          <tr><td><code>/admin/security/idp</code></td><td><code>/admin/integrations/identity-providers</code></td></tr>
          <tr><td><code>/admin/integration/github</code></td><td><code>/admin/integrations/source-control/github</code></td></tr>
          <tr><td><code>/admin/integrations/itsm</code></td><td><code>/admin/integrations/change-management</code></td></tr>
          <tr><td><code>/admin/integrations/collaboration</code></td><td><code>/admin/integrations/chatops</code></td></tr>
          <tr><td><code>/enterprise</code></td><td>Legacy SSO &amp; SCIM (see Authentication Providers)</td></tr>
        </tbody>
      </table>
    </div>
  </section>

  <section>
    <h2>Related documentation</h2>
    <ul>
      <li><a href="{{ '/axio/ai/model-platform/' | relative_url }}">Model Platform</a> — route AI workloads after providers are configured</li>
      <li><a href="{{ '/axio/administration/mfa/' | relative_url }}">MFA</a> — org MFA enforcement (uses Communication integrations for delivery)</li>
      <li><a href="{{ '/axio/administration/audit-logs/' | relative_url }}">Audit Logs</a> — integration, connection, and credential change history</li>
      <li><a href="{{ '/axio/operations/cost/' | relative_url }}">Cost</a> — FinOps and Infracost estimation sources</li>
      <li><a href="{{ '/axio/security-governance/index/' | relative_url }}">Security &amp; Governance</a> — Jira change-management tickets from policy findings</li>
    </ul>
  </section>

</div>
