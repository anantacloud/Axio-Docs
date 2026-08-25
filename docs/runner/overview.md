---
layout: default
title: Overview 
parent: Runner
nav_order: 1
---


# Axio Runner Overview

Axio Runner is a lightweight, secure, outbound-only execution agent that runs in your environment, connects to the Axio Control Plane, picks up workloads, executes them securely, streams logs, and reports execution status.

It provides the execution layer between your infrastructure and the Axio platform.

---

## What is Axio Runner?

The Axio Enterprise Runner is an execution agent designed to run workloads on infrastructure managed by the customer or by Axio.

### Core capabilities

- Secure registration and authentication
- Workload polling and lease-based execution
- Machine, Docker, and Kubernetes executors
- Runner groups and pools
- Autoscaling and fleet management
- Crash recovery and automatic reconnection
- Structured logging and live log streaming
- CPU, memory, uptime, and execution telemetry
- Health checks and diagnostics
- Artifact upload and download
- Secure secret injection
- Offline resilience and local job history
- Plugin and executor extensibility
- Provider-hosted execution through `axio-*` labels

---

## Runner Types

Axio supports two runner models.

### Self-Hosted Runners

Self-hosted runners run on infrastructure provisioned and operated by the customer.

**Customer responsibilities:**

- Provision the infrastructure.
- Install and configure the runner.
- Manage runner groups and pools.
- Manage labels and capacity.
- Maintain the host and executor dependencies.
- Control networking and security.

Example workload targeting:

```yaml
runner:
  labels:
    - production
    - linux
```

Self-hosted runners use customer-defined labels and never receive reserved `axio-*` labels.

### Provider-Hosted Runners

Provider-hosted runners are provisioned and operated by Axio.

They are similar to GitHub-hosted runners: tenants select a hosted runner label without seeing the underlying infrastructure.

Examples:

```yaml
runner:
  strategy: provider-runner
  providerRunner: axio-linux
```

or:

```yaml
runner:
  labels:
    - axio-linux
```

Common hosted labels include:

| Label | Purpose |
|---|---|
| `axio-linux` | Linux runner |
| `axio-linux-x86` | Linux x86 runner |
| `axio-linux-arm64` | Linux ARM64 runner |
| `axio-windows` | Windows runner |
| `axio-docker` | Docker-based runner |
| `axio-kubernetes` | Kubernetes-based runner |
| `axio-gpu` | GPU-capable runner |

Provider runners are invisible to tenants. Tenants reference the hosted labels on workloads rather than managing the provider fleet.

---

## Self-Hosted vs Provider-Hosted

| | Self-Hosted | Provider-Hosted |
|---|---|---|
| Infrastructure | Customer | Axio |
| Ownership | Customer | Axio/provider |
| Fleet visibility | Visible to customer | Hidden from tenant |
| Targeting | Customer labels | `axio-*` labels |
| Registration | Customer registration token | Internal provider registration |
| Scaling | Customer/configured pool | Axio-managed fleet |
| Infrastructure cost | Customer responsibility | Subscription-based metering |
| Infrastructure management | Customer | Axio |

---


### Execution flow

```text
Workload
   ↓
Runner Selection
   ↓
Queue / Scheduler
   ↓
Lease
   ↓
Runner
   ↓
Executor
   ↓
Workspace + Secrets + Artifacts
   ↓
Execution
   ↓
Logs + Telemetry + Status
   ↓
Control Plane
```

---

## Runner Agent Responsibilities

The runner performs the following core operations:

1. **Register** with the Axio Control Plane.
2. **Authenticate** using its runner credential.
3. **Send heartbeats** containing status and telemetry.
4. **Poll for workloads** or receive work through the communication layer.
5. **Reserve workloads** using the lease mechanism.
6. **Execute workloads** using the configured executor.
7. **Stream logs** to the Control Plane.
8. **Upload/download artifacts** when required.
9. **Report completion** with status, duration, and exit information.
10. **Recover from transient failures** and reconnect automatically.
11. **Expose health and diagnostics** for operations.
12. **Participate in fleet scheduling** when managed as part of a runner pool.

---

# Runner Agent Components

The runner is organized into independent modules:

