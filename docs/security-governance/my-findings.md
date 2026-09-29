---

layout: default

title: My Findings

parent: Security & Governance

nav_order: 4

permalink: /axio/security-governance/my-findings/

---



<div class="security-insights-page">



&#x20; <div class="security-page-header">

&#x20;   <h1>My findings</h1>



&#x20;   <div class="security-admin-note">

&#x20;     <span class="security-note-icon">i</span>

&#x20;     <span>

&#x20;       Open <strong>Security \&amp; Governance → My findings</strong> (<code>/security/findings</code>).

&#x20;       Requires <code>security:read</code> (same access as Security Insights).

&#x20;     </span>

&#x20;   </div>



&#x20;   <p class="security-lead">

&#x20;     My findings is the <strong>engineer work queue</strong> for open misconfigurations and policy failures

&#x20;     on repositories and stacks you can access. Run IaC scans from

&#x20;     <a href="{{ '/axio/security-governance/security-insights/' | relative\_url }}">Security Insights</a>,

&#x20;     fix the infrastructure code, and track violations here until they clear.

&#x20;     For org-wide posture, exceptions, and analytics, admins use the

&#x20;     <a href="{{ '/axio/security-governance/' | relative\_url }}">Governance Dashboard</a> instead.

&#x20;   </p>

&#x20; </div>



&#x20; <section class="security-section">

&#x20;   <h2>Who should use this page</h2>



&#x20;   <table class="security-table">

&#x20;     <thead>

&#x20;       <tr>

&#x20;         <th>Audience</th>

&#x20;         <th>Use My findings when…</th>

&#x20;       </tr>

&#x20;     </thead>

&#x20;     <tbody>

&#x20;       <tr>

&#x20;         <td><strong>Engineers / members</strong></td>

&#x20;         <td>You need to see and fix violations on stacks and repos in your day-to-day work.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Admins / governance owners</strong></td>

&#x20;         <td>You want a focused violation list without leaving the security area; use Governance Dashboard for org-wide remediation and settings.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Viewers</strong></td>

&#x20;         <td>You need read-only visibility into open violations in scope.</td>

&#x20;       </tr>

&#x20;     </tbody>

&#x20;   </table>



&#x20;   <div class="security-info-note">

&#x20;     <span>i</span>

&#x20;     <p>

&#x20;       Non-admins see an info banner: organization-wide policy packs, scan defaults, and compliance

&#x20;       settings are managed by your administrator. You can still scan Git repositories and platform

&#x20;       resources you have access to from Security Insights.

&#x20;     </p>

&#x20;   </div>

&#x20; </section>



&#x20; <section class="security-section">

&#x20;   <h2>Page layout</h2>



&#x20;   <p>The page has three main areas:</p>



&#x20;   <ol class="security-numbered-list">

&#x20;     <li><strong>Header</strong> — title and short description of the work queue.</li>

&#x20;     <li><strong>Need to scan new code?</strong> — shortcut to run a Git repository scan on Security Insights.</li>

&#x20;     <li><strong>Open violations</strong> — filterable table of policy violations from the last 30 days.</li>

&#x20;   </ol>



&#x20;   <p>

&#x20;     The <strong>Scan Git repository</strong> button opens

&#x20;     <code>/security/insights?tab=scans\&amp;focus=repos</code>, scrolling to the live IaC scan panel

&#x20;     on the IaC scans tab.

&#x20;   </p>

&#x20; </section>



&#x20; <section class="security-section">

&#x20;   <h2>Open violations explorer</h2>



&#x20;   <p>

&#x20;     The <strong>Open violations</strong> panel uses the same violation explorer as the Governance Dashboard,

&#x20;     tuned for engineers. IaC scan findings appear here after you run a repository or platform scan;

&#x20;     policy evaluation results appear when assigned policies fail.

&#x20;   </p>



&#x20;   <h3>Filters and summaries</h3>



&#x20;   <table class="security-table">

&#x20;     <thead>

&#x20;       <tr>

&#x20;         <th>Control</th>

&#x20;         <th>What it does</th>

&#x20;       </tr>

&#x20;     </thead>

&#x20;     <tbody>

&#x20;       <tr>

&#x20;         <td><strong>Filter by stack</strong></td>

