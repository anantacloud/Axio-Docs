---
layout: default
title: Governance Dashboard
parent: Security & Governance
nav_order: 5
permalink: /axio/security-governance/governance-dashboard/
---



<div class="governance-dashboard">



&#x20; <div class="governance-intro">

&#x20;   <h1>Governance Dashboard</h1>



&#x20;   <p>

&#x20;     Open <strong>Security \&amp; Governance → Dashboard</strong> (<code>/governance</code>) for the org-wide

&#x20;     governance control center: compliance posture, policy violations, exceptions, remediation, analytics, and settings.

&#x20;     Requires <code>governance:read</code> (org Admin/Owner or users with governance read access).

&#x20;   </p>



&#x20;   <div class="governance-note">

&#x20;     <span class="governance-note-icon">i</span>

&#x20;     <span>

&#x20;       Engineers who only fix issues on their stacks should use

&#x20;       <a href="{{ '/axio/security-governance/my-findings/' | relative\_url }}">My findings</a>

&#x20;       instead of the full dashboard.

&#x20;     </span>

&#x20;   </div>

&#x20; </div>



&#x20; <section class="governance-section">

&#x20;   <h2>Page layout</h2>



&#x20;   <table class="governance-table">

&#x20;     <thead>

&#x20;       <tr>

&#x20;         <th>Area</th>

&#x20;         <th>What it shows</th>

&#x20;       </tr>

&#x20;     </thead>

&#x20;     <tbody>

&#x20;       <tr>

&#x20;         <td><strong>Quick actions</strong></td>

&#x20;         <td>Review violations (when any exist), Run IaC scan, Manage policies, Policy packs.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Filters</strong></td>

&#x20;         <td>Date range (7 / 30 / 90 days), cloud provider (All, AWS, Azure, GCP, OCI, DigitalOcean), framework (All, CIS, NIST, ISO 27001, SOC 2, PCI DSS, HIPAA).</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Hero banner</strong></td>

&#x20;         <td>Compliance score with posture status (Looking good / Needs attention / At risk), open violations, active policies, critical/high count.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Severity strip</strong></td>

&#x20;         <td>Critical, high, medium, and low violation counts with link to the Violations tab.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Recommended next steps</strong></td>

&#x20;         <td>Contextual suggestions (e.g. review violations, manage exceptions, run scans).</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Main tabs</strong></td>

&#x20;         <td>Violations, Exceptions, Remediation, Posture, Analytics, Settings — tab labels show live counts where applicable.</td>

&#x20;       </tr>

&#x20;     </tbody>

&#x20;   </table>



&#x20;   <p>

&#x20;     Use the header <strong>⋮</strong> menu to <strong>Export CSV</strong> (KPI snapshot),

&#x20;     open the <strong>Setup wizard</strong>, or <strong>Export PDF</strong> (browser print).

&#x20;     The refresh button reloads all dashboard data.

&#x20;   </p>

&#x20; </section>



&#x20; <section class="governance-section">

&#x20;   <h2>Hero KPIs</h2>



&#x20;   <p>Click a KPI card to jump to the related tab or filtered view:</p>



&#x20;   <table class="governance-table">

&#x20;     <thead>

&#x20;       <tr>

&#x20;         <th>KPI</th>

&#x20;         <th>Meaning</th>

&#x20;         <th>Click action</th>

&#x20;       </tr>

&#x20;     </thead>

&#x20;     <tbody>

&#x20;       <tr>

&#x20;         <td><strong>Compliance score</strong></td>

&#x20;         <td>Overall posture percentage; status band at 90%+ (healthy), 70–89% (attention), below 70% (at risk).</td>

&#x20;         <td>Analytics → compliance score trend</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Open violations</strong></td>

&#x20;         <td>Total open policy violations in scope.</td>

&#x20;         <td>Violations tab</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Active policies</strong></td>

&#x20;         <td>Enabled policies contributing to evaluation.</td>

&#x20;         <td>Analytics → policy distribution</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Critical / high</strong></td>

&#x20;         <td>Priority violations requiring review.</td>

&#x20;         <td>Violations tab filtered to critical and high</td>

