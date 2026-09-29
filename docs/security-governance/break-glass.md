---

layout: default

title: Break Glass

parent: Security & Governance

nav_order: 6

permalink: /axio/security-governance/break-glass/
---



<div class="compliance-risk-reports">



&#x20; <header class="crr-page-header">

&#x20;   <h1>Break glass</h1>

&#x20;   <p>

&#x20;     Break glass provides <strong>TTL-bound emergency role grants</strong> at project, workspace, or environment scope.

&#x20;     Sessions are logged immutably in the audit trail. This is separate from policy exceptions and compliance waivers.

&#x20;   </p>

&#x20; </header>



&#x20; <section class="crr-section">

&#x20;   <h2>Where to find it</h2>



&#x20;   <table class="crr-table">

&#x20;     <thead>

&#x20;       <tr>

&#x20;         <th>Surface</th>

&#x20;         <th>Route / path</th>

&#x20;         <th>Primary use</th>

&#x20;       </tr>

&#x20;     </thead>

&#x20;     <tbody>

&#x20;       <tr>

&#x20;         <td><strong>Break glass page</strong></td>

&#x20;         <td><code>/governance/break-glass</code></td>

&#x20;         <td>View active and historical break glass sessions (Platform Administrators).</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Administration → Roles \&amp; Access</strong></td>

&#x20;         <td><strong>Break Glass</strong> tab</td>

&#x20;         <td>Create, terminate, and delete sessions; full management UI.</td>

&#x20;       </tr>

&#x20;     </tbody>

&#x20;   </table>



&#x20;   <div class="crr-callout amber-callout">

&#x20;     <span class="callout-icon">!</span>

&#x20;     <p>

&#x20;       Break glass is <strong>restricted to Platform Administrators</strong>. The standalone page shows a read-only

&#x20;       session table when you have access; session creation and termination are managed from Roles \&amp; Access.

&#x20;     </p>

&#x20;   </div>

&#x20; </section>



&#x20; <section class="crr-section compliance-section">

&#x20;   <div class="crr-main-column">

&#x20;     <div class="crr-section-title">

&#x20;       <span class="crr-icon compliance-icon">♢</span>

&#x20;       <h2>What break glass does</h2>

&#x20;     </div>



&#x20;     <p>

&#x20;       During an incident, a Platform Administrator can grant a temporary role to a user, team, or synced group

&#x20;       at a scoped resource so they can perform emergency work without a permanent role change.

&#x20;     </p>



&#x20;     <ul>

&#x20;       <li>Each session has a <strong>time-to-live (TTL)</strong> — 15 minutes to 24 hours.</li>

&#x20;       <li>An <strong>incident number</strong> and <strong>justification</strong> are required when activating.</li>

&#x20;       <li>Sessions <strong>expire automatically</strong> when TTL elapses.</li>

&#x20;       <li>All actions are written to <strong>Administration → Audit Logs</strong>.</li>

&#x20;     </ul>

&#x20;   </div>



&#x20;   <aside class="crr-action-card green-card">

&#x20;     <h3>Supported scopes</h3>

&#x20;     <ul class="check-list">

&#x20;       <li><strong>Project</strong></li>

&#x20;       <li><strong>Workspace</strong></li>

&#x20;       <li><strong>Environment</strong></li>

&#x20;     </ul>

&#x20;     <p style="margin-top: 1rem;">

&#x20;       Grant targets: individual user, team, or synced SCIM group. Assign a role from the org role catalog

&#x20;       (Compliance Officer is excluded from break glass role pickers).

&#x20;     </p>

&#x20;   </aside>

&#x20; </section>



&#x20; <section class="crr-section">

&#x20;   <h2>Session table columns</h2>



&#x20;   <p>On <code>/governance/break-glass</code> and the Roles \&amp; Access tab, sessions show:</p>



&#x20;   <table class="crr-table">

&#x20;     <thead>

&#x20;       <tr>

&#x20;         <th>Column</th>

&#x20;         <th>Meaning</th>

&#x20;       </tr>

&#x20;     </thead>

&#x20;     <tbody>

&#x20;       <tr>

&#x20;         <td><strong>Scope</strong></td>

&#x20;         <td>Project, workspace, or environment.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Resource</strong></td>

&#x20;         <td>Scoped resource identifier.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Grant</strong></td>

&#x20;         <td>User email (or principal) receiving the temporary role.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Role</strong></td>

