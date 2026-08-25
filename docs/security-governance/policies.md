---
layout: default
title: Policies
parent: Security & Governance
nav_order: 2
---

<div class="policy-page">

  <div class="policy-page-header">
    <h1>Policies: library, packs, and evaluation</h1>
    <p>Policies define what Axio checks in IaC, Kubernetes, identity, CI/CD, and related domains.</p>
    <p>Packs group policies so you can assign a baseline in one step.</p>
  </div>

  <div class="policy-top-grid">

    <section class="policy-card policy-pack-card">
      <div class="policy-card-title">
        <span class="policy-icon policy-icon-purple">▱</span>
        <h2>Policy Packs</h2>
      </div>

      <div class="policy-meta">
        <span><strong>Route:</strong> /policy-packs</span>
        <span><strong>Who:</strong> Platform engineers and admins<br><small>(platform_engineer and above)</small></span>
      </div>

      <p>
        A <strong>policy pack</strong> is a versioned bundle of policies with a status
        (for example <strong>draft</strong> vs <strong>published</strong>) and assignments.
      </p>

      <h3>What you can do:</h3>

      <ul class="policy-check-list">
        <li>Create a pack, name it, set category and version label.</li>
        <li>Add installed policies to the pack.</li>
        <li>Assign the pack to a scope (organization, project, environment — see labels in the UI).</li>
        <li>Publish, archive, or restore a pack.</li>
        <li>View dashboard KPIs: pack count, assignment count, policy coverage.</li>
      </ul>

      <p>
        Use packs when several teams should share the same baseline
        (for example <strong>“AWS security baseline”</strong> or
        <strong>“Kubernetes hardening”</strong>) instead of assigning dozens of
        policies one by one.
      </p>

      <p>
        Catalog <strong>bundles</strong> (SOC 2, CIS, PCI, HIPAA, Zero Trust,
        AI Governance, and others) can be installed from the Policy Library
        and then grouped or assigned as packs.
      </p>
    </section>

    <section class="policy-card policy-library-card">
      <div class="policy-card-title">
        <span class="policy-icon policy-icon-blue">▣</span>
        <h2>Policy Library</h2>
      </div>

      <div class="policy-meta">
        <span><strong>Route:</strong> /policies</span>
        <span><strong>Who:</strong> OWNER and ADMIN</span>
      </div>

      <p>The library is the full policy catalog and the org’s installed policies.</p>

      <p class="policy-label">Typical tabs / panels:</p>

      <div class="policy-panel-list">
        <div class="policy-panel-item">
          <span class="mini-icon green">↗</span>
          <div><strong>Overview</strong><small>KPIs, quick actions, connectors to scans and packs</small></div>
        </div>

        <div class="policy-panel-item">
          <span class="mini-icon purple">⊞</span>
          <div><strong>Catalog</strong><small>Browse 200+ built-in policies by cloud, Kubernetes, IaC, identity, FinOps, AI, and more</small></div>
        </div>

        <div class="policy-panel-item">
          <span class="mini-icon orange">◇</span>
          <div><strong>Bundles</strong><small>Install an entire baseline (CIS, SOC 2, PCI DSS, HIPAA, Kubernetes hardening, …)</small></div>
        </div>

        <div class="policy-panel-item">
          <span class="mini-icon blue">▤</span>
          <div><strong>My policies</strong><small>Installed/custom policies: versions, assignments, tests, publish</small></div>
        </div>

        <div class="policy-panel-item">
          <span class="mini-icon red">▶</span>
          <div><strong>Evaluate</strong><small>Run a policy against a chosen target (stack/path) without waiting for a deploy</small></div>
        </div>

        <div class="policy-panel-item">
          <span class="mini-icon gray">◷</span>
          <div><strong>History</strong><small>Past evaluations</small></div>
        </div>
      </div>
    </section>

  </div>

  <section class="policy-info-card policy-domains-card">
    <span class="policy-info-icon green">◎</span>
    <div>
      <h2>Catalog domains (built-in)</h2>
      <p>AWS, Azure, GCP, Kubernetes, IaC, CI/CD, AI, identity, networking, FinOps, operations, containers.</p>
    </div>
  </section>

  <section class="policy-info-card policy-engines-card">
    <span class="policy-info-icon blue">⚙</span>
    <div>
      <h2>Engines</h2>
      <p>
        Policies can be expressed for engines such as OPA/Rego, Kyverno, CEL,
        Gatekeeper, Checkov, Trivy, and Axio-native rules. You pick an engine
        when creating a custom policy; catalog entries already have an engine.
      </p>
    </div>
  </section>

  <section class="policy-info-card policy-single-card">
    <span class="policy-info-icon orange">♢</span>
    <div>
      <h2>What you can do with a single policy</h2>

      <ul class="policy-check-list">
        <li>Install from catalog (creates an org copy you can assign).</li>
        <li>Assign to a scope so evaluations actually run.</li>
        <li>Test with saved test cases; <strong>publish</strong> a new version.</li>
        <li>Set enforcement (for example enforcing vs advisory) so the deploy gate knows whether to block.</li>
      </ul>

      <p>
        Installing a catalog policy does nothing until it is
        <strong class="green-text">assigned</strong> (directly or via a pack).
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
          <td class="purple-text">Evaluate in Policy Library</td>
          <td>On demand from the UI</td>
          <td>Pass/fail for that target</td>
        </tr>
        <tr>
          <td class="blue-text">Live scan</td>
          <td>On connected Git repos (if enabled)</td>
          <td>Findings + violations</td>
        </tr>
        <tr>
          <td class="red-text">Policy gate</td>
          <td>PLAN / APPLY</td>
          <td>Block, warn, or ignore per gate mode</td>
        </tr>
      </tbody>
    </table>

    <div class="policy-table-note">
      <span>ⓘ</span>
      <p>All three use the same policy definitions. The gate is the only one that can <strong>stop a deployment.</strong></p>
    </div>
  </section>

  <div class="policy-bottom-grid">

    <section class="policy-card policy-custom-card">
      <div class="policy-card-title">
        <span class="policy-icon policy-icon-purple">✎</span>
        <h2>Custom policies</h2>
      </div>

      <p>
        Admins can create a policy with name, engine, category, severity,
        and rule body (subject to <code>canCreatePolicy</code> in the UI).
      </p>

      <p>
        Prefer catalog policies for common CIS/cloud controls; use custom
        policies for org-specific rules.
      </p>

      <p>Keep versions: publish rather than silently editing production assignments.</p>
    </section>

    <section class="policy-card policy-roles-card">
      <div class="policy-card-title">
        <span class="policy-icon policy-icon-green">♧</span>
        <h2>Role presets (policy vs approval)</h2>
      </div>

      <p>
        Apply governance role presets from the API
        (<code>POST /organizations/:orgId/roles/governance-presets</code>)
        or as documented in enterprise governance.
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
            <td>No</td>
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
        This is how you implement <strong class="green-text">separation of duties</strong>
        without giving everyone ADMIN.
      </p>
    </section>

  </div>

</div>
