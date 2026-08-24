# Conexus Methodology

Canonical home of the DevelopmentConexus cross-repository engineering methods.

## Start with the router

Agents do not read every Method by default.

```text
repository state
→ ROUTER.md
→ METHOD.md when material
→ at most one specialist method by default
→ task-owning repository authority
```

[`ROUTER.md`](ROUTER.md) is routing only; it owns no Product, repository status or engineering decision.

## Authority map

- [`METHOD.md`](METHOD.md) — **Engineering Method v1.1.0 candidate**: Evidence, Root Cause, Global Maximum, authority, proof, Findings, reopen and bounded rebaseline.
- [`REPOSITORY-STANDARD.md`](REPOSITORY-STANDARD.md) — **Repository Standard v1.1.0 candidate**: fresh-session recovery, documentation authority, acceptance increments, Git/PR lifecycle, context control and methodology consumption.
- [`FRONTEND-METHOD.md`](FRONTEND-METHOD.md) — **Frontend Product Experience Method v1.0.0 candidate**: needs/flows/IA, block-by-block functional low-fi HTML, operator LOCK, backend trace, whole-product assembly and readiness.
- [`REALIZATION-METHOD.md`](REALIZATION-METHOD.md) — **Evidence-Grounded Realization Method v1.0.0 candidate**: technology/dependency research, exact-version admission, `ADOPT | ADAPT | BUILD | DEFER | STOP`, implementation and claim-matched proof.
- [`ADVERSARIAL-REVIEW-METHOD.md`](ADVERSARIAL-REVIEW-METHOD.md) — **Independent Adversarial Review Method v1.0.0 candidate**: exact-candidate independent challenge, temporary `ai-dialog.md`, Lead adjudication and convergence.

Specialist methods apply `METHOD.md`; they do not silently replace upstream Product/architecture authority.

Product semantics, Product architecture, stage/block names, exact technologies, runtime topology, repository status and local verification remain owned by consuming repositories.

## Current operating deployment

The methods are actor-oriented rather than vendor-oriented. Current DevelopmentConexus use is:

```text
Lead        = ChatGPT
Challenger  = Claude Code
Operator    = human operator
Transport   = Git/GitHub
Review chat = docs/work/current/ai-dialog.md on isolated review branch
```

This is an operating assignment, not an agent platform. Replacing a model does not require redesigning the methodology.

## Context principle

```text
AUTO CONTEXT
= compact bootstrap + routing + current repository state

SELECTED CONTEXT
= only the Method/profile required now
+ 1–2 task owners

DEEP CONTEXT
= research/Evidence/code/history only when a current claim requires it
```

The goal is better decisions with less context, not more process.

## Fresh-session continuity

A new session must be able to continue from repository state without reconstructing chat history:

```text
revalidate repo / main / current branch + HEAD / relevant PR / CI
→ AGENTS.md
→ docs/index.md
→ docs/roadmap.md
→ pinned methodology ROUTER.md
→ selected Method profile
→ 1–2 task owners
```

The candidate-branch roadmap owns candidate status; `main` owns integrated status. PR descriptions help locate a candidate but never replace the roadmap.

Chat handoffs are routing convenience only.

## Independent adversarial review

Use [`ADVERSARIAL-REVIEW-METHOD.md`](ADVERSARIAL-REVIEW-METHOD.md) when `METHOD.md` or repository governance requires an independent challenge.

Current normal flow:

```text
Lead creates exact candidate
→ Challenger revalidates/fetches remote authority
→ isolated review branch/worktree from exact candidate
→ Challenger appends one turn to docs/work/current/ai-dialog.md and pushes
→ Lead fetches, adjudicates and appends response
→ Challenger counterchallenges only if material uncertainty survives
→ accepted corrections land on candidate, not review branch
→ review branch/PR closes unmerged
```

`ai-dialog.md` is temporary versioned transport, not Product/architecture/status authority and never enters `main`.

A normal operator handoff can therefore be very small:

```text
Repository: <owner/repo>
Candidate PR: #<n>
Expected HEAD: <optional>

Perform the independent adversarial review for the current gate.
Revalidate remote authority first.
Use the pinned DevelopmentConexus methodology.
Publish only through the temporary ai-dialog channel and push it.
Do not modify the candidate.
```

The substantive reviewer conversation stays in Git rather than being copied through operator chat.

## Consumption contract

A consuming repository keeps its compact local `AGENTS.md`, `docs/index.md`, `docs/roadmap.md` and repository-specific engineering rules.

It MUST pin the exact Git commit of this methodology repository that it consumes. Normative auto-follow of methodology `main` is prohibited because it would change rules underneath open Product work.

Default consumption is by canonical reference. If real tool/local/offline use requires the bytes physically present, a pinned read-only Git submodule or generated projection MAY be used as a delivery/cache mechanism. It remains bound to the canonical repo + exact commit and upgrades only through an explicit PR that moves the pin.

Do not build sync bots/frameworks merely for convenience. If repeated real cost later justifies automation, automation should open an explicit methodology-upgrade PR rather than silently mutating consumers.

## Change rule

Changing an organizational Method/Standard is material cross-repository work. Apply the current accepted Method, inspect affected consumers, run independent/fresh challenge when required, and require explicit operator ratification before the candidate becomes authority.

Keep this repository intentionally small. Git history is the change record. No Product-specific guidance, prompt/template libraries, agent framework, permanent dialogue archive or synchronization platform without a demonstrated failure class and real consumer.
