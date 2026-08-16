# Agent Instructions

## Start here

1. Read [`METHOD.md`](METHOD.md).
2. Treat `METHOD.md` as the only normative engineering-method authority in this repository.
3. Use `README.md` only as a repository map.

## Editing rule

- A change to `METHOD.md` is a **material decision** and requires explicit operator ratification.
- Apply the current method to any proposed amendment.
- Keep the normative method LLM-first: maximum decision signal per token; no duplicated rule, tutorial prose, repo-specific facts, or ceremony without demonstrated value.
- Do not create a second normative summary, prompt, template, or local reinterpretation.
- Derived aids must identify themselves as non-authoritative and cite the canonical method/version.

## Repository boundary

This repository owns the organizational engineering method only. Product architecture, repository status, workflows, verification commands, tool-specific bootstraps, and repo-specific safety rails belong in consuming repositories.

Do not add sync machinery, CI, distribution tooling, or governance frameworks until a real failure class or consumer justifies them.
