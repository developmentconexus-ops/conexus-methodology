# Conexus Methodology — Agent Bootstrap

## Start here

Before editing, revalidate repository/branch/HEAD and any open methodology PR. Current repository authority beats chat or an old handoff.

Read only what the task requires:

1. [`METHOD.md`](METHOD.md) — reasoning kernel for every material engineering decision.
2. [`REPOSITORY-STANDARD.md`](REPOSITORY-STANDARD.md) — when repository organization, continuity, documentation, Git/PR, review, or methodology consumption is in scope.
3. [`FRONTEND-METHOD.md`](FRONTEND-METHOD.md) — when human-facing Product experience/frontend planning is in scope.
4. [`REALIZATION-METHOD.md`](REALIZATION-METHOD.md) — when technology research, dependency/version choice, production implementation, integration, or proof is in scope.
5. [`README.md`](README.md) — authority/composition map and canonical Fable review workflow.

Do not load all specialist methods by default merely because they exist.

## Authority rules

- `METHOD.md` is the sole organizational engineering reasoning kernel.
- `REPOSITORY-STANDARD.md` is the organizational repository operating authority.
- `FRONTEND-METHOD.md` specializes the Method for Product experience/frontend planning.
- `REALIZATION-METHOD.md` specializes the Method for production realization.
- Specialist methods MUST return material upstream contradictions to `METHOD.md`; they may not silently redefine Product/architecture authority.
- Product architecture, repository status, stage/block names, exact technology, verification commands, and repo-specific safety rails remain local to consuming repositories.
- Local copies, generated projections, submodules, summaries, and prompt snippets are delivery aids only unless explicitly designated canonical. Consumers pin the exact methodology commit; normative auto-follow of `main` is prohibited.

## Editing rule

A change to any organizational authority here is a material cross-repository decision.

Apply the current accepted Method, inspect affected consumers/local lineages, challenge the candidate independently when required, and require explicit operator ratification before it becomes organizational authority.

Keep authorities LLM-first: maximum decision signal per token, one owner per rule, no duplicated tutorial prose, repository-specific fact, template ceremony, or synchronization machinery without demonstrated value.

## Repository boundary

This repository owns only:

- organizational engineering reasoning;
- organizational repository operation/continuity;
- reusable frontend Product-experience planning;
- reusable evidence-grounded realization engineering;
- the small canonical Fable review convention and method-composition map in `README.md`.

Do not add Product-specific technology decisions, stage roadmaps, prompt libraries, template packs, CI/distribution frameworks, or automatic cross-repository sync until a demonstrated failure class and real consumer justify them.
