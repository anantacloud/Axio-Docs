---
layout: default
title: Runner – Overview
parent: Runner
nav_order: 1
has_toc: false
permalink: /axio/administration/runner/overview-runner/
---

<link rel="stylesheet" href="{{ '/assets/css/runners-overview.css' | relative_url }}">

<div class="runners-doc">

  <h1>Runners – Overview</h1>

  <p class="intro">
    This page helps you manage and monitor all self-hosted runners in your organization.
    You can view fleet summary, check runner status, and perform actions such as
    updating labels, entering maintenance, or removing offline runners.
  </p>

  <section class="runner-metrics" aria-label="Fleet summary">

    <div class="metric-card">
      <div class="metric-icon metric-blue">♧</div>
      <div>
        <div class="metric-label">Registered</div>
        <div class="metric-value">12</div>
      </div>
    </div>

    <div class="metric-card">
      <div class="metric-icon metric-green"></div>
      <div>
        <div class="metric-label">Online</div>
        <div class="metric-value">8</div>
      </div>
    </div>

    <div class="metric-card">
      <div class="metric-icon metric-red"></div>
      <div>
        <div class="metric-label">Offline</div>
        <div class="metric-value">4</div>
      </div>
    </div>

    <div class="metric-card">
      <div class="metric-icon metric-blue gear">⚙</div>
      <div>
        <div class="metric-label">Running</div>
        <div class="metric-value">3</div>
      </div>
    </div>

    <div class="metric-card">
      <div class="metric-icon metric-purple">◷</div>
      <div>
        <div class="metric-label">Idle</div>
        <div class="metric-value">5</div>
      </div>
    </div>

    <div class="metric-card">
      <div class="metric-icon metric-blue chart">◔</div>
      <div>
        <div class="metric-label">Utilization</div>
        <div class="metric-value">37%</div>
      </div>
    </div>

    <div class="metric-card">
      <div class="metric-icon metric-orange">↑</div>
      <div>
        <div class="metric-label">Outdated</div>
        <div class="metric-value">2</div>
      </div>
    </div>

  </section>

  <section class="runner-alert">

    <div class="alert-icon">!</div>

    <div>
      <div class="alert-title">2 runners are outdated or blocked</div>

      <div class="alert-text">
        Some runners are using deprecated or blocked agent versions.
        Please review and update them to ensure smooth operation.
      </div>
    </div>

  </section>

  <section class="cleanup-panel">

    <div class="cleanup-icon">▣</div>

    <div>
      <div class="cleanup-title">Offline runner cleanup</div>

      <div class="cleanup-text">
        Remove runners that are offline and no longer in use from your organization.
      </div>
    </div>

  </section>

  <section class="inventory">

    <h2>Runner inventory</h2>

    <p class="inventory-description">
      The following table lists all registered runners in your organization.
    </p>

    <div class="table-wrapper">

      <table>

        <thead>
          <tr>
            <th>Runner ID</th>
            <th>Name</th>
            <th>Hostname</th>
            <th>Execution profile</th>
            <th>Scope name</th>
            <th>Version</th>
            <th>Registered</th>
            <th>Last heartbeat</th>
          </tr>
        </thead>

        <tbody>

          <tr>
            <td>axrun_1a2b3c</td>
            <td>runner-prod-1</td>
            <td>ip-172-31-1-135</td>
            <td>Linux · Docker</td>
            <td>Acme Corporation</td>
            <td>
              v2.3.1
              <span class="badge latest">Latest</span>
            </td>
            <td>Sep 12, 2026 10:24 AM</td>
            <td>2 minutes ago</td>
          </tr>

          <tr>
            <td>axrun_3c4d5e</td>
            <td>runner-ci-1</td>
            <td>runner-01</td>
            <td>Linux · Process</td>
            <td>Axio</td>
            <td>
              v2.3.0
              <span class="badge update">Update</span>
            </td>
            <td>Sep 10, 2026 02:11 PM</td>
            <td>30 seconds ago</td>
          </tr>

          <tr>
            <td>axrun_5e6f7g</td>
            <td>runner-k8s-1</td>
            <td>axio-runner-7</td>
            <td>Kubernetes</td>
            <td>prod</td>
            <td>
              v2.3.1
              <span class="badge latest">Latest</span>
            </td>
            <td>Sep 08, 2026 11:45 AM</td>
            <td>1 minute ago</td>
          </tr>

          <tr>
            <td>axrun_7g8h9i</td>
            <td>runner-dev-1</td>
            <td>ip-172-31-5-22</td>
            <td>Linux · Process</td>
            <td>dev-team</td>
            <td>
              v2.2.0
              <span class="badge deprecated">Deprecated</span>
            </td>
            <td>Aug 28, 2026 09:12 AM</td>
            <td>3 days ago</td>
          </tr>

          <tr>
            <td>axrun_9i0j1k</td>
            <td>runner-test-1</td>
            <td>ip-172-31-6-44</td>
            <td>Linux · Docker</td>
            <td>Trustary</td>
            <td>
              v2.3.1
              <span class="badge latest">Latest</span>
            </td>
            <td>Aug 20, 2026 04:20 PM</td>
            <td>5 minutes ago</td>
          </tr>

        </tbody>

      </table>

    </div>

  </section>

</div>