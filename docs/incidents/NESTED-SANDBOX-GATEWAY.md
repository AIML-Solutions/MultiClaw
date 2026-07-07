# Incident Note: Nested Sandbox And Gateway Execution

Public-safe incident note for OpenClaw/NemoClaw-style runtimes.

## Pattern

Nested sandbox failures can happen when an agent runtime tries to create another sandbox from inside an already sandboxed or containerized environment. The symptom may appear as a bubblewrap/bwrap, Docker, permission, or gateway execution error.

## Practical Resolution Pattern

In many cases, the fix is configuration and routing rather than rebuilding a new image from scratch:

- make tool execution path explicit
- route execution through the gateway/host layer where appropriate
- avoid nesting sandbox modes that compete for the same isolation primitive
- document the chosen execution boundary in runtime notes

## Example Tradeoff

Disabling a nested sandbox layer or routing execution through the gateway can be appropriate when the outer runtime already provides isolation and the inner sandbox prevents tools from functioning. This should be documented as a conscious runtime decision, not an accidental workaround.

## What Not To Claim

- Do not claim sandboxing is removed globally without explaining the remaining boundary.
- Do not treat a local workaround as a universal fix for every OpenClaw/NemoClaw deployment.
- Do not mutate a client runtime without backup and rollback notes.

## Service Tie-In

This belongs in the Agent Runtime Rescue Call and Runtime Audit playbooks because it is a concrete issue that can block agent adoption quickly.
