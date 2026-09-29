---
layout: default
title: Workload targeting
parent: Runner
nav_order: 7
permalink: /axio/administration/runner/targeting/
---



<link rel="stylesheet" href="{{ '/assets/css/workload-targeting.css' | relative_url }}">


<div class="workload-targeting-doc">

 <h1>Workload targeting</h1>

 <p class="lead">

   Stacks, deployments, and workflow templates choose <strong>how</strong> work finds a runner.

   The Runners page only registers and organizes agents; targeting lives on the workload.

 </p>

 <section class="doc-panel strategies-panel">

   <div class="section-heading">

     <span class="section-icon green">◎</span>

     <h2>Strategies</h2>

   </div>

   <div class="table-wrap">

     <table>

       <thead>

         <tr>

           <th>Strategy</th>

           <th>What you set</th>

           <th>Scheduler behavior</th>

         </tr>

       </thead>

       <tbody>

         <tr>

           <td><code>automatic</code></td>

           <td>Nothing required</td>

           <td>Best available self-hosted runner in scope; hosted fleet if <code>axio-\*</code> labels require it</td>

         </tr>

         <tr>

           <td><code>runner-group</code></td>

           <td>Group name</td>

           <td>Only runners in that group (still must be online, in scope, and have capacity)</td>

         </tr>

         <tr>

           <td><code>specific-runner</code></td>

           <td>Runner name</td>

           <td>Pin to one agent</td>

         </tr>

         <tr>

           <td><code>labels</code></td>

           <td>Customer or hosted labels</td>

           <td>All listed labels must match</td>

         </tr>

         <tr>

           <td><code>provider-runner</code></td>

           <td>Hosted label such as <code>axio-linux</code></td>

           <td>Shared Axio fleet only (subscription required)</td>

         </tr>

       </tbody>

     </table>

   </div>

 </section>

 <section class="doc-panel examples-panel">

   <div class="section-heading">

     <span class="section-icon purple">▤</span>

     <h2>Examples (axio.yaml)</h2>

   </div>

   <p>

     These strategies map to the stack provisioning wizard and to <code>axio.yaml</code>:

   </p>

   <div class="code-grid">

     <div class="code-card">

       <h3>Self-hosted by labels</h3>

       <div class="code-block">

         <div class="code-header"><span>yaml</span><span>▣</span></div>

         <pre><code>runner:

 strategy: labels

 labels:

   - linux

   - terraform</code></pre>

       </div>

     </div>

     <div class="code-card">

       <h3>Self-hosted by group</h3>

       <div class="code-block">

         <div class="code-header"><span>yaml</span><span>▣</span></div>

         <pre><code>runner:

 strategy: runner-group

 runnerGroup: production</code></pre>

       </div>

     </div>

     <div class="code-card">

       <h3>Pin to one agent</h3>

       <div class="code-block">

         <div class="code-header"><span>yaml</span><span>▣</span></div>

         <pre><code>runner:

 strategy: specific-runner

 runnerName: prod-runner-1</code></pre>

       </div>

     </div>

     <div class="code-card">

       <h3>Axio-managed (hosted)</h3>

       <div class="code-block">

         <div class="code-header"><span>yaml</span><span>▣</span></div>

         <pre><code>runner:

 strategy: provider-runner

 providerRunner: axio-linux</code></pre>

       </div>

     </div>

   </div>

   <div class="callout info">

     <span class="callout-icon">i</span>

     <p>

       <code>providerRunner: axio-linux</code> and

       <code>labels: \[axio-linux]</code> are equivalent for hosted routing.

       The API also accepts <code>requiredLabels</code> and <code>runnerPreference</code>.

     </p>

   </div>

 </section>

 <div class="two-column">

   <section class="doc-panel">

     <div class="section-heading">

       <span class="section-icon blue">⚙</span>

       <h2>Preference</h2>

     </div>

     <p>Controls whether the scheduler considers self-hosted or provider runners.</p>

     <div class="table-wrap">

       <table>

         <thead>

           <tr>

             <th>Preference</th>

             <th>Behavior</th>

           </tr>

         </thead>

         <tbody>

           <tr>

             <td><code>customer</code></td>

             <td>Self-hosted only</td>

           </tr>

           <tr>

             <td><code>provider</code></td>

             <td>Shared Axio fleet only</td>

           </tr>

           <tr>

             <td><code>automatic</code></td>

             <td>Self-hosted first; hosted if <code>axio-\*</code> labels are present</td>

           </tr>

         </tbody>

       </table>

     </div>

     <div class="callout info">

       <span class="callout-icon">i</span>

       <p><code>runnerPreference: provider</code> is set automatically when hosted labels are present.</p>

     </div>

   </section>

   <section class="doc-panel">

     <div class="section-heading">

       <span class="section-icon green">⌘</span>

       <h2>Scope chain</h2>

     </div>

     <p>

       For customer-hosted work, the scheduler walks

       <strong>environment → project → organization</strong> and only considers

       runners whose group scope covers that resource.

     </p>

     <div class="scope-chain">

       <div class="scope-item environment">

         <span class="scope-icon">◆</span>

         <div>

           <strong>Environment</strong>

           <span>Runners in groups scoped to this environment</span>

         </div>

       </div>

       <div class="scope-arrow">↓</div>

       <div class="scope-item project">

         <span class="scope-icon">■</span>

         <div>

           <strong>Project</strong>

           <span>Runners in groups scoped to this project</span>

         </div>

       </div>

       <div class="scope-arrow">↓</div>

       <div class="scope-item organization">

         <span class="scope-icon">▦</span>

         <div>

           <strong>Organization</strong>

           <span>Runners in groups scoped to this organization</span>

         </div>

       </div>

     </div>

     <div class="callout info">

       <span class="callout-icon">i</span>

       <p>

         A workspace-scoped group is not used by another workspace.

         An organization-scoped group is eligible everywhere in the org

         (subject to labels and capacity).

       </p>

     </div>

   </section>

 </div>

 <div class="two-column bottom-grid">

   <section class="doc-panel eligibility-panel">

     <div class="section-heading">

       <span class="section-icon pink">✓</span>

       <h2>Eligibility checklist</h2>

     </div>

     <p>A runner can take a job only if all of these are true:</p>

     <ol class="checklist">

       <li>Effective status is <code>ONLINE</code> (heartbeat ≤ 90 seconds)</li>

       <li>Not paused, draining, disabled, or in maintenance</li>

       <li>Has a free job slot <code>activeJobs \&lt; maxConcurrentJobs</code></li>

       <li>Labels match</li>

       <li>Group / scope covers the workload</li>

       <li>Version is not <code>BLOCKED</code></li>

       <li>

         For hosted labels: tenant plan has

         <code>providerRunnerAccessEnabled</code> and the fleet has capacity

       </li>

     </ol>

   </section>

   <div class="right-stack">

     <section class="doc-panel auto-panel">

       <div class="section-heading">

         <span class="section-icon pink">ϟ</span>

         <h2>AUTO_SELECT</h2>

       </div>

       <p>

         Some APIs expose <code>AUTO_SELECT</code> as “best available runner” —

         same idea as <code>strategy: automatic</code>.

       </p>

     </section>

     <section class="doc-panel no-match-panel">

       <div class="section-heading">

         <span class="section-icon orange">!</span>

         <h2>When no runner matches</h2>

       </div>

       <p>Deployment/workflow logs typically show:</p>

       <div class="error-box">

         <ul>

           <li><code>No runner is available</code></li>

           <li><code>No hosted runner available for label "axio-linux"</code></li>

           <li>IaC CLI missing on the assigned runner</li>

         </ul>

       </div>

       <p class="links">

         See

         <a href="{{ '/runners/troubleshooting' | relative_url }}">troubleshooting</a>

         and

         <a href="{{ '/runners/iac-requirements' | relative_url }}">IaC requirements</a>.

       </p>

     </section>

   </div>

 </div>

</div>