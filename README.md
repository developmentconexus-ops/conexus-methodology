# Conexus Methodology

Canonical home of the **DevelopmentConexus Engineering Method**.

## Authority

- [`METHOD.md`](METHOD.md) is the **single normative organizational engineering method**.
- Current accepted version: **1.0.0**.
- It governs **how engineering is reasoned about and decided** across DevelopmentConexus repositories.
- Product architecture, repository status, technology, verification commands, and repo-specific safety rails remain owned by each repository.

Derived summaries, prompt snippets, templates, or local projections MUST cite the canonical method/version and MUST NOT become independent authorities.

## Standard Fable review workflow

Use Fable as the independent adversarial challenger for material engineering analysis when the Method or the repository calls for independent review — for example architecture/planning packages, batches of related decisions, rebaseline stages, or other high-impact decisions.

Standard flow:

```text
1. Lead performs the analysis independently.
2. Lead prepares a bounded NON-AUTHORITATIVE candidate/review package.
3. Lead sends Fable a compact chat handoff with repo/branch/HEAD, target and review focus.
4. Fable reconstructs repository authority first, applies METHOD.md, challenges the candidate adversarially, researches when materially useful, and looks for a better Global Maximum without adding YAGNI/overengineering.
5. Fable materializes its review as NON-AUTHORITATIVE review input in the working repository when the review is part of the repo workflow. If the operator explicitly authorizes publication, completion includes commit + push to the designated remote branch + verification that the remote HEAD contains the review commit; a local-only commit is not completion. Without publication authorization, Fable stops after the local commit and reports its SHA.
6. Lead confronts each material finding technically; reviewer output is evidence, never authority.
7. Round 2 happens only if a real material contradiction survives.
8. Lead consolidates the candidate.
9. Operator ratifies when required (for example `Aprovado`). Only then may the repository's normal process turn the result into authority/status.
```

Publication authorization applies only to the review artifact and branch named in the task; it does not imply merge authorization or permission for unrelated repository writes.

Fable must not be used for agreement theater. It should attack root cause, assumptions, boundaries, authority, YAGNI, foreseeable retrofit and credible alternatives. External references, current framework documentation, Context7, source inspection or other research may be used when they materially improve the decision, but references do not create requirements.

Do not split one coherent decision package into artificial micro-reviews. Review the smallest coherent batch that can be challenged meaningfully.

A task-specific Fable handoff should stay short because this workflow is already canonical. Normally it only needs the repository/ref, the candidate to review and the specific risks/questions to attack.

## Consumption by repositories

A repository should keep its own `AGENTS.md` as the local bootstrap/router. It does not copy this workflow.

When Fable review is used, the local `AGENTS.md` only needs to route the agent to this README section after the repository's own authority/read order has been reconstructed.

Example:

```text
For material independent review with Fable, follow the canonical
"Standard Fable review workflow" in
`developmentconexus-ops/conexus-methodology/README.md`.
Repository authority remains local; Fable review is non-authoritative input until ratified.
```

## Change rule

Changing `METHOD.md` is a material decision. Apply the method to the amendment and require explicit operator ratification.

Keep this repository small. Git history is the change record. Do not add frameworks, sync machinery, CI, templates, or duplicated guidance without a demonstrated failure class or real consumer.
