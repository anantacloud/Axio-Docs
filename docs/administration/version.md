---
layout: default
title: Runner versions
parent: Runner
nav_order: 11
permalink: /axio/administration/runner/version/
---



<link rel="stylesheet" href="{{ '/assets/css/runner-versions.css' | relative_url }}">


<div class="runner-versions-doc">

 <h1>Runner versions</h1>

 <p class="lead">

   Each agent reports a version on heartbeat. Overview shows it with optional chips.

 </p>

 <div class="summary-grid">

   <div class="metric-card">

     <span class="metric-icon green">♣</span>

     <div><span>Total runners</span><strong>12</strong></div>

   </div>

   <div class="metric-card">

     <span class="metric-icon blue">⬡</span>

     <div><span>Current</span><strong>8</strong></div>

   </div>

   <div class="metric-card">

     <span class="metric-icon orange">⬆</span>

     <div><span>Outdated</span><strong>3</strong></div>

   </div>

   <div class="metric-card">

     <span class="metric-icon pink">⊘</span>

     <div><span>Blocked</span><strong>1</strong></div>

   </div>

 </div>

 <div class="two-column">

   <section class="doc-panel">

     <div class="section-heading">

       <span class="section-icon purple">◆</span>

       <h2>Version chips</h2>

     </div>

     <p>Overview shows the runner version with optional chips:</p>

     <div class="table-wrap">

       <table>

         <thead>

           <tr><th>Chip</th><th>Meaning</th></tr>

         </thead>

         <tbody>

           <tr>

             <td><span class="chip blue-chip">update</span></td>

             <td>A newer target version is available <code>updateAvailable</code>.</td>

           </tr>

           <tr>

             <td><span class="chip yellow-chip">deprecated</span></td>

             <td>Version is in the deprecation window; tooltip may show days until blocked.</td>

           </tr>

           <tr>

             <td><span class="chip red-chip">blocked</span></td>

             <td>Unsupported — runner will not accept new workloads.</td>

           </tr>

         </tbody>

       </table>

     </div>

   </section>

   <section class="doc-panel">

     <div class="section-heading">

       <span class="section-icon green">⌁</span>

       <h2>Example in Overview</h2>

     </div>

     <div class="table-wrap">

       <table class="overview-table">

         <thead>

           <tr><th>Runner</th><th>Version</th><th>Status</th></tr>

         </thead>

         <tbody>

           <tr>

             <td>prod-runner-1</td>

             <td><code>2.3.1</code> <span class="chip blue-chip">update</span></td>

             <td><span class="status"><i class="green-dot"></i>CURRENT</span></td>

           </tr>

           <tr>

             <td>dev-runner-2</td>

             <td><code>2.2.0</code> <span class="chip yellow-chip">deprecated</span></td>

             <td><span class="status"><i class="orange-dot"></i>DEPRECATED</span></td>

           </tr>

           <tr>

             <td>k8s-runner-3</td>

             <td><code>1.9.0</code> <span class="chip red-chip">blocked</span></td>

             <td><span class="status"><i class="red-dot"></i>BLOCKED</span></td>

           </tr>

           <tr>

             <td>ci-runner-4</td>

             <td><code>2.3.1</code></td>

             <td><span class="status"><i class="green-dot"></i>CURRENT</span></td>

           </tr>

           <tr>

             <td>win-runner-5</td>

             <td><code>2.1.5</code></td>

             <td><span class="status"><i class="blue-dot"></i>SUPPORTED</span></td>

           </tr>

         </tbody>

       </table>

     </div>

   </section>

 </div>

 <div class="two-column">

   <section class="doc-panel">

     <div class="section-heading">

       <span class="section-icon blue">▤</span>

       <h2>Lifecycle statuses</h2>

     </div>

     <div class="table-wrap">

       <table>

         <thead>

           <tr><th>Status</th><th>Scheduling</th></tr>

         </thead>

         <tbody>

           <tr><td><span class="status-chip current">CURRENT</span></td><td>Latest recommended</td></tr>

           <tr><td><span class="status-chip supported">SUPPORTED</span></td><td>Still allowed</td></tr>

           <tr><td><span class="status-chip deprecated">DEPRECATED</span></td><td>Allowed, but upgrade soon</td></tr>

           <tr><td><span class="status-chip blocked">BLOCKED</span></td><td>Maintenance — no new workloads</td></tr>

           <tr><td><span class="status-chip unknown">UNKNOWN</span></td><td>Version not in the catalog</td></tr>

         </tbody>

       </table>

     </div>

   </section>

   <section class="doc-panel">

     <div class="section-heading">

       <span class="section-icon pink">⚑</span>

       <h2>App banner</h2>

     </div>

     <p>

       The app banner (<strong>N runners blocked</strong> / upgrade notice) links to

       <code>/admin/runners?filter=outdated</code>. The Overview

       <code>Outdated</code> metric uses the same set.

     </p>

     <div class="alert red-alert">

       <span class="alert-icon">▲</span>

       <div>

         <strong>1 runner blocked</strong>

         <p>Some runners are on unsupported versions and will not accept new workloads.</p>

       </div>

       <button type="button">View runners</button>

       <span class="close">×</span>

     </div>

   </section>

 </div>

 <div class="two-column">

   <section class="doc-panel">

     <div class="section-heading">

       <span class="section-icon purple">⚙</span>

       <h2>Auto-update channels</h2>

     </div>

     <p>

       Self-hosted Linux packages support signed auto-update channels

       <code>stable</code>, <code>preview</code>, <code>nightly</code>, <code>lts</code>

       in <code>config.yaml</code>. Docker and Kubernetes fleets usually roll the

       image tag instead.

     </p>

     <div class="callout info">

       <span class="callout-icon">i</span>

       <p>

         See <a href="{{ '/runners/runner-enterprise' | relative_url }}">RUNNER_ENTERPRISE</a>

         and <a href="{{ '/runners/runner-release' | relative_url }}">RUNNER_RELEASE</a>

         for more details.

       </p>

     </div>

   </section>

   <section class="doc-panel">

     <div class="section-heading">

       <span class="section-icon green">✓</span>

       <h2>What to do</h2>

     </div>

     <ol class="steps">

       <li>Open Overview → filter <code>Outdated</code>.</li>

       <li>Rebuild or restart agents on the new <code>@axio/runner-core</code> image / release tarball.</li>

       <li>Confirm Version matches <code>runner/package.json</code> (or the GHCR tag you deployed).</li>

       <li>Dismiss the banner after the fleet is current.</li>

     </ol>

   </section>

 </div>

 <div class="two-column">

   <section class="doc-panel">

     <div class="section-heading">

       <span class="section-icon pink">◆</span>

       <h2>Release artifacts</h2>

     </div>

     <div class="table-wrap">

       <table>

         <thead><tr><th>Asset</th><th>Example</th></tr></thead>

         <tbody>

           <tr>

             <td><strong>Linux tarball</strong></td>

             <td><code>runner-linux-x64.tar.gz</code> / <code>runner-linux-arm64.tar.gz</code></td>

           </tr>

           <tr>

             <td><strong>Windows zip</strong></td>

             <td><code>runner-windows-x64.zip</code></td>

           </tr>

           <tr>

             <td><strong>macOS</strong></td>

             <td><code>runner-macos-arm64.tar.gz</code></td>

           </tr>

           <tr>

             <td><strong>Images</strong></td>

             <td><code>ghcr.io/anantacloud-oss/runner-core:&lt;version&gt;</code></td>

           </tr>

           <tr>

             <td><strong>K8s manifest</strong></td>

             <td><code>kubernetes/runner-deployment.yaml</code> on tag <code>v\*</code></td>

           </tr>

         </tbody>

       </table>

     </div>

     <div class="callout warning">

       <span class="callout-icon">!</span>

       <p>

         Tag <code>vX.Y.Z</code> must match <code>runner/package.json</code>.

         Control plane env <code>RUNNER_ARTIFACT_BASE_URL</code> and

         <code>RUNNER_IMAGE</code> are what Setup embeds in install commands.

       </p>

     </div>

   </section>

   <section class="doc-panel">

     <div class="section-heading">

       <span class="section-icon purple">&lt;/&gt;</span>

       <h2>Build locally</h2>

     </div>

     <div class="code-block">

       <div class="code-header">

         <span>bash</span><span>▢</span>

       </div>

       <pre><code>npm run build:runner

\# or

npm run build --workspace=@axio/api-contracts

npm run build --workspace=@axio/runner-core

npm test --workspace=@axio/runner-core</code></pre>

     </div>

     <div class="callout info">

       <span class="callout-icon">i</span>

       <p>

         <code>@axio/api-contracts</code> must be built first; runner-core tests

         import it from <code>dist</code>.

       </p>

     </div>

   </section>

 </div>

</div>