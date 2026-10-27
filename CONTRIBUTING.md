# Contributing to llm-d-infra-providers

Thank you for your interest in contributing. This repository hosts community-owned infrastructure provisioning guides, tooling, and cluster readiness checks for [llm-d](https://github.com/llm-d/llm-d).

Please read the [Code of Conduct](CODE_OF_CONDUCT.md). Repository approvers are listed in [OWNERS](OWNERS).

## Ownership Model

Each provider lives under [`cloud-providers/<name>/`](cloud-providers/), [`gateway-providers/<name>/`](gateway-providers/), or [`storage-providers/<name>/`](storage-providers/) with its own `OWNERS` file and `README.md` entry point. Pull requests scoped to a provider sub-folder are reviewed and approved by that provider's owners. Repository approvers curate repository structure and the shared conformance framework. See [GOVERNANCE.md](GOVERNANCE.md).

## Submitting a Pull Request

1. Fork the repository and work on a feature branch.
2. **Sign off your commits.** This project requires the [Developer Certificate of Origin](DCO); use `git commit -s`.
3. Open a pull request with a concise description of what changed and why, linking the relevant issue.

## Adding a new provider

Create `cloud-providers/<name>/` (or `gateway-providers/<name>/`, `storage-providers/<name>/`) containing at minimum:

1. **`OWNERS`** - at least one approver. Owners review all PRs for the sub-folder and are reachable in llm-d Slack `#sig-installation`.
2. **`README.md`** - the entry point. It must state:
   * Supported machine shapes / accelerators and version floors.
   * The provisioning methods offered (docs, scripts, IaC, AI skill) and where they live. External links (Terraform registry, vendor repo) are acceptable; this repository is the discovery entry point.
   * The conformance profiles the tooling is qualified against, with evidence (see [GOVERNANCE.md](GOVERNANCE.md), "Quality bar").
3. **At least one provisioning method** that produces a cluster passing `conformance/bin/llmd-infra-check --profile <claimed profile> --microtests`.

Use [`cloud-providers/gke/`](cloud-providers/gke/) as the reference layout:

```
cloud-providers/<name>/
  OWNERS
  README.md                 # entry point: methods, coverage matrix, qualification
  docs/                     # guided documentation
  scripts/                  # deterministic provisioning scripts / IaC
  skills/                   # AI skills (optional)
```

## Contributing conformance checks

Checks live under `conformance/checks/<scope>/` where `<scope>` is `common` or a provider name. Each check is a self-contained executable script with a metadata header; see [conformance/README.md](conformance/README.md#check-contract) for the contract. Provider-specific checks are reviewed by the provider's owners plus one repository approver (the framework contract must stay portable to core llm-d).

New dimension keys or values must be proposed to the llm-d maintainers first (the vocabulary is shared with guides, CI, and benchmarking), then added to [conformance/dimensions.yaml](conformance/dimensions.yaml).

## Style

* Shell scripts: `bash`, `set -euo pipefail`, pass `shellcheck`.
* Scripts that create cloud resources must print what they are about to create and the target project/region before doing it, and must be idempotent or fail fast with a clear message on conflict.
* Kubernetes manifests: plain YAML, no templating unless necessary; parameterize via environment variables consumed by a wrapper script.

## Security

Do **not** open a public issue for a security vulnerability. Follow [SECURITY.md](SECURITY.md).

## License

By contributing, you agree that your contributions will be licensed under the [Apache 2.0 License](LICENSE.md).
