---

layout: default

title: AI Dashboard

parent: AI

nav_order: 5

permalink: /axio/ai/dashboard/
---



<div class="ai-dashboard-page">



&#x20; <div class="ai-hero">

&#x20;   <h1>AI Dashboard</h1>

&#x20;   <p>

&#x20;     Open <strong>AI → Dashboard</strong> (<code>/ai/dashboard</code>) for a quick view of security,

&#x20;     compliance, and operations signals from AI Intelligence scans across your organization.

&#x20;     Legacy routes such as <code>/ai</code>, <code>/ai/insights</code>, <code>/ai-analytics</code>, and

&#x20;     <code>/operations/recommendations</code> redirect here.

&#x20;   </p>

&#x20; </div>



&#x20; <div class="ai-info-banner">

&#x20;   <span class="ai-banner-icon">ⓘ</span>

&#x20;   <span>

&#x20;     Requires <code>copilot:read</code>. Use <strong>Ask Assistant</strong> to investigate findings or

&#x20;     <a href="{{ '/axio/ai/activity/' | relative\_url }}">Activity</a> for scan and conversation history.

&#x20;   </span>

&#x20; </div>



&#x20; <h2>At a glance</h2>

&#x20; <p class="ai-section-description">

&#x20;   KPI cards summarize the latest intelligence findings aggregated for your org.

&#x20; </p>



&#x20; <div class="ai-kpi-grid">

&#x20;   <div class="ai-kpi-card">

&#x20;     <h3>Open findings</h3>

&#x20;     <p>Total open AI insight findings (critical, high, medium, low). Subtitle highlights critical or high counts when present.</p>

&#x20;   </div>

&#x20;   <div class="ai-kpi-card">

&#x20;     <h3>Compliance score</h3>

&#x20;     <p>Percentage derived from compliance-category findings. Shows failed control count when issues exist. Green at 80% or above.</p>

&#x20;   </div>

&#x20;   <div class="ai-kpi-card">

&#x20;     <h3>Cost opportunities</h3>

&#x20;     <p>Count of cost-optimization signals from recent analysis runs.</p>

&#x20;   </div>

&#x20;   <div class="ai-kpi-card">

&#x20;     <h3>Operations to review</h3>

&#x20;     <p>Combined drift, reliability, and deprecated-resource signals that may need attention.</p>

&#x20;   </div>

&#x20; </div>



&#x20; <h2>Status banner</h2>

&#x20; <p class="ai-section-description">

&#x20;   A contextual alert appears below the page header:

&#x20; </p>

&#x20; <div class="ai-check-grid">

&#x20;   <div class="ai-check-column">

&#x20;     <div>⚠ <span><strong>Warning</strong> — critical or high findings need review; suggests asking the Assistant</span></div>

&#x20;     <div>✓ <span><strong>Success</strong> — no open findings from recent scans</span></div>

&#x20;   </div>

&#x20;   <div class="ai-check-column">

&#x20;     <div>ⓘ <span><strong>Info</strong> — findings exist but none are critical/high; review the summary or ask the Assistant</span></div>

&#x20;   </div>

&#x20; </div>



&#x20; <h2>Findings by severity</h2>

&#x20; <p class="ai-section-description">

&#x20;   When open findings exist, a chart breaks them down by severity (Critical, High, Medium, Low).

&#x20; </p>



&#x20; <h2>Last analysis</h2>

&#x20; <p class="ai-section-description">

&#x20;   Shows when the most recent AI analysis job run completed, or <strong>No scans yet</strong> if none have run.

&#x20; </p>



&#x20; <h2>Data sources</h2>

&#x20; <p class="ai-section-description">

&#x20;   The dashboard aggregates <strong>AI Intelligence</strong> insight findings from repository scans

&#x20;   (security severity and category), compliance posture, and operations categories such as drift, cost,

&#x20;   reliability, and maintainability. It is a summary view — not a replacement for

&#x20;   Security \&amp; Governance dashboards or stack-level run history.

&#x20; </p>



&#x20; <h2>Related pages</h2>

&#x20; <div class="ai-check-grid">

&#x20;   <div class="ai-check-column">

&#x20;     <div>→ <span><a href="{{ '/axio/ai/assistant/' | relative\_url }}">AI Assistant</a> — ask about findings and next steps</span></div>

&#x20;   </div>

&#x20;   <div class="ai-check-column">

&#x20;     <div>→ <span><a href="{{ '/axio/ai/activity/' | relative\_url }}">Activity</a> — timeline of scans, insights, and reports</span></div>

&#x20;   </div>

&#x20;   <div class="ai-check-column">

&#x20;     <div>→ <span><a href="{{ '/axio/ai/prompt-library/' | relative\_url }}">Prompt Library</a> — built-in prompts for drift, FinOps, and security</span></div>

&#x20;   </div>

&#x20; </div>



</div>



