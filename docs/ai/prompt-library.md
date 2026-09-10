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
      Built-in, org-seeded prompt templates for IaC, cloud, security, and governance.
      They are curated system instructions, not one-click generators.
    </p>
  </div>

  <div class="prompt-info-banner">
    <span class="prompt-info-icon">ⓘ</span>
    <span>
      Using a prompt opens the AI Assistant. Custom versioned prompts
      (draft → approve) live on the
      <a href="{{ '/axio/ai/model-platform/' | relative_url }}">Model Platform</a>
    </span>
  </div>

  <h2>How to use</h2>

  <div class="prompt-steps">

    <div class="prompt-step">
      <div class="prompt-step-number">1</div>
      <div class="prompt-step-icon">⌕</div>
      <h3>Pick a built-in prompt</h3>
      <p>Filter by category or search.</p>
    </div>

    <div class="prompt-step">
      <div class="prompt-step-number">2</div>
      <div class="prompt-step-icon">▣</div>
      <h3>Use in Assistant</h3>
      <p>
        Axio applies production guardrails as hidden system guidance:
        least privilege, encryption, no hardcoded secrets, tagging,
        HA, and pinned versions.
      </p>
    </div>

    <div class="prompt-step">
      <div class="prompt-step-number">3</div>
      <div class="prompt-step-icon">▤</div>
      <h3>Fill optional</h3>
      <p>
        Add cloud, region, existing code, and compliance targets in chat.
      </p>
    </div>

    <div class="prompt-step">
      <div class="prompt-step-number">4</div>
      <div class="prompt-step-icon">✓</div>
      <h3>Review the reply</h3>
      <p>
        Copy into a repo or run plan/apply through a governed stack.
      </p>
    </div>

  </div>



  <h2>Categories</h2>

  <div class="prompt-category-grid">

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