&#x20;         <td>Chip filters for stacks with open violations (up to eight shown). Click again to clear, or use <strong>Clear filter</strong>.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Policy summary chips</strong></td>

&#x20;         <td>Top policies by violation count — quick context before drilling into rows.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Time window</strong></td>

&#x20;         <td>Violations from the last <strong>30 days</strong> (default query period).</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Pagination</strong></td>

&#x20;         <td>Page through results; change page size (10, 20, 50, or 100 rows).</td>

&#x20;       </tr>

&#x20;     </tbody>

&#x20;   </table>



&#x20;   <h3>Violation table columns</h3>



&#x20;   <table class="security-table">

&#x20;     <thead>

&#x20;       <tr>

&#x20;         <th>Column</th>

&#x20;         <th>Meaning</th>

&#x20;       </tr>

&#x20;     </thead>

&#x20;     <tbody>

&#x20;       <tr>

&#x20;         <td><strong>Policy</strong></td>

&#x20;         <td>Policy name and violation message.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Resource</strong></td>

&#x20;         <td>Resource address in IaC (monospace).</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Severity</strong></td>

&#x20;         <td>Critical, high, medium, or low.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Trigger</strong></td>

&#x20;         <td>What produced the evaluation (e.g. scan, deployment gate, policy evaluation).</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Status</strong></td>

&#x20;         <td>Remediation status: <strong>OPEN</strong>, <strong>IN PROGRESS</strong>, or <strong>RESOLVED</strong>.</td>

&#x20;       </tr>

&#x20;     </tbody>

&#x20;   </table>



&#x20;   <p>

&#x20;     At the bottom of the table, <strong>Open remediation center</strong> links to

&#x20;     <strong>Governance Dashboard → Remediation</strong> (<code>/governance?tab=remediation</code>).

&#x20;   </p>

&#x20; </section>



&#x20; <section class="security-section">

&#x20;   <h2>Empty state</h2>



&#x20;   <p>

&#x20;     When there are no open violations for the selected period, the page shows

&#x20;     <strong>No open violations</strong> with guidance to keep posture current.

&#x20;   </p>



&#x20;   <div class="security-action-grid">



&#x20;     <div class="security-action-card">

&#x20;       <span class="security-action-icon green">⌕</span>

&#x20;       <h4>Run IaC scan</h4>

&#x20;       <p>Primary action — opens Security Insights on the IaC scans tab to scan Git repos or platform resources.</p>

&#x20;     </div>



&#x20;   </div>



&#x20;   <p>

&#x20;     On the Governance Dashboard, admins see an additional <strong>Evaluate policies</strong> action in the

&#x20;     empty state; My findings does not show that secondary action (engineers scan IaC instead).

&#x20;   </p>

&#x20; </section>



&#x20; <section class="security-section security-findings-section">

&#x20;   <h2>Typical workflow</h2>



&#x20;   <ol class="security-numbered-list">

&#x20;     <li>Open <strong>My findings</strong> and review open violations, optionally filtering by stack.</li>

&#x20;     <li>Identify the policy and resource address; open the corresponding repo or stack in your editor.</li>

&#x20;     <li>Fix the IaC misconfiguration or policy failure in source code.</li>

&#x20;     <li>Re-scan from <strong>Security Insights → IaC scans</strong> (Git live scan, Scan now, or platform on-demand scan).</li>

&#x20;     <li>Retry deployment if a gate blocked <strong>PLAN</strong> or <strong>APPLY</strong>.</li>

&#x20;     <li>Confirm the violation moves to <strong>RESOLVED</strong> or drops off the list after the next evaluation.</li>

&#x20;   </ol>



&#x20;   <div class="security-two-column">



&#x20;     <div class="security-capability-card allowed">

&#x20;       <h3>What you can do</h3>

&#x20;       <ul>

&#x20;         <li>Filter and inspect violations on stacks and repos in your work queue.</li>

&#x20;         <li>Jump to Security Insights to run new scans.</li>

&#x20;         <li>Open the remediation center for tracking (shared with Governance Dashboard).</li>

&#x20;       </ul>

&#x20;     </div>



&#x20;     <div class="security-capability-card restricted">

&#x20;       <h3>What you cannot do here</h3>

&#x20;       <ul>

&#x20;         <li>Install org-wide policy packs or assign compliance frameworks.</li>

&#x20;         <li>Change policy gate mode or live-scan defaults.</li>

