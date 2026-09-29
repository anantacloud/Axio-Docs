---

layout: default

title: Activity

parent: AI

nav_order: 6

permalink: /axio/ai/activity/

---



<div class="ai-activity-page">



&#x20; <div class="ai-hero">

&#x20;   <h1>Activity</h1>

&#x20;   <p>

&#x20;     Open <strong>AI → Activity</strong> (<code>/ai/history</code>) to review recent assistant conversations,

&#x20;     intelligence scans, insights, recommendations, reports, and Platform MCP tool executions for your organization.

&#x20;   </p>

&#x20; </div>



&#x20; <div class="ai-info-banner">

&#x20;   <span class="ai-banner-icon">ⓘ</span>

&#x20;   <span>

&#x20;     Requires <code>copilot:read</code> to view the timeline.

&#x20;     Approving or rejecting HIGH-risk tool runs requires <code>ai\_gateway:approve</code>.

&#x20;     Tool runs also appear from the <a href="{{ '/axio/ai/assistant/' | relative\_url }}">AI Assistant</a> and

&#x20;     <a href="{{ '/axio/ai/mcp-servers/' | relative\_url }}">MCP Servers</a> pages.

&#x20;   </span>

&#x20; </div>



&#x20; <h2>Tabs</h2>



&#x20; <div class="ai-tab-grid">

&#x20;   <div class="ai-tab-card">

&#x20;     <h3>Timeline</h3>

&#x20;     <p>

&#x20;       Unified activity feed with type, title, summary, and timestamp. Filter by kind or search by keyword.

&#x20;       Deep link: <code>/ai/history</code> (default tab).

&#x20;     </p>

&#x20;   </div>

&#x20;   <div class="ai-tab-card">

&#x20;     <h3>Tool runs</h3>

&#x20;     <p>

&#x20;       Governed MCP tool executions with risk, status, summary, and approval actions.

&#x20;       Deep link: <code>/ai/history?tab=tools</code>.

&#x20;     </p>

&#x20;   </div>

&#x20; </div>



&#x20; <h2>Timeline</h2>



&#x20; <p class="ai-section-description">

&#x20;   Each row shows <strong>Type</strong>, <strong>Title</strong> (with optional summary), and <strong>When</strong>.

&#x20;   Use the type filter and search box to narrow results. Results are paginated client-side.

&#x20; </p>



&#x20; <div class="ai-type-table-wrapper">

&#x20;   <table class="ai-type-table">

&#x20;     <thead>

&#x20;       <tr>

&#x20;         <th>Filter value</th>

&#x20;         <th>Label in UI</th>

&#x20;         <th>Description</th>

&#x20;       </tr>

&#x20;     </thead>

&#x20;     <tbody>

&#x20;       <tr><td><code>ANALYSIS\_JOB</code></td><td>Scans</td><td>AI Intelligence analysis job runs</td></tr>

&#x20;       <tr><td><code>ASSISTANT\_CONVERSATION</code></td><td>Assistant</td><td>AI Assistant chat sessions</td></tr>

&#x20;       <tr><td><code>INSIGHT</code></td><td>Insights</td><td>Generated insight records</td></tr>

&#x20;       <tr><td><code>RECOMMENDATION</code></td><td>Recommendations</td><td>Action recommendations from analysis</td></tr>

&#x20;       <tr><td><code>REPORT</code></td><td>Reports</td><td>Exported or generated AI reports</td></tr>

&#x20;     </tbody>

&#x20;   </table>

&#x20; </div>



&#x20; <h2>Tool runs</h2>



&#x20; <p class="ai-section-description">

&#x20;   The Tool runs tab lists recent Platform MCP executions recorded by the Copilot tool-calling framework.

&#x20;   Each row includes tool name, risk level, status, result summary, latency, and actions.

&#x20; </p>



&#x20; <div class="ai-check-grid">

&#x20;   <div class="ai-check-column">

&#x20;     <div>✓ <span><strong>Statuses:</strong> <code>PENDING</code>, <code>AWAITING\_APPROVAL</code>, <code>SUCCEEDED</code>, <code>FAILED</code>, <code>REJECTED</code></span></div>

&#x20;     <div>✓ <span><strong>Risk:</strong> <code>LOW</code>, <code>MEDIUM</code>, <code>HIGH</code> (HIGH requires approval)</span></div>

&#x20;   </div>

&#x20;   <div class="ai-check-column">

&#x20;     <div>✓ <span><strong>Approve / Reject</strong> — available when status is <code>AWAITING\_APPROVAL</code> and you have <code>ai\_gateway:approve</code></span></div>

&#x20;     <div>✓ <span><strong>Details</strong> — inspect input, output, and errors for completed runs</span></div>

&#x20;   </div>

&#x20;   <div class="ai-check-column">

&#x20;     <div>✓ <span><strong>Refresh</strong> — reload the execution list after decisions or new runs</span></div>

&#x20;   </div>

&#x20; </div>



&#x20; <div class="ai-warning">

&#x20;   <span>♢</span>

&#x20;   <span>

&#x20;     A warning banner appears when one or more HIGH-risk executions are awaiting approval.

&#x20;     Users with <code>ai\_gateway:manage</code> can see all org tool executions; others see only their own runs.

&#x20;   </span>

&#x20; </div>



&#x20; <h2>Quick access</h2>

&#x20; <p class="ai-section-description">

&#x20;   The MCP Servers page links here via <strong>Tool runs</strong> and <strong>Pending approvals</strong> quick actions

&#x20;   when executions are waiting for a decision.

&#x20; </p>



&#x20; <h2>Related pages</h2>

&#x20; <div class="ai-check-grid">

&#x20;   <div class="ai-check-column">

&#x20;     <div>→ <span><a href="{{ '/axio/ai/dashboard/' | relative\_url }}">AI Dashboard</a> — summary KPIs from intelligence scans</span></div>

&#x20;   </div>

&#x20;   <div class="ai-check-column">

&#x20;     <div>→ <span><a href="{{ '/axio/ai/assistant/' | relative\_url }}">AI Assistant</a> — chat and tool execution from natural language</span></div>

&#x20;   </div>

&#x20;   <div class="ai-check-column">

&#x20;     <div>→ <span><a href="{{ '/axio/ai/mcp-servers/' | relative\_url }}">MCP Servers</a> — browse and run tools by domain</span></div>

&#x20;   </div>

&#x20; </div>



</div>



