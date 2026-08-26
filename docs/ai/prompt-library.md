---
layout: default
title: AI Prompt Library
parent: AI
nav_order: 2
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
      <a href="{{ '/docs/ai/model-platform/' | relative_url }}">Model Platform</a>
      (<code>/ai-platform?tab=prompts</code>).
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
      <h3>Fill optional <code>{{"{{variables}}"}}</code></h3>
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

  <div class="prompt-link-banner">
    <span class="prompt-link-icon">↗</span>
    <span>
      Stack wizard and deployment review can deep-link here
      (<code>?slug=</code>) or straight to Assistant
      (<code>?librarySlug=</code>).
    </span>
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

  <h2>Built-in prompts</h2>

  <p class="prompt-section-description">
    Seeded per organization (<code>library: true</code>, status:
    <span class="approved">APPROVED</span>). Variables use
    <code>{{"{{name}}"}}</code>.
  </p>

  <div class="prompt-table-wrapper">
    <table class="prompt-table">
      <thead>
        <tr>
          <th>Slug</th>
          <th>Name</th>
          <th>Variables</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>explain-terraform-plan</td>
          <td>Explain Terraform Plan</td>
          <td><code>{{"{{plan}}"}}</code>, <code>{{"{{workspace}}"}}</code></td>
        </tr>
        <tr>
          <td>terraform-production-module</td>
          <td>Production Terraform Module</td>
          <td><code>{{"{{requirements}}"}}</code>, <code>{{"{{cloud_provider}}"}}</code>, <code>{{"{{region}}"}}</code></td>
        </tr>
        <tr>
          <td>terraform-security-hardening</td>
          <td>Terraform Security Hardening</td>
          <td><code>{{"{{terraform_code}}"}}</code>, <code>{{"{{compliance_framework}}"}}</code></td>
        </tr>
        <tr>
          <td>opentofu-production-stack</td>
          <td>Production OpenTofu Stack</td>
          <td><code>{{"{{requirements}}"}}</code>, <code>{{"{{cloud_provider}}"}}</code></td>
        </tr>
        <tr>
          <td>opentofu-terraform-migration</td>
          <td>OpenTofu Migration from Terraform</td>
          <td><code>{{"{{current_setup}}"}}</code></td>
        </tr>
        <tr>
          <td>pulumi-production-component</td>
          <td>Production Pulumi Component</td>
          <td><code>{{"{{language}}"}}</code>, <code>{{"{{requirements}}"}}</code>, <code>{{"{{cloud_provider}}"}}</code></td>
        </tr>
        <tr>
          <td>pulumi-policy-review</td>
          <td>Pulumi Policy &amp; Preview Review</td>
          <td><code>{{"{{preview_output}}"}}</code>, <code>{{"{{stack_name}}"}}</code></td>
        </tr>
        <tr>
          <td>crossplane-composition</td>
          <td>Crossplane Composition (XRD)</td>
          <td><code>{{"{{platform_requirements}}"}}</code>, <code>{{"{{kubernetes_context}}"}}</code></td>
        </tr>
        <tr>
          <td>crossplane-drift-operations</td>
          <td>Crossplane Drift &amp; Operations</td>
          <td><code>{{"{{resources}}"}}</code>, <code>{{"{{symptoms}}"}}</code></td>
        </tr>
        <tr>
          <td>cloud-aws-well-architected</td>
          <td>AWS Well-Architected IaC Review</td>
          <td><code>{{"{{architecture_description}}"}}</code>, <code>{{"{{workload_type}}"}}</code></td>
        </tr>
        <tr>
          <td>cloud-aws-landing-zone</td>
          <td>AWS Landing Zone Blueprint</td>
          <td><code>{{"{{org_size}}"}}</code>, <code>{{"{{requirements}}"}}</code></td>
        </tr>
        <tr>
          <td>cloud-azure-landing-zone</td>
          <td>Azure Landing Zone IaC</td>
          <td><code>{{"{{requirements}}"}}</code>, <code>{{"{{subscription_model}}"}}</code></td>
        </tr>
        <tr>
          <td>cloud-gcp-foundation</td>
          <td>GCP Foundation &amp; IaC</td>
          <td><code>{{"{{requirements}}"}}</code>, <code>{{"{{folder_structure}}"}}</code></td>
        </tr>
        <tr>
          <td>security-iac-remediation</td>
          <td>IaC Security Remediation</td>
          <td><code>{{"{{findings}}"}}</code>, <code>{{"{{iac_snippet}}"}}</code></td>
        </tr>
        <tr>
          <td>security-secrets-and-keys</td>
          <td>Secrets &amp; Key Management</td>
          <td><code>{{"{{cloud_provider}}"}}</code>, <code>{{"{{current_pattern}}"}}</code></td>
        </tr>
        <tr>
          <td>governance-policy-as-code</td>
          <td>Governance Policy as Code</td>
          <td><code>{{"{{policy_goals}}"}}</code>, <code>{{"{{iac_engine}}"}}</code></td>
        </tr>
        <tr>
          <td>governance-deployment-checklist</td>
          <td>Pre-Deploy Governance Checklist</td>
          <td><code>{{"{{environment}}"}}</code>, <code>{{"{{change_summary}}"}}</code></td>
        </tr>
      </tbody>
    </table>
  </div>

</div>

