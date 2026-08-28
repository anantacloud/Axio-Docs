---
layout: default
title: Integrations
parent: Administration
nav_order: 9
---

<div class="integrations-page">

  <h1>Administration — Integrations</h1>
  <p class="page-subtitle">
    Connect external tools and services to Axio. Manage credentials, settings and connection health in one place.
  </p>

  <div class="info-banner">
    <span class="info-icon">ⓘ</span>
    <span>
      Overview: <code>ADMINISTRATION.md</code>
      <span class="separator">•</span>
      AI provider routing after credentials are saved:
      <code>AI_MODEL_PLATFORM.md</code>
    </span>
  </div>

  <section class="integration-hub">
    <div class="hub-intro">
      <div class="hub-icon">♧</div>
      <div>
        <h2>Integration hub</h2>
        <p>Central place to connect and manage all integrations across Axio.</p>
      </div>
    </div>

    <div class="health">
      <strong>Connection health</strong>
      <div class="health-items">
        <span><i class="dot green"></i> Healthy <b>18</b></span>
        <span><i class="dot orange"></i> Warning <b>2</b></span>
        <span><i class="dot red"></i> Error <b>1</b></span>
        <span><i class="dot gray"></i> Inactive <b>3</b></span>
      </div>
    </div>

    <div class="hub-actions">
      <button>〽 Test all connections</button>
      <button>⇧ Export config</button>
      <button>⇩ Import config</button>
    </div>
  </section>

  <section>
    <h2 class="section-title">Integration categories</h2>
    <p class="section-description">Select a category to view and manage integrations.</p>

    <div class="integration-grid">

      <div class="integration-card">
        <div class="card-icon purple">⌘</div>
        <div class="card-content">
          <h3>Source Control <span>›</span></h3>
          <p>GitHub, GitLab, Bitbucket,<br>Azure DevOps</p>
          <small>♧ 4 integrated</small>
        </div>
      </div>

      <div class="integration-card">
        <div class="card-icon green">♙</div>
        <div class="card-content">
          <h3>Secret Management <span>›</span></h3>
          <p>Platform Secrets, AWS Secrets Manager, Azure Key Vault,<br>GCP Secret Manager, OCI Vault, HashiCorp Vault</p>
          <small>♧ 6 integrated</small>
        </div>
      </div>

      <div class="integration-card">
        <div class="card-icon blue">☁</div>
        <div class="card-content">
          <h3>Cloud Providers <span>›</span></h3>
          <p>AWS, Azure, GCP, OCI,<br>DigitalOcean</p>
          <small>♧ 5 integrated</small>
        </div>
      </div>

      <div class="integration-card">
        <div class="card-icon orange">♙</div>
        <div class="card-content">
          <h3>Authentication Providers <span>›</span></h3>
          <p>Entra ID, LDAP, Okta, Google Workspace, GitHub, GitLab,<br>generic OIDC, generic SAML</p>
          <small>♧ 7 integrated</small>
        </div>
      </div>

      <div class="integration-card">
        <div class="card-icon purple">⚿</div>
        <div class="card-content">
          <h3>API Keys <span>›</span></h3>
          <p>Org API keys, PATs, service<br>accounts, OAuth</p>
          <small>♧ 5 integrated</small>
        </div>
      </div>

      <div class="integration-card">
        <div class="card-icon purple">◈</div>
        <div class="card-content">
          <h3>AI Providers <span>›</span></h3>
          <p>OpenAI, Gemini, Bedrock,<br>Ollama, Vertex AI, Azure AI Foundry</p>
          <small>♧ 6 integrated</small>
        </div>
      </div>

      <div class="integration-card">
        <div class="card-icon green">□</div>
        <div class="card-content">
          <h3>ChatOps <span>›</span></h3>
          <p>Slack, Microsoft Teams, Google Chat, webhooks<br>(Discord also in types)</p>
          <small>♧ 4 integrated</small>
        </div>
      </div>

      <div class="integration-card">
        <div class="card-icon pink">⌁</div>
        <div class="card-content">
          <h3>Infracost <span>›</span></h3>
          <p>API key or CLI token for<br>cost estimation</p>
          <small>♧ 1 integrated</small>
        </div>
      </div>

      <div class="integration-card">
        <div class="card-icon orange">▣</div>
        <div class="card-content">
          <h3>Change Management <span>›</span></h3>
          <p>Jira, ServiceNow</p>
          <small>♧ 2 integrated</small>
        </div>
      </div>

      <div class="integration-card">
        <div class="card-icon cyan">◇</div>
        <div class="card-content">
          <h3>Container Registry <span>›</span></h3>
          <p>Generic, ECR, ACR, GCR,<br>GHCR, Docker Hub</p>
          <small>♧ 5 integrated</small>
        </div>
      </div>

      <div class="integration-card">
        <div class="card-icon blue">✉</div>
        <div class="card-content">
          <h3>Communication <span>›</span></h3>
          <p>SMTP, SendGrid, Twilio,<br>AWS SNS</p>
          <small>♧ 4 integrated</small>
        </div>
      </div>

      <div class="integration-card">
        <div class="card-icon purple">▣</div>
        <div class="card-content">
          <h3>Payments <span>›</span></h3>
          <p>Platform payment processors —<br>platform provider only</p>
          <small>— &nbsp; Not applicable for tenants</small>
        </div>
      </div>

    </div>
  </section>

  <div class="scim-banner">
    <span class="info-icon">ⓘ</span>
    <span>SCIM-capable IdPs for user/group sync: Entra, Okta, Google Workspace, plus a generic SCIM client.</span>
  </div>

</div>

