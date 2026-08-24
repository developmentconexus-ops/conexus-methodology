# Conexus Methodology — Agent Bootstrap

## Start here

Before editing, revalidate repository, branch/HEAD and any active methodology PR. Current repository authority beats chat or an old handoff.

Read in this order:

```text
AGENTS.md
→ ROUTER.md
→ only the Method(s) selected for the current task
```

Do **not** load the whole suite by default.

## Authority

- `METHOD.md` — reasoning kernel for material engineering decisions.
- `REPOSITORY-STANDARD.md` — repository operation, continuity, Git/PR, context and methodology consumption.
- `FRONTEND-METHOD.md` — specialist for human-facing Product experience/frontend planning.
- `REALIZATION-METHOD.md` — specialist for technology/dependency/production realization.
- `ADVERSARIAL-REVIEW-METHOD.md` — specialist for independent challenge.
- `ROUTER.md` — routing only; it owns no engineering/Product decision.

Product architecture, repository status, stage/block names, exact technology and local safety rails remain owned by consuming repositories.

Local copies/submodules/projections are delivery aids only. Consumers pin the exact methodology commit; normative auto-follow of `main` is prohibited.

## Current operating deployment

The methods are tool-neutral. Current DevelopmentConexus use is:

```text
Lead        = ChatGPT
Challenger  = Claude Code
Operator    = human operator
```

Do not encode model-specific behavior into Product authority.

## Editing rule

A change to an organizational Method/Standard is material cross-repository work. Apply the currently accepted Method, inspect affected consumers, challenge material candidates independently when required, and require explicit operator ratification before they become organizational authority.

Keep this repository small and LLM-first. Do not add Product-specific decisions, stage roadmaps, prompt/template libraries, agent frameworks, sync bots or CI/distribution machinery without a demonstrated failure class and real consumer.
