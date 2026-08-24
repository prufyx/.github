<div align="center">
  <a href="https://prufyx.com">
    <img src="assets/prufyx-mark.svg" width="88" height="88" alt="Prufyx mark">
  </a>
  <h1>Prufyx</h1>
  <p><strong>Know what will break before the cluster changes.</strong></p>
  <p>Kubernetes change validation for the bundle you actually run.</p>
  <p>
    <a href="https://prufyx.com">Website</a> ·
    <a href="https://prufyx.com/#waitlist">Private preview</a> ·
    <a href="mailto:hello@prufyx.com">Contact</a>
  </p>
</div>

## Kubernetes changes are bundle problems

A Kubernetes upgrade rarely changes Kubernetes alone. It changes a system of CNI, CSI, DNS, ingress, admission, observability, GitOps, operating-system, runtime, provider, version, and configuration choices.

Prufyx is being built to evaluate the exact transition:

```text
validate(current_bundle, proposed_bundle, policy_profile, knowledge_revision)
```

The result is scoped: which claims pass, what blocks the change, what remains unknown, and which source or reproducible test supports each conclusion.

## What we are building

| Capability | Purpose | Status |
| --- | --- | --- |
| Local snapshot and inspection | Capture a minimized, content-addressed description of the relevant environment | Early local tooling |
| Configuration-aware compatibility graph | Bind version claims to deployment modes, options, dependencies, and environment predicates | Planned |
| Source-linked knowledge bundles | Preserve exact release-note, changelog, documentation, and test provenance | Planned |
| Reproducible validation backends | Test high-impact component and Kubernetes transitions against declared fidelity boundaries | Planned |
| Replayable TestRecords | Record inputs, assertions, artifacts, evidence, and invalidation conditions | Planned |
| Release workflow guardrails | Return a scoped decision to customer-owned CI/CD and GitOps workflows | Enterprise, planned |

## How a decision earns trust

```text
upstream source + matching configuration predicate + reproduced test
                              |
                              v
                    scoped compatibility claim
```

- `PASS` applies only to the named claim and evidence policy.
- `BLOCKED` includes the matching constraint and a concrete remediation.
- `UNKNOWN` identifies the missing evidence and the next bounded test.
- A model may extract, retrieve, compare, and explain. It does not authorize a release.
- Final apply, sync, promotion, and rollout remain customer-owned.

## Design principles

- Local-first and disconnected-capable evaluation
- Exact current-bundle to proposed-bundle comparison
- Configuration and deployment mode, not versions alone
- Explicit unknowns instead of inferred confidence
- Source spans and test receipts for material claims
- No raw Secrets, credentials, or unrestricted cluster objects
- Independently replayable decisions without a hosted model

## Current status

Prufyx is in early development. Public repositories will open in stages. Today we are validating the product with concrete Kubernetes and component transitions, not claiming universal coverage or production safety.

If your team operates a Kubernetes fleet and spends days researching or repeating upgrade validation, [bring us one real change](https://prufyx.com/#waitlist). We want to compare Prufyx with the process you use today.

<p align="center"><strong>Evidence before confidence.</strong></p>
