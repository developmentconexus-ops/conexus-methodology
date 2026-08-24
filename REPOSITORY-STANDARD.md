# DevelopmentConexus Repository Standard

**Version:** 1.1.0  
**Status:** CANDIDATE FOR ORGANIZATIONAL RATIFICATION  
**Scope:** active DevelopmentConexus Product and platform repositories

## 1. Purpose

This standard defines **how a DevelopmentConexus repository is organized and operated** so humans and agents can enter any project with the same navigation, authority, Git, review, continuity, and context-management model.

It does not define Product semantics, architecture, technology, implementation language, stage names, or domain-specific verification. Those remain local to each repository.

`METHOD.md` governs **how engineering decisions are reasoned about**. `FRONTEND-METHOD.md` and `REALIZATION-METHOD.md` specialize that reasoning for their named work classes. This document governs **how repository knowledge and delivery are structured**. None may silently replace another.

The target property is:

> A fresh actor can recover current repository state, find the exact owning authority, select the smallest task-specific context, and continue safely without conversation archaeology, recursive repository reading, or guessing which document/PR is current.

## 2. Hard standard versus repository freedom

### Hard standard

Every conforming repository MUST provide:

- a landing-only `README.md`;
- a bootstrap-only `AGENTS.md`;
- `docs/index.md` as the canonical task/intention router;
- `docs/roadmap.md` as the sole mutable stage/status/next-action authority;
- semantic durable documentation paths under `docs/`;
- one current authority per meaning;
- branch-only temporary work that cannot enter `main`;
- one coherent **acceptance increment** per PR by default;
- squash merge as the normal integration method;
- protected `main` with no force-push or deletion;
- at least one required aggregate verification check;
- task-selective reading with a default pack of at most five files;
- a mechanically enforced bootstrap budget of at most 20 KiB for `AGENTS.md + docs/index.md + docs/roadmap.md`;
- an exact pinned `conexus-methodology` commit for the organizational method suite consumed by the repository;
- fresh-session recovery that does not depend on chat/handoff continuity;
- Git/closed PRs as history, subject to the reachability law in §10.

### Repository freedom

Each repository owns:

- Product and architecture content;
- stage/gate/block names such as `D5`, `3M`, `T8-E`, `B09`, or another local scheme;
- implementation languages and frameworks;
- exact directory trees for source/runtime code;
- exact verification jobs and commands;
- whether `reference/`, `research/`, `evidence/`, `qualification/`, or `diagrams/` are needed;
- domain-specific safety rails and stop conditions;
- the exact semantic size of an acceptance increment, subject to §11.

Standardization applies to the **operating envelope**, not the Product.

## 3. Fresh-actor and fresh-session route

### 3.1 Default authority route

```text
AGENTS.md
→ docs/index.md
→ docs/roadmap.md
→ 1–2 task-specific owning documents
```

Normal task context MUST fit in five files or fewer. Exceeding that pack requires a named material reason.

Agents MUST NOT recursively read `docs/`, phase history, Git history, raw research, qualification harnesses, implementation Evidence, or closed review dialogue before a concrete task requires them.

`docs/index.md` MUST include a task/intention table naming the smallest starting document and what must not be read by default.

### 3.2 Repository-state revalidation before work

A fresh session MUST establish the current repository state before relying on a remembered/chat state.

As applicable, revalidate:

```text
repository identity / remote
current checkout branch + HEAD
remote main HEAD
worktree cleanliness/unowned local state
open candidate PR(s) relevant to the current stage
candidate PR base/head relationship
current aggregate CI/check status
```

Do not assume `main`, an old handoff SHA, or a prior conversation is current.

### 3.3 Continuation without conversation history

Chat history and handoffs are optional convenience, never required continuation authority.

For an active unmerged candidate:

- the candidate branch version of `docs/roadmap.md` owns candidate stage/gate/next-action state;
- `main` remains the integrated authority and may legitimately lag the candidate;
- the Draft PR may point to the candidate and exact proof lineage, but MUST NOT become a second mutable status authority;
- current durable/temporary candidate artifacts must make the next material action discoverable from the roadmap/router without reconstructing the prior conversation.

A material checkpoint MUST NOT exist only in an uncommitted scratchpad or chat if another session is expected to continue it. Preserve the smallest lawful branch state needed to resume: durable authority when accepted, or `docs/work/current/**` when still temporary and non-authoritative.

If a fresh actor starts from `main` with no current checkout context and multiple open PRs could plausibly be the active continuation, do not guess. Use roadmap/PR routing to disambiguate; if ambiguity survives, ask the operator.

## 4. Root files

