---
layout: default
title: AI MCP Servers
parent: AI
nav_order: 4
---

<link rel="stylesheet" href="{{ '/assets/css/ai-mcp-servers.css' | relative_url }}">

<div class="mcp-page">

  <h1 class="mcp-title">AI MCP Servers</h1>

  <p class="mcp-intro">
    Browse and run Platform MCP tools, or ask the Assistant to run them.
    Executions and HIGH-risk approvals also appear on Activity
    <code>/ai/history?tab=tools</code>.
  </p>

  <div class="mcp-info-banner">
    <span class="mcp-banner-icon">ⓘ</span>
    <span>Overview: <code>AI.md</code>.</span>
  </div>

  <h2>What it is</h2>

  <p class="mcp-description">
    Axio exposes Model Context Protocol–style <strong>servers</strong> (domains)
    and <strong>tools</strong> over HTTP:
  </p>

  <div class="mcp-numbered-list">

    <div class="mcp-numbered-item">
      <span class="mcp-number">1</span>
      <p>
        <strong>Platform MCP</strong> — org-scoped tools bound to real platform
        services (projects, stacks, policies, …), each with RBAC, parameter
        validation, audit, and risk-based approval.
      </p>
    </div>

    <div class="mcp-numbered-item">
      <span class="mcp-number">2</span>
      <p>
        <strong>Classic MCP</strong> — JSON-RPC 2.0 Streamable HTTP
        <code>POST /organizations/:organizationId/mcp</code> plus a
        human-readable manifest. Protocol version <code>2025-06-18</code>,
        server name <code>axio-mcp</code>.
      </p>
    </div>

  </div>

  <div class="mcp-warning-banner">
    <span class="mcp-banner-icon">♢</span>
    <span>
      The MCP Servers page uses Platform MCP discovery plus the Copilot
      tool-calling API (same executions as Assistant).
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
        Browse servers by domain; inspect tool name, parameters,
        required permission, and risk.
      </p>
    </div>

    <div class="mcp-step-card">
      <div class="mcp-step-top">
        <span class="mcp-step-number">2</span>
        <span class="mcp-step-icon">▣</span>
      </div>
      <p>
        Run a tool from the catalog (form) or ask Assistant in
        natural language.
      </p>
    </div>

    <div class="mcp-step-card">
      <div class="mcp-step-top">
        <span class="mcp-step-number">3</span>
        <span class="mcp-step-icon">♢</span>
      </div>
      <p>
        Review results; approve or reject HIGH-risk runs on
        Activity → Tool runs.
      </p>
    </div>

  </div>

  <h2>Platform MCP servers</h2>

  <p class="mcp-section-description">
    Registered in
    <code>apps/api/src/platform-mcp/platform-mcp-servers.ts</code>.
    URI pattern <code>axio://&lt;domain&gt;</code>.
    Qualified tool names: <code>&lt;domain&gt;.&lt;tool&gt;</code>
    (short names stay unique when possible).
  </p>

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
        <tr><td>Projects</td><td><code>axio://projects</code></td><td>List/create projects</td><td>IaC</td><td><code>axio://iac</code></td><td>IaC engines / runs</td></tr>
        <tr><td>Workspaces</td><td><code>axio://workspaces</code></td><td>Workspace context</td><td>Integrations</td><td><code>axio://integrations</code></td><td>Connected providers</td></tr>
        <tr><td>Environments</td><td><code>axio://environments</code></td><td>Environment context</td><td>Repositories</td><td><code>axio://repositories</code></td><td>Git repos</td></tr>
        <tr><td>Stacks</td><td><code>axio://stacks</code></td><td>Stack operations</td><td>Variables</td><td><code>axio://variables</code></td><td>Variable sets</td></tr>
        <tr><td>GitOps</td><td><code>axio://gitops</code></td><td>GitOps configs</td><td>Secrets</td><td><code>axio://secrets</code></td><td>Secret metadata (values never returned)</td></tr>
        <tr><td>Catalog</td><td><code>axio://catalog</code></td><td>Service catalog</td><td>Policy Packs</td><td><code>axio://policy-packs</code></td><td>Packs</td></tr>
        <tr><td>Policies</td><td><code>axio://policies</code></td><td>Policy library</td><td>Workflow Templates</td><td><code>axio://workflow-templates</code></td><td>Templates</td></tr>
        <tr><td>Drift</td><td><code>axio://drift</code></td><td>Drift monitors</td><td>Compliance</td><td><code>axio://compliance</code></td><td>Frameworks / scores</td></tr>
        <tr><td>Cost</td><td><code>axio://cost</code></td><td>Cost explorer</td><td>Analysis</td><td><code>axio://analysis</code></td><td>Intelligence jobs</td></tr>
        <tr><td>Audit</td><td><code>axio://audit</code></td><td>Audit events</td><td>Notifications</td><td><code>axio://notifications</code></td><td>Notification channels</td></tr>
      </tbody>
    </table>
  </div>

  <div class="mcp-success-banner">
    <span class="mcp-success-icon">✓</span>
    <span>
      Every tool has <code>requiredPermission</code>. Copilot lists tools with
      <code>copilotExpose</code>. HIGH <code>AiToolRiskLevel</code> requires
      <code>ai_gateway:approve</code> before execute completes.
    </span>
  </div>

  <h2>Classic MCP tools and resources</h2>

  <p class="mcp-section-description">
    Built-in JSON-RPC tools (in addition to Platform MCP tools on the manifest):
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
      <span>Copilot question</span>
    </div>

    <div class="mcp-classic-item">
      <span class="classic-icon green">✓</span>
      <strong>apply</strong>
      <span>Apply workspace</span>
    </div>

    <div class="mcp-classic-item">
      <span class="classic-icon blue">⟳</span>
      <strong>rollback</strong>
      <span>Previous state version</span>
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
      <span>Run a drift monitor</span>
    </div>

    <div class="mcp-classic-item">
      <span class="classic-icon purple">✦</span>
      <strong>generate</strong>
      <span>Generate Terraform or Pulumi from a prompt</span>
    </div>

    <div class="mcp-classic-item">
      <span class="classic-icon orange">♢</span>
      <strong>approve / cancel</strong>
      <span>Approval requests</span>
    </div>

    <div class="mcp-classic-item">
      <span class="classic-icon purple">▥</span>
      <strong>analyze</strong>
      <span>Architecture / cost / security analysis for a workspace</span>
    </div>

  </div>

  <div class="mcp-resources">
    <p>
      <strong>Resources</strong> (values masked where sensitive):
      <code>axio://projects</code>,
      <code>stacks</code>,
      <code>runs</code>,
      <code>variables</code>,
      <code>secrets</code>,
      <code>policies</code>,
      <code>runners</code>,
      <code>jobs</code>,
      <code>resources</code>,
      <code>costs</code>,
      <code>drift</code>,
      <code>logs</code>.
    </p>

    <p>
      <strong>Templates:</strong>
      <code>axio://stacks/{stackId}</code>,
      <code>axio://runs/{runId}</code>.
    </p>
  </div>

</div>

