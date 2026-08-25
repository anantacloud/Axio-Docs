---
layout: default
nav_order: 3
parent: Operations
title: Cost Explorer
---

<div class="cost-page">

<div class="cost-breadcrumb">
  <span>Operations</span>
  <span>/</span>
  <strong>Cost Explorer</strong>
</div>

<h1>Cost Explorer</h1>

<p class="cost-intro">
Cost Explorer helps you understand the financial impact of your infrastructure before you deploy.
Axio scans your Terraform stacks to provide cost estimates, savings opportunities, and anomaly detection.
</p>

<div class="cost-info-box">
  <div class="cost-info-icon">ⓘ</div>
  <div>
    <h3>Why cost analysis?</h3>
    <p>
      Cost analysis enables you to make informed decisions by showing the potential cost impact
      of changes before they are applied to your environment.
    </p>
  </div>
</div>

<h2>How it works</h2>

<p>
Axio estimates the cost of your infrastructure and highlights changes, savings, and potential issues.
</p>

<div class="cost-flow">

  <div class="cost-flow-card cost-flow-blue">
    <div class="cost-flow-icon">▱</div>
    <strong>1. Scan Stack</strong>
    <p>Axio scans your Terraform stack and its resources</p>
  </div>

  <div class="cost-flow-arrow">→</div>

  <div class="cost-flow-card cost-flow-green">
    <div class="cost-flow-icon">◉</div>
    <strong>2. Estimate Cost</strong>
    <p>We calculate the monthly and annual cost</p>
  </div>

  <div class="cost-flow-arrow">→</div>

  <div class="cost-flow-card cost-flow-purple">
    <div class="cost-flow-icon">▥</div>
    <strong>3. Analyze Impact</strong>
    <p>Compare with the current baseline to find changes</p>
  </div>

  <div class="cost-flow-arrow">→</div>

  <div class="cost-flow-card cost-flow-orange">
    <div class="cost-flow-icon">♧</div>
    <strong>4. Provide Insights</strong>
    <p>Identify savings opportunities and cost anomalies</p>
  </div>

</div>

<h2>Cost summary (All Scanned Stacks)</h2>

<div class="cost-summary-grid">

  <div class="cost-metric-card">
    <div class="cost-metric-label">MONTHLY COST <span>$</span></div>
    <div class="cost-metric-value green">$180</div>
    <div class="cost-metric-description">Current monthly cost</div>
  </div>

  <div class="cost-metric-card">
    <div class="cost-metric-label">ANNUAL FORECAST <span>▣</span></div>
    <div class="cost-metric-value">$2,160</div>
    <div class="cost-metric-description">Projected 12-month cost</div>
  </div>

  <div class="cost-metric-card">
    <div class="cost-metric-label">POTENTIAL SAVINGS <span>◇</span></div>
    <div class="cost-metric-value green">$210</div>
    <div class="cost-metric-description">Estimated monthly savings</div>
  </div>

  <div class="cost-metric-card">
    <div class="cost-metric-label">COST ANOMALIES <span>△</span></div>
    <div class="cost-metric-value red">3</div>
    <div class="cost-metric-description">Stacks with anomalies</div>
  </div>

</div>

<h2>Consolidated spend by dimension</h2>

<p>
View your estimated spend broken down by organization, project, workspace, environment, and stack.
</p>

<div class="cost-tabs">
  <span class="active">By Organization</span>
  <span>By Project</span>
  <span>By Workspace</span>
  <span>By Environment</span>
  <span>By Stack</span>
</div>

<div class="cost-table-wrapper">
<table class="cost-table">
<thead>
<tr>
  <th>Organization</th>
  <th>Monthly Cost</th>
  <th>Annual Forecast</th>
  <th>Potential Savings</th>
  <th>Anomalies</th>
</tr>
</thead>
<tbody>
<tr>
  <td>acme-corp</td>
  <td>$120</td>
  <td>$1,440</td>
  <td>$120</td>
  <td><span class="cost-anomaly">2</span></td>
</tr>
<tr>
  <td>product-org</td>
  <td>$45</td>
  <td>$540</td>
  <td>$60</td>
  <td><span class="cost-anomaly">1</span></td>
</tr>
<tr>
  <td>platform-org</td>
  <td>$15</td>
  <td>$180</td>
  <td>$30</td>
  <td>0</td>
</tr>
</tbody>
</table>
</div>

<div class="cost-two-column">

<div>
<h2>What you can do</h2>

<ul class="cost-check-list">
  <li>Scan stacks on demand or on a schedule.</li>
  <li>Compare cost against your current baseline.</li>
  <li>Identify savings opportunities before deployment.</li>
  <li>Detect unusual cost changes and anomalies.</li>
  <li>Export detailed cost reports for sharing and audit.</li>
</ul>
</div>

<div class="cost-report-box">
  <h3>Cost report includes</h3>
  <ul>
    <li>Resource-level cost breakdown</li>
    <li>Monthly cost and 12-month forecast</li>
    <li>Cost difference vs. baseline</li>
    <li>Savings opportunities</li>
    <li>Cost anomalies and recommendations</li>
  </ul>
</div>

</div>


