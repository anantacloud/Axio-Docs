---
layout: default
title: Platforms
parent: Runner
nav_order: 4
permalink: /axio/administration/runner/platform/
---



<link rel="stylesheet" href="{{ '/assets/css/platforms.css' | relative_url }}">



<div class="platforms-doc">

 <h1>Platforms</h1>

 <p class="lead">

   Step 2 of Setup asks which platform the agent will run on. The choice changes the

   install command and the <strong>execution profile</strong> shown in inventory.

 </p>

 <div class="platform-summary table-wrap">

   <table>

     <thead>

       <tr>

         <th>Platform</th>

         <th>Install style</th>

         <th>Default isolation</th>

         <th>Typical use</th>

       </tr>

     </thead>

     <tbody>

       <tr>

         <td><span class="platform-name"><span class="os-icon linux">◖</span>Linux</span></td>

         <td>Bash script <code>configure.sh</code> / release tarball</td>

         <td>Process (or Container if you pick it)</td>

         <td>VM or bare metal with IaC CLIs on PATH</td>

       </tr>

       <tr>

         <td><span class="platform-name"><span class="os-icon windows">⊞</span>Windows</span></td>

         <td>PowerShell install script</td>

         <td>Process (or Container)</td>

         <td>Windows VM</td>

       </tr>

       <tr>

         <td><span class="platform-name"><span class="os-icon docker">▣</span>Docker</span></td>

         <td><code>docker run</code> / Compose</td>

         <td>Container</td>

         <td>Host with Docker; IaC in engine images</td>

       </tr>

       <tr>

         <td><span class="platform-name"><span class="os-icon k8s">◈</span>Kubernetes</span></td>

         <td><code>kubectl</code> / Helm</td>

         <td>Kubernetes pod</td>

         <td>In-cluster agent; IaC as Jobs</td>

       </tr>

     </tbody>

   </table>

 </div>

 <div class="platform-grid">

   <section class="platform-card">

     <div class="platform-heading">

       <span class="large-icon linux">◖</span>

       <div>

         <h2>Linux</h2>

         <p>Use when Terraform, OpenTofu, Pulumi, or the AWS CLI is installed on the machine.</p>

       </div>

     </div>

     <div class="code-block">

       <div class="code-header">

         <span>bash</span>

         <span class="copy-mark">▣</span>

       </div>

       <pre><code>cd runner/installer

./configure.sh \\

 --url https://platform.example.com/api/v1 \\

 --token axreg_xxxxxxxx \\

 --name production-runner

./run.sh

\# or

sudo ./svc.sh install --config /etc/axio-runner/config.yaml

sudo ./svc.sh start</code></pre>

     </div>

     <div class="callout info">

       <span class="callout-icon">i</span>

       <p>

         If you select <strong>Container</strong> isolation on a Linux card, the generated

         command switches to the Docker registration path so IaC runs in engine images.

       </p>

     </div>

   </section>

   <section class="platform-card">

     <div class="platform-heading">

       <span class="large-icon windows">⊞</span>

       <div>

         <h2>Windows</h2>

         <p>

           Same flow as Linux with a PowerShell script from the generated command.

           Process isolation expects CLIs on PATH. Container isolation requires Docker on that Windows host.

         </p>

       </div>

     </div>

     <div class="code-block">

       <div class="code-header">

         <span>powershell</span>

         <span class="copy-mark">▣</span>

       </div>

       <pre><code>cd runner\\installer