&#x20;         <td>Role granted for the session.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Incident</strong></td>

&#x20;         <td>Incident or ticket reference number.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Started / Expires</strong></td>

&#x20;         <td>Session window.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Remaining</strong></td>

&#x20;         <td>Minutes left before automatic expiry.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Assigned by</strong></td>

&#x20;         <td>Administrator who activated the session.</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Status</strong></td>

&#x20;         <td><strong>ACTIVE</strong> or expired/terminated state.</td>

&#x20;       </tr>

&#x20;     </tbody>

&#x20;   </table>

&#x20; </section>



&#x20; <section class="crr-section">

&#x20;   <h2>Typical workflow</h2>



&#x20;   <ol class="security-numbered-list">

&#x20;     <li>Confirm the incident requires temporary elevated access (not a permanent role change).</li>

&#x20;     <li>Open <strong>Administration → Roles \&amp; Access → Break Glass</strong>.</li>

&#x20;     <li>Select scope (project, workspace, or environment), target user/team/group, role, TTL, incident number, and justification.</li>

&#x20;     <li>Activate the session; the grantee receives temporary permissions until expiry.</li>

&#x20;     <li>Monitor active sessions on the Break Glass tab or <code>/governance/break-glass</code>.</li>

&#x20;     <li><strong>Terminate</strong> early when the incident is resolved, or let TTL expire.</li>

&#x20;     <li>Review audit logs for the full session history.</li>

&#x20;   </ol>

&#x20; </section>



&#x20; <section class="crr-section">

&#x20;   <h2>Break glass vs other waivers</h2>



&#x20;   <table class="crr-table">

&#x20;     <thead>

&#x20;       <tr>

&#x20;         <th>Mechanism</th>

&#x20;         <th>What it grants</th>

&#x20;         <th>Where</th>

&#x20;       </tr>

&#x20;     </thead>

&#x20;     <tbody>

&#x20;       <tr>

&#x20;         <td><strong>Break glass</strong></td>

&#x20;         <td>Temporary <strong>role</strong> at project/workspace/environment scope</td>

&#x20;         <td>Roles \&amp; Access → Break Glass</td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Policy exceptions</strong></td>

&#x20;         <td>Time-bound waiver for an enforcing <strong>policy violation</strong></td>

&#x20;         <td><a href="{{ '/axio/security-governance/governance-dashboard/' | relative\_url }}">Governance Dashboard → Exceptions</a></td>

&#x20;       </tr>

&#x20;       <tr>

&#x20;         <td><strong>Compliance waivers</strong></td>

&#x20;         <td>Approval to mark a <strong>framework control</strong> as waived</td>

&#x20;         <td><a href="{{ '/axio/security-governance/compliance/' | relative\_url }}">Compliance → Exceptions</a></td>

&#x20;       </tr>

&#x20;     </tbody>

&#x20;   </table>

&#x20; </section>



&#x20; <section class="crr-section audit-section">

&#x20;   <div class="crr-main-column">

&#x20;     <div class="crr-section-title">

&#x20;       <span class="crr-icon audit-icon">♢</span>

&#x20;       <h2>Audit and governance</h2>

&#x20;     </div>



&#x20;     <p>

&#x20;       Break glass activation, termination, and expiry events appear in

&#x20;       <strong>Administration → Audit Logs</strong> (<code>/administration/audit-logs</code>).

&#x20;       Viewing audit logs requires <code>audit:read</code>.

&#x20;     </p>



&#x20;     <p>

&#x20;       Active break glass session counts may also surface as alerts on the Roles \&amp; Access hub when sessions are in progress.

&#x20;     </p>

&#x20;   </div>



&#x20;   <div class="audit-webhook-card">

&#x20;     <span class="webhook-icon">⌁</span>

&#x20;     <p>

&#x20;       For day-to-day policy posture, use the

&#x20;       <a href="{{ '/axio/security-governance/governance-dashboard/' | relative\_url }}">Governance Dashboard</a>.

&#x20;       Break glass is for audited emergency access only — not a substitute for fixing policy violations.

&#x20;     </p>

&#x20;   </div>

&#x20; </section>



</div>



<div class="page-navigation">



<a

class="nav-button previous"

href="{{ '/axio/security-governance/compliance/' | relative\_url }}">



← Compliance, risk \&amp; reports



</a>



<a

class="nav-button next"

href="{{ '/axio/security-governance/' | relative\_url }}">



Security \&amp; Governance →



</a>



</div>



