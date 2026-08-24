# DevelopmentConexus Method Router

**Purpose:** select the smallest methodology context required for the current task.  
**Authority:** routing only; this file owns no Product, repository status, or engineering decision semantics.

## Context law

```text
AUTO CONTEXT
= repository state + routing only

SELECTED CONTEXT
= METHOD when material
+ at most one specialist by default
+ smallest repository-local task authority pack

DEEP CONTEXT
= only when current Evidence requires it
```

Do not load the whole methodology suite merely because it exists.

## Selection

| Current work | Load |
|---|---|
| trivial/mechanical change with no material decision | repository bootstrap + task owner; load `METHOD.md` only if a material question appears |
| Product/architecture/material engineering decision | `METHOD.md` |
| repository organization, continuity, Git/PR, docs authority, methodology consumption | `REPOSITORY-STANDARD.md`; add `METHOD.md` when material |
| human-facing Product experience/frontend planning | `METHOD.md` + `FRONTEND-METHOD.md` |
| technology/dependency/version/production implementation/integration/proof | `METHOD.md` + `REALIZATION-METHOD.md` |
| independent adversarial challenge | `METHOD.md` + `ADVERSARIAL-REVIEW-METHOD.md`; load another specialist only when the attacked claim requires it |

If more than one specialist appears necessary, first test whether the task actually contains multiple acceptance increments. Load multiple specialists only for a named cross-cutting reason.

## Repository authority pack

Follow the reviewed repository's own bootstrap shape.

For conforming Product/platform repositories, `REPOSITORY-STANDARD.md` normally routes:

```text
AGENTS.md
→ docs/index.md
→ docs/roadmap.md
→ 1–2 task owners
```

For `conexus-methodology` itself:

```text
AGENTS.md
→ ROUTER.md
→ selected Method(s)
```

The five-file default in the Repository Standard applies to the **repository-local task authority pack**. Selected methodology files are a separate method profile; an adversarial review is therefore not automatically over budget merely because it loads `METHOD.md` + the review method.

Research, Evidence, code, tests, qualification harnesses, Git history, and closed review dialogue are loaded on demand when a current claim requires them.

## Materiality escalation

A task may start mechanical and become material:

```text
mechanical work
→ material uncertainty / invariant / authority / external effect
→ load METHOD.md
→ decide before continuing materially
```

Do not load `METHOD.md` for every typo merely for ceremony; do not continue materially without it merely to save tokens.

## Specialist escalation

A specialist that exposes insufficient accepted upstream authority invokes the downstream-falsification law owned by `METHOD.md`; this router does not restate that law.

## Review selection

For independent review, load `METHOD.md` + `ADVERSARIAL-REVIEW-METHOD.md`. That review method owns candidate identity, context sequence, transport, handoff, dialogue and round behavior.

## Optional roadmap selector

A Product/platform repository may state a compact current method profile in `docs/roadmap.md` only when it materially reduces ambiguity, e.g. `METHOD + FRONTEND / B09`. This is routing, not duplicated methodology; omit it when obvious.

> Read enough methodology to decide the current task correctly, and no more by default.
