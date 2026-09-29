---
layout: default
title: Labels
parent: Runner
nav_order: 6
permalink: /axio/administration/runner/labels/
---


<link rel="stylesheet" href="{{ '/assets/css/labels.css' | relative_url }}">


<div class="labels-doc">

 <h1>Labels</h1>

 <p class="lead">

   Labels decide which runner a workload can use. They work like GitHub Actions

   <code>runs-on</code> labels.

 </p>

 <section class="flow-banner">

   <div class="flow-card">

     <div class="flow-icon blue">▤</div>

     <div>

       <h2>Workload</h2>

       <pre><code>runs-on:

 - linux

 - terraform</code></pre>

     </div>

   </div>

   <div class="flow-arrow">→</div>

   <div class="scheduler">

     <div class="scheduler-icon">⚙</div>

     <strong>Scheduler</strong>

     <span>Matches required<br>labels with<br>runners</span>

   </div>

   <div class="flow-arrow">→</div>

   <div class="flow-card">

     <div class="flow-icon purple">▤</div>

     <div>

       <h2>Runner</h2>

       <div class="chips">

         <span class="chip blue">linux</span>

         <span class="chip green">terraform</span>

         <span class="chip purple">gpu</span>

       </div>

       <div class="eligible"><span></span> Eligible to run</div>

     </div>

   </div>

 </section>

 <div class="two-column">

   <section class="panel">

     <div class="panel-heading">

       <span class="panel-icon blue">●●</span>

       <h2>Customer labels (self-hosted)</h2>

     </div>

     <p>

       You choose these at registration or later from <strong>Overview</strong>.

     </p>

     <div class="examples-box">

       <strong>Examples:</strong>

       <div class="chips">

         <span class="chip blue">linux</span>

         <span class="chip green">terraform</span>

         <span class="chip purple">gpu</span>

         <span class="chip blue">production</span>

         <span class="chip blue">eu-west</span>

       </div>

     </div>

     <h3>Rules:</h3>

     <ul>

       <li>Editable from the inventory Labels column, <strong>Edit labels &amp; group</strong>, or <strong>Bulk update labels</strong>.</li>

       <li>Cannot use the reserved <code>axio-</code> prefix.</li>

       <li>Comma-separated on the Setup form; the add-label popover accepts a single label only.</li>

     </ul>

     <div class="callout danger">

       <span class="callout-icon">!</span>

       <p>Self-hosted runners never receive <code>axio-\*</code> labels.</p>

     </div>

   </section>

   <section class="panel">

     <div class="panel-heading">

       <span class="panel-icon purple">♛</span>

       <h2>Reserved labels (axio-\*)</h2>

     </div>

     <p>

       The <code>axio-</code> prefix is globally reserved for Axio-managed (provider) runners.

     </p>

     <div class="table-wrap">

       <table>

         <thead>

           <tr>

             <th>Label</th>

             <th>Typical use</th>

           </tr>

         </thead>

         <tbody>

           <tr><td><code>axio-linux</code></td><td>Linux VM</td></tr>

           <tr><td><code>axio-linux-x86</code> / <code>axio-linux-arm64</code></td><td>Architecture</td></tr>

           <tr><td><code>axio-windows</code></td><td>Windows VM</td></tr>

           <tr><td><code>axio-docker</code></td><td>Docker host</td></tr>

           <tr><td><code>axio-kubernetes</code></td><td>Kubernetes</td></tr>

           <tr><td><code>axio-gpu</code></td><td>GPU</td></tr>

           <tr><td><code>axio-provider</code></td><td>Marker that the runner is on the shared fleet</td></tr>

         </tbody>

       </table>

     </div>

     <div class="callout warning">

       <span class="callout-icon">!</span>

       <p>

         Tenants reference these on stacks and workflows. They cannot create,

         rename, assign, or import <code>axio-\*</code> on self-hosted runners or groups.

       </p>

     </div>

   </section>

 </div>

 <div class="two-column">

   <section class="panel">

     <div class="panel-heading">

       <span class="panel-icon blue">⚙</span>

       <h2>Where labels are set</h2>

     </div>

     <div class="table-wrap">

       <table>

         <thead>

           <tr>

             <th>Place</th>

             <th>What you can set</th>

           </tr>

         </thead>

         <tbody>

           <tr>

             <td><strong>Setup → Register</strong></td>

             <td>Optional comma-separated list on the install command</td>

           </tr>

           <tr>

             <td><strong>Overview → label chips</strong></td>

             <td>Add / delete one label</td>

           </tr>

           <tr>

             <td><strong>Overview → Edit labels &amp; group</strong></td>

             <td>Full replace + move group</td>

           </tr>

           <tr>

             <td><strong>Overview → Bulk update labels</strong></td>

             <td>Add or replace on the selection</td>

           </tr>

           <tr>

             <td><strong>Hosted fleet</strong></td>

             <td>System labels on the hosted group (<code>axio-linux</code>, …)</td>

           </tr>

           <tr>

             <td><strong>axio.yaml / stack wizard</strong></td>

             <td>Required labels for scheduling — not assigned to the runner</td>

           </tr>

         </tbody>

       </table>

     </div>

   </section>

   <section class="panel">

     <div class="panel-heading">

       <span class="panel-icon green">☷</span>

       <h2>Matching</h2>

     </div>

     <p>

       The scheduler matches workload <code>requiredLabels</code> /

       <code>labels</code> against the runner’s labels (customer) or

       <code>systemLabels</code> (provider fleet).

     </p>

     <ol class="numbered-list">

       <li>All required labels must be present on the runner.</li>

       <li>Extra labels on the runner are fine.</li>

       <li><code>axio-\*</code> on a workload routes to the platform provider org fleet, not your self-hosted inventory.</li>

     </ol>

     <div class="callout info">

       <span class="callout-icon">i</span>

       <p>See <a href="{{ '/runners/targeting' | relative_url }}">Targeting</a> for more details.</p>

     </div>

   </section>

 </div>

 <div class="two-column bottom-row">

   <section class="panel">

     <div class="panel-heading">

       <span class="panel-icon pink">⌕</span>

       <h2>Filtering inventory</h2>

     </div>

     <p>Shows online runners that have <code>terraform</code>.</p>

     <div class="table-wrap">

       <table class="inventory-table">

         <thead>

           <tr>

             <th>Name</th>

             <th>Group</th>

             <th>Labels</th>

             <th>Status</th>

           </tr>

         </thead>

         <tbody>

           <tr>

             <td>prod-runner-1</td>

             <td>prod</td>

             <td>

               <span class="chip blue">linux</span>

               <span class="chip green">terraform</span>

             </td>

             <td><span class="online"><span></span> Online</span></td>

           </tr>

           <tr>

             <td>gpu-runner-2</td>

             <td>prod</td>

             <td>

               <span class="chip purple">gpu</span>

               <span class="chip green">terraform</span>

             </td>

             <td><span class="online"><span></span> Online</span></td>

           </tr>

         </tbody>

       </table>

     </div>

   </section>

   <section class="panel">

     <div class="panel-heading">

       <span class="panel-icon shield">♜</span>

       <h2>Validation</h2>

     </div>

     <p>

       All APIs, registration, heartbeat, bulk assign, and Platform-as-Code imports

       go through the same reserved-label rules. A self-hosted register or patch

       that includes <code>axio-\*</code> is rejected.

     </p>

     <div class="validation-error">

       <span class="error-icon">!</span>

       <div>

         <strong>Validation error</strong>

         <p>

           Labels with prefix <code>axio-</code> are reserved and cannot be assigned

           to self-hosted runners.

         </p>

       </div>

     </div>

   </section>

 </div>

</div>