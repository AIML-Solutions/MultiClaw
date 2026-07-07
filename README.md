# MultiClaw

[![Core Quality Gate](https://github.com/AIML-Solutions/MultiClaw/actions/workflows/ci.yml/badge.svg)](https://github.com/AIML-Solutions/MultiClaw/actions/workflows/ci.yml)
[![Website](https://img.shields.io/badge/site-live-0ea5e9)](https://aiml-solutions.github.io/multiclaw-frontend/)
[![License: MIT](https://img.shields.io/badge/license-MIT-22c55e.svg)](LICENSE)

**MultiClaw** is the architecture and governance command layer for AIML Solutions' MultiClaw OS: an agentic operating model for scoped runtimes, harness artifacts, evaluation workflows, intelligence pipelines, data validation, and cloud-ready delivery.

It defines how specialized departments (research intelligence, quant, ModelOps, cloud, docs, and public interfaces) operate with clear boundaries, measurable outputs, and cost-aware model routing.

## Positioning

MultiClaw is not a monolithic agent demo or a traditional operating system. It is the operating model for building auditable AI systems across multiple repos: runtime boundaries, harness artifacts, data pipelines, research monitors, CLI tools, cloud scaffolds, and public documentation.

For hiring and client discussions, this repo shows the management layer: scope control, approval gates, model routing, release discipline, and evidence standards.

## 🧭 Why this repository exists

MultiClaw avoids the common “single giant AI project” failure mode by separating concerns:

- operating model and department boundaries
- model routing policy and escalation rules
- cross-repo release standards
- reporting and decision hygiene

## Ecosystem map

- [**MultiClaw**](https://github.com/AIML-Solutions/MultiClaw) - operating model, release gates, and cross-repo coordination
- [**QuantTools**](https://github.com/AIML-Solutions/QuantTools) - quant/data validation, LEAN workflows, source matrix planning, and metrics-backed proof artifacts
- [**IntelliClaw**](https://github.com/AIML-Solutions/IntelliClaw) - configurable research-monitoring and signal-triage pipeline
- [**AgentTools**](https://github.com/AIML-Solutions/AgentTools) - reusable agent skills, harness artifacts, and MCP-facing workflow utilities
- [**CloudInfra**](https://github.com/AIML-Solutions/CloudInfra) - infrastructure patterns and deployment scaffolding
- [**MultiClaw-Public-Library**](https://github.com/AIML-Solutions/MultiClaw-Public-Library) - public notes, reports, and reusable portfolio assets
- [**SnorkelTools**](https://github.com/AIML-Solutions/SnorkelTools) - weak-supervision and labeling workflow experiments

## Portfolio Proof

| Lane | What it proves |
| --- | --- |
| QuantTools | Python data validation, provider readiness, no-auth smoke tests, source-matrix planning |
| AgentTools | CLI automation, repo audit tooling, AI harness artifacts, verification discipline |
| IntelliClaw | Configurable research monitoring, signal triage, source normalization |
| CloudInfra | IaC/Kubernetes safety patterns and local-first validation discipline |
| Public Library | Public communication, campaign planning, and reusable technical notes |

## Implementation status

| Area | Status | Notes |
| --- | --- | --- |
| Operating model | Active | Scope, departments, roadmap, and routing docs are maintained under `docs/` |
| Release discipline | Active | CI, PR template, release template, changelog, and contribution rules are present |
| Reporting cadence | Active | `reports/` contains dated technical briefings and meeting-minutes templates |
| Automation | Active | Snapshot capture script is included under `scripts/` |
| Quant integration | Scaffold | LEAN setup notes and compose scaffold are present; working quant implementation lives in `QuantTools` |

MultiClaw is intentionally documentation-and-governance heavy. The implementation work is distributed across the specialist repos listed above.

## 📚 Core documents

- [`docs/SCOPE.md`](docs/SCOPE.md)
- [`docs/MULTICLAW-OS.md`](docs/MULTICLAW-OS.md)
- [`docs/SERVICE-PACKAGES.md`](docs/SERVICE-PACKAGES.md)
- [`docs/REPO_TOPOLOGY.md`](docs/REPO_TOPOLOGY.md)
- [`docs/AGENT_MODEL_ROUTING.md`](docs/AGENT_MODEL_ROUTING.md)
- [`docs/HARNESS-ENGINEERING.md`](docs/HARNESS-ENGINEERING.md)
- [`docs/QUALITY-GATE.md`](docs/QUALITY-GATE.md)
- [`docs/ROADMAP.md`](docs/ROADMAP.md)
- [`docs/DEPARTMENTS.md`](docs/DEPARTMENTS.md)
- [`docs/README.md`](docs/README.md)

## 🎯 Current focus

1. Tighten quality/release gates across public repos.
2. Keep cost-speed-quality model routing explicit.
3. Make outputs stakeholder-ready (docs + website + release notes).
4. Keep runway discipline while shipping production-grade assets.

## What To Review First

1. Start with `QuantTools` for the strongest code/data proof.
2. Review `AgentTools/harness/` for AI harness engineering artifacts.
3. Review `docs/HARNESS-ENGINEERING.md` for the MultiClaw operating model.
4. Review `CloudInfra` for infrastructure safety and validation direction.

## 📰 Reporting

- Strategic and technical briefings: [`reports/`](reports/)
- Snapshot automation: [`scripts/capture_snapshot.sh`](scripts/capture_snapshot.sh)

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

MIT — see [LICENSE](LICENSE).
