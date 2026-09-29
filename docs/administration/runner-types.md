---
layout: default
title: Runner types
parent: Runner
nav_order: 13
permalink: /axio/administration/runner/runner-types/ 
---


<link rel="stylesheet" href="{{ '/assets/css/runner-types.css' | relative_url }}">


<div class="runner-doc">

 <h1>Runner types</h1>

 <p class="lead">Axio has two runner categories. They share the same job model; they differ in who owns the machines and what tenants can see.</p>

 <section class="card comparison">

   <table>

     <thead>

       <tr>

         <th>Aspect</th>

         <th><span class="icon purple">▤</span> Self-hosted</th>

         <th><span class="icon blue">☁</span> Provider (Axio-managed)</th>

       </tr>

     </thead>

     <tbody>

       <tr><th>Who provisions</th><td>You</td><td>Platform operator (Axio)</td></tr>

       <tr><th>UI</th><td><code>Administration → Runners</code></td><td>Invisible to tenants.<br><code>Hosted fleet</code> tab in the provider org only.</td></tr>

       <tr><th>How you target</th><td>Your labels and groups</td><td><code>axio-linux</code>, <code>axio-windows</code>, …</td></tr>

       <tr><th>Registration token</th><td><code>axreg_\*</code></td><td><code>axpreg_\*</code> (or internal API)</td></tr>

       <tr><th>Billing</th><td>Your infrastructure</td><td>Metered minutes and storage on the subscription</td></tr>

       <tr><th><code>axio-\*</code> labels</th><td>Never assigned</td><td>Applied automatically</td></tr>

     </tbody>

   </table>

 </section>

 <div class="two-col">

   <section class="card">

     <h2><span class="icon purple">▤</span> Self-hosted</h2>

     <p>Install <code>@axio/runner-core</code> on a VM, Docker host, or Kubernetes cluster. Connections are <strong>outbound-only</strong>.</p>

     <div class="flow">

       <div class="flow-box">

         <strong>Your<br>Infrastructure</strong>

         <span>▣ &nbsp; VM</span>

         <span>◉ &nbsp; Docker host</span>

         <span>✥ &nbsp; Kubernetes cluster</span>

       </div>

       <span class="arrow">→</span>

       <div class="flow-box agent">

         <strong>⚙</strong>

         <code>@axio/<br>runner-core</code>

         <small>Agent</small>

       </div>

       <span class="arrow">→</span>

       <div class="flow-box">

         <strong class="check">✓</strong>

         <strong>Axio</strong>

         <span>Overview inventory</span>

         <span>▤</span>

       </div>

     </div>

     <div class="steps">

       <div><b>1</b><strong>Group</strong><span>Create a runner group in Axio</span></div>

       <div><b>2</b><strong>Registration command</strong><span>Generate and run the command</span></div>

       <div><b>3</b><strong>Agent</strong><span>Registers and starts sending heartbeats</span></div>

       <div><b>4</b><strong>Overview inventory</strong><span>Runner appears in the inventory</span></div>

     </div>

     <div class="info">ⓘ &nbsp; See <a href="#">setup-and-registration</a> and <a href="#">deployment</a> for detailed steps.</div>

   </section>

   <section class="card">

     <h2><span class="icon orange">☁</span> Provider (hosted)</h2>

     <p>Like GitHub-hosted runners. Axio runs a shared fleet in the platform provider organization (seed: <code>anantacloud</code>). Tenants never list those runners, groups, or tokens.</p>

     <div class="flow">

       <div class="flow-box">

         <strong>Customer tenant</strong>

         <span>Select a hosted label on the workload</span>

         <code>axio-linux</code>

         <code>axio-windows</code>

         <span>…</span>

       </div>

       <span class="arrow">→</span>

       <div class="flow-box agent">

         <strong class="cloud">☁</strong>

         <strong>Axio-managed fleet</strong>

         <span>Runs in provider organization</span>

         <small>(anantacloud)</small>

       </div>

       <span class="arrow">→</span>

       <div class="flow-box">

         <strong>▤</strong>

         <strong>Executes</strong>

         <span>IaC jobs</span>

       </div>

     </div>

     <div class="warning">⚠ &nbsp; Customers only pick a hosted label on the workload. Requires <code>providerRunnerAccessEnabled</code> on the plan.</div>

     <p>Operators use Runners → <code>Hosted fleet</code> (or <code>scripts/setup-hosted-runner-fleet.ts</code> locally).</p>

     <div class="info">ⓘ &nbsp; See <a href="#">hosted-fleet</a> for more details.</div>

   </section>

 </div>

 <section class="card scheduling">

   <h2><span class="icon green">▣</span> Scheduling reminder</h2>

   <div class="schedule-row provider-row">

     <strong>☁ &nbsp; Workload with <code>axio-\*</code></strong>

     <span>Runs on provider org fleet.</span>

   </div>

   <div class="schedule-row customer-row">

     <strong>● &nbsp; Workload with customer labels</strong>

     <span>Runs on your inventory, scoped by group.</span>

   </div>

   <div class="schedule-row automatic-row">

     <strong>⚙ &nbsp; <code>automatic</code></strong>

     <span>Tries self-hosted first unless hosted labels force the shared fleet.</span>

   </div>

 </section>

</div>