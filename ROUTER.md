# DevelopmentConexus Method Router

**Purpose:** select the smallest methodology context required for the current task.  
**Authority:** routing only; this file owns no Product, repository status, or engineering decision semantics.

## 1. Context law

```text
AUTO CONTEXT
= routing + current repository state only

SELECTED CONTEXT
= METHOD kernel when material
+ at most one specialist method by default
+ 1–2 task-owning repository documents

DEEP CONTEXT
= only when current Evidence requires it
```

Do **not** load the whole methodology suite merely because it exists.

## 2. Selection table

| Current work | Load |
|---|---|
| trivial/mechanical change with no material decision | repository bootstrap + task owner; load `METHOD.md` only if a material question appears |
| Product/architecture/material engineering decision | `METHOD.md` |
| repository organization, continuity, Git/PR, docs authority, methodology consumption | `REPOSITORY-STANDARD.md`; add `METHOD.md` when the change is material |
| human-facing Product experience/frontend planning | `METHOD.md` + `FRONTEND-METHOD.md` |
| technology/dependency/version/production implementation/integration/proof | `METHOD.md` + `REALIZATION-METHOD.md` |
| independent adversarial challenge | `METHOD.md` + `ADVERSARIAL-REVIEW-METHOD.md`; add the specialist method whose decision is actually under review only when needed |

If more than one specialist appears necessary, first ask whether the task actually contains multiple acceptance increments. Load multiple specialists only for a named cross-cutting reason.

## 3. Repository task pack

After method selection, load the smallest repository authority pack:

```text
docs/index.md
→ docs/roadmap.md
→ 1–2 task-specific owners
```

Repository status remains in the repository roadmap, not in this router or any Method.

Research, Evidence, code, tests, qualification harnesses, Git history, and closed review dialogue are loaded **on demand** when a current claim requires them.

## 4. Materiality escalation

A task may start mechanical and become material.

```text
mechanical task
→ material uncertainty / invariant / authority / external effect discovered
→ load METHOD.md
→ classify and decide
```

Do not pre-load `METHOD.md` for every typo merely to satisfy ceremony; do not continue materially without it merely to save tokens.

## 5. Downstream Finding routing

When a specialist exposes a contradiction with accepted upstream authority:

```text
specialist work
→ material contradiction
→ UPSTREAM FINDING
→ METHOD.md
→ smallest owning authority reopen
→ accepted disposition
→ bounded specialist rebaseline
→ resume
```

The specialist does not silently patch around upstream authority and does not become a second authority.

## 6. Review profile

For an independent review:

```text
repository bootstrap/state
→ this ROUTER
→ METHOD.md
→ ADVERSARIAL-REVIEW-METHOD.md
→ exact candidate diff
→ exact task owner(s)
→ other method/research/Evidence only if a Finding requires it
```

Do not begin an adversarial review by recursively reading the repository or every Method.

## 7. Optional roadmap profile

A repository MAY state one compact current method profile in `docs/roadmap.md` when it materially reduces ambiguity, for example:

```text
Method profile: METHOD + FRONTEND / current block
```

or:

```text
Method profile: METHOD + ADVERSARIAL-REVIEW
```

This is a selector, not duplicated methodology. Omit it when the active task is already obvious from normal routing.

## 8. Final rule

> Read enough methodology to decide the current task correctly, and no more by default.
