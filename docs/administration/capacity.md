---
layout: default
title: Capacity and concurrent jobs
parent: Runner
nav_order: 10
permalink: /axio/administration/runner/capacity/
---


<link rel="stylesheet" href="{{ '/assets/css/capacity-and-concurrent-jobs.css' | relative_url }}">


<div class="capacity-doc">

 <h1>Capacity and concurrent jobs</h1>

 <p class="lead">

   Capacity is how many IaC jobs one agent executes at the same time. The Overview

   Utilization metric is the share of online runners that currently have at least one job.

 </p>

 <div class="summary-grid">

   <div class="metric-card">

     <span class="metric-icon green">♣</span>

     <div><span>Total runners</span><strong>12</strong></div>

   </div>

   <div class="metric-card">

     <span class="metric-icon green">●</span>

     <div><span>Online</span><strong>10</strong></div>

   </div>

   <div class="metric-card">

     <span class="metric-icon blue">●</span>

     <div><span>Running</span><strong>7 <small>Utilization: 70%</small></strong></div>

   </div>

   <div class="metric-card">

     <span class="metric-icon purple">●</span>

     <div><span>Idle</span><strong>3</strong></div>

   </div>

 </div>

 <div class="two-column">

   <section class="doc-panel capacity-panel">

     <div class="section-heading">

       <span class="section-icon blue">⚙</span>

       <h2>How capacity works</h2>

     </div>

     <p>

       Each runner can execute multiple IaC jobs in parallel, up to its

       <code>maxConcurrentJobs</code> limit. The scheduler assigns a new job to a

       runner only if <code>activeJobs &lt; maxConcurrentJobs</code>.

     </p>

     <div class="capacity-flow">

       <div class="queue">

         <h3>Jobs in queue</h3>

         <div class="queue-item">▧ &nbsp; Job 1</div>

         <div class="queue-item">▧ &nbsp; Job 2</div>

         <div class="queue-item">▧ &nbsp; Job 3</div>

       </div>

       <div class="flow-arrow">→</div>

       <div class="runner-box">

         <div class="runner-icon">▰</div>

         <strong>Runner</strong>

         <small>(maxConcurrentJobs = 3)</small>

         <div class="job running-green">⚙ &nbsp; Running Job 1</div>

         <div class="job running-blue">⚙ &nbsp; Running Job 2</div>

         <div class="job running-purple">⚙ &nbsp; Running Job 3</div>

       </div>

       <div class="flow-arrow">→</div>

       <div class="parallel-box">

         <span>✓</span>

         <p>All jobs run<br>in parallel<br>(up to limit)</p>

       </div>

     </div>

   </section>

   <section class="doc-panel">

     <div class="section-heading">

       <span class="section-icon purple">▤</span>

       <h2>Per-runner limit</h2>

     </div>

     <div class="table-wrap">

       <table>

         <thead><tr><th>Constant</th><th>Value</th></tr></thead>

         <tbody>

           <tr><td>Minimum <code>maxConcurrentJobs</code></td><td>1</td></tr>

           <tr><td>Maximum</td><td>100</td></tr>

         </tbody>

       </table>

     </div>

     <p>

       The control plane scheduler and the agent both honor this value.

       Organization plans can impose a lower cap; the edit dialog helper text shows

       <code>Organization limit: N</code> when one exists.

     </p>

     <div class="callout info">

       <span class="callout-icon">i</span>

       <p>

         Kubernetes agents often register with <code>maxConcurrentJobs: 50</code>

         (<code>AXIO_RUNNER_MAX_CONCURRENT_JOBS</code> to override).

       </p>

     </div>

     <div class="callout warning">

       <span class="callout-icon">!</span>

       <p>

         If inventory still shows “Running 1 job” at 1/1 after you expected more

         parallelism, the row may be on an older image or a stuck <code>RUNNING</code>

         workload. Cancel the run or restart the agent so heartbeats reconcile

         <code>activeJobs</code>.

       </p>

     </div>

   </section>

 </div>

 <div class="two-column">

   <section class="doc-panel full-panel">

     <div class="section-heading">

       <span class="section-icon purple">⌁</span>

       <h2>When a runner is “full”</h2>

     </div>

     <p>

       The scheduler treats a runner as busy when

       <code>activeJobs &gt;= maxConcurrentJobs</code>. That agent will not receive

       another lease until a job completes.

     </p>

     <div class="capacity-example">

       <div class="example-title">Example (maxConcurrentJobs = 2)</div>

       <div class="example-row">

         <span class="dot green"></span>

         <span>Running 2 jobs (2/2)</span>

         <b class="badge full">Full</b>

       </div>

       <div class="example-row">

         <span class="dot blue"></span>

         <span>Running 1 job (1/2)</span>

         <b class="badge not-full">Not full</b>

       </div>

       <div class="example-row">

         <span class="dot green"></span>

         <span>Idle (0/2)</span>

         <b class="badge available">Available</b>

       </div>

     </div>

     <p>

       Overview <code>Running</code> counts those busy online runners.

       <code>Idle</code> is online with zero active jobs.

     </p>

   </section>

   <section class="doc-panel">

     <div class="section-heading">

       <span class="section-icon green">♣</span>

       <h2>Fleet size</h2>

     </div>

     <div class="table-wrap">

       <table>

         <thead><tr><th>Scope</th><th>Description</th></tr></thead>

         <tbody>

           <tr>

             <td><strong>Group maxRunners</strong></td>

             <td>Optional cap on self-hosted agents in that group.</td>

           </tr>

           <tr>

             <td><strong>Plan maxCustomerRunners</strong></td>

             <td>Org-wide cap on customer-hosted agents.</td>

           </tr>

           <tr>

             <td><strong>Hosted fleet</strong></td>

             <td>

               Tenant minutes/storage limits

               (<code>maxProviderExecutionMinutes</code>,

               <code>maxProviderStorageBytes</code>), not a visible runner count.

             </td>

           </tr>

         </tbody>

       </table>

     </div>

     <div class="callout info">

       <span class="callout-icon">i</span>

       <p>

         Autoscaling (<code>AUTO</code> / <code>SCHEDULED</code> on the runner

         platform) mints tokens and launches infrastructure up to

         <code>maxRunners</code> on the internal pool. Manual Setup registration

         ignores that provisioner until you enable it.

       </p>

     </div>

     <p class="small-note">

       See <a href="{{ '/runners/deployment' | relative_url }}">deployment</a>

       and <a href="{{ '/runners/runner-deployment' | relative_url }}">RUNNER_DEPLOYMENT</a>.

     </p>

   </section>

 </div>

 <div class="two-column bottom-grid">

   <section class="doc-panel">

     <div class="section-heading">

       <span class="section-icon pink">↻</span>

       <h2>Lifecycle modes (internal pool)</h2>

     </div>

     <div class="table-wrap">

       <table>

         <thead><tr><th>Mode</th><th>Behavior</th></tr></thead>

         <tbody>

           <tr><td><code>PERSISTENT</code></td><td>Stay registered until you remove or scale down.</td></tr>

           <tr><td><code>EPHEMERAL</code></td><td>Idle managed runners terminate on scale-down.</td></tr>

           <tr><td><code>DYNAMIC</code></td><td>One runner per queued job (up to <code>maxRunners</code>).</td></tr>

         </tbody>

       </table>

     </div>

     <h3 class="subsection-title">Ephemeral assignment</h3>

     <div class="table-wrap">

       <table>

         <thead><tr><th>Scope</th><th>Behavior</th></tr></thead>

         <tbody>

           <tr><td><code>JOB</code> (default)</td><td>One ephemeral runner per job.</td></tr>

           <tr><td><code>WORKFLOW</code></td><td>Same runner for all workloads that share <code>workflowRunId</code>.</td></tr>

         </tbody>

       </table>

     </div>

     <div class="callout info">

       <span class="callout-icon">i</span>

       <p>

         These are pool/policy settings, not Overview columns. Tenants usually run

         persistent self-hosted agents from Setup.

       </p>

     </div>

   </section>

   <section class="doc-panel utilization-panel">

     <div class="section-heading">

       <span class="section-icon red">●</span>

       <h2>Utilization alerts</h2>

     </div>

     <p>

       Utilization above <strong>85%</strong> is highlighted on the overview chip.

       Add runners, raise <code>maxConcurrentJobs</code> (if the host can take it),

       or move work to hosted labels.

     </p>

     <div class="utilization-card">

       <div class="utilization-meter">

         <div class="meter-arc"></div>

         <strong>92%</strong>

         <span>7 of 10 runners busy</span>

       </div>

       <div class="high-alert">

         <span>!</span>

         <div>

           <strong>High utilization</strong>

           <p>

             Utilization is above 85%. Consider adding runners, raising

             <code>maxConcurrentJobs</code>, or using hosted labels.

           </p>

         </div>

       </div>

     </div>

   </section>

 </div>

</div>