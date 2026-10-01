<div align="center">
  <a href="https://prufyx.com">
    <img src="assets/prufyx-mark.svg" width="88" height="88" alt="Prufyx mark">
  </a>
  <h1>Prufyx</h1>
  <p><strong>Review configuration changes before a Kubernetes component upgrade.</strong></p>
  <p>Local, source-linked checks with explicit unknowns and replayable results.</p>
  <p>
    <a href="https://github.com/prufyx/prufyx">Source</a> ·
    <a href="https://github.com/prufyx/prufyx/blob/main/cli/docs/quickstart.md">Quickstart</a> ·
    <a href="https://github.com/prufyx/prufyx/blob/main/cli/docs/community-support-inventory.md">What is covered</a> ·
    <a href="https://prufyx.com">Website</a>
  </p>
</div>

## Upgrade checks with explicit unknowns

Prufyx evaluates local inputs offline. It does not upload values or
observations, and it needs no account or hosted model. Every rule is reviewed
by a person and cites the exact upstream commit and line range it relies on.
The current corpus covers Kubernetes API removals and reviewed transitions for
more than 60 CNCF and community projects.

Every outcome is bound to its named claim. `BLOCKED` identifies a matching
constraint and remediation. `UNKNOWN` keeps missing or ambiguous evidence
visible instead of guessing. A scoped `PASS` never means that the whole upgrade
is safe. The CLI provides exit codes for CI and a deterministic JSON receipt
that can be replayed with the original local input.

## Start with the source

- [Run your first check in five minutes](https://github.com/prufyx/prufyx/blob/main/cli/docs/quickstart.md).
- [Read the command and input contracts](https://github.com/prufyx/prufyx/blob/main/cli/docs/community-checks.md).
- [Verify release provenance before execution](https://github.com/prufyx/prufyx/blob/main/cli/docs/signing-provenance.md).
- [Review the optional local collector boundary](https://github.com/prufyx/prufyx/blob/main/cli/docs/local-collection.md).
- [Build, test, and contribute](https://github.com/prufyx/prufyx/blob/main/CONTRIBUTING.md).

## Contribute a transition

An actionable unsupported transition is useful feedback. Share the public
component, exact versions, relevant setting, upstream source, and a synthetic
reproduction. Keep customer configuration, cluster snapshots, credentials,
Secrets, private image paths, and sensitive logs private.

Prufyx is maintained by [Spas Atanasov](https://github.com/airstand). The source
code is licensed under the [GNU AGPL v3.0](https://github.com/prufyx/prufyx/blob/main/LICENSE) and the
reviewed knowledge data under [CC BY-SA 4.0](https://github.com/prufyx/prufyx/blob/main/DATA-LICENSE.md).
[Report security issues privately](https://github.com/prufyx/prufyx/blob/main/SECURITY.md).

<p align="center"><strong>Evidence before confidence.</strong></p>