### `README.md`

`README.md` is a public/human landing page only.

It MAY contain:

- one-paragraph Product/repository description;
- links to `AGENTS.md` and `docs/index.md`;
- stable public URLs;
- stable setup or verification entrypoints when useful.

It MUST NOT own mutable stage/status, exact next action, a parallel roadmap, architecture authority, or active review state.

### `AGENTS.md`

`AGENTS.md` is the repository bootstrap/router.

It MUST remain compact and contain only:

- the fresh-actor route;
- the fresh-session repository-state revalidation rule;
- the repository-local authority model;
- the exact pinned organizational methodology-suite commit and the organizational authorities applicable to the repository;
- repository-specific hard stops/safety rails;
- local verification command(s);
- Git/publication rules that are materially repository-specific.

It MUST NOT duplicate the full Method/specialist methods, roadmap, Product/architecture prose, full Fable workflow, long research/tool guidance, or session history.

A local `CLAUDE.md`, `GEMINI.md`, or similar tool bridge MAY exist only when the tool consumes it automatically or a real local consumer requires it. It MUST disclaim independent Product/status/method authority.

## 5. Canonical documentation structure

Create only directories with a real consumer. The reserved semantic model is:

```text
docs/
├── index.md
├── roadmap.md
├── product/
├── architecture/
├── decisions/
├── phases/
├── development/
├── reference/
├── research/
├── evidence/
├── diagrams/
└── work/
```

Responsibilities:

| Surface | Responsibility |
| --- | --- |
| `docs/index.md` | Task/intention routing only |
| `docs/roadmap.md` | Sole mutable stage, gate, implementation status, next action |
| `docs/product/` | What the Product is: scope, actors, journeys, invariants |
| `docs/architecture/` | Current structural architecture and semantic ownership |
| `docs/decisions/` | Current decisions, dispositions, consequences, reopen triggers |
| `docs/phases/` | Durable closure/result summaries for completed or active named stages when useful |
| `docs/development/` | Repository-local engineering, documentation, Git, CI, proof, and methodology specialization rules |
| `docs/reference/` | Detailed current technical reference; not default-read |
| `docs/research/` | Comparative/external study; never implicit Product authority |
| `docs/evidence/` | Durable proof summaries/provenance; never Product authority |
| `docs/diagrams/` | Source-first diagrams whose semantic owner is named |
| `docs/work/` | Temporary non-authoritative branch-only material |

Executable qualification/proof harnesses MAY live outside `docs/`, for example under `qualification/`, and MUST remain outside the default read pack.

## 6. Naming and metadata

Durable paths use lowercase kebab-case semantic names.

Good:

```text
product/contract.md
architecture/persistence.md
decisions/index.md
phases/3l-technology-qualification.md
```

Durable filenames SHOULD NOT encode dates, sessions, reviewers, `final`, `candidate`, `handoff`, `dialogue`, `round`, `adjudication`, `amendment`, `old`, `legacy`, or `historical` unless that token is genuinely part of the subject identity.

A repository MAY use minimal frontmatter when it materially improves machine navigation. Do not add metadata merely for uniformity when filenames/indexes already route correctly.

## 7. Status and roadmap law

`docs/roadmap.md` is the **only mutable current-program status authority**.

It MUST make it possible to determine:

- current stage/gate/block as applicable;
- completed stages/increments that matter to progression;
- exact next action;
- whether implementation is allowed or blocked;
- active blocking Findings/prerequisites when material;
- entry/exit conditions or reopen triggers where material.

A roadmap stage MAY remain OPEN across several integrated acceptance increments. Merge does not imply stage closure.

Other durable documents MAY contain frozen historical closure snapshots, but MUST label them as snapshots and route current status back to `docs/roadmap.md`.

Indexes, README, AGENTS, Product, Architecture, PR descriptions, and phase summaries MUST NOT become parallel mutable status authorities.

## 8. Decision register law

`docs/decisions/index.md` or an equivalent clearly named register MUST allow a fresh actor to discover current material decision disposition without reconstructing review chronology.

For material current decisions, preserve as applicable:

```text
ID
subject / decision
current disposition
rationale
consequences
owning authority
supersedes / refines
Evidence/reference
reopen trigger
```

Controlled dispositions SHOULD use a small stable vocabulary such as:

```text
CURRENT
PRESERVE
REFINED
REOPEN
DEFERRED
SUPERSEDED
REJECTED
```

A pointer table alone does not replace a decision register when forward obligations such as `REOPEN`, `DEFERRED`, or `PRESERVE` would be lost.

## 9. Temporary work and independent review

