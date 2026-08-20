# Conexus Methodology

Canonical home of the DevelopmentConexus cross-repository engineering authorities.

## Authorities

- [`METHOD.md`](METHOD.md) — **DevelopmentConexus Engineering Method v1.0.0**. Governs how engineering is reasoned about and decided.
- [`REPOSITORY-STANDARD.md`](REPOSITORY-STANDARD.md) — **DevelopmentConexus Repository Standard v1.0.0**. Governs the common repository operating envelope: bootstrap, documentation information architecture, status, temporary work, Git/PR lifecycle, review isolation, context control, and minimum verification properties.

Product semantics, product architecture, stage names, technology, runtime topology, exact verification commands, and repository-specific safety rails remain owned by each consuming repository.

Derived summaries, prompt snippets, templates, or local projections MUST cite the canonical authority/version and MUST NOT become independent authorities.

## Standard Fable review workflow

Use Fable as the independent adversarial challenger for material engineering analysis when the Method or the repository calls for independent review — for example architecture/planning packages, batches of related decisions, rebaseline stages, or other high-impact decisions.

Standard flow:

```text
1. Lead performs the analysis independently.
2. Lead prepares a bounded NON-AUTHORITATIVE candidate/review package.
3. Lead sends Fable a compact chat handoff with repo/branch/HEAD, target and review focus.
4. Fable reconstructs repository authority first, applies METHOD.md, challenges the candidate adversarially, researches when materially useful, and looks for a better Global Maximum without adding YAGNI/overengineering.
5. When repository workflow uses an isolated review branch, Fable writes only the temporary review channel admitted by REPOSITORY-STANDARD.md. Otherwise it materializes only the review artifact explicitly authorized by the task.
6. Publication authorization applies only to the named review artifact/branch. Local-only work is not completion when publication was authorized.
7. Lead confronts each material finding technically; reviewer output is evidence, never authority.
8. Round 2 happens only if a real material contradiction survives.
9. Lead consolidates the candidate.
10. Operator ratifies when required. Only then may repository process turn the result into authority/status.
```

Fable must not be used for agreement theater. It should attack root cause, assumptions, boundaries, authority, YAGNI, foreseeable retrofit and credible alternatives. External references, current framework documentation, Context7, source inspection or other research may be used when they materially improve the decision, but references do not create requirements.

Do not split one coherent decision package into artificial micro-reviews. Review the smallest coherent batch that can be challenged meaningfully.

A task-specific Fable handoff should stay short because this workflow is already canonical. Normally it only needs the repository/ref, candidate, and specific risks/questions to attack.

## Consumption by repositories

A repository keeps its own `AGENTS.md` as the local bootstrap/router. It cites these organizational authorities rather than copying them.

Example:

```text
Engineering reasoning:
developmentconexus-ops/conexus-methodology/METHOD.md v1.0.0

Repository operating envelope:
developmentconexus-ops/conexus-methodology/REPOSITORY-STANDARD.md v1.0.0
```

Repository-local rules may strengthen the standards for a real local constraint; they may not silently redefine or weaken them.

## Change rule

Changing `METHOD.md` or `REPOSITORY-STANDARD.md` is a material cross-repository decision. Apply the current Method, assess downstream consumers, and require explicit operator ratification.

Keep this repository small. Git history is the change record. Do not add sync machinery, CI frameworks, templates, prompt libraries, or duplicated local guidance without a demonstrated failure class or real consumer.
