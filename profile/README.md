<div align="center">
  <a href="https://prufyx.com">
    <img src="assets/prufyx-mark.svg" width="88" height="88" alt="Prufyx mark">
  </a>
  <h1>Prufyx</h1>
  <p><strong>Check the declared mode before you upgrade Prometheus.</strong></p>
  <p>Experimental, local-first compatibility checks with explicit evidence boundaries.</p>
  <p>
    <a href="https://prufyx.com">Website</a> ·
    <a href="https://github.com/prufyx/prufyx-cli">Source</a> ·
    <a href="https://github.com/prufyx/prufyx-cli/releases/tag/v0.1.0-alpha.3">v0.1.0-alpha.3</a> ·
    <a href="https://github.com/prufyx/prufyx-cli/blob/v0.1.0-alpha.3/CONTRIBUTING.md">Contribute</a>
  </p>
</div>

## First public Community alpha

Prufyx CLI v0.1.0-alpha.3 answers one bounded question: does an exact proposed Prometheus 3.1.0 declaration preserve the observed declared Agent or Server mode from Prometheus 2.55.1?

The released slice accepts only the reviewed Linux `arm64/v8` image manifests and exact proposed declaration grammar. It returns a scoped `PASS`, `ATTENTION`, or `UNKNOWN`. Every completed assessment keeps the whole-upgrade aggregate `UNKNOWN` and exits `11`.

Try the checked no-cluster synthetic demonstration with Git, Go 1.26.8 or newer, and Python 3 installed:

```sh
git clone https://github.com/prufyx/prufyx-cli.git
cd prufyx-cli
git checkout v0.1.0-alpha.3
./examples/prometheus-mode/run.sh
```

Expected scoped output:

```text
PASS      current=Agent proposed=Agent aggregate=UNKNOWN exit=11
ATTENTION current=Agent proposed=Server aggregate=UNKNOWN exit=11
UNKNOWN   current=Agent proposed=unresolved aggregate=UNKNOWN exit=11
```

The demonstration is explicitly synthetic and non-authoritative. It uses no cluster, account, network, model, or clock. Real read-only collection is a separate opt-in path.

## Exact boundary

- `PASS` covers declared mode preservation for the exact reviewed transition.
- The CLI does not prove process startup, applied runtime mode, data safety, remote-write behavior, rollback, or whole-upgrade compatibility.
- Unsupported versions, architectures, images, wrappers, arguments, and incomplete evidence remain `UNKNOWN` after valid input admission.
- Invalid or substituted input bytes are integrity errors.
- Evaluation stays local. The CLI does not apply, patch, delete, promote, or roll out a workload.

Read the [Prometheus mode contract](https://github.com/prufyx/prufyx-cli/blob/v0.1.0-alpha.3/cli/docs/prometheus-mode.md), [security policy](https://github.com/prufyx/prufyx-cli/blob/v0.1.0-alpha.3/SECURITY.md), and [contribution guide](https://github.com/prufyx/prufyx-cli/blob/v0.1.0-alpha.3/CONTRIBUTING.md).

Prufyx is maintained by Spas Atanasov and released under the [Apache License 2.0](https://github.com/prufyx/prufyx-cli/blob/v0.1.0-alpha.3/LICENSE).

<p align="center"><strong>Evidence before confidence.</strong></p>