.\\configure.ps1 `

 -Url "https://platform.example.com/api/v1" `

 -Token "axreg_xxxxxxxx" `

 -Name "production-runner"

.\\run.ps1</code></pre>

     </div>

     <div class="callout warning">

       <span class="callout-icon">!</span>

       <p>Container isolation on Windows requires Docker to be installed and running on the host.</p>

     </div>

   </section>

   <section class="platform-card docker-card">

     <div class="platform-heading">

       <span class="large-icon docker">▣</span>

       <div>

         <h2>Docker</h2>

         <p>Use <code>docker run</code> or Docker Compose to start the runner.</p>

       </div>

     </div>

     <div class="code-block">

       <div class="code-header">

         <span>bash</span>

         <span class="copy-mark">▣</span>

       </div>

       <pre><code>export AXIO_API_URL=https://platform.example.com/api/v1

export AXIO_REGISTRATION_TOKEN=axreg_xxxxxxxx

docker compose -f deploy/runner/docker-compose.agent.yml up -d --build</code></pre>

     </div>

     <h3>Manual run:</h3>

     <div class="code-block">

       <div class="code-header">

         <span>bash</span>

         <span class="copy-mark">▣</span>

       </div>

       <pre><code>docker run -d --restart always \\

 -e AXIO_API_URL=https://platform.example.com/api/v1 \\

 -e AXIO_REGISTRATION_TOKEN=axreg_xxxxxxxx \\

 -e AXIO_RUNNER_PLATFORM=DOCKER \\

 -v axio-runner-data:/var/lib/axio-runner \\

 ghcr.io/anantacloud-oss/runner-core:latest</code></pre>

     </div>

     <div class="callout warning">

       <span class="callout-icon">!</span>

       <p>

         For Terraform stages do not use <code>runner-core</code> alone.

         Use <code>runner-agent</code> (DooD) or <code>runner-iac-tools</code>.

         See <a href="{{ '/runners/iac-requirements' | relative_url }}">IaC requirements</a>.

       </p>

     </div>

     <div class="callout info">

       <span class="callout-icon">i</span>

       <p>

         Scale replicas with <code>RUNNER_REPLICAS</code> and a distinct

         <code>AXIO_RUNNER_NAME_PREFIX</code> per fleet. Mint a token with max uses ≥ replica count.

       </p>

     </div>

   </section>

   <section class="platform-card">

     <div class="platform-heading">

       <span class="large-icon k8s">◈</span>

       <div>

         <h2>Kubernetes</h2>

         <p>

           The generated command applies <code>kubernetes/runner-deployment.yaml</code>

           (or Helm) with a bootstrap Secret <code>apiUrl</code>, <code>token</code>,

           optional <code>runnerName</code> / <code>runnerNamePrefix</code>.

         </p>

       </div>

     </div>

     <div class="code-block">

       <div class="code-header">

         <span>bash</span>

         <span class="copy-mark">▣</span>

       </div>

       <pre><code>kubectl apply -f kubernetes/runner-deployment.yaml

\# or with Helm

helm upgrade --install axio-runner ./kubernetes/helm \\

 --set apiUrl="https://platform.example.com/api/v1" \\

 --set token="axreg_xxxxxxxx"</code></pre>

     </div>

     <div class="callout info">

       <span class="callout-icon">i</span>

       <p>

         Each replica must register as a distinct runner. Set

         <code>AXIO_RUNNER_NAME_PREFIX</code>; do not reuse one

         <code>AXIO_RUNNER_NAME</code> across pods.

       </p>

     </div>

   </section>

 </div>

 <div class="lower-grid">

   <section class="panel">

     <div class="panel-heading">

       <span class="panel-icon purple">⚙</span>

       <div>

         <h2>Isolation vs platform</h2>

         <p>The group's internal pool isolation restricts which platforms you can pick later.</p>

       </div>

     </div>

     <div class="table-wrap">

       <table>

         <thead>

           <tr>

             <th>Isolation</th>

             <th>Allowed platforms</th>

           </tr>

         </thead>

         <tbody>

           <tr>

             <td>Process</td>

             <td>Linux, Windows</td>

           </tr>

           <tr>

             <td>Container</td>

             <td>Linux, Windows, Docker</td>

           </tr>

           <tr>

             <td>Kubernetes pod</td>

             <td>Kubernetes only</td>

           </tr>

         </tbody>

       </table>

     </div>

     <p class="link-line">

       See <a href="{{ '/runners/isolation' | relative_url }}">Runner isolation</a>.

     </p>

   </section>

   <section class="panel execution-panel">

     <div class="panel-heading">

       <span class="panel-icon green">▥</span>

       <div>

         <h2>Execution profile in inventory</h2>

         <p>The execution profile shown in inventory is based on the persisted platform.</p>

       </div>

     </div>

     <div class="table-wrap">

       <table>

         <thead>

           <tr>

             <th>Persisted platform</th>

             <th>Profile shown</th>

           </tr>

         </thead>

         <tbody>

           <tr>

             <td>LINUX</td>

             <td>Linux · Process</td>

           </tr>

           <tr>

             <td>WINDOWS</td>

             <td>Windows · Process</td>

           </tr>

           <tr>

             <td>DOCKER</td>

             <td>Docker</td>

           </tr>

           <tr>

             <td>KUBERNETES</td>

             <td>Kubernetes</td>

           </tr>

         </tbody>

       </table>

     </div>

   </section>

 </div>

</div>