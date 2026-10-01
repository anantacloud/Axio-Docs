---
layout: default
title: Policies
parent: Security & Governance
nav_order: 3
permalink: /axio/security-governance/policies/
---

<div class="policy-page">

  <div class="policy-page-header">
    <h1>Policies: library, packs, and evaluation</h1>
    <p>
      Policies define what Axio checks in IaC, Kubernetes, cloud resources, identity, CI/CD, and related domains.
      <strong>Policy Library</strong> is where you discover, install, and evaluate policies.
      <strong>Policy Packs</strong> group installed policies into versioned baselines you assign in one step.
    </p>
  </div>

  <section class="policy-info-card policy-domains-card">
    <span class="policy-info-icon green">◎</span>
    <div>
      <h2>Access requirements</h2>
      <table class="policy-table">
        <thead>
          <tr>
            <th>Surface</th>
            <th>Route</th>
            <th>Typical permission</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td><strong>Policy Library</strong></td>
            <td><code>/policies</code></td>
            <td><code>governance:read</code>, <code>policy:manage</code>, or <code>compliance:manage</code></td>
          </tr>
          <tr>
            <td><strong>Policy Packs</strong></td>
            <td><code>/policy-packs</code></td>
            <td><code>policy:manage</code></td>
          </tr>
        </tbody>
      </table>
      <p>
        Installing catalog bundles and creating packs from official admin bundles may additionally require an
        organization administrator. Members with <code>policy:manage</code> can create and edit their own packs
        and assign published packs within their scope.
      </p>
    </div>
  </section>

  <div class="policy-top-grid">

    <section class="policy-card policy-pack-card">
      <div class="policy-card-title">
        <span class="policy-icon policy-icon-purple">▱</span>
        <h2>Policy Packs</h2>
      </div>

      <p>
        Open <strong>Security &amp; Governance → Policy Packs</strong>. A <strong>policy pack</strong> is a
        versioned bundle of installed policies with a lifecycle status:
        <strong>draft</strong>, <strong>published</strong>, or <strong>archived</strong>.
      </p>

      <h3>What you can do</h3>

      <ul class="policy-check-list">
        <li>Create a pack — name, description, category, version label, and selected policies.</li>
        <li>Edit, clone, publish (with version bump), archive, restore to draft, or delete (when unassigned).</li>
        <li>Assign a <strong>published</strong> pack to a scope; archived packs cannot be assigned.</li>
        <li>View dashboard KPIs: total packs, published, draft, archived (admin), assigned (admin), policies in packs.</li>
        <li>Search and filter the pack list; KPI cards filter or sort the table below.</li>
      </ul>

      <p><strong>Assignment scopes</strong> (labels shown in the UI):</p>

      <ul>
        <li>Organization</li>
        <li>Project</li>
        <li>Workspace</li>
        <li>Environment</li>
        <li>Stack</li>
      </ul>

      <p>
        Use packs when several teams should share the same baseline
        (for example <strong>AWS security baseline</strong> or <strong>Kubernetes hardening</strong>)
        instead of assigning dozens of policies one by one.
      </p>

      <p>
        From Policy Library <strong>Bundles</strong>, you can install a compliance baseline and optionally
        <strong>Create pack</strong> from that bundle to turn it into an assignable policy pack.
      </p>

      <div class="policy-table-note">
        <span>ⓘ</span>
        <p>
          Non-admins can edit packs they created. Organization and administrator packs are use-only — assign them
          in your scope, or clone to make your own. Org-wide catalog install and assignment may require an administrator.
        </p>
      </div>
    </section>

    <section class="policy-card policy-library-card">
      <div class="policy-card-title">
        <span class="policy-icon policy-icon-blue">▣</span>
        <h2>Policy Library</h2>
      </div>

      <p>
        Open <strong>Security &amp; Governance → Policy Library</strong>. The library is the full built-in catalog
        plus your organization’s installed policies.
      </p>

      <p class="policy-label">Tabs</p>

      <div class="policy-panel-list">
        <div class="policy-panel-item">
          <span class="mini-icon green">↗</span>
          <div><strong>Overview</strong><small>KPIs, category breakdown, recommendations, and navigation into other tabs</small></div>
        </div>

        <div class="policy-panel-item">
          <span class="mini-icon purple">⊞</span>
          <div><strong>Catalog</strong><small>Browse built-in policies by cloud, domain, severity, or framework; install individually or in bulk</small></div>
        </div>

        <div class="policy-panel-item">
          <span class="mini-icon orange">◇</span>
          <div><strong>Bundles</strong><small>Install compliance baselines (CIS, SOC 2, PCI DSS, HIPAA, Zero Trust, AI Governance, cloud baselines, …)</small></div>
        </div>

        <div class="policy-panel-item">
          <span class="mini-icon blue">▤</span>
          <div><strong>Installed</strong><small>Org policies: enable/disable, view detail, assign, test, publish versions, create custom policies</small></div>
        </div>

        <div class="policy-panel-item">
          <span class="mini-icon red">▶</span>
          <div><strong>Evaluate</strong><small>Run enabled policies against sample demo data or live Git repos, stacks, and workspaces</small></div>
        </div>

        <div class="policy-panel-item">
          <span class="mini-icon gray">◷</span>
          <div><strong>History</strong><small>Past evaluation runs with pass/fail and violation detail</small></div>
        </div>
      </div>

      <p class="policy-label">Quick actions and connectors</p>

      <ul>
        <li><strong>Quick actions:</strong> Browse catalog, Install bundle, Installed policies, Run evaluation (requires at least one enabled policy).</li>
        <li><strong>Related:</strong> Governance dashboard, Policy packs, Security insights (IaC scans), Compliance.</li>
      </ul>
    </section>

  </div>

  <section class="policy-info-card policy-domains-card">
    <span class="policy-info-icon green">◎</span>
    <div>
      <h2>Catalog domains (built-in)</h2>
      <p>
        AWS, Azure, GCP, Oracle Cloud, DigitalOcean, Kubernetes, IaC &amp; Templates (Terraform, OpenTofu, Helm,
        CloudFormation, Pulumi), CI/CD &amp; GitOps, AI Governance, Identity, Networking, Operations, Containers, FinOps.
      </p>
      <p>
        Catalog size is loaded live from the API (hundreds of built-in policies). Use Overview and Catalog facets
        to browse by platform, severity, and subcategory.
      </p>
    </div>
  </section>

  <section class="policy-info-card policy-engines-card">
    <span class="policy-info-icon blue">⚙</span>
    <div>
      <h2>Engines</h2>

      <p><strong>Policy as code</strong> — write rules in the engine’s native format:</p>
      <p>OPA, Rego, Kyverno, CEL, Gatekeeper, Cloud Custodian, Conftest, Sentinel.</p>

      <p><strong>Scanning engine profiles</strong> — classify controls and map to external tooling (Checkov, Trivy, Kubescape, Falco):</p>
      <p>
        Policy Evaluate uses built-in attribute checks for these profiles; run the external scanner in CI/CD or
        Security Insights and map findings to the policy.
      </p>

      <p><strong>Built-in</strong> — Axio-native attribute checks evaluated inside the platform without an external engine.</p>

      <p>You pick an engine when creating a custom policy; catalog entries already declare their engine.</p>
    </div>
  </section>

  <section class="policy-info-card policy-single-card">
    <span class="policy-info-icon orange">♢</span>
    <div>
      <h2>What you can do with a single policy</h2>

      <ul class="policy-check-list">
        <li><strong>Install</strong> from catalog or bundle (creates an org copy).</li>
        <li><strong>Enable</strong> on the Installed tab — disabled policies are not evaluated.</li>
        <li><strong>Assign</strong> to organization, project, stack, workspace, repository, or environment scope.</li>
        <li><strong>Test</strong> with saved test cases; <strong>publish</strong> a new version with change summary.</li>
        <li>Set <strong>enforcement</strong>: <strong>Enforcing</strong>, <strong>Advisory</strong>, or <strong>Disabled</strong> — the deploy gate respects enforcing policies when gate mode is Enforce.</li>
        <li>Create <strong>custom policies</strong> from templates or scratch (requires valid name, engine, and rule body or parameters).</li>
      </ul>

      <p>
        Installing a catalog policy does nothing until it is <strong class="green-text">enabled</strong> and
        <strong class="green-text">assigned</strong> (directly or via a policy pack).
      </p>
    </div>
  </section>

  <section class="policy-evaluation">
    <h2>Evaluation vs live scan vs gate</h2>

    <table class="policy-table">
      <thead>
        <tr>
          <th>Mechanism</th>
          <th>When it runs</th>
          <th>Result</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td class="purple-text">Evaluate (Policy Library)</td>
          <td>On demand — sample demo resources or live Git repo / stack / workspace</td>
          <td>Pass/fail per policy; saved to History</td>
        </tr>
        <tr>
          <td class="blue-text">Live scan (Security Insights)</td>
          <td>On connected Git repos when enabled, or manual Scan now</td>
          <td>IaC findings and policy violations</td>
        </tr>
        <tr>
          <td class="red-text">Policy gate (Governance settings)</td>
          <td><strong>PLAN</strong> / <strong>APPLY</strong></td>
          <td>Enforce blocks; Advisory records only; Fail-open blocks on enforcing violations but allows deploy on evaluation errors</td>
        </tr>
      </tbody>
    </table>

    <div class="policy-table-note">
      <span>ⓘ</span>
      <p>
        All three use the same policy definitions. The gate is the only mechanism that can
        <strong>stop a deployment</strong>. Fix IaC, re-scan or re-evaluate, then retry the deployment.
      </p>
    </div>
  </section>

  <section class="policy-evaluation">
    <h2>How it works (Policy Library)</h2>

    <ol class="policy-check-list">
      <li><strong>Browse &amp; install</strong> — pick policies from Catalog or install a baseline Bundle.</li>
      <li><strong>Enable for your org</strong> — toggle policies on under Installed; assign via policy packs or direct assignment.</li>
      <li><strong>Evaluate workloads</strong> — run enabled policies against sample or live targets.</li>
      <li><strong>Track violations</strong> — review History, then remediate on My findings or the Governance dashboard.</li>
    </ol>
  </section>

  <div class="policy-bottom-grid">

    <section class="policy-card policy-custom-card">
      <div class="policy-card-title">
        <span class="policy-icon policy-icon-purple">✎</span>
        <h2>Custom policies</h2>
      </div>

      <p>
        Users with <code>policy:manage</code> can create a policy with name, engine, category, severity,
        enforcement, rule body (or parameters for built-in/scanner engines), and optional templates.
      </p>

      <p>
        Prefer catalog policies for common CIS and cloud controls; use custom policies for org-specific rules.
        Keep versions — publish rather than silently editing production assignments.
      </p>
    </section>

    <section class="policy-card policy-roles-card">
      <div class="policy-card-title">
        <span class="policy-icon policy-icon-green">♧</span>
        <h2>Role presets (policy vs approval)</h2>
      </div>

      <p>
        Enterprise governance role presets implement <strong>separation of duties</strong>. 
      </p>

      <table class="policy-table role-table">
        <thead>
          <tr>
            <th>Preset</th>
            <th>Manage policies</th>
            <th>Approve exceptions</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td><strong>Compliance Officer</strong></td>
            <td class="red-text">No</td>
            <td class="green-text">Yes</td>
          </tr>
          <tr>
            <td><strong>DevSecOps Engineer</strong></td>
            <td class="green-text">Yes</td>
            <td class="red-text">No</td>
          </tr>
          <tr>
            <td><strong>Developer</strong></td>
            <td class="red-text">No</td>
            <td class="red-text">No</td>
          </tr>
        </tbody>
      </table>

      <p>
        Policy exception approval requires <code>governance:approve</code>, not <code>policy:manage</code>.
        Org Admin/Owner retains full access to both policy management and exception approval.
      </p>
    </section>

  </div>

  <section class="policy-evaluation">
    <h2>Permissions summary</h2>

    <table class="policy-table">
      <thead>
        <tr>
          <th>Permission</th>
          <th>Typical access</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><code>policy:read</code></td>
          <td>View policies, catalog, and evaluation results.</td>
        </tr>
        <tr>
          <td><code>policy:manage</code></td>
          <td>Install, create, enable, assign, evaluate, and manage policy packs.</td>
        </tr>
        <tr>
          <td><code>governance:manage</code></td>
          <td>Org-wide governance settings including policy gate mode and live-scan defaults.</td>
        </tr>
        <tr>
          <td><code>governance:approve</code></td>
          <td>Approve policy exceptions (Compliance Officer preset).</td>
        </tr>
      </tbody>
    </table>
  </section>

</div>

<div class="page-navigation">

<a
class="nav-button previous"
href="{{ '/axio/security-governance/my-findings/' | relative_url }}">

← My findings

</a>

<a
class="nav-button next"
href="{{ '/axio/security-governance/' | relative_url }}">

Governance Dashboard →

</a>

</div>