Temporary work is non-authoritative.

A material acceptance increment MAY use only the temporary files it actually needs, for example:

```text
docs/work/current/index.md
docs/work/current/proposal.md
docs/work/current/plan.md
```

They MUST be absorbed into durable authority or deleted before merge.

### Fable review isolation

The candidate branch SHOULD remain free of `ai-dialog.md`.

Create a bounded review branch from the exact candidate:

```text
<candidate-branch>
→ review/<increment>-fable
```

The review branch adds only:

```text
docs/work/current/ai-dialog.md
```

The review guard MUST be capable of proving:

```text
review branch - exact candidate branch
= docs/work/current/ai-dialog.md only
```

Fable writes review input there. The Lead/Codex applies accepted corrections to the candidate. The review branch is then closed/deleted. `ai-dialog.md` never enters the merge candidate or `main`.

Follow the canonical Standard Fable review workflow in this methodology repository README. Reviewer output is Evidence, never authority. A second review round occurs only when a real material contradiction survives.

## 10. Git is the archive — reachability law

`Git history is the archive` is true only when the history that matters remains reachable.

### Content previously merged to `main`

If superseded content was previously reachable from `main`, it may be removed from the live tree after surviving current semantics are consolidated. Normal Git history is sufficient provenance.

### Important content only on an unmerged branch/PR

Before deleting its last branch/reference:

1. consolidate every still-current semantic obligation into current durable authority;
2. identify whether byte-level provenance is still required by a current authority, Evidence claim, or future requalification;
3. if byte-level provenance is still required, create a durable annotated tag or another explicit durable ref to the exact head/blob lineage;
4. record the durable ref where a future actor can find it;
5. only then delete the branch.

Do not create archive directories in the working tree. Do not create tags for ordinary superseded work with no remaining provenance consumer.

## 11. Acceptance increments, branches, and PR lifecycle

### 11.1 Acceptance increment

An **acceptance increment** is the smallest semantically coherent change whose acceptance/rejection can stand independently and whose integration leaves the repository in a valid, reconstructable state.

It is not defined by line count, commit count, document count, or roadmap-stage boundaries.

Examples may include:

- one frontend material block through its stable LOCK + trace closure;
- one upstream Product/backend correction exposed by a downstream Finding;
- one bounded architecture/contract decision package;
- one implementation vertical slice with its real proof;
- one stage closeout after the substantive increments are already integrated.

A roadmap stage may therefore span many PRs.

### 11.2 Default lifecycle

```text
main
→ one branch / one Draft PR for one coherent acceptance increment
→ analysis + execution
→ consolidated candidate
→ independent review when required
→ bounded corrections
→ verification
→ explicit merge authorization when repository governance requires it
→ squash merge
→ head-branch deletion
→ revalidate updated main
→ next dependent acceptance increment starts from updated main
```

A stage MAY remain OPEN after merge. `docs/roadmap.md` records the integrated increment and the exact next action.

### 11.3 Split law

Split when two parts could be independently accepted/rejected without leaving either incoherent, especially when they:

- have different semantic owners;
- close different operator decisions;
- contain a downstream Finding plus a separable upstream correction;
- would benefit from different independent reviewers/proof;
- make one review surface materially harder to understand together.

Do NOT split mechanically by file, P-step, test, endpoint, or arbitrary LOC target when the resulting pieces cannot be meaningfully reviewed alone.

Diff size is a review-risk signal, not a hard correctness threshold. A materially large PR SHOULD state why it cannot be decomposed into smaller coherent acceptance increments.

### 11.4 Parallel and stacked work

Do not stack a **dependent** later increment on an unmerged earlier increment by default.

Independent parallel candidate work is allowed only when dependency/authority boundaries are explicit and the operator/repository workflow permits it. A dependent candidate must not treat an unratified/unmerged candidate as integrated authority.

### 11.5 General Git rules

- do not commit directly to `main`;
- do not force-push or rewrite shared history;
- declare both what changes and what deliberately does not change;
- dependency/lockfile changes require explicit scope;
- temporary plans, candidates, review channels, and handoffs do not survive merge;
- merge/rebase methods other than squash SHOULD be disabled for normal Product repositories unless a proven history-preservation requirement exists;
- `main` MUST be protected from force-push/deletion and require PR-based changes.

## 12. Verification contract

Each repository owns its tools, but verification MUST cover relevant organizational properties.

### Bootstrap and authority

