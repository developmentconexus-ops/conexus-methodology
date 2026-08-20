# DevelopmentConexus Repository Standard

**Version:** 1.0.0  
**Status:** OPERATOR-RATIFIED  
**Ratified:** 2026-08-20  
**Scope:** active DevelopmentConexus product and platform repositories

## 1. Purpose

This standard defines **how a DevelopmentConexus repository is organized and operated** so humans and agents can enter any project with the same navigation, authority, Git, review, and context-management model.

It does not define Product semantics, architecture, technology, implementation language, stage names, or domain-specific verification. Those remain local to each repository.

`METHOD.md` governs **how engineering decisions are reasoned about**. This document governs **how repository knowledge and delivery are structured**. Neither may silently replace the other.

The target property is:

> A fresh actor can find current status, the exact owning authority, and the smallest task-specific context without reconstructing conversation history, reading the repository recursively, or guessing which document is current.

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
- one coherent gate/stage per PR by default;
- squash merge as the normal integration method;
- protected `main` with no force-push or deletion;
- at least one required aggregate verification check;
- task-selective reading with a default pack of at most five files;
- a mechanically enforced bootstrap budget of at most 20 KiB for `AGENTS.md + docs/index.md + docs/roadmap.md`;
- Git/closed PRs as history, subject to the reachability law in §10.

### Repository freedom

Each repository owns:

- Product and architecture content;
- stage/gate names such as `D5`, `3M`, or `T8-E`;
- implementation languages and frameworks;
- exact directory trees for source/runtime code;
- exact verification jobs and commands;
- whether `reference/`, `research/`, `evidence/`, `qualification/`, or `diagrams/` are needed;
- domain-specific safety rails and stop conditions.

Standardization applies to the **operating envelope**, not the Product.

## 3. Required fresh-actor route

The default route is:

```text
AGENTS.md
→ docs/index.md
→ docs/roadmap.md
→ 1–2 task-specific owning documents
```

Normal work MUST fit in five files or fewer. Exceeding that pack requires a named material reason.

Agents MUST NOT recursively read `docs/`, phase history, Git history, raw research, qualification harnesses, or implementation evidence before a concrete task requires them.

`docs/index.md` MUST include a task/intention table that names the smallest starting document and what must not be read by default.

## 4. Root files

### `README.md`

`README.md` is a public/human landing page only.

It MAY contain:

- one-paragraph Product/repository description;
- links to `AGENTS.md` and `docs/index.md`;
- stable public URLs;
- stable setup or verification entrypoints when useful.

It MUST NOT own:

- mutable stage/status;
- exact next action;
- a parallel roadmap;
- architecture authority;
- active review state.

### `AGENTS.md`

`AGENTS.md` is the repository bootstrap/router.

It MUST remain compact and contain only:

- the fresh-actor route;
- the repository-local authority model;
- references to the canonical organizational Method and Repository Standard;
- repository-specific hard stops/safety rails;
- local verification command(s);
- Git/publication rules that are materially repository-specific.

It MUST NOT duplicate:

- the full engineering Method;
- the roadmap;
- Product/architecture prose;
- the full Fable workflow;
- long research/tool guidance.

A local `CLAUDE.md`, `GEMINI.md`, or similar tool bridge MAY exist only when the tool consumes it automatically or a real local consumer requires it. It MUST disclaim independent Product/status authority.

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
| `docs/development/` | Repository-local engineering, documentation, Git, CI, and proof rules |
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

A repository MAY use minimal frontmatter when it materially improves machine navigation, for example:

```yaml
---
id: persistence-architecture
kind: authority
owner: architecture
summary: Owns current persistence architecture.
---
```

Do not add metadata merely for uniformity when filenames/indexes already provide sufficient routing.

## 7. Status and roadmap law

`docs/roadmap.md` is the **only mutable current-program status authority**.

It MUST make it possible to determine:

- current stage/gate;
- completed stages that matter to progression;
- next stage or exact next action;
- whether implementation is allowed or blocked;
- entry/exit conditions or reopen triggers where material.

Other durable documents MAY contain frozen historical closure snapshots, but MUST label them as snapshots and route current status back to `docs/roadmap.md`.

Indexes, README, AGENTS, Product, Architecture, PR descriptions, and phase summaries MUST NOT become parallel mutable status authorities.

## 8. Decision register law

`docs/decisions/index.md` or an equivalent clearly named register MUST allow a fresh actor to discover current decision disposition without reconstructing review chronology.

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

A material gate MAY use:

