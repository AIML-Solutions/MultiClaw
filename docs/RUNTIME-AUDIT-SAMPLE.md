# MultiClaw Runtime Audit - Sample Report

Public-safe sample report. This is a representative deliverable format, not a disclosure of a client environment.

## Scope

| Field | Sample value |
| --- | --- |
| Runtime type | VPS-hosted agent runtime |
| Agent model | orchestrator plus specialist workers |
| Access mode | read-only review or guided screen-share preferred |
| Primary concern | runtime reliability, tool boundaries, handoff quality |

## Executive Summary

The reviewed runtime shows strong role separation and useful operating discipline, but the highest-value improvements are operational: document restart paths, add disk/log checks, verify tool boundaries per role, and produce compact handoff notes after each change.

## Sample Findings

| Severity | Finding | Impact | Recommendation |
| --- | --- | --- | --- |
| High | Restart and recovery procedure is not written in one place | operator knowledge becomes a single-person dependency | create a one-page recovery note with process checks, restart commands, and stale-session cleanup |
| High | Tool permissions are described informally but not mapped by role | workers may receive broader access than required | create a role/tool matrix and mark approval-gated actions explicitly |
| Medium | Disk and log growth checks are manual | long-running diagnostics can consume storage before the operator notices | add disk check, log rotation, and alert threshold to runtime checklist |
| Medium | Verification artifacts vary by task | completed work may be hard to review later | require each task to emit a diff, test output, report, or result note |
| Low | Public/private boundary depends on operator memory | accidental publication risk rises over time | keep public-safe examples and private delivery folders structurally separated |

## Approval Gate Recommendations

| Action | Default posture |
| --- | --- |
| shell execution | allowed only for scoped implementation roles |
| cloud spend | explicit approval required |
| paid APIs/data | explicit approval required |
| public posting/outbound messages | draft-only unless approved |
| live broker/financial actions | excluded unless separately approved in writing |
| destructive file operations | approval or clear rollback path required |

## Example Remediation Plan

1. Create runtime map and recovery note.
2. Add role/tool permission matrix.
3. Add disk/log checklist.
4. Add task-output contract for each recurring workflow.
5. Schedule optional implementation sprint if the audit finds repeated operational friction.

## Caveat

This sample is intentionally generic. Real client audits include environment-specific findings, but private hostnames, credentials, account identifiers, paid-platform details, and client data do not appear in public examples.