- `AGENTS.md + docs/index.md + docs/roadmap.md <= 20 KiB`;
- `docs/roadmap.md` is the sole mutable status/next-action authority;
- `README.md` is landing-only;
- the default task pack is at most five files;
- `AGENTS.md` contains fresh-session repository-state revalidation and exact methodology pin;
- durable documents are reachable from `docs/index.md` or a routed child index;
- relative links from current routers resolve;
- no durable authority depends on `docs/work/**`.

### Temporary/bloat controls

Merge candidates and `main` MUST contain no:

- `docs/work/**`;
- `AI-DIALOG`/`ai-dialog` review artifact;
- `docs/superpowers/`;
- permanent session handoff/dialogue/round trees;
- active `old/`, archive, tombstone, or duplicate-roadmap tree used as a second current surface.

### Decision and history controls

- decision dispositions are valid/current;
- unique unmerged provenance is not deleted while still required;
- a retired check/control requires current Evidence that its subject population is zero or replacement coverage is complete.

### Guard quality

- a material guard must be shown capable of firing through a deterministic negative control or equivalent falsifier;
- do not accept a presence-only control for a behavioral property;
- compare intended base to candidate for diff checks; clean checkout `git diff --check` with no range is not PR-diff proof;
- when implementation is blocked and the repository is intentionally architecture-only, prefer an explicit allowlist of permitted top-level surfaces over a denylist of old implementation names.

### Required aggregate check

Every Product/platform repository MUST expose at least one required aggregate status check protecting `main`.

New or fully realigned repositories SHOULD name it `required`. Existing repositories MAY retain a functioning protected check name until branch protection is deliberately migrated; do not break working protection solely for naming uniformity.

## 13. Research, Evidence, framework skills, and external docs

Research and Evidence support decisions; they do not create Product authority.

- `research/` may remain deep with a named current/future consumer, but is never default-read;
- `evidence/` and `qualification/` preserve proof boundaries/provenance;
- framework skills are execution aids, not Product architecture;
- current external documentation, Context7, framework source, and live probes are used only when materially relevant;
- exact pinned source/configuration and bounded Evidence decide version-specific claims;
- reusable realization work follows the pinned `REALIZATION-METHOD.md` rather than a silently forked local copy.

## 14. Organizational methodology consumption

### 14.1 Canonical authority + exact pin

Consuming repositories MUST reference the canonical repository:

```text
developmentconexus-ops/conexus-methodology
```

and pin the exact Git commit containing the accepted method suite they consume.

The pin may live compactly in `AGENTS.md` or `docs/development/engineering-rules.md`; it MUST be discoverable from bootstrap.

Do **not** consume normative methodology as an automatically moving `main` target. A cross-repository method change must not silently change the rules underneath an open Product PR.

### 14.2 Local materialization when a tool requires files

Default: reference/read canonical files directly; do not copy them into every Product repository.

If a real tool/offline/local-context consumer requires the bytes physically present, the repository MAY use a read-only local projection such as a Git submodule or generated/vendor snapshot, provided:

```text
canonical repo + exact commit are recorded
auto-follow of remote main is disabled
local edits are prohibited
the projection is explicitly non-independent authority
an update occurs through an explicit PR that moves the pin
methodology rebaseline/deviations are reviewed in that PR
```

A Git submodule is a delivery mechanism, not authority. A generated snapshot is a cache, not authority.

Do not create organization-wide sync/bot machinery until a real repeated consumer proves the need. If later automation is justified, it SHOULD open an explicit upgrade PR rather than mutating Product repositories silently.

### 14.3 Specialist-method applicability

A repository reads specialist methods only when the task requires them:

- `FRONTEND-METHOD.md` for material human-facing Product experience/frontend planning;
- `REALIZATION-METHOD.md` for material technology/dependency/production implementation/proof;
- `METHOD.md` always remains the reasoning kernel;
- this Repository Standard remains the operating envelope.

## 15. Repository-local specialization

A repository SHOULD keep local specialization in `docs/development/` and reference organizational methods instead of copying/redefining them.

Local rules may strengthen the standards for real Product/security/tooling constraints. They MUST NOT silently weaken them.

A justified deviation MUST state:

```text
standard/method rule
local deviation
real consumer/failure class
why default is insufficient
reopen/removal trigger
```

## 16. Conformance success test

A conforming repository passes this fresh-actor test:

> Starting from `AGENTS.md`, a new human or agent can revalidate the current repository/PR/CI state, find the sole current roadmap, identify the exact pinned organizational methods, choose the smallest task-specific authority pack, distinguish authority from research/Evidence/history, and continue the active work without conversation history.

If this requires several status dashboards, all phase documents, Git-history archaeology, permanent handoffs/dialogues, or guessing which open PR is current, the repository is not conforming even if every individual document is correct.
