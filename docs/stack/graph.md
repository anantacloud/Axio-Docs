---
layout: default
title: Designer Graph Format
parent: Workflow Template
nav_order: 2
---

# Designer Graph Format

The **Designer Graph format** is an alternative YAML representation for Axio Workflow Templates.

Instead of defining the workflow as an ordered `steps` list, the Designer Graph format represents the workflow as a collection of **nodes** and **edges**.

This format is useful when workflows are created or maintained through a visual workflow designer.

## When to Use the Designer Graph Format

Use the Designer Graph format when you need to:

- Represent workflows visually
- Define explicit stage dependencies
- Model complex workflow relationships
- Connect stages using nodes and edges
- Map visual nodes to enterprise catalog stages
- Convert a visual workflow into the standard deployment-step format

A basic Designer Graph template looks like this:

```yaml
id: my-custom-template
name: My Custom Template
version: "1.0.0"

supportedIacEngines:
  - TERRAFORM

supportedOperations:
  - PLAN
  - APPLY

nodes:
  - key: checkout1
    type: SCRIPT
    name: Repository Checkout
    config:
      catalogStage: code-checkout

  - key: plan1
    type: PLAN
    name: Terraform Plan
    config:
      catalogStage: plan

edges:
  - from: checkout1
    to: plan1

_meta:
  workflowTemplateId: terraform
```

---

## Graph Structure

A Designer Graph contains three primary parts:

| Property | Purpose |
|---|---|
| `nodes` | Defines the individual workflow stages |
| `edges` | Defines relationships and execution dependencies |
| `_meta` | Stores additional designer metadata |

The workflow can be visualized as:

```text
┌──────────────────┐
│ Repository       │
│ Checkout         │
└────────┬─────────┘
         │
         ▼
┌──────────────────┐
│ Terraform Plan   │
└──────────────────┘
```

The edge between the nodes determines the execution order.

---

# Nodes

Each item in the `nodes` array represents one stage or action in the workflow.

Example:

```yaml
nodes:
  - key: checkout1
    type: SCRIPT
    name: Repository Checkout
    config:
      catalogStage: code-checkout
```

A node generally contains:

- `key`
- `type`
- `name`
- `config`

## Node `key`

The `key` is the unique identifier for a node within the workflow graph.

```yaml
key: checkout1
```

It is used by edges to establish relationships between nodes.

For example:

```yaml
edges:
  - from: checkout1
    to: plan1
```

Here, `checkout1` and `plan1` must correspond to existing node keys.

### Node Key Guidelines

Use short, descriptive, unique keys:

```yaml
key: checkout1
key: validate1
key: plan1
key: approval1
key: apply1
```

Avoid using the same key for multiple nodes.

---

# Node Type

The `type` identifies the general kind of workflow node.

Example:

```yaml
type: PLAN
```

Common node types include:

- `VALIDATE`
- `PLAN`
- `APPLY`
- `APPROVAL`
- `SCRIPT`

Example:

```yaml
nodes:
  - key: validate1
    type: VALIDATE
    name: Validate Infrastructure

  - key: plan1
    type: PLAN
    name: Terraform Plan

  - key: approval1
    type: APPROVAL
    name: Production Approval

  - key: apply1
    type: APPLY
    name: Terraform Apply
```

The node type can provide a default mapping to a workflow stage.

For precise control, use `config.catalogStage`.

---

# Node Name

The `name` property provides a human-readable label for the node.

```yaml
name: Terraform Plan
```

The name is primarily intended for the workflow designer and UI.

Good node names describe the action clearly:

```yaml
name: Repository Checkout
name: Validate Terraform
name: Terraform Plan
name: Production Approval
name: Terraform Apply
```

---

# Catalog Stage Mapping

The `config.catalogStage` property explicitly maps a node to an enterprise stage catalog ID.

Example:

```yaml
config:
  catalogStage: code-checkout
```

Another example:

```yaml
config:
  catalogStage: plan
```

This is useful when the visual node type does not provide enough information to identify the exact catalog stage.

## Why Use `catalogStage`?

A node type such as:

```yaml
type: SCRIPT
```

may represent different kinds of script-based stages.

By specifying:

```yaml
config:
  catalogStage: code-checkout
```

the workflow explicitly identifies the catalog stage that should be used.

### Recommended Pattern

For important workflow stages, explicitly specify the catalog stage:

```yaml
nodes:
  - key: checkout1
    type: SCRIPT
    name: Repository Checkout
    config:
      catalogStage: code-checkout

  - key: plan1
    type: PLAN
    name: Terraform Plan
    config:
      catalogStage: plan
```

---

# Edges

The `edges` array defines dependencies between workflow nodes.

Example:

```yaml
edges:
  - from: checkout1
    to: plan1
```

This means:

```text
checkout1 → plan1
```

The `plan1` node can execute only after the `checkout1` node completes.

## Multiple Edges

A node can have multiple outgoing or incoming relationships.

Example:

