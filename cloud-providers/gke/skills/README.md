# AI skills for GKE provisioning

## create-gke-infra-llm-d

Interactive agent skill that provisions or prepares GKE infrastructure for
llm-d (cluster, GPU node pools, RDMA networking on either the DRA/DRANET or the
multi-networking/gIB path, Gateway API prerequisites), with IAM preflight,
announce-before-create guardrails, and a validation checklist.

Originated in the
[llm-d-skills](https://github.com/llm-d-incubation/llm-d-skills) repository; the
copy here is the provider-maintained version. The hand-off targets referenced
by the skill (`deploy-llm-d`, `llm-d-autoconfig`) live in that repository and
are linked by absolute URL.

Skill entry point: [create-gke-infra-llm-d/SKILL.md](create-gke-infra-llm-d/SKILL.md)
