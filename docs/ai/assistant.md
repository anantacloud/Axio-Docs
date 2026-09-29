---
layout: default
title: AI Assistant
parent: AI
nav_order: 1
permalink: /axio/ai/assistant/
---

<div class="ai-assistant-page">

  <div class="ai-hero">
    <h1>AI Assistant</h1>
    <p>
      Open <strong>AI → Assistant</strong> (<code>/ai/assistant</code>) for org-scoped conversations that answer
      infrastructure questions, leverage live platform context, and run governed Platform MCP tools.
      HIGH-risk tools pause for human approval before they execute.
    </p>
  </div>

  <div class="ai-info-banner">
    <span class="ai-banner-icon">ⓘ</span>
    <span>
      Powered by the Axio Model Platform. See
      <a href="{{ '/axio/ai/model-platform/' | relative_url }}">Model Platform</a>
      for supported providers, routing rules, and governance.
    </span>
  </div>

  <h2>What it does</h2>

  <div class="ai-feature-grid">
    <div class="ai-feature-card">
      <div class="ai-feature-icon purple">▣</div>
      <div><h3>Answer questions</h3><p>Chat with configured, approved models from your org’s AI providers.</p></div>
    </div>
    <div class="ai-feature-card">
      <div class="ai-feature-icon green">✓</div>
      <div><h3>Platform context</h3><p>Include a secret-masked snapshot of your tenant to ground responses (on by default).</p></div>
    </div>
    <div class="ai-feature-card">
      <div class="ai-feature-icon blue">⚒</div>
      <div><h3>Run tools</h3><p>Execute Platform MCP tools from chat or <strong>AI → MCP Servers</strong>. HIGH-risk tools require approval.</p></div>
    </div>
  </div>

  <h2>Prerequisites &amp; permissions</h2>
  <p class="ai-section-description">The Assistant adapts to what your organization has configured.</p>

  <div class="ai-check-grid">
    <div class="ai-check-column">
      <div>✓ <span><strong>Page access:</strong> <code>copilot:use</code></span></div>
      <div>✓ <span><strong>Send chat / run tools:</strong> <code>ai_gateway:use</code></span></div>
    </div>
    <div class="ai-check-column">
      <div>✓ <span><strong>Approve HIGH-risk tools:</strong> <code>ai_gateway:approve</code></span></div>
      <div>✓ <span><strong>Configure providers, preview context:</strong> <code>ai_gateway:manage</code></span></div>
    </div>
    <div class="ai-check-column">
      <div>✓ <span><strong>Browse MCP catalog:</strong> <code>mcp:use</code> (MCP Servers page)</span></div>
    </div>
  </div>

  <p class="ai-section-description">
    Administrators configure providers under <strong>Administration → Integrations → AI Providers</strong>.
    Only <strong>enabled</strong> providers with valid credentials, a verified connection, and at least one
    <strong>approved</strong> chat model appear in the Assistant picker.
  </p>

  <h2>Assistant modes</h2>
  <p class="ai-section-description">The available experience depends on configured AI providers and registered Platform MCP tools.</p>

  <div class="ai-mode-table">
    <div class="ai-mode-row ai-mode-header"><div>Mode</div><div>LLM Chat</div><div>MCP Tools</div><div>Behavior</div></div>
    <div class="ai-mode-row"><div><strong>Unavailable</strong></div><div>×</div><div>×</div><div>No AI provider and no MCP tools. Configure a provider or contact your administrator.</div></div>
    <div class="ai-mode-row"><div><strong>Tool runner</strong></div><div>×</div><div class="check">✓</div><div>Run tools by name; no conversational LLM. Banner offers <strong>Browse tools</strong> and <strong>Configure AI provider</strong>.</div></div>
    <div class="ai-mode-row"><div><strong>AI Assistant</strong></div><div class="check">✓</div><div>×</div><div>Chat with the assistant only (no tool catalog exposed in this mode).</div></div>
    <div class="ai-mode-row"><div><strong>Assistant + tools</strong></div><div class="check">✓</div><div class="check">✓</div><div>Full chat plus direct tool execution from natural-language requests.</div></div>
  </div>

  <h2>Chat experience</h2>
  <div class="ai-check-grid">
    <div class="ai-check-column">
      <div>✓ <span>Conversation list, create, delete</span></div>
      <div>✓ <span>Provider &amp; model picker — explicit model wins over Model Platform route rules</span></div>
      <div>✓ <span>Connection status chip (Connected, Connection Failed, Disabled, …)</span></div>
    </div>
    <div class="ai-check-column">
      <div>✓ <span>Include platform context (default on; toggle for <code>ai_gateway:manage</code> only)</span></div>
      <div>✓ <span>Markdown formatted assistant replies</span></div>
      <div>✓ <span>Starter suggestions for cost, drift, compliance, and troubleshooting</span></div>
    </div>
    <div class="ai-check-column">
      <div>✓ <span>Prompt Library hand-off (<code>?librarySlug=</code> — system guardrails + user starter)</span></div>
      <div>✓ <span>Legacy URLs <code>/ai-chat</code>, <code>/agents</code>, and <code>/copilot</code> redirect here</span></div>
    </div>
  </div>

  <p class="ai-section-description">
    Conversations are private to the creator unless you are an AI org administrator (<code>ai_gateway:manage</code>),
    who can list all org conversations. Changing the provider on an existing conversation requires confirmation or a new chat.
    Users with <code>ai_gateway:manage</code> also see per-message metadata chips (model, tokens, context-grounded, masked-field count).
  </p>

  <h2>Context Engine</h2>

  <p class="ai-section-description">
    Before each chat turn (when context is enabled), Axio gathers a live, tenant-scoped snapshot for grounding and analysis.
    All strings pass through the shared redactor (secrets, PII). Tool-runner mode never attaches platform context.
  </p>

  <div class="ai-context-grid">
    <div><span class="context-icon purple">♙</span>User, org, project/stack/workspace counts</div>
    <div><span class="context-icon green">↗</span>Recent and failed IaC runs</div>
    <div><span class="context-icon blue">♢</span>Compliance scores and open security findings (by severity)</div>
    <div><span class="context-icon green">▦</span>Runners (online/total) and Git repositories</div>
    <div><span class="context-icon purple">▤</span>Cost estimates, drift monitors, recent audit activity</div>
  </div>

  <div class="ai-warning"><span>♢</span><span>Deliberately omitted or masked fields are listed in <code>redactionFlags</code> on the gathered snapshot and on assistant messages.</span></div>

  <p class="ai-section-description">
    Administrators can click <strong>Preview context</strong> to inspect the masked snapshot before sending a message.
  </p>

  <h2>Tool calling</h2>

  <p class="ai-section-description">
    Tools are registered Platform MCP capabilities. Each tool declares a risk level (<code>LOW</code>, <code>MEDIUM</code>,
    <code>HIGH</code>), a required org permission, and input validation. Tool input is scanned for secrets before execution.
  </p>

  <div class="ai-flow">
    <div class="ai-flow-step"><div class="flow-number purple-bg">1</div><h3>Request</h3><p>User asks a question or names a tool (from Assistant or MCP Servers).</p></div>
    <div class="ai-flow-arrow">→</div>
    <div class="ai-flow-step"><div class="flow-number blue-bg">2</div><h3>Validate</h3><p>RBAC, input validation, and security scanning run before execution.</p></div>
    <div class="ai-flow-arrow">→</div>
    <div class="ai-flow-step"><div class="flow-number orange-bg">3</div><h3>Approve <small>(if HIGH risk)</small></h3><p>Execution pauses until a user with <code>ai_gateway:approve</code> approves or rejects.</p></div>
    <div class="ai-flow-arrow">→</div>
    <div class="ai-flow-step"><div class="flow-number green-bg">4</div><h3>Result</h3><p>Outcome is recorded, audited, and returned in chat or the tool-run history.</p></div>
  </div>

  <p class="ai-tool-note">
    Tool runs are recorded and visible under <strong>AI → Activity → Tool runs</strong> (<code>/ai/history?tab=tools</code>).
    Pending HIGH-risk executions show <strong>Approve</strong> / <strong>Reject</strong> actions for approvers.
    You can also run and approve tools from <strong>AI → MCP Servers</strong>.
  </p>

  <h2>Related pages</h2>
  <div class="ai-check-grid">
    <div class="ai-check-column">
      <div>→ <span><a href="{{ '/axio/ai/prompt-library/' | relative_url }}">Prompt Library</a> — built-in starters with production guardrails</span></div>
    </div>
    <div class="ai-check-column">
      <div>→ <span><a href="{{ '/axio/ai/mcp-servers/' | relative_url }}">MCP Servers</a> — browse, run, and approve tools by domain</span></div>
    </div>
    <div class="ai-check-column">
      <div>→ <span><a href="{{ '/axio/ai/activity/' | relative_url }}">Activity</a> — timeline of scans, conversations, and tool runs</span></div>
    </div>
  </div>

</div>