```yaml
edges:
  - from: validate1
    to: format1

  - from: validate1
    to: lint1

  - from: validate1
    to: security1
```

This creates a fan-out:

```text
                 ┌── Format
                 │
Validate ────────┼── Lint
                 │
                 └── Security
```

A later node can depend on all three:

```yaml
edges:
  - from: format1
    to: plan1

  - from: lint1
    to: plan1

  - from: security1
    to: plan1
```

The resulting graph is:

```text
                 ┌── Format ──────┐
                 │                │
Validate ────────┼── Lint ────────┼── Plan
                 │                │
                 └── Security ────┘
```

---

# Sequential Workflow Example

A simple deployment workflow can be represented as a graph:

```yaml
id: terraform-basic
name: Terraform Basic Deployment

version: "1.0.0"

supportedIacEngines:
  - TERRAFORM

supportedOperations:
  - PLAN
  - APPLY

nodes:
  - key: checkout1
    type: SCRIPT
    name: Repository Checkout
    config:
      catalogStage: code-checkout

  - key: validate1
    type: VALIDATE
    name: Validate Terraform
    config:
      catalogStage: validate

  - key: plan1
    type: PLAN
    name: Terraform Plan
    config:
      catalogStage: plan

  - key: approval1
    type: APPROVAL
    name: Deployment Approval
    config:
      catalogStage: approval

  - key: apply1
    type: APPLY
    name: Terraform Apply
    config:
      catalogStage: apply

edges:
  - from: checkout1
    to: validate1

  - from: validate1
    to: plan1

  - from: plan1
    to: approval1

  - from: approval1
    to: apply1

_meta:
  workflowTemplateId: terraform
```

The resulting workflow is:

```text
Checkout
   ↓
Validate
   ↓
Plan
   ↓
Approval
   ↓
Apply
```

---

# Parallel Workflow Example

Designer Graphs can also represent workflows with multiple branches.

Example:

```yaml
id: terraform-secure-deploy
name: Terraform Secure Deployment

version: "1.0.0"

supportedIacEngines:
  - TERRAFORM

supportedOperations:
  - PLAN
  - APPLY

nodes:
  - key: checkout1
    type: SCRIPT
    name: Repository Checkout
    config:
      catalogStage: code-checkout

  - key: validate1
    type: VALIDATE
    name: Validate
    config:
      catalogStage: validate

  - key: format1
    type: SCRIPT
    name: Format Check
    config:
      catalogStage: format

  - key: lint1
    type: SCRIPT
    name: Lint
    config:
      catalogStage: lint

  - key: security1
    type: SCRIPT
    name: Security Scan
    config:
      catalogStage: security

  - key: plan1
    type: PLAN
    name: Terraform Plan
    config:
      catalogStage: plan

edges:
  - from: checkout1
    to: validate1

  - from: validate1
    to: format1

  - from: validate1
    to: lint1

  - from: validate1
    to: security1

  - from: format1
    to: plan1

  - from: lint1
    to: plan1

  - from: security1
    to: plan1

_meta:
  workflowTemplateId: terraform
```

The graph represents:

```text
                    ┌── Format ────┐
                    │              │
Checkout → Validate ├── Lint ──────┼→ Plan
                    │              │
                    └── Security ──┘
```

The graph has a **fan-out** after validation and a **fan-in** before planning.

---

# `_meta` Configuration

The `_meta` section stores designer-specific metadata.

Example:

```yaml
_meta:
  workflowTemplateId: terraform
```

The `workflowTemplateId` can identify the underlying workflow template or designer context.

Keep `_meta` separate from the main workflow definition.

Example:

```yaml
nodes:
  ...

edges:
  ...

_meta:
  workflowTemplateId: terraform
```

---

# Node Type and Catalog Stage

When `catalogStage` is not specified, Axio can use the default stage mapping associated with the node `type`.

For example:

```yaml
nodes:
  - key: plan1
    type: PLAN
    name: Terraform Plan
```

The `PLAN` node type can map to the default `plan` stage.

For explicit mapping:

```yaml
nodes:
  - key: plan1
    type: PLAN
    name: Terraform Plan
    config:
      catalogStage: plan
```

The explicit `catalogStage` value takes precedence for identifying the catalog stage.

> **Best practice:** Use `config.catalogStage` when the exact enterprise catalog stage should be explicit and unambiguous.

---

# Graph Conversion

Axio converts Designer Graph YAML into the internal steps-based workflow representation.

For example, this graph:

```yaml
nodes:
  - key: checkout1
    type: SCRIPT
    config:
      catalogStage: code-checkout

  - key: plan1
    type: PLAN
    config:
      catalogStage: plan

edges:
  - from: checkout1
    to: plan1
```

can be interpreted as:

```yaml
steps:
  - code-checkout
  - plan
```

A more complex graph:

```text
              ┌── format ────┐
              │              │
checkout → validate ──┼── lint ──────┼→ plan
              │              │
              └── security ──┘
```

can be converted into:

```yaml
steps:
  - code-checkout
  - validate
  - parallel:
      - format
      - lint
      - security
  - plan
```

This allows the visual representation and deployment representation to describe the same workflow.

---

# Graph Integrity

Designer Graph templates must form a valid workflow graph.

Axio validates:

- Node keys are unique
- Edges reference existing nodes
- The graph contains valid dependencies
- The graph does not contain cycles
- Nodes are connected to the workflow
- Catalog stages are valid
- The graph can be converted into executable workflow steps

## Avoid Duplicate Node Keys

Incorrect:

```yaml
nodes:
  - key: plan1
    type: PLAN

  - key: plan1
    type: PLAN
```

Each node must have a unique key.

Correct:

```yaml
nodes:
  - key: plan1
    type: PLAN

  - key: plan2
    type: PLAN
```

---

# Avoid Invalid Edges

An edge must reference existing node keys.

Incorrect:

```yaml
nodes:
  - key: checkout1
    type: SCRIPT

edges:
  - from: checkout1
    to: plan1
```

Here, `plan1` does not exist.

Correct:

```yaml
nodes:
  - key: checkout1
    type: SCRIPT

  - key: plan1
    type: PLAN

edges:
  - from: checkout1
    to: plan1
```

---

# Avoid Cycles

A workflow graph must not contain circular dependencies.

Incorrect:

```yaml
edges:
  - from: checkout1
    to: validate1

  - from: validate1
    to: plan1

  - from: plan1
    to: checkout1
```

This creates:

```text
Checkout → Validate → Plan
    ↑                 │
    └─────────────────┘
```

The cycle prevents the graph from representing a valid sequential workflow.

---

# Designer Graph Best Practices

### Use Unique Node Keys

```yaml
key: checkout1
key: validate1
key: plan1
key: approval1
key: apply1
```

### Use Clear Node Names

```yaml
name: Repository Checkout
name: Terraform Validation
name: Terraform Plan
name: Production Approval
name: Terraform Apply
```

### Explicitly Map Important Stages

```yaml
config:
  catalogStage: plan
```

### Keep Dependencies Simple

Prefer clear relationships:

```text
Checkout
   ↓
Validate
   ↓
Plan
   ↓
Approval
   ↓
Apply
```

Use parallel branches only when stages are genuinely independent.

### Avoid Unnecessary Cycles

Every node should have a clear place in the execution graph.

---

# Designer Graph vs Deployment Template

Both YAML formats describe Workflow Templates, but they are optimized for different purposes.

| Feature | Deployment Template | Designer Graph |
|---|---|---|
| Representation | Steps | Nodes and edges |
| Best for | Git and configuration | Visual workflow design |
| Sequential stages | Yes | Yes |
| Parallel stages | `parallel` block | Multiple edges |
| Dependencies | Step order | Explicit edges |
| Catalog mapping | Stage ID directly | `config.catalogStage` |
| Visual editing | Limited | Designed for visual representation |
| Conversion | Native format | Converted to steps |

For most Git-based workflows, the **Deployment Template format is recommended**.

For workflows designed visually, the **Designer Graph format** provides explicit node and dependency information.

---

# Complete Designer Graph Example

```yaml
id: terraform-production
name: Terraform Production Workflow

version: "1.0.0"
status: ACTIVE

supportedCloudProviders:
  - AWS

supportedIacEngines:
  - TERRAFORM

supportedOperations:
  - PLAN
  - APPLY

nodes:
  - key: checkout1
    type: SCRIPT
    name: Repository Checkout
    config:
      catalogStage: code-checkout

  - key: validate1
    type: VALIDATE
    name: Validate Terraform
    config:
      catalogStage: validate

  - key: format1
    type: SCRIPT
    name: Format Check
    config:
      catalogStage: format

  - key: lint1
    type: SCRIPT
    name: Lint
    config:
      catalogStage: lint

  - key: security1
    type: SCRIPT
    name: Security Scan
    config:
      catalogStage: security

  - key: plan1
    type: PLAN
    name: Terraform Plan
    config:
      catalogStage: plan

  - key: approval1
    type: APPROVAL
    name: Production Approval
    config:
      catalogStage: approval

  - key: apply1
    type: APPLY
    name: Terraform Apply
    config:
      catalogStage: apply

  - key: notify1
    type: SCRIPT
    name: Deployment Notification
    config:
      catalogStage: notification

edges:
  - from: checkout1
    to: validate1

  - from: validate1
    to: format1

  - from: validate1
    to: lint1

  - from: validate1
    to: security1

  - from: format1
    to: plan1

  - from: lint1
    to: plan1

  - from: security1
    to: plan1

  - from: plan1
    to: approval1

  - from: approval1
    to: apply1

  - from: apply1
    to: notify1

_meta:
  workflowTemplateId: terraform
```

This produces the following logical workflow:

```text
                         ┌── Format ────┐
                         │              │
Checkout → Validate ─────┼── Lint ──────┼→ Plan → Approval → Apply → Notify
                         │              │
                         └── Security ──┘
```



