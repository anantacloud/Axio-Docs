---
layout: default
title: AI Model Platform
parent: AI
nav_order: 3
permalink: /axio/ai/model-platform/
---

<link rel="stylesheet" href="{{ '/assets/css/ai-model-platform.css' | relative_url }}">

<div class="ai-model-platform-page">

  <div class="model-hero">
    <h1>AI Model Platform</h1>
    <p>
      Open <strong>AI → Model Platform</strong> to manage the org-scoped LLM gateway:
      provider catalog, model approval, routing rules, feature bindings, custom prompts, document libraries (RAG),
      runtime policies, quotas, and usage analytics. Legacy redirects here.
    </p>
  </div>

  <div class="model-info-banner">
    <span class="model-info-icon">ⓘ</span>
    <span>
      Requires <code>ai_gateway:manage</code>. Connect credentials under
      <strong>Administration → Integrations → AI Providers</strong> before models become available to the
      <a href="{{ '/axio/ai/assistant/' | relative_url }}">AI Assistant</a> and other gateway consumers.
    </span>
  </div>

  <h2>Architecture</h2>

  <div class="architecture-flow">

    <div class="architecture-top">
      <span class="architecture-icon">▥</span>
      Assistant (<code>copilot</code>) · Intelligence · Playground · other gateway features
    </div>

    <div class="architecture-arrow">↓</div>

    <div class="architecture-service">
      <code>AiGatewayService.complete()</code> / <code>embed()</code> / <code>ragQuery()</code>
    </div>

    <div class="architecture-arrow branch-arrow">↓</div>

    <div class="architecture-branch">

      <div class="architecture-card">
        <div class="architecture-card-icon">▣</div>
        <h3>Quota enforcement</h3>
        <p>Org spend and rate limits before routing</p>
      </div>

      <div class="architecture-card">
        <div class="architecture-card-icon">↝</div>
        <h3>Route select</h3>
        <p>Explicit model → feature binding → route rules → cost/latency → default approved model</p>
      </div>

      <div class="architecture-card">
        <div class="architecture-card-icon">♧</div>
        <h3>Runtime policies</h3>
        <p>Require approved models, deny by feature/task/provider, security rule signals</p>
      </div>

      <div class="architecture-card security-card">
        <div class="architecture-card-icon">♢</div>
        <h3>Security scan + redact</h3>
        <p>Secrets, PII redaction; injection and moderation blocked on user turns</p>
      </div>

      <div class="architecture-card">
        <div class="architecture-card-icon">▤</div>
        <h3>RAG + memory</h3>
        <p>Knowledge-base retrieval and scoped conversation memory</p>
      </div>

      <div class="architecture-card">
        <div class="architecture-card-icon">♆</div>
        <h3>Provider adapter</h3>
        <p>OpenAI-compatible and vendor-specific APIs with failover</p>
      </div>

      <div class="architecture-card">
        <div class="architecture-card-icon">▥</div>
        <h3>AiRequestLog</h3>
        <p>Tokens, cost, latency, status, security flags, feedback</p>
      </div>

    </div>

  </div>

  <h2>Dashboard &amp; tabs</h2>
  <p class="model-section-description">
    A <strong>Model Health</strong> dashboard (availability, utilization charts, token/cost KPIs) appears above the tabs on every visit.
    On first open, Axio bootstraps the built-in provider and model catalog for the organization when none exists yet.
  </p>

  <div class="platform-tabs">

    <div class="platform-tab active">
      <div class="platform-tab-icon">◔</div>
      <strong>Overview</strong>
      <p>Configured providers, model health, request/token/cost KPIs, success rate, prompt count</p>
    </div>

    <div class="platform-tab">
      <div class="platform-tab-icon">⌂</div>
      <strong>Providers</strong>
      <p>Configured integrations (from AI Providers), health check, credential storage</p>
    </div>

    <div class="platform-tab">
      <div class="platform-tab-icon">◇</div>
      <strong>Models</strong>
      <p>Chat and multimodal models from configured providers — approve or revoke for Assistant use</p>
    </div>

    <div class="platform-tab">
      <div class="platform-tab-icon">↯</div>
      <strong>Routing</strong>
      <p>Priority rules: task, privacy, geography, compliance, cost/latency preference, failover model ids</p>
    </div>

    <div class="platform-tab">
      <div class="platform-tab-icon">⊞</div>
      <strong>Features</strong>
      <p>Bind platform feature keys to preferred models (seeded defaults on bootstrap)</p>
    </div>

    <div class="platform-tab">
      <div class="platform-tab-icon">▤</div>
      <strong>Prompts</strong>
      <p>Custom org templates — version, test, approve (<code>DRAFT</code> → <code>APPROVED</code>)</p>
    </div>

    <div class="platform-tab">
      <div class="platform-tab-icon">▦</div>
      <strong>Documents</strong>
      <p>Knowledge bases, document ingest, embedding model, gateway RAG</p>
    </div>

    <div class="platform-tab">
      <div class="platform-tab-icon">♢</div>
      <strong>Policy &amp; Quotas</strong>
      <p>Runtime AI policies and org request/token/cost quotas</p>
    </div>

    <div class="platform-tab">
      <div class="platform-tab-icon">▥</div>
      <strong>Usage</strong>
      <p>Volume by provider/feature, recent requests, feedback, routing playground</p>
    </div>

  </div>

  <h2>Provider catalog (gateway bootstrap)</h2>

  <p class="model-section-description">
    Bootstrap seeds <strong>21 provider kinds</strong> with reference models into the org catalog.
    Categories: <span class="pill green">COMMERCIAL</span>
    <span class="pill blue">SELF_HOSTED</span>
    <span class="pill purple">ENTERPRISE</span>.
    Seeded modalities are primarily <span class="pill cyan">CHAT</span> and <span class="pill blue">EMBEDDING</span>
    (the platform enum also supports <span class="pill red">COMPLETION</span> and <span class="pill purple">MULTIMODAL</span>).
  </p>

  <div class="provider-grid">

    <div class="provider-card commercial">
      <div class="provider-card-title">
        <span>▥</span>
        <h3>Commercial</h3>
      </div>
      <p>
        OpenAI, Anthropic, Google Gemini, AWS Bedrock, Cohere,
        Mistral AI, xAI (Grok), Together AI, Fireworks AI
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
        Azure AI Foundry, Databricks Mosaic AI, Red Hat OpenShift AI,
        IBM watsonx.ai, Vertex AI
      </p>
    </div>

  </div>

  <div class="model-info-banner provider-note">
    <span class="model-info-icon">♧</span>
    <span>
      <strong>Administration → Integrations → AI Providers</strong> exposes configure cards for
      OpenAI, Google Gemini, AWS Bedrock, Ollama, Vertex AI, and Azure AI Foundry.
      Other catalog kinds can be enabled via Model Platform providers API or future admin cards once credentials are stored.
    </span>
  </div>

  <div class="model-content-grid">

    <div class="model-main-column">

      <h2>Feature bindings (defaults)</h2>

      <p class="model-section-description">
        Seeded on bootstrap. Used as the preferred model when callers pass a <code>featureKey</code> but no explicit
        <code>modelId</code>. The AI Assistant uses feature key <code>copilot</code> and typically passes an explicit
        model from the picker, which wins over routing rules.
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
              <td><code>explain-terraform-plans</code></td>
              <td>Explain Terraform Plans</td>
              <td>gpt-5</td>
            </tr>
            <tr>
              <td><code>iac-generation</code></td>
              <td>IaC Generation</td>
              <td>claude-sonnet</td>
            </tr>
            <tr>
              <td><code>kubernetes-troubleshooting</code></td>
              <td>Kubernetes Troubleshooting</td>
              <td>llama-3-3</td>
            </tr>
            <tr>
              <td><code>cost-optimization</code></td>
              <td>Cost Optimization</td>
              <td>gemini-2-flash</td>
            </tr>
            <tr>
              <td><code>compliance-analysis</code></td>
              <td>Compliance Analysis</td>
              <td>bedrock-claude</td>
            </tr>
            <tr>
              <td><code>air-gapped-deployment</code></td>
              <td>Air-Gapped Deployment</td>
              <td>llama-3-3</td>
            </tr>
            <tr>
              <td><code>copilot</code></td>
              <td>AI Assistant</td>
              <td>— (explicit model from Assistant picker)</td>
            </tr>
            <tr>
              <td><code>ai_intelligence</code></td>
              <td>AI Intelligence scans</td>
              <td>— (routed via rules / defaults)</td>
            </tr>
          </tbody>
        </table>
      </div>

      <div class="routing-note">
        <span>♧</span>
        <span>
          <strong>Routing order:</strong> explicit <code>modelId</code> (Assistant picker) →
          feature-bound model id → enabled route rule (priority) → cost/latency preference →
          cheapest approved non-embedding model.
          Failover model ids are tried when the primary provider call fails.
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
          Shared gateway security engine applied to every completion request.
        </p>

        <ul class="security-list">
          <li>Secrets (AWS keys, OpenAI <code>sk-</code>, GitHub PAT, generic api_key/password/token)</li>
          <li>PII (email, SSN, card, phone) → redacted placeholders</li>
          <li>Prompt injection / jailbreak patterns (user messages only)</li>
          <li>Moderation (violence/malware phrasing)</li>
        </ul>

        <div class="security-alert">
          Injection and moderation are <strong>BLOCKED</strong> on user turns by default.
          Secrets and PII are redacted in outbound content.
          Request log statuses:
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
          <strong>Custom prompt lifecycle:</strong>
          <span class="status draft">DRAFT</span> →
          <span class="status approved">APPROVED</span>
          (new versions reset to <span class="status draft">DRAFT</span> until re-approved).
          Built-in library prompts are read-only — see
          <a href="{{ '/axio/ai/prompt-library/' | relative_url }}">Prompt Library</a>.
        </p>

        <p>
          Enum also supports
          <span class="status pending">PENDING_APPROVAL</span>,
          <span class="status rejected">REJECTED</span>,
          <span class="status archived">ARCHIVED</span>.
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
          Install the <strong>AI Governance Pack</strong> from Security &amp; Governance → Policy Library for
          infrastructure-level AI controls. Model Platform policies enforce at LLM request time.
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