&#x20;       </tr>

&#x20;     </tbody>

&#x20;   </table>

&#x20; </section>



&#x20; <section class="governance-section">

&#x20;   <h2>Tabs</h2>



&#x20;   <table class="governance-table">

&#x20;     <thead>

&#x20;       <tr>

&#x20;         <th>Tab</th>

&#x20;         <th>Purpose</th>

&#x20;       </tr>

&#x20;     </thead>

&#x20;     <tbody>

&#x20;       <tr>

&#x20;         <td class="enforce-text">Violations</td>

&#x20;         <td>Org-wide <strong>Open violations</strong> explorer — drill down by stack, policy, and resource; filter by severity from hero KPIs. Uses admin audience (includes <strong>Evaluate policies</strong> in empty state).</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td class="advisory-text">Exceptions</td>

&#x20;         <td>Time-bound <strong>policy waivers</strong> with approval workflow. Requires <code>governance:approve</code> to approve (Compliance Officer preset).</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td class="failopen-text">Remediation</td>

&#x20;         <td>Remediation center — track enforcing violations, assign owners, sync with external tickets when change management is connected.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td>Posture</td>

&#x20;         <td>Policy coverage by cloud and stack; <strong>Scheduled compliance</strong> panel for automatic policy re-evaluation interval.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td>Analytics</td>

&#x20;         <td>Evaluation trend, compliance score trend, policy distribution by category, framework coverage, cloud distribution, policy pack usage, findings severity trend.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td>Settings</td>

&#x20;         <td>Policy gate, live-scan defaults, audit webhook, evidence delivery schedules, integrations — grouped by purpose.</td>

&#x20;       </tr>

&#x20;     </tbody>

&#x20;   </table>



&#x20;   <p>

&#x20;     Deep-link to a tab with query params, e.g. <code>/governance?tab=violations</code>,

&#x20;     <code>/governance?tab=settings</code>, <code>/governance?tab=remediation</code>.

&#x20;   </p>

&#x20; </section>



&#x20; <section class="governance-section">

&#x20;   <h2>Setup wizard</h2>



&#x20;   <p>

&#x20;     Open from the header <strong>⋮ → Setup wizard</strong> or Settings when onboarding is incomplete.

&#x20;     Four steps:

&#x20;   </p>



&#x20;   <ol class="settings-checklist">

&#x20;     <li><strong>Install pack</strong> — install the recommended SOC 2 demo policy pack (<code>soc2-pack</code>) or continue with existing policies.</li>

&#x20;     <li><strong>Gate mode</strong> — set org-wide <strong>Enforce</strong>, <strong>Advisory</strong>, or <strong>Fail-open</strong> for PLAN/APPLY.</li>

&#x20;     <li><strong>Evaluate</strong> — run an organization-wide policy evaluation (or skip).</li>

&#x20;     <li><strong>Done</strong> — mark onboarding complete; review violations or export from Reports.</li>

&#x20;   </ol>



&#x20;   <p>

&#x20;     Manual setup alternative: use

&#x20;     <a href="{{ '/axio/security-governance/policies/' | relative\_url }}">Policy Packs</a> and

&#x20;     <a href="{{ '/axio/security-governance/policies/' | relative\_url }}">Policy Library</a>,

&#x20;     then return to finish gate mode and evaluation.

&#x20;   </p>

&#x20; </section>



&#x20; <section class="governance-bottom-grid">



&#x20;   <div class="governance-panel">

&#x20;     <h2>Policy gate modes</h2>



&#x20;     <table class="governance-table">

&#x20;       <thead>

&#x20;         <tr>

&#x20;           <th>Mode</th>

&#x20;           <th>Deploy behavior</th>

&#x20;         </tr>

&#x20;       </thead>

&#x20;       <tbody>

&#x20;         <tr>

&#x20;           <td class="enforce-text">Enforce</td>

&#x20;           <td>Blocks deployment when policies fail or the gate cannot evaluate.</td>

&#x20;         </tr>

&#x20;         <tr>

&#x20;           <td class="advisory-text">Advisory</td>

