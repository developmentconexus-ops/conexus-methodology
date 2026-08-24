# Conexus Methodology

Canonical home of the DevelopmentConexus cross-repository engineering authorities.

## Authority map

The suite has one reasoning kernel and three bounded specializations:

- [`METHOD.md`](METHOD.md) — **DevelopmentConexus Engineering Method v1.1.0 candidate**. Governs how material engineering is reasoned about, challenged, decided, reopened, and boundedly rebaselined.
- [`REPOSITORY-STANDARD.md`](REPOSITORY-STANDARD.md) — **Repository Standard v1.1.0 candidate**. Governs repository bootstrap, fresh-session recovery, documentation authority, acceptance increments, Git/PR lifecycle, review isolation, methodology consumption, and minimum verification properties.
- [`FRONTEND-METHOD.md`](FRONTEND-METHOD.md) — **Frontend Product Experience Method v1.0.0 candidate**. Governs human-needs-first frontend planning, IA, block-by-block functional low-fidelity HTML, operator LOCK, frontend/backend trace, assembled UX, and implementation readiness.
- [`REALIZATION-METHOD.md`](REALIZATION-METHOD.md) — **Evidence-Grounded Realization Method v1.0.0 candidate**. Governs property-first technology research, dependency/version admission, `ADOPT | ADAPT | BUILD | DEFER | STOP`, production implementation, and claim-matched proof.

Composition:

```text
METHOD.md
  reasoning kernel / Global Maximum / authority / Findings
      │
      ├── REPOSITORY-STANDARD.md   repository operating envelope
      ├── FRONTEND-METHOD.md       human-facing Product experience
      └── REALIZATION-METHOD.md    technology + production realization

specialist Evidence contradicts upstream authority
→ UPSTREAM FINDING
→ METHOD.md smallest-owner reopen
→ accepted authority update
→ bounded specialist rebaseline
→ resume
```

Product semantics, Product architecture, stage/block names, exact technology choices, runtime topology, verification commands, and repository-specific safety rails remain owned by consuming repositories.

## Consumption contract

A consuming repository keeps its own compact `AGENTS.md` and repository-local `docs/development/engineering-rules.md`.

It MUST pin the exact Git commit of this methodology repository that it consumes. Do not bind normative engineering rules to an automatically moving `main` target: changing organizational methodology underneath an open Product PR would create invisible authority drift.

Default consumption is by canonical reference, not copy.

When a real local/tool/offline consumer requires the method bytes physically present, a pinned Git submodule or generated/vendor projection is allowed as a **delivery/cache mechanism** only. It must record the canonical repo + exact commit, prohibit local edits, disable auto-follow of remote `main`, and upgrade through an explicit PR that moves the pin.

A future update bot may be justified by repeated consumer cost, but it should open explicit methodology-upgrade PRs rather than silently mutate Product repositories.

## Fresh-session principle

A new session must be able to continue from repository state without a chat handoff.

The consuming `AGENTS.md` routes:

```text
revalidate repo / branch / HEAD / relevant PR / CI
→ AGENTS.md
→ docs/index.md
→ docs/roadmap.md
→ 1–2 task owners
```

The candidate-branch roadmap owns candidate status; `main` owns integrated status. PR descriptions point to candidate state but never replace the roadmap.

## Standard Fable review workflow

Use Fable as the independent adversarial challenger when `METHOD.md` or repository governance requires independent review.

```text
1. Lead performs analysis independently.
2. Lead prepares the smallest coherent NON-AUTHORITATIVE candidate.
3. Freeze exact candidate repo/branch/HEAD and review focus.
4. Fable reconstructs current authority, applies METHOD.md and applicable specialist method, and attacks Global Maximum, assumptions, boundaries, YAGNI, failure modes, and evidence quality.
5. Under repository isolation, the review branch differs from the exact candidate only by `docs/work/current/ai-dialog.md`.
6. Reviewer output is Evidence, never authority.
7. Lead adjudicates every material Finding against current authority.
8. Round 2 occurs only if a real material contradiction survives.
9. Lead consolidates and verifies the candidate.
10. Operator/owning authority ratifies where required.
```

Do not use independent review as agreement theater. Do not split one coherent decision into artificial micro-reviews; equally, do not force several independently acceptable increments into one review merely because they share a roadmap stage.

## Change rule

Changing any organizational authority in this repository is a material cross-repository decision.

Apply the current accepted Method, inspect affected consumers and known local-method lineages, run independent/fresh challenge when the Method requires it, and require explicit operator ratification before the candidate becomes organizational authority.

Keep this repository small. Git history is the change record. Do not add sync frameworks, CI frameworks, template libraries, prompt libraries, or duplicated local guidance without a demonstrated failure class and real consumer.
