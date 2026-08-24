# Conexus Methodology

Canonical home of the DevelopmentConexus cross-repository engineering methods.

## Current suite status

**PR #2 OPERATOR-RATIFIED / NOT YET INTEGRATED / NOT YET ORGANIZATIONAL AUTHORITY.**

Independent adversarial review R1–R3 is converged and the operator ratified this candidate on 2026-08-24. `main` remains the accepted organizational authority until this candidate is integrated.

## Start with the router

Agents start with [`ROUTER.md`](ROUTER.md) and load only the method profile required by the current task. The router owns context selection; this README does not duplicate that logic.

## Authority map

- [`METHOD.md`](METHOD.md) — Engineering Method v1.1.0: Evidence, Root Cause, Global Maximum, authority, proof, Findings, reopen, bounded rebaseline.
- [`REPOSITORY-STANDARD.md`](REPOSITORY-STANDARD.md) — Repository Standard v1.1.0: fresh-session recovery, documentation authority, acceptance increments, Git/PR lifecycle, context control, methodology consumption.
- [`FRONTEND-METHOD.md`](FRONTEND-METHOD.md) — Frontend Product Experience Method v1.0.0: needs/flows/IA, functional low-fi HTML, operator LOCK, backend trace, whole-product assembly, readiness.
- [`REALIZATION-METHOD.md`](REALIZATION-METHOD.md) — Evidence-Grounded Realization Method v1.0.0: technology/dependency research, exact-version admission, `ADOPT | ADAPT | BUILD | DEFER | STOP`, implementation, claim-matched proof.
- [`ADVERSARIAL-REVIEW-METHOD.md`](ADVERSARIAL-REVIEW-METHOD.md) — Independent Adversarial Review Method v1.0.0: exact-candidate challenge, temporary review transport, Lead adjudication, convergence.
- [`ROUTER.md`](ROUTER.md) — routing only; no Product/status/engineering decision authority.

Each method file owns its own version and document lifecycle. This README owns only the current **suite-level** status of this methodology repository.

Product semantics, Product architecture, stage/block names, exact technologies, runtime topology, repository status, and local verification remain owned by consuming repositories.

## Current operating deployment

The methods are actor-oriented. Current DevelopmentConexus use is:

```text
Lead        = ChatGPT
Challenger  = Claude Code
Operator    = human operator
Transport   = Git/GitHub
```

For the canonical `ai-dialog` profile, both Lead and Challenger require write-capable Git/GitHub access. This requirement was proved during PR #2 Round 1 by a direct ChatGPT Lead write to the remote review branch. If either actor lacks that capability, stop and explicitly choose another transport rather than silently pretending the canonical profile is operational.

This is an operating assignment, not an agent platform. Replacing a model does not require redesigning the methodology.

## Repository-specific bootstrap

This repository deliberately stays smaller than a Product/platform repository:

```text
AGENTS.md
→ ROUTER.md
→ selected method(s)
```

It does not manufacture `docs/index.md` or `docs/roadmap.md` solely for symmetry. Product/platform repositories follow the bootstrap required by `REPOSITORY-STANDARD.md`.

## Independent review

[`ADVERSARIAL-REVIEW-METHOD.md`](ADVERSARIAL-REVIEW-METHOD.md) owns the review transport, branch/worktree protocol, minimal operator handoff, `ai-dialog.md`, Lead adjudication, round rules, and closure.

Current PR #2 dogfooded that protocol with ChatGPT as Lead and Claude Code as Challenger through converged R1–R3. Do not copy the review workflow into other routing surfaces.

## Consumption contract

A consuming repository keeps its compact local bootstrap and pins the exact accepted Git commit of this methodology repository. Normative auto-follow of methodology `main` is prohibited because it would change rules underneath open Product work.

Default consumption is by canonical reference. If a real tool/local/offline consumer needs the bytes physically present, a pinned read-only Git submodule or generated projection may be used only as a delivery/cache mechanism and upgraded through an explicit pin-move PR.

Do not build sync bots/frameworks merely for convenience. If repeated real cost later justifies automation, it should open explicit methodology-upgrade PRs rather than silently mutating consumers.

## Change rule

Changing an organizational Method/Standard is material cross-repository work. Apply the current accepted Method, inspect affected consumers, run independent/fresh challenge when required, and require explicit operator ratification before the candidate becomes authority.

Keep this repository intentionally small. Git history is the change record. No Product-specific guidance, prompt/template library, generic agent framework, permanent dialogue archive, CI framework, or synchronization platform without a demonstrated failure class and real consumer.