&#x20;           <td>Records violations but does not block deployment.</td>

&#x20;         </tr>

&#x20;         <tr>

&#x20;           <td class="failopen-text">Fail-open</td>

&#x20;           <td>Blocks on enforcing violations; evaluation engine errors allow deploy with warnings.</td>

&#x20;         </tr>

&#x20;       </tbody>

&#x20;     </table>



&#x20;     <div class="policy-gate-note">

&#x20;       ⓘ \&nbsp; The policy gate runs during <strong>PLAN</strong> and <strong>APPLY</strong>.

&#x20;       Enable <strong>per-environment gates</strong> in Settings to override the org default by environment type.

&#x20;     </div>

&#x20;   </div>



&#x20;   <div class="governance-panel governance-settings">

&#x20;     <h2>Settings tab checklist</h2>



&#x20;     <ul class="settings-checklist">

&#x20;       <li>Org-wide policy gate mode and optional per-environment overrides.</li>

&#x20;       <li>Live scanning defaults for new repositories (enabled, scanners, fail-on severity, runner, notify on failure).</li>

&#x20;       <li>Audit webhook URL for governance-category events (JSON POST).</li>

&#x20;       <li>Unified schedules — evidence export, compliance assessments, and related jobs.</li>

&#x20;       <li>Integrations panel for governance-related connectors.</li>

&#x20;       <li>Related links: IaC runtime images (Administration → IaC Engines), Jira/evidence (Administration → Integrations → Change Management).</li>

&#x20;     </ul>



&#x20;     <div class="governance-delivery-note">

&#x20;       <strong>Evidence delivery:</strong> Scheduled evidence bundles are delivered via <strong>webhook</strong>

&#x20;       (HTTP POST). Email and S3 delivery may log intent until credentials are configured in Administration.

&#x20;     </div>

&#x20;   </div>



&#x20; </section>



&#x20; <section class="governance-section">

&#x20;   <h2>Related pages</h2>



&#x20;   <ul class="settings-checklist">

&#x20;     <li><a href="{{ '/axio/security-governance/security-insights/' | relative\_url }}">Security Insights</a> — IaC scans and live scan</li>

&#x20;     <li><a href="{{ '/axio/security-governance/my-findings/' | relative\_url }}">My findings</a> — engineer work queue</li>

&#x20;     <li><a href="{{ '/axio/security-governance/policies/' | relative\_url }}">Policies</a> — Policy Library and Policy Packs</li>

&#x20;     <li><a href="{{ '/axio/security-governance/compliance/' | relative\_url }}">Compliance, risk, and reports</a></li>

&#x20;     <li><a href="{{ '/axio/security-governance/break-glass/' | relative\_url }}">Break glass</a> — emergency role grants</li>

&#x20;   </ul>

&#x20; </section>



&#x20; <section class="governance-section">

&#x20;   <h2>Permissions</h2>



&#x20;   <table class="governance-table">

&#x20;     <thead>

&#x20;       <tr>

&#x20;         <th>Permission / role</th>

&#x20;         <th>Typical access</th>

&#x20;       </tr>

&#x20;     </thead>

&#x20;     <tbody>

&#x20;       <tr>

&#x20;         <td><code>governance:read</code></td>

&#x20;         <td>View the dashboard, analytics, and read-only tabs.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><code>governance:manage</code> or org Admin/Owner</td>

&#x20;         <td>Change settings, gate mode, webhooks, and schedules.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><code>governance:approve</code></td>

&#x20;         <td>Approve policy exceptions on the Exceptions tab.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><code>security:manage</code>, <code>policy:manage</code></td>

&#x20;         <td>Act on findings and remediations where permitted.</td>

&#x20;       </tr>

&#x20;     </tbody>

&#x20;   </table>

&#x20; </section>



</div>



<div class="page-navigation">



<a

class="nav-button previous"

href="{{ '/axio/security-governance/' | relative\_url }}">



← Security \&amp; Governance



</a>



<a

class="nav-button next"

href="{{ '/axio/security-governance/security-insights/' | relative\_url }}">



Security Insights →



</a>



</div>



