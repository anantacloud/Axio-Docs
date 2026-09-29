---
layout: default
title: Offline runner cleanup
parent: Runner
nav_order: 12
permalink: /axio/administration/runner/offline-cleanup/ 
---


<link rel="stylesheet" href="{{ '/assets/css/offline-runner-cleanup.css' | relative_url }}">


<div class="offline-cleanup-doc">

 <h1>Offline runner cleanup</h1>

 <p class="lead">

   The Offline runner cleanup panel sits on <strong>Overview</strong> for users with

   <strong>manage</strong> permission. It removes runners that stay OFFLINE

   (no heartbeat) longer than a retention period so crashed CI agents and replaced

   VMs do not clutter inventory.

 </p>

 <section class="doc-section cleanup-overview">

   <div class="section-title">

     <span class="section-icon red">▥</span>

     <div>

       <h2>Offline runner cleanup (Overview)</h2>

       <p>

         This panel lets you configure automatic cleanup and shows a preview of

         runners that will be removed on the next cleanup run.

       </p>

     </div>

   </div>

   <div class="overview-grid">

     <div class="cleanup-settings">

       <div class="setting-row">

         <span class="toggle on"><span></span></span>

         <div>

           <strong>Enable automatic cleanup</strong>

           <p>Automatically remove runners that have been offline for a specified number of days.</p>

         </div>

       </div>

       <label class="field-label" for="offline-days">Days offline before removal</label>

       <div class="number-row">

         <div class="number-input">

           <span>30</span>

           <span class="spinner">↕</span>

         </div>

         <span>days (1 – 365)</span>

       </div>

       <p class="helper">Runners offline for more than this number of days will be removed.</p>

       <div class="info-note">

         <span class="note-icon">i</span>

         <span>Runners with active jobs are never removed, even if they look offline.</span>

       </div>

     </div>

     <div class="preview">

       <div class="subheading">

         <span class="search-icon">⌕</span>

         <div>

           <h3>Next cleanup preview</h3>

           <p>

             12 runners will be removed on the next cleanup run

             (these runners have been offline for more than 30 days).

           </p>

         </div>

       </div>

       <table>

         <thead>

           <tr>

             <th>Runner name</th>

             <th>Offline since</th>

           </tr>

         </thead>

         <tbody>

           <tr><td>ci-runner-1</td><td>2026-07-10&nbsp; (45 days)</td></tr>

           <tr><td>dev-runner-2</td><td>2026-07-08&nbsp; (47 days)</td></tr>

           <tr><td>k8s-runner-3</td><td>2026-06-28&nbsp; (57 days)</td></tr>

           <tr><td>win-runner-4</td><td>2026-06-20&nbsp; (65 days)</td></tr>

           <tr><td>test-runner-5</td><td>2026-06-18&nbsp; (67 days)</td></tr>

         </tbody>

       </table>

     </div>

   </div>

 </section>

 <section class="doc-section">

   <div class="section-title">

     <span class="section-icon purple">⚙</span>

     <div>

       <h2>Policy</h2>

       <p>Configure when offline runners should be automatically removed.</p>

     </div>

   </div>

   <table>

     <thead>

       <tr>

         <th>Setting</th>

         <th>Range</th>

         <th>Default</th>

       </tr>

     </thead>

     <tbody>

       <tr>

         <td><strong>Enable automatic cleanup</strong></td>

         <td>on / off</td>

         <td>off</td>

       </tr>

       <tr>

         <td><strong>Days offline before removal</strong></td>

         <td>1 – 365</td>

         <td>30</td>

       </tr>

     </tbody>

   </table>

   <div class="notice info">

     <span class="notice-icon">i</span>

     <span>Runners with active jobs are never removed, even if they look offline.</span>

   </div>

   <div class="notice warning">

     <span class="notice-icon">!</span>

     <span>

       When auto-cleanup is on, the panel previews how many runners the next job

       would delete and lists their names.

     </span>

   </div>

 </section>

 <section class="doc-section">

   <div class="section-title">

     <span class="section-icon red">▥</span>

     <div>

       <h2>Manual remove</h2>

       <p>Remove offline runners immediately without waiting for the scheduled cleanup job.</p>

     </div>

   </div>

   <div class="steps">

     <div class="step">

       <span class="step-number">1</span>

       <h3>Filter or select</h3>

       <p>Filter Overview to <code>Offline</code>, or select specific offline rows.</p>

       <div class="mock-control">

         <strong>Status</strong>

         <div><span class="offline-dot"></span> Offline <span class="chevron">⌄</span></div>

       </div>

     </div>

     <div class="step-arrow">→</div>

     <div class="step">

       <span class="step-number">2</span>

       <h3>Click remove</h3>

       <p>Click Remove offline runners (N).</p>

       <div class="remove-action">▥ &nbsp; Remove offline runners (N)</div>

     </div>

     <div class="step-arrow">→</div>

     <div class="step">

       <span class="step-number">3</span>

       <h3>Confirm</h3>

       <p>Confirm the removal in the dialog.</p>

       <div class="confirm-box">

         <strong>Remove 5 offline runners?</strong>

         <div>

           <button>Cancel</button>

           <button class="remove-button">Remove</button>

         </div>

       </div>

     </div>

     <div class="step-arrow">→</div>

     <div class="step">

       <span class="step-number">4</span>

       <h3>Re-register</h3>

       <p>Agents must re-register with a new command to reconnect.</p>

       <pre><code>$ axioctl runner register

 --name my-runner</code></pre>

     </div>

   </div>

   <div class="notice info">

     <span class="notice-icon">i</span>

     <span>

       Online or non-offline selections are skipped. Disconnect from the row menu

       is the same delete for a single runner.

     </span>

   </div>

 </section>

 <section class="doc-section related-section">

   <div class="section-title">

     <span class="section-icon purple">↗</span>

     <div>

       <h2>Related</h2>

     </div>

   </div>

   <div class="related-grid">

     <article>

       <span class="related-icon green">✓</span>

       <div>

         <h3>Graceful stop</h3>

         <p>Keeps the row unless <a href="#">deregister on shutdown</a> is enabled.</p>

       </div>

     </article>

     <article>

       <span class="related-icon red">×</span>

       <div>

         <h3>Hard kill</h3>

         <p>Becomes Offline after ~90 seconds, then sits until cleanup or manual remove.</p>

       </div>

     </article>

     <article>

       <span class="related-icon purple">⚙</span>

       <div>

         <h3>Autoscaled managed runners</h3>

         <p>Can also be reclaimed after ~180 seconds by the provisioner.</p>

       </div>

     </article>

   </div>

 </section>

</div>