---
layout: default
title: Isolation
parent: Runner
nav_order: 9
permalink: /axio/administration/runner/isolation/
---



<link rel="stylesheet" href="{{ '/assets/css/isolation.css' | relative_url }}">


<div class="isolation-doc">

 <h1>Isolation</h1>

 <p class="lead">

   Isolation describes where IaC commands run relative to the agent process. It is stored on the group’s internal default pool and chosen when you generate a registration command (Linux/Windows: Process vs Container). Docker and Kubernetes lock the mode.

 </p>

 <section class="doc-panel">

   <div class="section-heading">

     <span class="section-icon purple">▤</span>

     <h2>Modes</h2>

   </div>

   <div class="table-wrap">

     <table>

       <thead>

         <tr>

           <th>Mode</th>

           <th>UI label</th>

           <th>Where IaC runs</th>

           <th>Compatible platforms</th>

         </tr>

       </thead>

       <tbody>

         <tr>

           <td><code>PROCESS</code></td>

           <td>Process</td>

           <td>CLIs on the runner host PATH</td>

           <td>Linux, Windows</td>

         </tr>

         <tr>

           <td><code>CONTAINER</code></td>

           <td>Container</td>

           <td>Engine Docker images (DooD or a Docker platform host)</td>

           <td>Linux, Windows, Docker</td>

         </tr>

         <tr>

           <td><code>KUBERNETES_POD</code></td>

           <td>Kubernetes pod</td>

           <td>Short-lived Jobs in the cluster</td>

           <td>Kubernetes</td>

         </tr>

         <tr>

           <td><code>NONE</code></td>

           <td>None (shared host)</td>

           <td>Shared host (legacy / API)</td>

           <td>Linux, Windows</td>

         </tr>

         <tr>

           <td><code>MICROVM</code></td>

           <td>MicroVM</td>

           <td>Reserved; treat like process for platform allow-lists</td>

           <td>Linux, Windows</td>

         </tr>

       </tbody>

     </table>

   </div>

   <div class="callout info">

     <span class="callout-icon">i</span>

     <p>

       Setup only offers Process and Container for VM registration. Kubernetes and Docker set pod / container isolation automatically.

     </p>

   </div>

 </section>

 <section class="doc-panel setup-panel">

   <div class="section-heading">

     <span class="section-icon green">⚙</span>

     <h2>Setup options for registration</h2>

   </div>

   <p>When you generate a registration command on a Linux or Windows VM, choose the isolation mode:</p>

   <div class="mode-cards">

     <div class="mode-card">

       <span class="radio"></span>

       <div class="mode-icon blue">›_</div>

       <h3>Process</h3>

       <p>IaC CLIs on the runner host (Linux or Windows VM).</p>

       <div class="platform-tags">

         <span>Linux</span><span>Windows</span>

       </div>

     </div>

     <div class="mode-card">

       <span class="radio"></span>

       <div class="mode-icon purple">◇</div>

       <h3>Container</h3>

       <p>IaC in engine Docker images (VM with Docker, or Docker platform).</p>

       <div class="platform-tags">

         <span>Linux</span><span>Windows</span><span>Docker</span>

       </div>

     </div>

     <div class="mode-card">

       <span class="radio"></span>

       <div class="mode-icon green">✥</div>

       <h3>Kubernetes pod</h3>

       <p>IaC runs as Jobs in the cluster.</p>

       <div class="platform-tags">

         <span>Kubernetes</span>

       </div>

     </div>

     <div class="mode-card">

       <span class="radio"></span>

       <div class="mode-icon red">▣</div>

       <h3>MicroVM</h3>

       <p>Reserved; treat like process for platform allow-lists.</p>

       <div class="platform-tags">

         <span>Linux</span><span>Windows</span>

       </div>

     </div>

   </div>

 </section>

 <section class="doc-panel modes-for-panel">

   <div class="section-heading">

     <span class="section-icon blue">▣</span>

     <h2>What each mode is for</h2>

   </div>

   <div class="mode-explanations">

     <article class="explanation-card">

       <div class="explanation-title">

         <span class="mode-icon blue">›_</span>

         <h3>Process</h3>

       </div>

       <p>

         Install Terraform, OpenTofu, Pulumi, or the AWS CLI on the VM.

         Fastest path for a dedicated Linux box.

       </p>

       <div class="flow">

         <span>Agent</span>

         <b>⟶</b>

         <span class="flow-target">⚙ &nbsp; IaC CLI<br><small>(on host)</small></span>

       </div>

     </article>

     <article class="explanation-card">

       <div class="explanation-title">

         <span class="mode-icon purple">◇</span>

         <h3>Container</h3>

       </div>

       <p>

         The agent pulls official engine images and runs stages in containers.

         Use runner-agent (docker.sock) or a VM that already has Docker.

         runner-core alone cannot run Terraform in this mode.

       </p>

       <div class="flow">

         <span>Agent</span>

         <b>⟶</b>

         <span class="flow-target">◈ &nbsp; IaC CLI<br><small>(in container)</small></span>

       </div>

     </article>

     <article class="explanation-card">

       <div class="explanation-title">

         <span class="mode-icon green">✥</span>

         <h3>Kubernetes pod</h3>

       </div>

       <p>

         Each IaC stage is a Job. The agent needs cluster RBAC, workspace volume/checkout,

         and HTTPS egress for provider registries.

       </p>

       <div class="flow">

         <span>Agent</span>

         <b>⟶</b>

         <span class="flow-target">◈ &nbsp; IaC Job<br><small>(in cluster)</small></span>

       </div>

     </article>

   </div>

 </section>

 <div class="two-column">

   <section class="doc-panel immutability-panel">

     <div class="section-heading">

       <span class="section-icon red">●</span>

       <h2>Immutability</h2>

     </div>

     <p>

       Execution isolation cannot be changed after the internal pool is created.

       The product message is:

     </p>

     <div class="callout danger">

       <span class="callout-icon">!</span>

       <p>

         “Execution isolation cannot be changed after a pool is created.

         Create a new pool with the desired isolation instead.”

       </p>

     </div>

     <p>

       In the UI that means: create a new runner group (which gets a new internal pool)

       and register agents there, or use the runner-platform API to create another pool.

     </p>

     <p>

       If you pick the wrong isolation, the platform cards on a later registration

       against that group are disabled with:

     </p>

     <div class="callout warning">

       <span class="callout-icon">!</span>

       <p>

         “This group uses &lt;isolation&gt; isolation — choose &lt;allowed platforms&gt;.”

       </p>

     </div>

   </section>

   <div class="right-stack">

     <section class="doc-panel helper-panel">

       <div class="section-heading">

         <span class="section-icon purple">▢</span>

         <h2>Helper text in Setup</h2>

       </div>

       <div class="table-wrap">

         <table>

           <thead>

             <tr>

               <th>Isolation</th>

               <th>Setup helper</th>

             </tr>

           </thead>

           <tbody>

             <tr>

               <td><code>Process</code></td>

               <td>IaC CLIs on the runner host (Linux or Windows VM).</td>

             </tr>

             <tr>

               <td><code>Container</code></td>

               <td>IaC in engine Docker images (VM with Docker, or Docker platform).</td>

             </tr>

             <tr>

               <td><code>Kubernetes pod</code></td>

               <td>IaC runs as Jobs in the cluster.</td>

             </tr>

           </tbody>

         </table>

       </div>

     </section>

     <section class="doc-panel hosted-panel">

       <div class="section-heading">

         <span class="section-icon orange">☁</span>

         <h2>Hosted fleet</h2>

       </div>

       <p>

         Provider groups also set isolation when the operator creates the hosted group.

         Default system labels follow isolation

         (<code>axio-linux</code>, <code>axio-docker</code>, <code>axio-kubernetes</code>).

       </p>

       <div class="callout info">

         <span class="callout-icon">i</span>

         <p>

           See <a href="{{ '/runners/hosted-fleet' | relative_url }}">hosted-fleet</a> for more details.

         </p>

       </div>

     </section>

   </div>

 </div>

</div>