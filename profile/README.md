<div align="center">
  <a href="https://prufyx.com">
    <img src="assets/prufyx-mark.svg" width="88" height="88" alt="Prufyx mark">
  </a>
  <h1>Prufyx</h1>
  <p><strong>Review configuration changes before a Kubernetes component upgrade.</strong></p>
  <p>Local, source-linked checks with explicit unknowns and replayable results.</p>
  <p>
    <a href="https://github.com/prufyx/prufyx-cli">Source</a> ·
    <a href="https://github.com/prufyx/prufyx-cli/releases/tag/v0.1.0-alpha.4">Community alpha.4</a> ·
    <a href="https://github.com/prufyx/prufyx-cli/blob/v0.1.0-alpha.4/cli/docs/community-checks.md">Checks and examples</a> ·
    <a href="https://prufyx.com">Website</a>
  </p>
</div>

## Two focused Community checks

Prufyx Community evaluates local inputs offline. It does not upload values or
observations, and it needs no account or hosted model.

| Check | Reviewed transition | What the result means |
| --- | --- | --- |
| cert-manager removed monitoring values | 1.20.3 → 1.21.1 | Finds three removed Helm settings in proposed merged JSON values and explains the migration. `PASS` covers only their absence; Helm remains the full target-schema check. |
| Prometheus declared Agent mode | 2.55.1 → 3.1.0 on exact reviewed Linux arm64/v8 images | Evaluates whether the declared mode is preserved from an optional minimized local observation to a proposed workload. It does not establish startup, applied runtime mode, data safety, remote-write behavior, rollback, or whole-upgrade compatibility. |

Every outcome is bound to its named claim. `BLOCKED` identifies a matching
constraint and remediation. `ATTENTION` and `UNKNOWN` keep missing or ambiguous
evidence visible. A scoped `PASS` never means that the whole upgrade is safe.
The CLI provides claim-specific exit codes for CI and a deterministic JSON
receipt that can be replayed with the original local input and digest.

## Start with the source

- [Read the command and input contracts](https://github.com/prufyx/prufyx-cli/blob/v0.1.0-alpha.4/cli/docs/community-checks.md).
- [Verify release provenance before execution](https://github.com/prufyx/prufyx-cli/blob/v0.1.0-alpha.4/cli/docs/signing-provenance.md).
- [Review the optional local collector boundary](https://github.com/prufyx/prufyx-cli/blob/v0.1.0-alpha.4/cli/docs/local-collection.md).
- [Build, test, and contribute](https://github.com/prufyx/prufyx-cli/blob/v0.1.0-alpha.4/CONTRIBUTING.md).

The Prometheus demo is a synthetic legacy demonstration. It does not use an
actual observation or carry compatibility authority.

## Contribute a transition

An actionable unsupported transition is useful feedback. Share the public
component, exact versions, relevant setting, upstream source, and a synthetic
reproduction. Keep customer configuration, cluster snapshots, credentials,
Secrets, private image paths, and sensitive logs private.

Prufyx is maintained by [Spas Atanasov](https://github.com/airstand) and licensed
under the [Apache License 2.0](https://github.com/prufyx/prufyx-cli/blob/v0.1.0-alpha.4/LICENSE).
[Report security issues privately](https://github.com/prufyx/prufyx-cli/blob/v0.1.0-alpha.4/SECURITY.md).

<p align="center"><strong>Evidence before confidence.</strong></p>
