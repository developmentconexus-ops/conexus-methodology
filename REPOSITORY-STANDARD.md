# DevelopmentConexus Repository Standard

**Version:** 1.1.0  
**Status:** CANDIDATE FOR ORGANIZATIONAL RATIFICATION  
**Scope:** active DevelopmentConexus Product and platform repositories

## 1. Purpose

Define the common repository operating envelope so a fresh human/agent can recover current state, select the minimum context, work safely, review independently when needed, and continue without conversation archaeology.

This standard does not define Product semantics, architecture, technology, stage names, or local verification commands.

Organizational composition:

```text
ROUTER.md                    select minimum method context
METHOD.md                    material engineering reasoning kernel
REPOSITORY-STANDARD.md       repository operation/continuity
FRONTEND-METHOD.md           frontend Product-experience specialization
REALIZATION-METHOD.md        production realization specialization
ADVERSARIAL-REVIEW-METHOD.md independent challenge specialization
```

No specialist silently replaces Product/architecture authority.

## 2. Hard standard versus repository freedom

### Required organizational envelope

Every conforming Product/platform repository MUST provide:

- landing-only `README.md`;
- compact bootstrap-only `AGENTS.md`;
- `docs/index.md` as canonical task/intention router;
- `docs/roadmap.md` as sole mutable stage/status/next-action authority;
- one current authority per meaning;
- exact pinned `conexus-methodology` commit;
- task-selective reading with a default pack of at most five repository files;
- fresh-session recovery independent from chat history;
- one coherent acceptance increment per PR by default;
- branch-only temporary work that cannot enter `main`;
- squash merge as normal integration;
- protected `main` with no force-push/deletion;
- at least one required aggregate verification check;
- mechanically enforced `AGENTS.md + docs/index.md + docs/roadmap.md <= 20 KiB`.

### Repository-owned freedom

Each repository owns Product/architecture content, local stage/block names, implementation stack/tree, exact verification, additional documentation surfaces, domain safety rails, and the semantic size of an acceptance increment.

Standardize the operating envelope, not the Product.

## 3. Fresh-session recovery and context loading

### 3.1 Revalidate state before reading remembered state

A fresh session first establishes, as applicable:

```text
repository identity / remote
current checkout branch + HEAD
remote main HEAD
worktree cleanliness / unowned state
relevant active candidate PR + base/head
aggregate CI/check status
```

Do not assume an old handoff SHA or prior chat is current.

### 3.2 Default repository route

```text
AGENTS.md
→ docs/index.md
→ docs/roadmap.md
→ pinned methodology ROUTER.md
→ selected Method profile
→ 1–2 task-owning repository documents
```

Normal repository task context MUST fit in five files or fewer. Exceed only for a named material reason.

Do not recursively read `docs/`, phase history, Git history, research, Evidence, qualification harnesses, code or closed review dialogue before a current claim requires them.

### 3.3 Method loading

`ROUTER.md` selects methodology. Do not auto-load the entire methodology suite.

Default:

```text
material decision     → METHOD
frontend planning     → METHOD + FRONTEND
production realization→ METHOD + REALIZATION
adversarial review    → METHOD + ADVERSARIAL-REVIEW
repo/governance work  → REPOSITORY-STANDARD (+ METHOD when material)
```

At most one specialist method is loaded by default. Multiple specialists require a named cross-cutting reason or a reconsideration of whether the task should split.

### 3.4 Optional current method profile

`docs/roadmap.md` MAY contain one compact selector when useful:

```text
Method profile: METHOD + FRONTEND / B09
```

or:

```text
Method profile: METHOD + ADVERSARIAL-REVIEW
```

This is routing, not duplicated methodology. Omit it when obvious.

### 3.5 Continuation without chat

For an active unmerged candidate:

- candidate branch `docs/roadmap.md` owns candidate status/next action;
- `main` owns integrated status and may legitimately lag;
- PR descriptions help locate proof/candidate identity but never replace the roadmap;
- a resumable material checkpoint must exist in lawful repository state, not only chat/uncommitted scratchpad.

Chat/handoffs are optional routing convenience.

## 4. Root files

### `README.md`

Landing page only. It MAY identify the Product and stable setup/verification entrypoints. It MUST NOT own mutable status, next action, architecture authority, or active review state.

### `AGENTS.md`

Bootstrap/router only. Keep it compact and include:

- fresh-session state revalidation;
- repository authority route;
- exact methodology pin and route to `ROUTER.md`;
- local hard stops/safety rails;
- local verification commands;
- materially repository-specific Git/publication rules.

