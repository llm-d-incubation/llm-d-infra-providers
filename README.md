# llm-d-infra-providers

Community-owned infrastructure provisioning tooling and guides for preparing Kubernetes clusters to run [llm-d](https://github.com/llm-d/llm-d).

## Purpose and Goal

Setting up an environment for `llm-d` involves two layers:

1. **Infrastructure provisioning**: preparing a Kubernetes cluster with hardware accelerators, high-performance networking (RDMA, RoCE, InfiniBand), device and DRA drivers, Gateway API, and storage prerequisites so the cluster is ready to host `llm-d`.
2. **Stack installation**: deploying the `llm-d` software components, documented by the [llm-d well-lit path guides](https://github.com/llm-d/llm-d/tree/main/guides).

This repository serves as the community-owned entry point for layer 1 provisioning guides, scripts, infrastructure-as-code templates, and cluster readiness conformance checks across [`cloud-providers/`](cloud-providers/), [`gateway-providers/`](gateway-providers/), and [`storage-providers/`](storage-providers/). Each provider directory is maintained by its own provider owners via a per-directory `OWNERS` file.

## Contributing

Contributions are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for the workflow and [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) for community expectations. Repository approvers are listed in [OWNERS](OWNERS). To report a vulnerability, follow [SECURITY.md](SECURITY.md) rather than opening a public issue.

## License

Apache 2.0. See [LICENSE.md](LICENSE.md).
