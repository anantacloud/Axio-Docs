---
layout: default
title: AI MCP Servers
parent: AI
nav_order: 4
permalink: /axio/ai/mcp-servers/
---

<link rel="stylesheet" href="{{ '/assets/css/ai-mcp-servers.css' | relative_url }}">

<div class="mcp-page">

  <h1 class="mcp-title">AI MCP Servers</h1>

  <div class="mcp-info-banner">
    <span class="mcp-banner-icon">ⓘ</span>
    <span>
      Open <strong>AI → MCP Servers</strong> (<code>/ai/mcp-servers</code>).
      Legacy <code>/platform-mcp</code> and <code>/mcp</code> redirect here.
      See also the <a href="{{ '/axio/ai/assistant/' | relative_url }}">AI Assistant</a> and
      <a href="{{ '/axio/ai/model-platform/' | relative_url }}">Model Platform</a>.
    </span>
  </div>

  <h2>Permissions</h2>
  <p class="mcp-description">
    Browse the catalog with <code>mcp:use</code>.
    Run tools from the UI or Assistant with <code>ai_gateway:use</code> plus each tool’s
    <code>requiredPermission</code>.
    Approve or reject HIGH-risk executions with <code>ai_gateway:approve</code> on
    <strong>AI → Activity → Tool runs</strong>.
  </p>

  <h2>What it is</h2>

  <p class="mcp-description">
    Axio exposes Model Context Protocol–style <strong>servers</strong> (domains)
    and <strong>tools</strong> over HTTP in two layers:
  </p>

  <div class="mcp-numbered-list">

    <div class="mcp-numbered-item">
      <span class="mcp-number">1</span>
      <p>
        <strong>Platform MCP</strong> — <strong>22</strong> org-scoped domain servers
        (<code>axio://…</code>) bound to real platform services. Each tool declares
        <code>requiredPermission</code>, parameter validation, audit logging, and a risk level
        (<code>LOW</code>, <code>MEDIUM</code>, <code>HIGH</code>). HIGH-risk tools pause for
        human approval before execution completes.
      </p>
    </div>

    <div class="mcp-numbered-item">
      <span class="mcp-number">2</span>
      <p>
        <strong>Classic MCP</strong> — JSON-RPC 2.0 Streamable HTTP at
        <code>POST /organizations/:organizationId/mcp</code>, plus a human-readable manifest at
        <code>GET …/mcp/manifest</code>. Protocol version <code>2025-06-18</code>,
        server name <code>axio-mcp</code>. The manifest merges classic tools with all Platform MCP
        tools (qualified names such as <code>projects.list_projects</code>).
      </p>
    </div>

  </div>

  <div class="mcp-warning-banner">
    <span class="mcp-banner-icon">♢</span>
    <span>
      The MCP Servers page loads Platform MCP discovery (<code>GET …/platform-mcp/servers</code>)
      and the Copilot tool-calling API (<code>GET/POST …/ai/tools</code>) — the same execution
      records as the Assistant. The UI lists <strong>all</strong> Platform MCP tools; the Assistant
      system prompt only recommends tools marked <code>copilotExpose</code>.
    </span>
  </div>

  <h2>How to use</h2>

  <div class="mcp-step-grid">

    <div class="mcp-step-card">
      <div class="mcp-step-top">
        <span class="mcp-step-number">1</span>
        <span class="mcp-step-icon">⌕</span>
      </div>
      <p>
        Browse servers by domain; search and filter by risk. Inspect tool name, qualified name,
        parameters, required permission, and risk badge.
      </p>
    </div>

    <div class="mcp-step-card">
      <div class="mcp-step-top">
        <span class="mcp-step-number">2</span>
        <span class="mcp-step-icon">▣</span>
      </div>
      <p>
        <strong>Run</strong> from the catalog form, use <strong>Ask Copilot</strong> to open the
        Assistant with a prefilled prompt, or name a tool in natural language in chat.
      </p>
    </div>

    <div class="mcp-step-card">
      <div class="mcp-step-top">
        <span class="mcp-step-number">3</span>
        <span class="mcp-step-icon">♢</span>
      </div>
      <p>
        Review results in the run dialog. Approve or reject HIGH-risk runs on
        <strong>AI → Activity → Tool runs</strong> (<code>/ai/history?tab=tools</code>) or via
        quick-action badges when pending approvals exist.
      </p>
    </div>

  </div>

  <h2>Catalog features</h2>
  <div class="mcp-feature-list">
    <div>✓ <span>Domain-grouped tool table with server metadata from discovery</span></div>
    <div>✓ <span>Risk filter (ALL / LOW / MEDIUM / HIGH) and text search</span></div>
    <div>✓ <span>Favorites, tool details drawer, and recent execution history on the page</span></div>
    <div>✓ <span>Project/workspace pickers for tools that accept hierarchy refs</span></div>
    <div>✓ <span>Quick actions: Open Assistant, Tool runs, Pending approvals</span></div>
  </div>

  <h2>Platform MCP servers</h2>

  <div class="mcp-server-table-wrapper">
    <table class="mcp-server-table">
      <thead>
        <tr>
          <th>Server</th>
          <th>URI</th>
          <th>Domain examples</th>
          <th>Server</th>
          <th>URI</th>
          <th>Domain examples</th>
        </tr>
      </thead>
      <tbody>
        <tr><td>Organization</td><td><code>axio://organization</code></td><td>Profile, members</td><td>Runners</td><td><code>axio://runners</code></td><td>Runner fleet</td></tr>
        <tr><td>Projects</td><td><code>axio://projects</code></td><td>List/create/update/delete projects</td><td>IaC</td><td><code>axio://iac</code></td><td>IaC engines / runs</td></tr>
        <tr><td>Workspaces</td><td><code>axio://workspaces</code></td><td>Workspace context</td><td>Integrations</td><td><code>axio://integrations</code></td><td>Connected providers</td></tr>
        <tr><td>Environments</td><td><code>axio://environments</code></td><td>Environment context</td><td>Repositories</td><td><code>axio://repositories</code></td><td>Git repos</td></tr>
        <tr><td>Stacks</td><td><code>axio://stacks</code></td><td>Stack operations, plan/apply</td><td>Variables</td><td><code>axio://variables</code></td><td>Variable sets</td></tr>
        <tr><td>GitOps</td><td><code>axio://gitops</code></td><td>GitOps configs, sync runs</td><td>Secrets</td><td><code>axio://secrets</code></td><td>Secret metadata (values never returned)</td></tr>
        <tr><td>Catalog</td><td><code>axio://catalog</code></td><td>Service catalog</td><td>Policy Packs</td><td><code>axio://policy-packs</code></td><td>Policy packs</td></tr>
        <tr><td>Policies</td><td><code>axio://policies</code></td><td>Policy library</td><td>Workflow Templates</td><td><code>axio://workflow-templates</code></td><td>Workflow templates</td></tr>
        <tr><td>Drift</td><td><code>axio://drift</code></td><td>Drift monitors</td><td>Compliance</td><td><code>axio://compliance</code></td><td>Frameworks / scores</td></tr>
        <tr><td>Cost</td><td><code>axio://cost</code></td><td>Cost explorer</td><td>Analysis</td><td><code>axio://analysis</code></td><td>Intelligence jobs</td></tr>
        <tr><td>Audit</td><td><code>axio://audit</code></td><td>Audit events</td><td>Notifications</td><td><code>axio://notifications</code></td><td>Notification channels</td></tr>
      </tbody>
    </table>
  </div>

  <div class="mcp-success-banner">
    <span class="mcp-success-icon">✓</span>
    <span>
      Every tool enforces <code>requiredPermission</code> at execution time.
      HIGH <code>riskLevel</code> tools enter <code>AWAITING_APPROVAL</code> until a user with
      <code>ai_gateway:approve</code> approves or rejects.
      LOW and MEDIUM tools run immediately after RBAC and input validation (including secret scanning on string inputs).
    </span>
  </div>

  <h2>Classic MCP tools</h2>

  <p class="mcp-section-description">
    Built-in JSON-RPC tools (short names, in addition to qualified Platform MCP tools on
    <code>tools/list</code>):
  </p>

  <div class="mcp-classic-grid">

    <div class="mcp-classic-item">
      <span class="classic-icon blue">▣</span>
      <strong>plan</strong>
      <span>Terraform/OpenTofu plan for a workspace</span>
    </div>

    <div class="mcp-classic-item">
      <span class="classic-icon purple">▱</span>
      <strong>chat</strong>
      <span>Legacy copilot chat message</span>
    </div>

    <div class="mcp-classic-item">
      <span class="classic-icon green">✓</span>
      <strong>apply</strong>
      <span>Apply workspace</span>
    </div>

    <div class="mcp-classic-item">
      <span class="classic-icon blue">⟳</span>
      <strong>rollback</strong>
      <span>Previous Terraform state version</span>
    </div>

    <div class="mcp-classic-item">
      <span class="classic-icon red">▱</span>
      <strong>destroy</strong>
      <span>Destroy workspace resources</span>
    </div>

    <div class="mcp-classic-item">
      <span class="classic-icon purple">⌕</span>
      <strong>search</strong>
      <span>Search projects, stacks, workspaces, policies, variables</span>
    </div>

    <div class="mcp-classic-item">
      <span class="classic-icon blue">⌁</span>
      <strong>drift</strong>
      <span>Run a drift monitor check</span>
    </div>

    <div class="mcp-classic-item">
      <span class="classic-icon purple">✦</span>
      <strong>generate</strong>
      <span>Generate Terraform or Pulumi from a prompt</span>
    </div>

    <div class="mcp-classic-item">
      <span class="classic-icon orange">♢</span>
      <strong>approve / cancel</strong>
      <span>Approval request decisions</span>
    </div>

    <div class="mcp-classic-item">
      <span class="classic-icon purple">▥</span>
      <strong>analyze</strong>
      <span>Architecture / cost / security analysis for a workspace</span>
    </div>

  </div>

  <div class="mcp-resources">
    <p>
      <strong>Resources</strong> (<code>resources/list</code>; values masked where sensitive):
      <code>axio://projects</code>,
      <code>axio://stacks</code>,
      <code>axio://runs</code>,
      <code>axio://variables</code>,
      <code>axio://secrets</code>,
      <code>axio://policies</code>,
      <code>axio://runners</code>,
      <code>axio://jobs</code>,
      <code>axio://resources</code>,
      <code>axio://costs</code>,
      <code>axio://drift</code>,
      <code>axio://logs</code>.
    </p>
    <p>
      <strong>Resource templates:</strong>
      <code>axio://stacks/{stackId}</code>,
      <code>axio://runs/{runId}</code>.
    </p>
  </div>

  <h2>Related pages</h2>
  <div class="mcp-related-grid">
    <div>→ <span><a href="{{ '/axio/ai/assistant/' | relative_url }}">AI Assistant</a> — run tools via natural language</span></div>
    <div>→ <span><a href="{{ '/axio/ai/activity/' | relative_url }}">Activity</a> — tool run history and approvals</span></div>
    <div>→ <span><a href="{{ '/axio/ai/model-platform/' | relative_url }}">Model Platform</a> — LLM gateway that powers Assistant chat</span></div>
  </div>

</div>