It MUST NOT duplicate Methods, roadmap, Product/architecture prose, full review protocol, long research guidance, or session history.

A tool-specific `CLAUDE.md`, `GEMINI.md`, etc. MAY exist only for a real automatic consumer and MUST disclaim independent Product/status/method authority. For Claude Code, prefer a tiny bridge to `AGENTS.md`; do not import the entire method suite into auto-context.

## 5. Documentation structure

Create only paths with a real consumer. Reserved semantic model:

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

| Surface | Responsibility |
|---|---|
| `docs/index.md` | task/intention routing only |
| `docs/roadmap.md` | sole mutable current status/next action |
| `docs/product/` | Product scope, actors, journeys, invariants |
| `docs/architecture/` | current structural architecture/ownership |
| `docs/decisions/` | current decisions/dispositions/reopen triggers |
| `docs/phases/` | durable closure/result summaries when useful |
| `docs/development/` | local engineering/Git/CI/proof specialization |
| `docs/reference/` | detailed current reference; not default-read |
| `docs/research/` | comparative study; never implicit authority |
| `docs/evidence/` | durable proof/provenance; never Product authority |
| `docs/diagrams/` | source-first diagrams with named semantic owner |
| `docs/work/` | temporary non-authoritative branch work |

Executable proof/qualification MAY live outside `docs/`; it remains opt-in context.

Durable names use semantic lowercase kebab-case. Avoid session/reviewer/date/final/old naming unless genuinely part of subject identity.

## 6. Roadmap and decision authority

`docs/roadmap.md` is the only mutable current-program status authority. It must make discoverable:

```text
current stage/gate/block
integrated increments relevant to progression
exact next action
implementation allowed/blocked
active blocking Finding/prerequisite when material
```

A stage MAY remain OPEN across several integrated acceptance increments. Merge does not imply stage closure.

Other documents may contain frozen closure snapshots but route current status to the roadmap.

A decision register (`docs/decisions/index.md` or equivalent) must make current material decisions/dispositions discoverable without reconstructing review chronology. Preserve, as applicable:

```text
ID / subject
disposition
rationale/consequences
owning authority
supersedes/refines
Evidence
reopen trigger
```

## 7. Temporary work

Temporary work is non-authoritative and branch-only.

Use only files actually needed, e.g.:

```text
docs/work/current/proposal.md
docs/work/current/plan.md
docs/work/current/ai-dialog.md
```

Temporary work MUST be absorbed into durable authority or deleted before merge.

No permanent session handoff/dialogue/round/archive tree is allowed in the live documentation surface.

## 8. Independent adversarial review transport

Follow pinned `ADVERSARIAL-REVIEW-METHOD.md`.

Candidate branch remains free of `ai-dialog.md`. Create an isolated review branch/worktree from the exact candidate, normally:

```text
review/<increment>-adversarial-r1
```

The review branch SHOULD differ from the exact candidate only by:

```text
docs/work/current/ai-dialog.md
```

Repository verification SHOULD prove:

```text
review branch - exact candidate
= docs/work/current/ai-dialog.md only
```

`ai-dialog.md` is temporary versioned Lead↔Challenger transport, never Product/architecture/status authority and never merged.

Current operating deployment is ChatGPT Lead + Claude Code Challenger, but the repository contract depends on roles, not vendor identity.

A later review round starts from the exact corrected candidate on a fresh review branch only when the review method says Round 2 is justified.

## 9. Git is the archive — reachability law

Git history is sufficient archive only while required history remains reachable.

For content previously merged to `main`, normal Git history is generally sufficient after current semantics are consolidated.

Before deleting the last branch/ref for important unmerged work:

1. consolidate still-current semantic obligations into durable authority;
2. determine whether byte-level provenance is still required;
3. if required, preserve an explicit durable ref/tag to the exact lineage and record where to find it;
4. only then delete the branch.

Do not create working-tree archive directories or tags for ordinary superseded material with no current consumer.

## 10. Acceptance increments and PR lifecycle

### 10.1 Definition

An **acceptance increment** is the smallest semantically coherent change that can be independently accepted/rejected while leaving the repository in a valid reconstructable state.

It is not defined by LOC, commit count, file count, or roadmap-stage boundary.

Typical increments:

- one frontend material block through operator LOCK + trace closure;
- one upstream Product/backend correction exposed by a downstream Finding;
- one bounded architecture/contract decision package;
- one implementation vertical slice with its proof;
- one stage closeout after substantive increments are already integrated.