&#x20;         <li>Create or approve organization-wide policy exceptions.</li>

&#x20;         <li>Run org-wide platform scans (reserved for org owner on Security Insights).</li>

&#x20;       </ul>

&#x20;     </div>



&#x20;   </div>

&#x20; </section>



&#x20; <section class="security-section">

&#x20;   <h2>My findings vs Governance Dashboard</h2>



&#x20;   <table class="security-table">

&#x20;     <thead>

&#x20;       <tr>

&#x20;         <th>My findings</th>

&#x20;         <th>Governance Dashboard</th>

&#x20;       </tr>

&#x20;     </thead>

&#x20;     <tbody>

&#x20;       <tr>

&#x20;         <td>Engineer-focused work queue at <code>/security/findings</code></td>

&#x20;         <td>Org control center at <code>/governance</code></td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td>Open violations table and scan shortcut</td>

&#x20;         <td>Violations, exceptions, remediation, posture, analytics, settings</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td>Linked from Security Insights KPIs (non-admin)</td>

&#x20;         <td>Linked from Security Insights KPIs (admin) and connectors</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td>No policy pack or gate configuration</td>

&#x20;         <td>Gate mode, live-scan defaults, evidence export, integrations</td>

&#x20;       </tr>

&#x20;     </tbody>

&#x20;   </table>



&#x20;   <div class="security-warning">

&#x20;     <span>⚠</span>

&#x20;     <p>

&#x20;       Admins see a footer link to the Governance Dashboard for org-wide remediation, exceptions,

&#x20;       and posture analytics. Do not disable deploy gates globally to clear a single stack unless

&#x20;       leadership explicitly approves it.

&#x20;     </p>

&#x20;   </div>

&#x20; </section>



&#x20; <section class="security-section">

&#x20;   <h2>How findings get here</h2>



&#x20;   <ol class="security-numbered-list">

&#x20;     <li><strong>IaC scans</strong> (Security Insights) — Terraform, OpenTofu, Pulumi, CloudFormation, and secrets-in-code checks produce misconfiguration findings.</li>

&#x20;     <li><strong>Live scan</strong> — continuous evaluation on connected Git repositories surfaces new issues automatically.</li>

&#x20;     <li><strong>Policy evaluation</strong> — assigned policy packs add guardrails; failures become violations.</li>

&#x20;     <li><strong>Deploy gates</strong> — enforcing policies during <strong>PLAN/APPLY</strong> record violations when deployments are blocked or warned.</li>

&#x20;   </ol>



&#x20;   <div class="security-info-note">

&#x20;     <span>i</span>

&#x20;     <p>

&#x20;       Built-in misconfiguration and secrets checks always run during scans; policy packs are optional

&#x20;       but add organizational rules on top. Violations from scans and policy evaluation appear together

&#x20;       in the Open violations table.

&#x20;     </p>

&#x20;   </div>

&#x20; </section>



&#x20; <section class="security-section">

&#x20;   <h2>Permissions</h2>



&#x20;   <table class="security-table">

&#x20;     <thead>

&#x20;       <tr>

&#x20;         <th>Permission / role</th>

&#x20;         <th>Typical access on My findings</th>

&#x20;       </tr>

&#x20;     </thead>

&#x20;     <tbody>

&#x20;       <tr>

&#x20;         <td><code>security:read</code></td>

&#x20;         <td>View My findings and the violations table (required for nav access).</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><code>security:manage</code>, <code>policy:manage</code>, or <code>governance:manage</code></td>

&#x20;         <td>Act on findings — resolve, suppress, or update remediations (viewers stay read-only).</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><code>governance:manage</code> or org Admin/Owner</td>

&#x20;         <td>Same violation explorer with admin empty-state actions; full org tools on Governance Dashboard.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td>Viewers</td>

&#x20;         <td>Read-only access to violations in scope.</td>

&#x20;       </tr>

&#x20;     </tbody>

&#x20;   </table>

&#x20; </section>



</div>



<div class="page-navigation">



<a

class="nav-button previous"

href="{{ '/axio/security-governance/security-insights/' | relative\_url }}">



← Security Insights



</a>



<a

class="nav-button next"

href="{{ '/axio/security-governance/' | relative\_url }}">



Governance Dashboard →



</a>



</div>



