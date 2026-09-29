---
layout: default
title: AI Prompt Library
parent: AI
nav_order: 2
permalink: /axio/ai/prompt-library/
---

<link rel="stylesheet" href="{{ '/assets/css/ai-prompt-library.css' | relative_url }}">

<div class="ai-prompt-library-page">

  <div class="prompt-hero">
    <h1>AI Prompt Library</h1>
    <p>
      Open <strong>AI → Prompt Library</strong> (<code>/ai/prompt-library</code>) for built-in, org-seeded prompt
      templates covering getting started, drift, FinOps, GitOps, operations, IaC engines, cloud, security, and governance.
      They are curated system instructions for the Assistant — not one-click code generators.
    </p>
  </div>

  <div class="prompt-info-banner">
    <span class="prompt-info-icon">ⓘ</span>
    <span>
      <strong>Use in Assistant</strong> opens the AI Assistant with hidden system guidance from the selected template.
      Custom org prompts (draft → new version → approve) are managed separately on the
      <a href="{{ '/axio/ai/model-platform/' | relative_url }}">Model Platform</a>
      and do not replace these built-in library entries.
    </span>
  </div>

  <h2>Permissions</h2>
  <p class="prompt-section-description">
    Requires <code>copilot:read</code> to browse the catalog.
    Sending messages after hand-off requires <code>copilot:use</code> and <code>ai_gateway:use</code> on the Assistant.
    Creating or approving custom prompts on Model Platform requires <code>ai_gateway:manage</code>.
  </p>

  <h2>How to use</h2>

  <div class="prompt-steps">

    <div class="prompt-step">
      <div class="prompt-step-number">1</div>
      <div class="prompt-step-icon">⌕</div>
      <h3>Pick a built-in prompt</h3>
      <p>Search by keyword or filter by category chip. Each card is labeled <strong>Built-in</strong>.</p>
    </div>

    <div class="prompt-step">
      <div class="prompt-step-number">2</div>
      <div class="prompt-step-icon">▣</div>
      <h3>Use in Assistant</h3>
      <p>
        Click <strong>Use in Assistant</strong>. Axio applies production guardrails as hidden system guidance:
        least privilege, encryption at rest and in transit, no hardcoded secrets, logging and tagging,
        high availability, pinned provider/module versions, and structured replies (summary, actions, risks, next steps).
      </p>
    </div>

    <div class="prompt-step">
      <div class="prompt-step-number">3</div>
      <div class="prompt-step-icon">▤</div>
      <h3>Fill optional variables</h3>
      <p>
        The variable dialog collects optional <code>{{variable}}</code> fields (cloud, region, plan output, error logs, compliance targets).
        You can also add details in the Assistant chat after hand-off.
      </p>
    </div>

    <div class="prompt-step">
      <div class="prompt-step-number">4</div>
      <div class="prompt-step-icon">✓</div>
      <h3>Review the reply</h3>
      <p>
        Iterate in chat, use <strong>Copy starter</strong> to paste a template elsewhere, or run plan/apply through a governed stack.
      </p>
    </div>

  </div>

  <h2>Catalog features</h2>

  <div class="prompt-check-grid">
    <div class="prompt-check-column">
      <div>✓ <span><strong>24</strong> built-in prompts seeded per organization (<code>library: true</code>, <code>APPROVED</code>)</span></div>
      <div>✓ <span>Expandable prompt preview on each card (<strong>Show full prompt</strong>)</span></div>
    </div>
    <div class="prompt-check-column">
      <div>✓ <span><strong>Copy starter</strong> — clipboard message with bracket placeholders for variables</span></div>
      <div>✓ <span>Deep link <code>?slug=</code> opens the variable dialog for a matching prompt</span></div>
    </div>
    <div class="prompt-check-column">
      <div>✓ <span>Stack wizard links to engine-specific prompts (Terraform, OpenTofu, Pulumi, Crossplane, …)</span></div>
      <div>✓ <span>Hand-off URL: <code>/ai/assistant?librarySlug=&lt;slug&gt;</code></span></div>
    </div>
  </div>

  <h2>Categories</h2>
  <p class="prompt-section-description">
    Filter chips match the catalog. Workflow-oriented categories appear alongside IaC engine and cloud templates.
  </p>

  <div class="prompt-category-grid">

    <div class="prompt-category-card">
      <span class="category-icon getting-started">★</span>
      <div><strong>getting-started</strong><small>Getting started</small></div>
    </div>

    <div class="prompt-category-card">
      <span class="category-icon gitops">↗</span>
      <div><strong>gitops</strong><small>GitOps</small></div>
    </div>

    <div class="prompt-category-card">
      <span class="category-icon drift">⇄</span>
      <div><strong>drift</strong><small>Drift</small></div>
    </div>

    <div class="prompt-category-card">
      <span class="category-icon finops">$</span>
      <div><strong>finops</strong><small>FinOps</small></div>
    </div>

    <div class="prompt-category-card">
      <span class="category-icon operations">⚙</span>
      <div><strong>operations</strong><small>Operations</small></div>
    </div>

    <div class="prompt-category-card">
      <span class="category-icon terraform">◆</span>
      <div><strong>terraform</strong><small>Terraform</small></div>
    </div>

    <div class="prompt-category-card">
      <span class="category-icon opentofu">◇</span>
      <div><strong>opentofu</strong><small>OpenTofu</small></div>
    </div>

    <div class="prompt-category-card">
      <span class="category-icon pulumi">✿</span>
      <div><strong>pulumi</strong><small>Pulumi</small></div>
    </div>

    <div class="prompt-category-card">
      <span class="category-icon crossplane">+</span>
      <div><strong>crossplane</strong><small>Crossplane</small></div>
    </div>

    <div class="prompt-category-card">
      <span class="category-icon aws">aws</span>
      <div><strong>cloud-aws</strong><small>AWS</small></div>
    </div>

    <div class="prompt-category-card">
      <span class="category-icon azure">△</span>
      <div><strong>cloud-azure</strong><small>Azure</small></div>
    </div>

    <div class="prompt-category-card">
      <span class="category-icon gcp">●</span>
      <div><strong>cloud-gcp</strong><small>GCP</small></div>
    </div>

    <div class="prompt-category-card">
      <span class="category-icon security">◇</span>
      <div><strong>security</strong><small>Security</small></div>
    </div>

    <div class="prompt-category-card">
      <span class="category-icon governance">⚖</span>
      <div><strong>governance</strong><small>Governance</small></div>
    </div>

  </div>

  <h2>Example prompts</h2>
  <p class="prompt-section-description">Representative built-ins — the full catalog is searchable on the page.</p>

  <div class="prompt-example-grid">
    <div class="prompt-example-card"><strong>Plan Your First Stack</strong><small>getting-started</small></div>
    <div class="prompt-example-card"><strong>Understand &amp; Fix Drift</strong><small>drift</small></div>
    <div class="prompt-example-card"><strong>Review Cloud Spend &amp; Savings</strong><small>finops</small></div>
    <div class="prompt-example-card"><strong>Troubleshoot a Failed Run</strong><small>operations</small></div>
    <div class="prompt-example-card"><strong>Explain a Terraform Plan (Plain Language)</strong><small>terraform</small></div>
    <div class="prompt-example-card"><strong>Pre-Deploy Checklist</strong><small>governance</small></div>
  </div>

  <h2>Tips for better results</h2>
  <div class="prompt-tips">
    <div>• Start with <strong>Plan Your First Stack</strong> or <strong>Axio Platform Orientation</strong> if you are new.</div>
    <div>• Name cloud provider, region, and environment (prod vs non-prod) in your message.</div>
    <div>• Paste plan output, drift summaries, or error logs — the Assistant works best with real context.</div>
    <div>• For spend questions, use <strong>Review Cloud Spend &amp; Savings</strong> and mention your billing period.</div>
    <div>• Prefer plan-first workflows; apply through a governed stack when you are ready.</div>
  </div>

  <h2>Built-in vs custom prompts</h2>
  <p class="prompt-section-description">
    Built-in library prompts are refreshed from the platform catalog and <strong>cannot be edited</strong> on Model Platform.
    Administrators create <strong>custom</strong> prompts on Model Platform (<strong>Prompts</strong> tab): initial status is
    <code>DRAFT</code>, new versions bump the template, and <strong>Approve</strong> sets <code>APPROVED</code>.
    Custom prompts use <code>{{variable}}</code> placeholders and are intended for gateway administration — they are not mixed into the end-user Prompt Library grid.
  </p>

  <h2>Related pages</h2>
  <div class="prompt-check-grid">
    <div class="prompt-check-column">
      <div>→ <span><a href="{{ '/axio/ai/assistant/' | relative_url }}">AI Assistant</a> — chat with library hand-off and platform context</span></div>
    </div>
    <div class="prompt-check-column">
      <div>→ <span><a href="{{ '/axio/ai/model-platform/' | relative_url }}">Model Platform</a> — providers, routing, and custom prompt lifecycle</span></div>
    </div>
  </div>

</div>
