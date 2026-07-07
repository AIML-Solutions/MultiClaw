# Model Routing Policy

MultiClaw OS uses model-routing discipline to control cost, improve review quality, and reduce unnecessary high-reasoning calls.

## Principle

Do not use the strongest model for mechanical work. Use low-cost observation for facts, standard execution for bounded changes, and max-reasoning only for decisions that justify it.

## Routing Lanes

| Lane | Role | Typical work |
| --- | --- | --- |
| Observe | gather and compress evidence | search, file inventory, log summaries, command-output compression, environment facts |
| Execute | apply bounded changes | tests, small refactors, dependency cleanup, focused implementation after the plan is clear |
| Decide | handle high-risk reasoning | architecture, security, auth/OAuth, sandboxing, approval plumbing, ambiguous failures, final risky review |

## Operating Loop

1. Observe gathers facts and returns relevant paths, outputs, and open questions.
2. Decide sets strategy only when the problem is risky, ambiguous, or cross-system.
3. Execute applies the bounded change.
4. Observe collects test and validation output.
5. Decide reviews only when tests fail, risk remains high, or a final approval is required.

## Escalation Triggers

Escalate to the Decide lane when work involves:

- authentication, OAuth, tokens, permissions, or approvals
- sandbox, gateway, dashboard, plugin, or runtime plumbing
- secrets, payments, production infrastructure, or destructive commands
- agent policies, harnesses, schemas, contracts, or safety boundaries
- repeated failures after cheaper triage

## Public Value

This policy is part of AIML Solutions' runtime discipline: spend strong reasoning where it changes outcomes, not where it merely reads logs or formats files.
