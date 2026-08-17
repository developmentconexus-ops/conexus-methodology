# Agent Instructions

## Start here

1. Read [`METHOD.md`](METHOD.md).
2. Treat `METHOD.md` as the only normative engineering-method authority in this repository.
3. Use `README.md` as the repository map and for the standard Fable review workflow.

## Editing rule

- A change to `METHOD.md` is a **material decision** and requires explicit operator ratification.
- Apply the current method to any proposed amendment.
- Keep the normative method LLM-first: maximum decision signal per token; no duplicated rule, tutorial prose, repo-specific facts, or ceremony without demonstrated value.
- Do not create a second normative summary or local reinterpretation of `METHOD.md`.

## Repository boundary

This repository owns the organizational engineering method and the small cross-repository Fable review convention documented in `README.md`.

Product architecture, repository status, verification commands and repo-specific safety rails remain owned by consuming repositories.

Do not add sync machinery, CI, distribution tooling, prompt libraries or governance frameworks until a real failure class or consumer justifies them.
