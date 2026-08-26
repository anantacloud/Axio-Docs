---
layout: default
title: AI Assistant
parent: AI
nav_order: 1
---

<link rel="stylesheet" href="{{ '/assets/css/ai-assistant.css' | relative_url }}">

<div class="ai-assistant-page">

  <div class="ai-hero">
    <h1>AI Assistant</h1>
    <p>The AI Assistant enables org-scoped conversations that answer infrastructure questions, leverage live platform context, and run governed MCP tools with human approval for HIGH-risk actions.</p>
  </div>

  <div class="ai-info-banner">
    <span class="ai-banner-icon">ⓘ</span>
    <span>Powered by the Axio Model Platform. See <a href="{{ '/docs/ai/model-platform/' | relative_url }}">Model Platform</a> for supported providers and routing.</span>
  </div>

  <h2>What it does</h2>

  <div class="ai-feature-grid">
    <div class="ai-feature-card">
      <div class="ai-feature-icon purple">▣</div>
      <div><h3>Answer questions</h3><p>Get accurate answers from the LLM using your configured AI provider.</p></div>
    </div>
    <div class="ai-feature-card">
      <div class="ai-feature-icon green">✓</div>
      <div><h3>Platform context</h3><p>Include a secret-masked snapshot of your tenant to ground responses.</p></div>
    </div>
    <div class="ai-feature-card">
      <div class="ai-feature-icon blue">⚒</div>
      <div><h3>Run tools</h3><p>Execute Platform MCP tools. HIGH-risk tools require human approval.</p></div>
    </div>
  </div>

  <h2>Assistant modes</h2>
  <p class="ai-section-description">The available experience depends on your organization's configuration.</p>

  <div class="ai-mode-table">
    <div class="ai-mode-row ai-mode-header"><div>Mode</div><div>LLM Chat</div><div>MCP Tools</div><div>Behavior</div></div>
    <div class="ai-mode-row"><div><strong>Unavailable</strong></div><div>×</div><div>×</div><div>Configure an AI provider and/or MCP tools.</div></div>
    <div class="ai-mode-row"><div><strong>Tool runner</strong></div><div>×</div><div class="check">✓</div><div>Run tools by name; no conversational LLM.</div></div>
    <div class="ai-mode-row"><div><strong>AI Assistant</strong></div><div class="check">✓</div><div>×</div><div>Chat with the assistant only.</div></div>
    <div class="ai-mode-row"><div><strong>Assistant + tools</strong></div><div class="check">✓</div><div class="check">✓</div><div>Chat and tool execution.</div></div>
     </div>

  <h2>Chat experience</h2>
  <div class="ai-check-grid">
    <div class="ai-check-column">
      <div>✓ <span>Conversation list, create, delete</span></div>
      <div>✓ <span>Provider &amp; model picker (explicit model wins over gateway route rules)</span></div>
    </div>
    <div class="ai-check-column">
      <div>✓ <span>Optional include platform context (default on)</span></div>
      <div>✓ <span>Markdown formatted replies</span></div>
    </div>
    <div class="ai-check-column">
      <div>✓ <span>Prompt Library hand-off (system guardrails + user starter)</span></div>
      <div>✓ <span>Deep links: <code>?prompt=</code> and <code>?librarySlug=</code></span></div>
    </div>
  </div>

  <h2>Context Engine</h2>
  
  <p class="ai-section-description">Gathers a live, secret-masked snapshot for grounding and analysis. All strings pass through the shared redactor (secrets, PII).</p>

  <div class="ai-context-grid">
    <div><span class="context-icon purple">♙</span>User, org, project/stack counts</div>
    <div><span class="context-icon green">↗</span>Recent/failed runs, cost, drift</div>
    <div><span class="context-icon blue">♢</span>Compliance, security findings</div>
    <div><span class="context-icon green">▦</span>Runners, repositories</div>
    <div><span class="context-icon purple">▤</span>Recent audit</div>
  </div>

  <div class="ai-warning"><span>♢</span><span>Deliberately omitted fields are listed in <code>redactionFlags</code>.</span></div>

  <h2>Tool calling</h2>
  <p class="ai-section-description">Tools are listed via <code>GET /ai/tools</code> and executed via <code>POST /ai/tools/execute</code>.</p>

  <div class="ai-flow">
    <div class="ai-flow-step"><div class="flow-number purple-bg">1</div><h3>Request</h3><p>User asks a question or requests an action.</p></div>
    <div class="ai-flow-arrow">→</div>
    <div class="ai-flow-step"><div class="flow-number blue-bg">2</div><h3>Execute</h3><p>Assistant validates and runs the tool.</p></div>
    <div class="ai-flow-arrow">→</div>
    <div class="ai-flow-step"><div class="flow-number orange-bg">3</div><h3>Approve <small>(if HIGH risk)</small></h3><p>Human approval is required.</p></div>
    <div class="ai-flow-arrow">→</div>
    <div class="ai-flow-step"><div class="flow-number green-bg">4</div><h3>Result</h3><p>Outcome is recorded and returned.</p></div>
  </div>

  <p class="ai-tool-note">Tool runs are recorded and visible in <strong>Activity → Tool runs</strong>.</p>

</div>
