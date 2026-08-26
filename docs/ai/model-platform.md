---
layout: default
title: AI Model Platform
parent: AI
nav_order: 3
---

<link rel="stylesheet" href="{{ '/assets/css/ai-model-platform.css' | relative_url }}">

<div class="ai-model-platform-page">

  <div class="model-hero">
    <h1>AI Model Platform</h1>
    <p>
      Multi-provider LLM gateway to manage providers, routing, prompts, RAG,
      policies, quotas, and usage.
    </p>
  </div>

  <div class="model-info-banner">
    <span class="model-info-icon">ⓘ</span>
    <span>
      Legacy <code>/ai-gateway</code> redirects here.
      Use <code>?tab=</code> to open a tab directly
      (overview, providers, models, routing, features, prompts, rag,
      policies, usage).
    </span>
  </div>

  <h2>Architecture</h2>

  <div class="architecture-flow">

    <div class="architecture-top">
      <span class="architecture-icon">▥</span>
      Feature / Assistant / Intelligence / Playground
    </div>

    <div class="architecture-arrow">↓</div>

    <div class="architecture-service">
      AiGatewayService.complete() / embed() / ragQuery()
    </div>

    <div class="architecture-arrow branch-arrow">↓</div>

    <div class="architecture-branch">

      <div class="architecture-card security-card">
        <div class="architecture-card-icon">♢</div>
        <h3>Security scan + redact</h3>
        <p>Secrets, PII, injection, moderation</p>
      </div>

      <div class="architecture-card">
        <div class="architecture-card-icon">↝</div>
        <h3>Route select</h3>
        <p>Rules → feature binding → default / cheapest approved</p>
      </div>

      <div class="architecture-card">
        <div class="architecture-card-icon">♆</div>
        <h3>Provider adapter</h3>
        <p>OpenAI-compatible and vendor APIs</p>
      </div>

      <div class="architecture-card">
        <div class="architecture-card-icon">▣</div>
        <h3>Policy + quota enforcement</h3>
        <p>Allow/deny, quota, rate limiting</p>
      </div>

      <div class="architecture-card">
        <div class="architecture-card-icon">▤</div>
        <h3>AiRequestLog</h3>
        <p>Tokens, cost, latency, status</p>
      </div>

    </div>

  </div>

  <div class="model-warning-banner">
    <span>♢</span>
    <span>
      Credentials at rest: AES-256-GCM via AiCredentialCryptoService.
      Prefer platform secret refs (<code>apiKeySecretRef</code>) over inline keys.
    </span>
  </div>

  <div class="model-success-banner">
    <span>♧</span>
    <span>
      First visit can <code>POST .../bootstrap</code> to seed the provider/model
      catalog for this organization.
    </span>
  </div>

  <h2>Platform tabs</h2>

  <div class="platform-tabs">

    <div class="platform-tab active">
      <div class="platform-tab-icon">◔</div>
      <strong>Overview</strong>
      <p>Provider/model counts, analytics and playground</p>
    </div>

    <div class="platform-tab">
      <div class="platform-tab-icon">⌂</div>
      <strong>Providers</strong>
      <p>Catalog instances, health check, credentials</p>
    </div>

    <div class="platform-tab">
      <div class="platform-tab-icon">◇</div>
      <strong>Models</strong>
      <p>Register models, approve / unapprove</p>
    </div>

    <div class="platform-tab">
      <div class="platform-tab-icon">↯</div>
      <strong>Routing</strong>
      <p>Priority rules, failover, cost, latency, geography</p>
    </div>

    <div class="platform-tab">
      <div class="platform-tab-icon">⊞</div>
      <strong>Features</strong>
      <p>Bind features to preferred models (defaults)</p>
    </div>

    <div class="platform-tab">
      <div class="platform-tab-icon">▤</div>
      <strong>Prompts</strong>
      <p>Org prompt templates (version, test)</p>
    </div>

    <div class="platform-tab">
      <div class="platform-tab-icon">▤</div>
      <strong>Documents</strong>
      <p>Knowledge bases, ingest, RAG query</p>
    </div>

    <div class="platform-tab">
      <div class="platform-tab-icon">♢</div>
      <strong>Policy &amp; Quotas</strong>
      <p>Policies and spend / rate quotas</p>
    </div>

    <div class="platform-tab">
      <div class="platform-tab-icon">▥</div>
      <strong>Usage</strong>
      <p>Request volume, cost, latency analytics</p>
    </div>

  </div>

  <div class="playground-banner">
    <span>♙</span>
    <span>
      Playground calls <code>POST .../complete</code> with a feature key,
      task, and privacy hint.
    </span>
  </div>

  <h2>Provider catalog (gateway)</h2>

  <p class="model-section-description">
    Kinds in the engine catalog include commercial, self-hosted, and enterprise providers.
  </p>

  <div class="provider-grid">

    <div class="provider-card commercial">
      <div class="provider-card-title">
        <span>▥</span>
        <h3>Commercial</h3>
      </div>
      <p>
        OpenAI, Azure OpenAI, Anthropic, Google Gemini, AWS Bedrock, Cohere,
        Mistral, xAI, Together, Fireworks
      </p>
    </div>

    <div class="provider-card self-hosted">
      <div class="provider-card-title">
        <span>⌂</span>
        <h3>Self-hosted</h3>
      </div>
      <p>
        Ollama, vLLM, Hugging Face TGI, NVIDIA NIM, LM Studio,
        Open WebUI, llama.cpp
      </p>
    </div>

    <div class="provider-card enterprise">
      <div class="provider-card-title">
        <span>♢</span>
        <h3>Enterprise</h3>
      </div>
      <p>
        Azure AI Foundry, Databricks Mosaic, OpenShift AI,
        IBM watsonx, Vertex AI, SageMaker
      </p>
    </div>

  </div>

  <div class="model-info-banner provider-note">
    <span class="model-info-icon">♧</span>
    <span>
      <strong>Administration → Integrations → AI Providers</strong> currently exposes
      configure cards for OpenAI, Google Gemini, AWS Bedrock, Ollama, Vertex AI,
      and Azure AI Foundry. Other kinds can still be created via Model Platform / API.
    </span>
  </div>

  <div class="model-meta-row">
    <div>
      <strong>Categories:</strong>
      <span class="pill green">COMMERCIAL</span>
      <span class="pill blue">SELF_HOSTED</span>
      <span class="pill purple">ENTERPRISE</span>
    </div>

    <div>
      <strong>Modalities:</strong>
      <span class="pill cyan">CHAT</span>
      <span class="pill red">COMPLETION</span>
      <span class="pill blue">EMBEDDING</span>
      <span class="pill purple">MULTIMODAL</span>
    </div>
  </div>

  <div class="model-content-grid">

    <div class="model-main-column">

      <h2>Feature bindings (defaults)</h2>

      <p class="model-section-description">
        These defaults are used when no explicit model is selected and routing rules do not match.
      </p>

      <div class="feature-table-wrapper">
        <table class="feature-table">
          <thead>
            <tr>
              <th>Feature key</th>
              <th>Label</th>
              <th>Preferred model slug</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>◉ explain-terraform-plans</td>
              <td>Explain Terraform Plans</td>
              <td>gpt-5</td>
            </tr>
            <tr>
              <td>✣ iac-generation</td>
              <td>IaC Generation</td>
              <td>claude-sonnet</td>
            </tr>
            <tr>
              <td>∞ kubernetes-troubleshooting</td>
              <td>Kubernetes Troubleshooting</td>
              <td>llama-3-3</td>
            </tr>
            <tr>
              <td>✦ cost-optimization</td>
              <td>Cost Optimization</td>
              <td>gemini-2-flash</td>
            </tr>
            <tr>
              <td>♧ compliance-analysis</td>
              <td>Compliance Analysis</td>
              <td>bedrock-claude</td>
            </tr>
            <tr>
              <td>∞ air-gapped-deployment</td>
              <td>Air-Gapped Deployment</td>
              <td>llama-3-3</td>
            </tr>
          </tbody>
        </table>
      </div>

      <div class="routing-note">
        <span>♧</span>
        <span>
          <strong>Routing order:</strong> explicit model id (Assistant) →
          enabled route rule (priority) → cost/latency preference →
          org default / cheapest approved non-embedding model.
          Failover model ids are used when the primary call fails.
        </span>
      </div>

    </div>

    <div class="model-side-column">

      <div class="security-panel">
        <div class="panel-title">
          <span>♢</span>
          <h2>Security scan</h2>
        </div>

        <p class="panel-source">
          Shared engine:
          <code>apps/api/src/ai-gateway/engine/security.ts</code>
        </p>

        <ul class="security-list">
          <li>Secrets (AWS keys, OpenAI sk-, GitHub PAT, generic api_key/password/token)</li>
          <li>PII (email, SSN, card, phone) → redacted placeholders</li>
          <li>Prompt injection / jailbreak patterns</li>
          <li>Moderation (violence/malware phrasing)</li>
        </ul>

        <div class="security-alert">
          Injection and moderation are <strong>BLOCKED</strong> by default.
          Statuses:
          <span>SUCCESS</span>,
          <span>FAILED</span>,
          <span>BLOCKED</span>,
          <span>RATE_LIMITED</span>,
          <span>FAILOVER</span>.
        </div>
      </div>

      <div class="governance-panel">
        <div class="panel-title">
          <span>♧</span>
          <h2>Governance</h2>
        </div>

        <p>
          <strong>Prompt lifecycle:</strong>
          <span class="status draft">DRAFT</span> →
          <span class="status pending">PENDING_APPROVAL</span> →
          <span class="status approved">APPROVED</span> |
          <span class="status rejected">REJECTED</span> |
          <span class="status archived">ARCHIVED</span>
        </p>

        <p>
          <strong>Policy actions:</strong>
          <span class="status allow">ALLOW</span>,
          <span class="status deny">DENY</span>,
          <span class="status approval">REQUIRE_APPROVAL</span>,
          <span class="status redact">REDACT</span>,
          <span class="status reroute">REROUTE</span>
        </p>

        <p>
          <strong>Memory scopes:</strong>
          <span class="status session">SESSION</span>,
          <span class="status project">PROJECT</span>,
          <span class="status organization">ORGANIZATION</span>,
          <span class="status knowledge">KNOWLEDGE</span>
        </p>
      </div>

    </div>

  </div>

</div>

