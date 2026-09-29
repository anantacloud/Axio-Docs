---
layout: default
title: Registration tokens
parent: Runner
nav_order: 5
permalink: /axio/administration/runner/tokens/
---



<link rel="stylesheet" href="{{ '/assets/css/registration-tokens.css' | relative_url }}">



<div class="registration-tokens-doc">

 <h1>Registration tokens</h1>

 <p class="lead">

   Registration tokens are short-lived secrets used only to <strong>create</strong> a runner.

   After <code>configure</code> / <code>docker run</code> / <code>kubectl apply</code>,

   the agent exchanges the token for a long-lived runner credential and discards it.

 </p>

 <section>

   <h2>Token kinds</h2>

   <div class="table-wrap">

     <table class="token-kinds-table">

       <thead>

         <tr>

           <th>Prefix</th>

           <th>Kind</th>

           <th>Who mints it</th>

           <th>Where</th>

         </tr>

       </thead>

       <tbody>

         <tr>

           <td><code>axreg_</code></td>

           <td>Customer / self-hosted</td>

           <td>Tenant admin on <a href="{{ '/runners/setup' | relative_url }}">Setup</a></td>

           <td>Bound to a runner group</td>

         </tr>

         <tr>

           <td><code>axpreg_</code></td>

           <td>Provider / hosted fleet</td>

           <td>Platform provider on <a href="{{ '/runners/hosted-fleet' | relative_url }}">Hosted fleet</a></td>

           <td>Bound to a hosted group</td>

         </tr>

         <tr>

           <td><code>axrun_</code></td>

           <td>Runner auth (not a registration token)</td>

           <td>Issued at register</td>

           <td>Stored on the agent; used for heartbeat, lease, logs</td>

         </tr>

       </tbody>

     </table>

   </div>

   <div class="callout warning">

     <span class="callout-icon">!</span>

     <p>

       Do not put <code>axrun_</code> into a new install command.

       If the agent is gone, generate a new <code>axreg_</code> /

       <code>axpreg_</code> command and register again (or reuse the existing

       <code>axrun_</code> only if the same config file is still on disk).

     </p>

   </div>

 </section>

 <div class="two-column">

   <section class="panel">

     <div class="panel-heading">

       <span class="panel-icon purple">⚙</span>

       <div>

         <h2>Setup fields</h2>

       </div>

     </div>

     <p>

       When you click <strong>Generate registration command</strong>:

     </p>

     <div class="table-wrap">

       <table>

         <thead>

           <tr>

             <th>Field</th>

             <th>Behavior</th>

           </tr>

         </thead>

         <tbody>

           <tr>

             <td><strong>Max uses</strong></td>

             <td>

               Blank = unlimited until expiry. Set <code>1</code> for a single host.

               Set ≥ replica count for Compose/Kubernetes scale-out.

               Range 1 – 10000.

             </td>

           </tr>

           <tr>

             <td><strong>Token TTL</strong></td>

             <td>

               Minutes until the registration token expires.

               Range 1 – 43200 (30 days).

             </td>

           </tr>

         </tbody>

       </table>

     </div>

     <div class="callout info">

       <span class="callout-icon">i</span>

       <p>

         The generated panel shows token prefix, expiry, max uses, group, and labels.

       </p>

     </div>

   </section>

   <section class="panel">

     <div class="panel-heading">

       <span class="panel-icon green">⟳</span>

       <div>

         <h2>Lifecycle</h2>

       </div>

     </div>

     <ol class="lifecycle">

       <li>Control plane mints the token and returns platform install instructions.</li>

       <li>You run the command on the host.</li>

       <li>

         <code>POST /runner-agent/register</code> validates expiry, remaining uses,

         revocation, and group.

       </li>

       <li>A runner row is created. Uses remaining decrement.</li>

       <li>Agent stores <code>axrun_\*</code> and starts heartbeats.</li>

     </ol>

     <div class="callout danger">

       <span class="callout-icon">!</span>

       <p>

         <strong>Revoke token</strong> on the generated command immediately stops

         further registrations. Existing online runners keep working.

       </p>

     </div>

   </section>

 </div>

 <div class="two-column">

   <section class="panel">

     <div class="panel-heading">

       <span class="panel-icon purple">▣</span>

       <div>

         <h2>Cleanup on Setup</h2>

       </div>

     </div>

     <p>If the org has revoked or obsolete token rows, Setup shows:</p>

     <div class="cleanup-item">

       <span class="cleanup-icon">▣</span>

       <div>

         <strong>Clean revoked</strong>

         <p>Remove revoked records.</p>

       </div>

     </div>

     <div class="cleanup-item">

       <span class="cleanup-icon">▣</span>

       <div>

         <strong>Clean obsolete</strong>

         <p>Remove expired / unused historical records.</p>

       </div>

     </div>

     <div class="callout info">

       <span class="callout-icon">i</span>

       <p>

         These cleanups do not break an install command you have already copied

         unless you revoke that token.

       </p>

     </div>

   </section>

   <section>

     <div class="panel compact-panel">

       <div class="panel-heading">

         <span class="panel-icon blue">▣</span>

         <div>

           <h2>Copy registration from an existing runner</h2>

         </div>

       </div>

       <p>

         <strong>Overview → ⋮ → Copy registration command</strong> mints a new token

         for the same group/platform placement so you can rebuild a host without

         re-entering Setup options.

       </p>

     </div>

     <div class="panel security-panel">

       <div class="panel-heading">

         <span class="panel-icon green">+</span>

         <div>

           <h2>Security</h2>

         </div>

       </div>

       <ul class="security-list">

         <li>Treat <code>axreg_\*</code> / <code>axpreg_\*</code> like a one-time bootstrap secret.</li>

         <li>Tokens are hashed at rest on the control plane.</li>

         <li>

           Customer tokens cannot register into the provider fleet; provider tokens

           cannot register as tenant self-hosted runners.

         </li>

         <li>

           Runner JWTs (<code>axrun_\*</code>) are hashed at rest.

           A 401 on heartbeat means re-run configure with a new registration token.

         </li>

       </ul>

       <p>

         See <a href="{{ '/runners/security' | relative_url }}">Security</a>.

       </p>

     </div>

   </section>

 </div>

 <section class="panel environment-panel">

   <div class="panel-heading">

     <span class="panel-icon blue">›_</span>

     <div>

       <h2>Environment variables (agent)</h2>

     </div>

   </div>

   <div class="table-wrap">

     <table>

       <thead>

         <tr>

           <th>Variable</th>

           <th>Purpose</th>

         </tr>

       </thead>

       <tbody>

         <tr>

           <td><code>AXIO_API_URL</code> / <code>AXIO_SERVER_URL</code></td>

           <td>Control plane API including <code>/api/v1</code></td>

         </tr>

         <tr>

           <td><code>AXIO_REGISTRATION_TOKEN</code></td>

           <td><code>axreg_\*</code> or <code>axpreg_\*</code> for first boot</td>

         </tr>

         <tr>

           <td><code>AXIO_RUNNER_TOKEN</code></td>

           <td>Override long-lived bearer after register</td>

         </tr>

         <tr>

           <td><code>AXIO_RUNNER_NAME</code></td>

           <td>Fixed name (one host only)</td>

         </tr>

         <tr>

           <td><code>AXIO_RUNNER_NAME_PREFIX</code></td>

           <td>Unique names per replica</td>

         </tr>

         <tr>

           <td><code>AXIO_RUNNER_LABELS</code></td>

           <td>Comma-separated labels</td>

         </tr>

       </tbody>

     </table>

   </div>

 </section>

</div>