```text
runner/
├── cmd/            CLI, configure, daemon, service helpers
├── config/         YAML schema, loading, validation, saving
├── registration/   Registration and token exchange
├── authentication/ JWT / credential handling
├── heartbeat/      Periodic status and telemetry
├── polling/        Resilient work polling
├── worker/         Job lifecycle state machine
├── execution/      Executor interface and implementations
├── logs/           Structured log streaming
├── telemetry/      CPU, memory, uptime collection
├── installer/      configure.sh, run.sh, svc.sh, uninstall.sh
├── api/            Control Plane REST client
└── crypto/         Checksums, signatures, secure random, HMAC
```

The runner depends on:

```text
shared/api-contracts/
```

and is designed to remain independent from Control Plane implementation classes.

---

# Key Benefits

## Secure

- Outbound-only communication model
- TLS verification enabled by default
- Secure runner credentials
- Token and secret redaction
- Role and ownership boundaries
- Reserved `axio-*` label protection
- Isolated execution workspaces

## Scalable

- Runner pools
- Multiple executors
- Autoscaling
- Ephemeral runners
- Dynamic runners
- Fleet-wide scheduling
- Queue-based workload routing

## Reliable

- Heartbeat monitoring
- Lease-based execution
- Crash recovery
- Automatic workload requeue
- Network retries and backoff
- Offline resilience
- Graceful draining and shutdown

## Flexible

- Machine execution
- Docker execution
- Kubernetes execution
- Plugin framework
- Artifact management
- Configurable communication transports
- Customer-hosted and provider-hosted execution

## Observable

- Structured logs
- Live log streaming
- CPU and memory telemetry
- Execution metrics
- Health endpoint
- Diagnostics CLI
- Job history
- Fleet health and capacity metrics

---

# Enterprise Runner Capabilities

The Axio Runner evolves through multiple capability phases.

| Phase | Focus |
|---|---|
| Phase 1 | Registration, authentication, heartbeat, polling, worker, machine execution |
| Phase 2 | CLI, packaging, service management, diagnostics, health, secure credentials |
| Phase 3 | Automatic updates, artifacts, live logs, secure cache, plugins, rollback |
| Phase 4 | Machine, Docker, Kubernetes executor framework |
| Phase 5 | Fleet management, scheduling, queues, leases, autoscaling, provider runners |

---

# Where the Runner Fits

```text
                 AXIO CONTROL PLANE
                        │
           ┌────────────┴────────────┐
           │                         │
    Customer Hosted             Provider Hosted
           │                         │
      Customer Pools              Axio Fleet
           │                         │
    ┌──────┼──────┐           ┌──────┼──────┐
    │      │      │           │      │      │
  Linux  Docker  K8s        Linux  Windows  GPU
    │      │      │           │      │      │
 Customer Customer Customer  axio-* axio-*  axio-*
  Labels   Labels   Labels    Labels Labels Labels
```

### Choose Self-Hosted when:

- Workloads require customer-controlled infrastructure.
- Workloads need private network access.
- Custom host tooling is required.
- Compliance requires infrastructure ownership.
- Customer controls scaling and infrastructure.

### Choose Provider-Hosted when:

- Workloads should run on Axio-managed infrastructure.
- Customers do not want to manage runner infrastructure.
- Hosted execution is enabled by subscription.
- Workloads can use Axio's supported hosted environments.

---

# Explore More

The Runner documentation is organized into focused guides:

- **Runner Architecture** — registration, lifecycle, worker, communication, and internal modules.
- **Executors & Execution** — Machine, Docker, Kubernetes, workspace, secrets, and artifacts.
- **Operations Guide** — CLI, configuration, service management, health, diagnostics, and logging.
- **Deployment Guide** — Linux, Docker, Kubernetes, autoscaling, lifecycle modes, and crash recovery.
- **Fleet Guide** — pools, queues, leases, scheduling, capacity, and autoscaling.
- **Runner Types** — self-hosted vs provider-hosted runners.
- **Runner Security** — ownership, reserved labels, provider isolation, and registration security.
- **Hosted Runner Testing** — end-to-end testing of Axio-managed runners.

---

## Summary

Axio Runner is the execution foundation of the Axio platform.

It connects the Control Plane to execution infrastructure while providing:

```text
Secure Registration
        ↓
Workload Scheduling
        ↓
Lease-Based Assignment
        ↓
Runner Execution
        ↓
Logs + Artifacts + Telemetry
        ↓
Completion + Recovery
```

Whether the infrastructure is **customer-managed** or **Axio-managed**, the runner provides a consistent execution model with enterprise security, scalability, observability, and operational controls.
