# Incident Note: Disk And Log Growth

Public-safe incident note for long-running agent runtime operations.

## What Happened

Diagnostic loops and verbose logs can grow faster than expected on small VPS environments. If disk usage is not checked early, ordinary troubleshooting can become a runtime reliability issue.

## Why It Matters

- Agent runtimes often produce logs, traces, artifacts, cached dependencies, and temporary files.
- Small VPS disks make storage growth visible sooner.
- A full disk can create confusing secondary failures that look like application or model issues.

## Controls

- document disk check commands in the handoff note
- add log rotation before long-running use
- separate generated artifacts from source repos
- prune stale containers/images only after confirming what is safe to remove
- include disk status in rescue-call and runtime-audit checklists

## Service Tie-In

This is part of the OpenClaw / NemoClaw Runtime Rollout and MultiClaw OS Runtime Audit checklists.
