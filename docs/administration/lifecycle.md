---
layout: default
title: Status and lifecycle
parent: Runner
nav_order: 8
permalink: /axio/administration/runner/lifecycle/
---


<link rel="stylesheet" href="{{ '/assets/css/status-and-lifecycle.css' | relative_url }}">



<div class="status-lifecycle-doc">

 <h1>Status and lifecycle</h1>

 <p class="lead">

   Overview shows a single presence chip per runner (not a separate busy chip).

 </p>

 <section class="doc-panel glance-panel">

   <div class="section-heading">

     <span class="section-icon blue">▣</span>

     <h2>Runner status at a glance</h2>

   </div>

   <div class="status-chips">

     <span class="status-chip idle"><i></i>Idle</span>

     <span class="status-chip running"><i>✣</i>Running 1 job</span>

     <span class="status-chip running"><i>✣</i>Running 3 jobs</span>

     <span class="status-chip offline"><i></i>Offline</span>

     <span class="status-chip pending"><i></i>Pending</span>

     <span class="status-chip maintenance"><i>⌕</i>Maintenance</span>

     <span class="status-chip paused"><i>Ⅱ</i>Paused</span>

     <span class="status-chip draining"><i>◷</i>Draining</span>

     <span class="status-chip disabled"><i>⊘</i>Disabled</span>

   </div>

 </section>

 <section class="doc-panel presence-panel">

   <div class="section-heading">

     <span class="section-icon purple">▤</span>

     <h2>Presence labels</h2>

   </div>

   <div class="table-wrap">

     <table>

       <thead>

         <tr>

           <th>You see</th>

           <th>Stored / computed status</th>

           <th>Meaning</th>

         </tr>

       </thead>

       <tbody>

         <tr>

           <td><span class="status-chip idle"><i></i>Idle</span></td>

           <td><code>ONLINE</code>, no active jobs</td>

           <td>Ready for work</td>

         </tr>

         <tr>

           <td><span class="status-chip running"><i>✣</i>Running 1 job / Running N jobs</span></td>

           <td><code>ONLINE</code>, <code>activeJobs \&gt; 0</code></td>

           <td>Executing</td>

         </tr>

         <tr>

           <td><span class="status-chip offline"><i></i>Offline</span></td>

           <td><code>OFFLINE</code></td>

           <td>No heartbeat for 90 seconds, or agent sent <code>status: OFFLINE</code> on shutdown</td>

         </tr>

         <tr>

           <td><span class="status-chip pending"><i></i>Pending</span></td>

           <td><code>PENDING</code></td>

           <td>Registered but no heartbeat yet</td>

         </tr>

         <tr>

           <td><span class="status-chip maintenance"><i>⌕</i>Maintenance</span></td>

           <td><code>MAINTENANCE</code></td>

           <td>Admin put the runner in maintenance</td>

         </tr>

         <tr>

           <td><span class="status-chip paused"><i>Ⅱ</i>Paused</span></td>

           <td><code>PAUSED</code></td>

           <td>Same idea as maintenance (legacy label)</td>

         </tr>

         <tr>

           <td><span class="status-chip draining"><i>◷</i>Draining</span></td>

           <td><code>DRAINING</code></td>

           <td>Current jobs may finish; no new leases</td>

         </tr>

         <tr>

           <td><span class="status-chip disabled"><i>⊘</i>Disabled</span></td>

           <td><code>DISABLED</code></td>

           <td>Hard-blocked from scheduling</td>

         </tr>

       </tbody>

     </table>

   </div>

   <div class="callout info">

     <span class="callout-icon">i</span>

     <p>

       ONLINE does not mean “the process in my terminal is still running.”

       It means a valid <code>axrun_\*</code> token sent a heartbeat (or log ingest)

       within 90 seconds.

     </p>

   </div>

 </section>

 <div class="two-column">

   <section class="doc-panel online-panel">

     <div class="section-heading">

       <span class="section-icon green">⚙</span>

       <h2>How ONLINE / OFFLINE is computed</h2>

     </div>

     <ol class="numbered-list">

       <li>If status is <code>DISABLED</code>, <code>PAUSED</code>, <code>MAINTENANCE</code>, or <code>DRAINING</code> → show that.</li>

       <li>Else if the last heartbeat payload said <code>OFFLINE</code> → Offline immediately.</li>

       <li>Else if there is no <code>lastHeartbeatAt</code> → Pending.</li>

       <li>Else if heartbeat is ≤ 90 seconds old → Online (Idle or Running).</li>

       <li>Else → Offline.</li>

     </ol>

     <div class="callout info">

       <span class="callout-icon">i</span>

       <p>

         Default agent heartbeat interval is about 10 seconds. Restarting the API or UI

         does not reset these rows — they live in PostgreSQL.

       </p>

     </div>

   </section>

   <section class="doc-panel stop-panel">

     <div class="section-heading">

       <span class="section-icon red">⏻</span>

       <h2>Graceful stop vs hard kill</h2>

     </div>

     <div class="table-wrap">

       <table>

         <thead>

           <tr>

             <th>Stop</th>

             <th>What the UI does</th>

           </tr>

         </thead>

         <tbody>

           <tr>

             <td><strong>SIGTERM / Ctrl+C / systemd stop</strong></td>

             <td>Agent sends a final <code>OFFLINE</code> heartbeat. UI shows Offline right away. Row stays registered by default.</td>

           </tr>

           <tr>

             <td><strong>SIGKILL / power loss</strong></td>

             <td>No final heartbeat. UI shows Offline after ~90 seconds.</td>

           </tr>

         </tbody>

       </table>

     </div>

     <div class="sub-panel">

       <div class="sub-heading">

         <span class="sub-icon blue">●</span>

         <h3>Deregister on shutdown</h3>

       </div>

       <p>

         Default: the runner stays registered so the same <code>axrun_\*</code> token

         works on restart.

       </p>

       <p>

         If the group’s internal pool has <code>deregisterOnShutdown: true</code>,

         a graceful stop calls <code>POST /runner-agent/deregister</code> and deletes

         the row. Use this for ephemeral CI runners, not long-lived systemd services.

       </p>

     </div>

   </section>

 </div>

 <div class="two-column lower-grid">

   <section class="doc-panel admin-panel">

     <div class="section-heading">

       <span class="section-icon purple">⚒</span>

       <h2>Admin actions</h2>

     </div>

     <div class="table-wrap">

       <table>

         <thead>

           <tr>

             <th>Action</th>

             <th>Result</th>

           </tr>

         </thead>

         <tbody>

           <tr>

             <td><strong>Enter maintenance</strong></td>

             <td>Status → Maintenance. No new jobs.</td>

           </tr>

           <tr>

             <td><strong>Resume / Exit maintenance / Stop draining</strong></td>

             <td>Back to Online when heartbeats are fresh.</td>

           </tr>

           <tr>

             <td><strong>Drain</strong></td>

             <td>Status → Draining. Finish in-flight jobs; accept none.</td>

           </tr>

           <tr>

             <td><strong>Disable</strong></td>

             <td>Status → Disabled. Blocked until Enable.</td>

           </tr>

           <tr>

             <td><strong>Enable</strong></td>

             <td>Clears Disabled.</td>

           </tr>

           <tr>

             <td><strong>Disconnect</strong></td>

             <td>Deletes the row. Agent must re-register with a new <code>axreg_\*</code> command.</td>

           </tr>

         </tbody>

       </table>

     </div>

     <div class="callout warning">

       <span class="callout-icon">!</span>

       <p>

         Disconnect is permanent for that identity. If the process is still running,

         stop it so it does not confuse operators.

       </p>

     </div>

   </section>

   <div class="right-stack">

     <section class="doc-panel crash-panel">

       <div class="section-heading">

         <span class="section-icon green">⌁</span>

         <h2>Busy after a crash</h2>

       </div>

       <p>If a runner stays <strong>Running</strong> after the process died:</p>

       <ol class="numbered-list compact">

         <li>Wait ~15 seconds for stale-busy reconcile.</li>

         <li>If an execution lease is still active, wait up to ~3 minutes.</li>

         <li>Cancel the stuck deployment/workflow if needed, or restart the agent so heartbeats reset <code>activeJobs</code>.</li>

       </ol>

       <div class="callout info">

         <span class="callout-icon">i</span>

         <p>

           Managed (autoscaled) runners that crash without deregistering can be reclaimed

           after ~180 seconds.

         </p>

       </div>

     </section>

     <section class="doc-panel stale-panel">

       <div class="section-heading">

         <span class="section-icon red">▥</span>

         <h2>Stale offline rows</h2>

       </div>

       <p>

         Use <strong>Remove offline runners</strong> or the offline cleanup policy.

         The agent must re-register to come back.

       </p>

     </section>

     <section class="doc-panel more-panel">

       <div class="section-heading">

         <span class="section-icon purple">▣</span>

         <h2>More information</h2>

       </div>

       <p>

         Deep dive:

         <a href="{{ '/runners/status-and-troubleshooting' | relative_url }}">

           RUNNER_STATUS_AND_TROUBLESHOOTING

         </a>.

       </p>

     </section>

   </div>

 </div>

</div>