# Agent Instructions

## Start here

1. Read [`METHOD.md`](METHOD.md) for engineering reasoning.
2. Read [`REPOSITORY-STANDARD.md`](REPOSITORY-STANDARD.md) for the cross-repository operating envelope when repository structure/workflow is in scope.
3. Use [`README.md`](README.md) as the authority map and canonical Fable review workflow.

## Authority rules

- `METHOD.md` is the only normative organizational engineering-method authority.
- `REPOSITORY-STANDARD.md` is the only normative organizational repository-operating-standard authority.
- Product architecture, repository status, stage names, technology, verification commands, and repo-specific safety rails remain local to consuming repositories.
- Local copies/summaries are derived aids only unless explicitly ratified as a different authority.

## Editing rule

A change to either organizational authority is a material cross-repository decision. Apply the current Method, inspect affected consumers, and require explicit operator ratification.

Keep both documents LLM-first: maximum decision signal per token; no duplicated rule, tutorial prose, repository-specific fact, or ceremony without demonstrated value.

## Repository boundary

This repository owns only:

- the organizational Engineering Method;
- the organizational Repository Standard;
- the small canonical Fable review convention in `README.md`.

Do not add sync machinery, CI/distribution frameworks, prompt libraries, templates, or governance tooling until a demonstrated cross-repository failure class and real consumer justify them.
