# Harness Engineering

MultiClaw treats reliable agentic work as a model-harness-environment problem, not a model-only problem.

The model provides latent reasoning and coding capability. The environment provides repositories, tests, tools, logs, APIs, and deployment surfaces. The harness is the runtime substrate that determines whether the model's capability becomes auditable work.

## MultiClaw Interpretation

MultiClaw is AIML Solutions' operating model for harnessed multi-agent work. It defines lanes, responsibilities, approval boundaries, verification expectations, and evidence artifacts across specialist repos.

The goal is not to claim fully autonomous software engineering. The goal is to move agent work toward verifiable, attributed, maintainable episodes.

## Harness Responsibilities

| Harness responsibility | MultiClaw mapping |
| --- | --- |
| Task specification | Roadmaps, work orders, repo issues, release gates |
| Context selection | Repo topology, docs, source matrix, research memory |
| Tool access | AgentTools skills, OpenCode/OpenClaw tool scopes, command contracts |
| Project memory | Architecture docs, known-failure notes, implementation-status docs |
| Task state | Todo lists, meeting minutes, task ledgers, execution policy notes |
| Observability | Test output, smoke reports, logs, Docker/runtime diagnostics |
| Failure attribution | Quarantine records, runtime diagnosis, benchmark/eval notes |
| Verification | Unit tests, deterministic checks, source-matrix reports, release gates |
| Permissions | Human approval for cloud spend, public posting, credentials, live execution |
| Entropy auditing | Repo health checks, stale-doc detection, dependency/release discipline |
| Intervention recording | Private ops logs, technical review notes, missing-harness lessons |

## H0-H3 Maturity Ladder

MultiClaw can describe agent workflow maturity with a four-level ladder:

- `H0`: the agent receives only the task and repository. Output may be useful but evidence is weak.
- `H1`: tool and test registries make the action surface explicit.
- `H2`: project memory, task state, and context-selection protocols reduce wrong-file and wrong-layer work.
- `H3`: deterministic checks, failure attribution, reproduction steps, and verification reports make completion evidence-based.

Most public AIML Solutions work should honestly label where it sits on this ladder. The near-term target is not universal H3 autonomy; it is more H2/H3 evidence where risk or client value justifies it.

## Episode Packages

For serious work, a final patch or prose answer is not enough. A harnessed episode should produce evidence such as:

- action trace
- tool trace
- context trace
- verification trace
- failure-attribution log
- intervention log
- entropy audit
- outcome record

AgentTools contains lightweight public-safe templates for these artifacts under its `harness/` directory.

## Domain Examples

### QuantTools

QuantTools is a domain-specific harness for data and research workflows. Its asset master, provider catalog, source matrix, canonical records, freshness metadata, quarantine records, and opt-in smoke tests demonstrate validation before prediction.

### AgentTools

AgentTools is the harness artifact toolkit: task specs, tool registries, verification reports, failure attribution, entropy audit, and intervention log examples.

### CloudInfra

CloudInfra should provide local-first infrastructure patterns that let agent workflows generate or validate deployment artifacts before cloud spend or cluster mutation.

### IntelliClaw

IntelliClaw should preserve source memory and provenance for research workflows so summaries do not become unsupported claims.

## Operating Rule

If an agentic workflow cannot explain what it saw, what it changed, what failed, what was verified, what needed approval, and what residue it introduced, it is not yet a reliable workflow.
