# MultiClaw Fleet Case Study

Public-safe case study for AIML Solutions' MultiClaw OS operating model. Details are sanitized: role names are representative, private channels and paths are omitted, and credentials/account identifiers are excluded.

## Summary

MultiClaw OS is not a traditional operating system. It is an operating model and runtime pattern for coordinating agents, tools, data workflows, approvals, and evidence artifacts.

This case study shows how a small multi-agent runtime can be organized around scoped roles, a shared task board, least-privilege tool access, and explicit escalation paths.

## Reference Fleet

| Public role name | Working name | Primary lane | Boundary |
| --- | --- | --- | --- |
| Operations Steward | Stew | orchestration, task intake, scope control | coordinates but does not silently expand scope |
| Data Quality Analyst | Dana | source checks, schema quality, provenance | no paid data pulls without approval |
| Quant Research Analyst | Quinn | market/research workflows and LEAN-facing review | no broker, paper/live trade, or investment claims |
| Implementation Engineer | Ingrid | repo edits, tests, docs, integration work | no production mutation without handoff/rollback notes |
| Communications Analyst | Connie | drafts, summaries, outbound copy | draft-only for public posting unless approved |
| Research Analyst | Ronnie | public-source monitoring, OSINT-style triage, literature review | public/permitted sources only |
| Runtime Coordinator | Ruth | runtime health, containers, logs, restart/recovery notes | changes require backup/rollback awareness |

## Architecture Pattern

```text
Operator / client request
        |
        v
Operations Steward
        |
        +--> task board: queued -> claimed -> running -> blocked -> done/failed
        |
        +--> specialist worker role
                |
                +--> scoped tools
                +--> output contract
                +--> verification artifact
                +--> handoff note
```

## Operating Rules

- Workers receive only the context needed for their task.
- Tool access is treated as a contract, not a convenience.
- Destructive actions, cloud spend, paid APIs, public posting, and financial actions are approval-gated.
- Every completed task should leave behind a reviewable artifact: diff, test output, report, note, or structured result.
- Private project, client, paid-platform, credential, and account details stay out of public examples.

## Why A File-Based Task Board

The fleet uses a simple file-based task-board pattern at small scale because it is easy to inspect, easy to recover, and easy to explain to humans.

Tradeoff:

- File coordination is not a high-scale queue.
- It works well for low-concurrency agent operations where auditability and simplicity matter more than throughput.
- A SQLite-backed state table is the natural next step when task volume, concurrent writers, or reporting needs exceed the file-board model.

## Incidents And Lessons

| Incident | Lesson | Public note |
| --- | --- | --- |
| Disk/log growth during diagnostics | monitoring and log rotation belong in the first runtime checklist | see `docs/incidents/DISK-AND-LOG-GROWTH.md` |
| Nested sandbox / gateway execution conflict | runtime execution paths must be explicit; not every fix requires rebuilding an image | see `docs/incidents/NESTED-SANDBOX-GATEWAY.md` |

## Service Relevance

This case study backs three AIML Solutions service packages:

- Agent Runtime Rescue Call
- OpenClaw / NemoClaw Runtime Rollout
- MultiClaw OS Runtime Audit

The public artifact shows the shape of the work. Client-specific delivery uses private intake, SOW, audit, and handoff documents.
