---
layout: default
nav_order: 3
parent: Operations
title: Cost Explorer
permalink: /axio/operations/cost/
---

<div class="cost-page">

<h1>Cost Explorer</h1>

<p class="cost-intro">
Open <strong>Operations → Cost Explorer</strong> to price Terraform stacks, forecast spend, and find savings opportunities.
Select a stack, run <strong>Scan now</strong>, and view consolidated totals across your organization hierarchy — before or after deployment.
</p>

<div class="cost-info-box">
  <div class="cost-info-icon">ⓘ</div>
  <div>
    <h3>Why cost analysis?</h3>
    <p>
      Cost analysis shows the estimated monthly and annual impact of your IaC configuration so you can
      compare options, rightsizing, and commitment purchases before changes reach production.
    </p>
  </div>
</div>

<h2>Stack cost scan</h2>

<p>
At the top of the page, pick a <strong>Terraform stack</strong> and pricing engine, then run <strong>Scan now</strong>.
Each scan prices all Terraform workspaces in that stack. Optionally enable a <strong>recurring schedule</strong>
(Daily, Weekly, or Monthly with a local time) per stack.
</p>

<ul>
  <li><strong>Built-in pricing</strong> — Available out of the box</li>
  <li><strong>Infracost</strong> — Cloud-accurate estimates when configured under <strong>Administration → Integrations → Infracost</strong></li>
</ul>

<h2>How it works</h2>

<p>
Axio discovers Terraform resources in the selected stack, prices them, and rolls results into forecasts, showback, and recommendations.
</p>

<div class="cost-flow">

  <div class="cost-flow-card cost-flow-blue">
    <div class="cost-flow-icon">▱</div>
    <strong>1. Select stack</strong>
    <p>Choose a Terraform stack and pricing engine</p>
  </div>

  <div class="cost-flow-arrow">→</div>

  <div class="cost-flow-card cost-flow-green">
    <div class="cost-flow-icon">◉</div>
    <strong>2. Scan &amp; price</strong>
    <p>Runner prices each Terraform workspace in the stack</p>
  </div>

  <div class="cost-flow-arrow">→</div>

  <div class="cost-flow-card cost-flow-purple">
    <div class="cost-flow-icon">▥</div>
    <strong>3. Roll up spend</strong>
    <p>Totals consolidate by org, project, workspace, environment, and stack</p>
  </div>

  <div class="cost-flow-arrow">→</div>

  <div class="cost-flow-card cost-flow-orange">
    <div class="cost-flow-icon">♧</div>
    <strong>4. Insights</strong>
    <p>Savings, commitments, anomalies, and chargeback reports</p>
  </div>

</div>

<h2>Consolidated spend summary</h2>

<p>
After at least one stack scan, the hero banner shows live totals (not sample data):
</p>

<div class="cost-summary-grid">

  <div class="cost-metric-card">
    <div class="cost-metric-label">MONTHLY SPEND <span>$</span></div>
    <div class="cost-metric-value green">—</div>
    <div class="cost-metric-description">All scanned stacks</div>
  </div>

  <div class="cost-metric-card">
    <div class="cost-metric-label">ANNUAL FORECAST <span>▣</span></div>
    <div class="cost-metric-value">—</div>
    <div class="cost-metric-description">12-month projection</div>
  </div>

  <div class="cost-metric-card">
    <div class="cost-metric-label">POTENTIAL SAVINGS <span>◇</span></div>
    <div class="cost-metric-value green">—</div>
    <div class="cost-metric-description">Estimated monthly opportunity</div>
  </div>

  <div class="cost-metric-card">
    <div class="cost-metric-label">OPEN ANOMALIES <span>△</span></div>
    <div class="cost-metric-value red">—</div>
    <div class="cost-metric-description">Unacknowledged cost spikes</div>
  </div>

</div>

<h2>Page tabs</h2>

<p>Cost Explorer organizes results into six tabs:</p>

<table class="cost-table">
<thead>
<tr>
  <th>Tab</th>
  <th>What it shows</th>
</tr>
</thead>
<tbody>
<tr>
  <td><strong>Overview</strong></td>
  <td>Allocation coverage, budget utilization, savings breakdown, spend by team, top recommendations, cost estimates table</td>
</tr>
<tr>
  <td><strong>Costs</strong></td>
  <td>Monthly cost, annual forecast, potential savings, idle resources; cost by Terraform target; optimization recommendations</td>