```text
docs/work/current/index.md
docs/work/current/proposal.md
docs/work/current/plan.md
```

Use only files the gate actually needs. They MUST be absorbed or deleted before merge.

### Fable review isolation

The candidate branch SHOULD remain free of `ai-dialog.md`.

Create a bounded review branch from the exact candidate:

```text
<stage-branch>
→ review/<stage>-fable
```

The review branch adds only:

```text
docs/work/current/ai-dialog.md
```

The review guard MUST be capable of proving:

```text
review branch - candidate branch
= docs/work/current/ai-dialog.md only
```

Fable writes review input there. The Lead/Codex applies accepted corrections to the candidate branch. The review branch is then closed/deleted. `ai-dialog.md` never enters the merge candidate or `main`.

Follow the canonical **Standard Fable review workflow** in `README.md` of this methodology repository. Reviewer output is Evidence, never authority. A second review round occurs only when a real material contradiction survives.

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

## 11. Branch and PR lifecycle

Default lifecycle:

```text
main
→ one branch / one Draft PR for one coherent stage or gate
→ analysis + execution
→ consolidated candidate
→ final independent review when required
→ bounded corrections
→ verification
→ explicit merge authorization when repository governance requires it
→ squash merge
→ automatic head-branch deletion
→ next stage starts from updated main
```

Rules:

- do not stack a later stage on an unmerged earlier stage by default;
- do not commit directly to `main`;
- do not force-push or rewrite shared history;
- declare both what changes and what deliberately does not change;
- dependency/lockfile changes require explicit scope;
- temporary plans, candidates, review channels and handoffs do not survive merge;
- merge/rebase methods other than squash SHOULD be disabled for normal product repositories unless a repository has a proven history-preservation requirement;
- `main` MUST be protected from force-push and deletion and require PR-based changes.

## 12. Verification contract

Each repository owns its tools, but its verification MUST cover the relevant organizational properties below.

### Bootstrap and authority

- `AGENTS.md + docs/index.md + docs/roadmap.md <= 20 KiB`;
- `docs/roadmap.md` is the sole mutable status/next-action authority;
- `README.md` is landing-only;
- the default task pack is at most five files;
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

- decision dispositions are valid and current;
- unique unmerged provenance is not deleted while still required;
- a retired check/control requires current evidence that its subject population is zero or replacement coverage is complete.

### Guard quality

- a material guard must be shown capable of firing through a deterministic negative control or equivalent falsifier;
- do not accept a presence-only control for a behavioral property;
- compare the intended base to candidate for diff checks; a clean checkout `git diff --check` with no range is not proof of the PR diff;
- when implementation is blocked and the repository is intentionally architecture-only, prefer an explicit **allowlist of permitted top-level surfaces** over a denylist of old implementation names.

### Required aggregate check

Every repository MUST expose at least one required aggregate status check protecting `main`.

New or fully realigned repositories SHOULD name the aggregate `required`. Existing repositories MAY retain a functioning protected check name until its GitHub branch-protection configuration is deliberately migrated; do not break a working protection rule solely for naming uniformity.

## 13. Research, Evidence, framework skills, and external docs

Research and Evidence support decisions; they do not create Product authority.

- `research/` may remain deep when it has a named current/future consumer, but is never default-read;
- `evidence/` and `qualification/` preserve proof boundaries and exact provenance;
- vendored framework skills are execution aids, not Product architecture;
- current external documentation, Context7, framework source, and live probes are used only when materially relevant;
- exact pinned source/configuration and bounded Evidence decide version-specific qualification claims.

## 14. Repository-local specialization

A repository SHOULD keep its local specialization in `docs/development/` and reference this standard instead of copying it.

Local rules may strengthen this standard for real Product/security/tooling constraints. They MUST NOT silently weaken it.

A justified deviation MUST state:

```text
standard rule
local deviation
real consumer/failure class
why the default is insufficient
reopen/removal trigger
```

Do not create a synchronization framework to distribute this document. Repositories cite the canonical version and migrate deliberately when a material amendment is ratified.

## 15. Conformance success test

A conforming repository passes this fresh-actor test:

> Starting from `AGENTS.md`, a new human or agent can find the sole current roadmap, choose the smallest task-specific authority pack, distinguish authority from research/Evidence/history, understand the PR/review/verification boundary, and begin work without conversation archaeology or recursive repository reading.

If achieving that requires reading several status dashboards, all phase documents, Git history, review dialogues, or a tool-specific plan tree, the repository is not conforming even if every individual document is correct.