### 10.2 Default lifecycle

```text
main
→ branch + Draft PR for one acceptance increment
→ analysis/execution
→ candidate
→ independent review when triggered
→ bounded corrections
→ verification
→ explicit merge authorization when required
→ squash merge
→ delete head branch
→ revalidate main
→ next dependent increment from updated main
```

A stage may remain OPEN after any merge.

### 10.3 Split law

Split when parts can be independently accepted/rejected and especially when they have different semantic owners, separate operator decisions, a separable downstream Finding/upstream correction, materially different proof/review needs, or one combined surface becomes hard to reason about.

Do not split mechanically by file, P-step, endpoint or arbitrary LOC.

Diff size is a review-risk signal, not a hard threshold. A materially large PR should state why it cannot be decomposed into coherent increments.

Dependent later increments do not stack on unmerged earlier increments by default. Independent parallel work requires explicit boundaries and must not treat unmerged candidates as integrated authority.

### 10.4 General Git rules

- no direct commits to `main`;
- no force-push/shared-history rewrite;
- declare what changes and deliberately does not;
- dependency/lockfile changes require explicit scope;
- temporary work/review transport does not survive merge;
- squash is normal integration;
- `main` must be protected from force-push/deletion and changed through PRs.

## 11. Verification contract

Each repository owns its tools, but verification covers relevant organizational properties.

### Bootstrap/context

- bootstrap trio <= 20 KiB;
- roadmap is sole mutable status/next-action authority;
- README landing-only;
- default repository task pack <= 5 files;
- AGENTS has fresh-session revalidation + exact methodology pin/route;
- routers/relative links resolve;
- durable authority does not depend on `docs/work/**`.

### Temporary/review hygiene

Merge candidates and `main` contain no:

```text
docs/work/**
ai-dialog / AI-DIALOG
docs/superpowers/
permanent handoff/dialogue/round trees
active old/archive/duplicate-roadmap trees
```

Review isolation is mechanically checked when the repository uses adversarial review branches.

### Guard quality

- material guards demonstrate a deterministic negative path/falsifier;
- presence-only control does not prove behavioral property;
- PR diff proof compares intended base...candidate, not an empty checkout diff;
- retired controls require attributable zero subject population or proved replacement coverage.

### Aggregate check

Every Product/platform repository exposes at least one required aggregate check protecting `main`. Existing working protected names may remain until deliberately migrated.

## 12. Research/Evidence/external docs

Research and Evidence support decisions; they do not create Product authority.

Use external/current docs, framework source, Context7, live probes and deep Evidence only when materially relevant. Exact selected source/configuration decides version-sensitive claims.

Reusable production realization follows pinned `REALIZATION-METHOD.md`; reusable frontend planning follows pinned `FRONTEND-METHOD.md` rather than silently forked local copies.

## 13. Organizational methodology consumption

Consumers reference:

```text
developmentconexus-ops/conexus-methodology
+ exact accepted commit
```

The pin is discoverable from bootstrap.

Never consume normative methodology as automatically moving `main`; that would change rules underneath open Product work.

Default: canonical reference. If a proven tool/local/offline consumer needs physical bytes, a read-only pinned Git submodule or generated projection MAY be used as a delivery/cache mechanism provided:

```text
canonical repo + exact commit recorded
auto-follow main disabled
local edits prohibited
explicit non-independent authority
upgrade only through explicit PR moving pin
```

Do not introduce organization-wide sync/bot machinery until repeated real consumer cost proves the need. If later justified, automation opens methodology-upgrade PRs; it does not silently mutate consumers.

## 14. Repository-local specialization

Keep local specialization in `docs/development/` and reference organizational Methods instead of copying/redefining them.

A local rule may strengthen the standard for a real Product/security/tooling constraint; it may not silently weaken it.

A deviation records:

```text
organizational rule
local deviation
real consumer/failure class
why default is insufficient
reopen/removal trigger
```

## 15. Conformance success test

A conforming repository passes:

> From a fresh session, an agent can revalidate repository/PR/CI state, follow `AGENTS → index → roadmap → methodology router`, load only the required Method profile and task owners, distinguish authority from Evidence/history/review transport, and continue active work without chat archaeology or recursive repository reading.

If that requires several dashboards, all Methods, whole-repo reading, permanent handoffs/dialogues, or guessing which PR is current, the repository is not conforming.