</tr>
<tr>
  <td><strong>Showback</strong></td>
  <td>Consolidated spend grouped by dimension (see below)</td>
</tr>
<tr>
  <td><strong>Savings</strong></td>
  <td>Commitment recommendations (Savings Plans / Reserved Instances) and rightsizing opportunities</td>
</tr>
<tr>
  <td><strong>Chargeback</strong></td>
  <td>Generate and download monthly invoices by scope</td>
</tr>
<tr>
  <td><strong>Anomalies</strong></td>
  <td>Unexpected spend spikes detected by comparing cost snapshots</td>
</tr>
</tbody>
</table>

<h2>Consolidated spend by dimension</h2>

<p>
On the <strong>Showback</strong> tab, use <strong>Group by</strong> to break down estimated spend. Available dimensions include:
</p>

<div class="cost-tabs">
  <span class="active">Organization</span>
  <span>Project</span>
  <span>Workspace</span>
  <span>Environment</span>
  <span>Stack</span>
  <span>Team / repository</span>
  <span>Terraform target</span>
  <span>Service</span>
  <span>Provider</span>
  <span>Region</span>
  <span>Engine</span>
</div>

<p>
The <strong>Cost estimates</strong> table (Overview and Costs tabs) uses cascading filters for organization, project, workspace, environment, and stack. Click a resource count to open resource-level pricing details.
</p>

<div class="cost-table-wrapper">
<table class="cost-table">
<thead>
<tr>
  <th>Column</th>
  <th>Description</th>
</tr>
</thead>
<tbody>
<tr>
  <td>Organization / Project / Workspace / Environment / Stack</td>
  <td>Hierarchy attribution from the scanned stack</td>
</tr>
<tr>
  <td>TF workspace</td>
  <td>Terraform workspace name within the stack</td>
</tr>
<tr>
  <td>Monthly</td>
  <td>Estimated monthly cost for that row</td>
</tr>
<tr>
  <td>Resources</td>
  <td>Number of priced resources (click to open detail dialog)</td>
</tr>
<tr>
  <td>Savings</td>
  <td>Potential monthly savings for that estimate</td>
</tr>
</tbody>
</table>
</div>

<div class="cost-two-column">

<div>
<h2>What you can do</h2>

<ul class="cost-check-list">
  <li>Scan Terraform stacks on demand or on a Daily / Weekly / Monthly schedule.</li>
  <li>Switch between <strong>Built-in pricing</strong> and <strong>Infracost</strong> (when configured).</li>
  <li>Compare cost against a previous scan baseline (delta shown on estimates).</li>
  <li>Identify rightsizing, idle resources, and commitment (RI / Savings Plan) opportunities.</li>
  <li>Detect anomalies with <strong>Check for anomalies</strong> on the Anomalies tab.</li>
  <li>Generate chargeback invoices and download reports for audit and sharing.</li>
</ul>
</div>

<div class="cost-report-box">
  <h3>Resource detail includes</h3>
  <ul>
    <li>Per-resource monthly and annual cost</li>
    <li>Discovery source (provisioned state, workspace config, or repository IaC preview)</li>
    <li>Cost delta vs. previous scan</li>
    <li>Idle resource count and optimization recommendations</li>
    <li>Infracost badge when that engine was used</li>
  </ul>
</div>

</div>

<h2>Permissions</h2>

<table class="cost-table">
<thead>
<tr>
  <th>Permission</th>
  <th>Capability</th>
</tr>
</thead>
<tbody>
<tr>
  <td><code>cost:read</code></td>
  <td>View Cost Explorer tabs, forecasts, showback, and estimates</td>
</tr>
<tr>
  <td><code>cost:manage</code></td>
  <td>Run scans, configure schedules, generate chargeback, acknowledge anomalies</td>
</tr>
</tbody>
</table>

<h2>Anomalies</h2>

<p>
On the <strong>Anomalies</strong> tab, click <strong>Check for anomalies</strong> to capture a baseline snapshot and compare current spend.
Open anomalies show severity, dimension, previous vs. current amounts, and percent change. Use <strong>Acknowledge</strong> to close reviewed items.
</p>

<div class="cost-note">

<strong>Tip:</strong> Run at least one stack scan before using Showback, Savings, or Anomalies — those tabs populate from scan results and inventory attribution.

</div>

<div class="page-navigation">

<a
class="nav-button previous"
href="{{ '/axio/operations/drift/' | relative_url }}">

← Drift Detection

</a>

</div>

</div>
