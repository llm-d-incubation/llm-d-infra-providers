# Contributing to llm-d-infra-providers

Thank you for your interest in contributing. This repository hosts community-owned infrastructure provisioning guides, tooling, and cluster readiness checks for [llm-d](https://github.com/llm-d/llm-d).

Please read the [Code of Conduct](CODE_OF_CONDUCT.md). Approvers are listed in [OWNERS](OWNERS).

## Ownership Model

Each provider lives under [`cloud-providers/<name>/`](cloud-providers/), [`gateway-providers/<name>/`](gateway-providers/), or [`storage-providers/<name>/`](storage-providers/) with its own `OWNERS` file and `README.md` entry point. Pull requests scoped to a provider sub-folder are reviewed and approved by that provider's owners. Root maintainers curate repository structure and shared conformance checks.

## Submitting a Pull Request

1. Fork the repository and work on a feature branch.
2. **Sign off your commits.** This project requires the [Developer Certificate of Origin](https://developercertificate.org/); use `git commit -s`.
3. Open a pull request with a concise description of what changed and why, linking the relevant issue.

## Security

Do **not** open a public issue for a security vulnerability. Follow [SECURITY.md](SECURITY.md).

## License

By contributing, you agree that your contributions will be licensed under the [Apache 2.0 License](LICENSE.md).
