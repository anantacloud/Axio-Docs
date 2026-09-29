---
layout: default
title: Setup and registration
parent: Runner
nav_order: 3
permalink: /axio/administration/runner/registration/
---



<link rel="stylesheet" href="{{ '/assets/css/setup-registration.css' | relative_url }}">



<div class="setup-doc">

 <h1>Setup and registration</h1>

 <p class="lead">

   <strong>Administration → Runners → Setup</strong>

   <code>/admin/runners?tab=setup</code> is the two-step flow for self-hosted agents.

 </p>

 <div class="step-cards">

   <div class="step-card step-blue">

     <div class="step-number">1</div>

     <div>

       <h2>Step 1 — Create a runner group</h2>

       <p>

         See <a href="{{ '/runners/groups' | relative_url }}">Groups</a>.

         You must have at least one enabled group before you can generate an install command.

       </p>

     </div>

     <div class="step-icon">♙</div>

   </div>

   <div class="step-card step-green">

     <div class="step-number">2</div>

     <div>

       <h2>Step 2 — Register runners</h2>

       <p>

         Select a group, platform, and options, then generate an install command and run it on the host.

       </p>

     </div>

     <div class="step-icon terminal">›_</div>

   </div>

 </div>

 <div class="two-column top-section">

   <section>

     <h2>Register runners</h2>

     <ol class="numbered-list">

       <li>Select a <strong>runner group</strong>. The helper text shows the group's scope.</li>

       <li>

         Select a <strong>platform</strong>: Linux, Windows, Docker, or Kubernetes.

         See <a href="{{ '/runners/platforms' | relative_url }}">Platforms</a>.

       </li>

       <li>

         For Linux or Windows, choose <strong>isolation</strong>: Process or Container.

         Docker and Kubernetes lock isolation automatically.

       </li>

       <li>

         Optionally set a runner name, name prefix, and labels

         (not used for Kubernetes YAML identity — the cluster assigns unique names).

       </li>

       <li>Optionally set <strong>max uses</strong> and <strong>token TTL</strong>.</li>

       <li>Click <strong>Generate registration command</strong>.</li>

       <li>Copy the command and run it on the host.</li>

       <li>

         Refresh <strong>Overview</strong>. The runner appears when registration and the first heartbeat succeed.

       </li>

     </ol>

   </section>

   <aside>

     <div class="callout info">

       <div class="callout-icon">i</div>

       <div>

         <strong>Required permissions</strong>

         <p>

           Read-only users see an info alert instead of the generator.

           Ask an admin for <code>runner:manage</code> or

           <code>runner:customer:register</code>.

           See <a href="{{ '/runners/permissions' | relative_url }}">Permissions</a>.

         </p>

       </div>

     </div>

     <div class="platform-panel">

       <h2>Platform options</h2>

       <div class="platform-grid">

         <div class="platform">

           <span class="platform-symbol">◖</span>

           <strong>Linux</strong>

         </div>

         <div class="platform">

           <span class="platform-symbol">⊞</span>

           <strong>Windows</strong>

         </div>

         <div class="platform">

           <span class="platform-symbol">▣</span>

           <strong>Docker</strong>

         </div>

         <div class="platform">

           <span class="platform-symbol">◈</span>

           <strong>Kubernetes</strong>

         </div>

       </div>

       <div class="isolation-box">

         <div class="isolation-icon">⚙</div>

         <div>

           <strong>Isolation</strong>

           <p>

             For Linux or Windows, choose Process or Container.

             Docker and Kubernetes lock isolation automatically.

             See <a href="{{ '/runners/platforms' | relative_url }}">Platforms</a>.

           </p>

         </div>

       </div>

     </div>

   </aside>

 </div>

 <div class="two-column">

   <section>

     <h2>Runner name</h2>

     <div class="table-wrap">

       <table>

         <thead>

           <tr>

             <th>Option</th>

             <th>When to use</th>

           </tr>

         </thead>

         <tbody>

           <tr>

             <td><strong>Runner name</strong></td>

             <td>Fixed unique name in this organization.</td>

           </tr>

           <tr>

             <td><strong>Runner name prefix</strong></td>

             <td>

               Scale replicas: each registration becomes

               <code>prefix</code> + random suffix (e.g. <code>prod-482913</code>).

             </td>

           </tr>

           <tr>

             <td><strong>Blank</strong></td>

             <td>Agent uses the host name from the install environment.</td>

           </tr>

         </tbody>

       </table>

     </div>

   </section>

   <aside>

     <div class="callout danger">

       <div class="callout-icon">!</div>

       <div>

         <strong>Runner name rules</strong>

         <ul>

           <li>Max 64 characters</li>

           <li>Start with a letter or number</li>

           <li>Only letters, numbers, dots, hyphens, underscores</li>

           <li>Unique in the organization (case-insensitive)</li>

           <li>Name and prefix are mutually exclusive</li>

         </ul>

         <p class="divider-text">

           Kubernetes registration does not take a fixed name in this form.

           Use <code>AXIO_RUNNER_NAME_PREFIX</code> on the Deployment so each pod

           registers uniquely. See

           <a href="{{ '/runners/kubernetes' | relative_url }}">Kubernetes</a>.

         </p>

       </div>

     </div>

   </aside>

 </div>

 <div class="two-column">

   <section>

     <h2>Labels at registration</h2>

     <p>

       Comma-separated labels are baked into the install command and applied on register.

       You can edit them later from Overview. Do not assign <code>axio-\*</code> to self-hosted runners.

       See <a href="{{ '/runners/labels' | relative_url }}">Labels</a>.

     </p>

     <h2>After the command is ready</h2>

     <p>The page shows:</p>

     <div class="check-list">

       <div>✓ <span>Execution profile (e.g. <code>Linux · Process</code>)</span></div>

       <div>✓ <span>Token prefix, expiry, max uses, group, labels</span></div>

       <div>✓ <span>System / network prerequisites</span></div>

       <div>✓ <span>Copyable install script for the selected platform</span></div>

     </div>

     <div class="callout info">

       <div class="callout-icon">i</div>

       <p>

         You can switch the platform cards to view the Linux vs Docker vs Kubernetes

         variant of the same token when instructions exist for those platforms.

         <strong>Register another one</strong> starts a new token so two hosts do not share identity.

       </p>

     </div>

   </section>

   <section>

     <h2>Token options</h2>

     <div class="table-wrap">

       <table>

         <thead>

           <tr>

             <th>Field</th>

             <th>Default</th>

             <th>Limit</th>

           </tr>

         </thead>

         <tbody>

           <tr>

             <td><strong>Max uses</strong></td>

             <td>Unlimited until expiry (static fleet token)</td>

             <td>1 – 10000</td>

           </tr>

           <tr>

             <td><strong>Token TTL</strong></td>

             <td>Shown in the generated instruction (often 60 minutes if unset)</td>

             <td>1 – 43200 minutes (30 days)</td>

           </tr>

         </tbody>

       </table>

     </div>

     <p>

       Leave max uses blank for a long-lived install token you reuse across a static fleet.

       Set max uses to <code>1</code> for a single machine. For Docker/Kubernetes replicas,

       set max uses ≥ replica count.

     </p>

     <p>

       After generate you can <strong>Revoke token</strong> so the command stops working.

       Historical revoked or obsolete tokens can be cleaned without affecting the command you

       just copied. See <a href="{{ '/runners/tokens' | relative_url }}">Tokens</a>.

     </p>

   </section>

 </div>

 <div class="two-column bottom-section">

   <section>

     <h2>What happens on the host</h2>

     <div class="flow">

       <div class="flow-item">

         <span class="flow-icon">›_</span>

         <span>configure / docker run / kubectl apply</span>

       </div>

       <div class="flow-arrow">↓</div>

       <div class="flow-item">

         <span class="flow-icon api">API</span>

         <span>POST /runner-agent/register <code>(axreg_\* token)</code></span>

       </div>

       <div class="flow-arrow">↓</div>

       <div class="flow-item">

         <span class="flow-icon db">●</span>

         <span>Runner row created + long-lived <code>axrun_\*</code> token stored on the host</span>

       </div>

       <div class="flow-arrow">↓</div>

       <div class="flow-item">

         <span class="flow-icon heart">♥</span>

         <span>Heartbeat + poll for work</span>

       </div>

       <div class="flow-arrow">↓</div>

       <div class="flow-item">

         <span class="flow-icon users">♧</span>

         <span>Row appears on Overview</span>

       </div>

     </div>

     <p class="small-note">

       The registration token is discarded after exchange. The agent keeps the long-lived

       token in config (mode <code>0600</code>) or the encrypted credential store.

     </p>

   </section>

   <section>

     <h2>Control plane URL</h2>

     <p>

       Install commands embed <code>API_PUBLIC_URL</code> (must include <code>/api/v1</code>).

       If registration returns HTML or HTTP 405, the URL is the web UI, not the API.

       Fix ingress or the public API URL, then generate a new command.

     </p>

     <div class="callout info">

       <div class="callout-icon">i</div>

       <p>

         From a Docker runner on the same host as the API, use

         <code>http://host.docker.internal:3001/api/v1</code>.

         Machine-mode on the same VM can use

         <code>http://localhost:3001/api/v1</code>.

       </p>

     </div>

     <h2>Local quick start</h2>

     <div class="code-block">

       <div class="code-title">bash</div>

       <pre><code>npm run build:runner

cd runner/installer

./configure.sh --url http://localhost:3001/api/v1 --token axreg_... --name my-runner

./run.sh</code></pre>

     </div>

   </section>

 </div>

</div>