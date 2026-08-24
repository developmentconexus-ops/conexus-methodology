# DevelopmentConexus Engineering Method

**Version:** 1.1.0  
**Authority:** organizational engineering reasoning standard  
**Scope:** all DevelopmentConexus repositories; human, agent, or hybrid engineering

## Objective

Find the **smallest sustainable solution** that preserves essential complexity, removes accidental complexity, resolves the root cause, and avoids foreseeable structural dead ends.

**LLM-first:** maximize decision signal per token. State each normative rule once. Prefer short imperatives, stable vocabulary, and explicit conditionals. Do not add exposition, examples, artifacts, reviews, classifications, or ceremony unless they materially improve decision correctness, evidence quality, or risk control.

This is a **reasoning method, not a process framework**.

## 1. Scope and governance

- This method governs **how engineering is reasoned about and decided**. It does not define Product architecture, technology, status, workflow, or repository-specific policy.
- Repository instructions or organizational specialist methods may specialize or operationalize this method; they MUST NOT silently weaken or redefine it. Conflicts inside this method's scope must be surfaced.
- **Authority freezes execution, not inquiry.** Discovery may challenge accepted authority with material Evidence; execution may not silently ignore accepted authority.
- A change to this method is itself a material decision: apply the current accepted Method, assess affected consumers, record the amendment, and require operator ratification.
- Summaries, prompt snippets, templates, local copies, and tool-specific projections are derived aids unless explicitly designated canonical. They MUST cite the canonical version and MUST NOT become a second authority.

Current organizational specialist authorities may include the Repository Standard, Frontend Product Experience Method, Evidence-Grounded Realization Method, and Independent Adversarial Review Method. They compose with this Method; they do not become alternative reasoning kernels.

Reopen this method only when Evidence shows a core rule is systematically misclassifying work, creating ceremony without decision-quality gain, forcing repository bindings to violate the method, or failing for a materially new actor/work class.

## 2. Materiality and proportionality

A decision is **material** when it touches—creates, changes, removes, or deliberately leaves unprotected—any of:

- an invariant or correctness property;
- authority, ownership, or an architectural boundary;
- a public/external contract or persistent data meaning;
- a security property or trust boundary;
- an external or irreversible effect;
- concurrency, recovery, or temporal correctness;
- user-observable behavior on which another actor/system depends;
- a hard-to-reverse technology or topology commitment.

If materiality cannot be determined safely, treat the decision as material until clarified.

For a material decision, the non-degradable minimum is:

- a citeable decision/outcome with its basis;
- the invariant, when one is touched;
- a proof strategy proportional to the claim;
- reopen triggers.

Depth scales with **materiality, irreversibility, uncertainty, and blast radius**. Ceremony—format, length, section count, named profiles—may shrink. Correctness obligations may not. Trivial or mechanical work should remain trivial.

## 3. Decision core

Use this flow proportionally:

```text
Evidence
→ Known / Inferred / Unknown / Deferred
→ Root Cause
→ Target Invariant
→ Constraints
→ Credible Alternatives
→ Local Maximum vs Global Maximum
→ Essential vs Accidental Complexity
→ YAGNI / Overengineering / Future Cost
→ Authority / Boundary when relevant
→ Enforcement
→ Proof Strategy
→ Adversarial Challenge
→ Decision
→ Reopen Triggers
```

### Evidence

- Start from Evidence, not a preferred solution.
- Evidence strength is **claim-relative**. A mock may prove local contract behavior; it does not prove a real integration.
- Unknown MUST remain unknown; never convert uncertainty into a convenient default.
- Current code, schemas, APIs, tests, runtime, history, and prior decisions are Evidence. Existing implementation is not target authority merely because it exists.
- Structural Inversion Test: **if the current implementation were the opposite in every relevant respect, which parts of the conclusion would still be true?**
- Prefer primary/official sources for unstable external facts.

### Root cause and invariant

Do not patch the symptom before identifying the structural condition that made it possible. Ask whether the same condition can produce other failures and whether a local correction leaves the defect class reachable.

State the target invariant independently of implementation: what must remain true in every valid realization?

### Global Maximum

A **Local Maximum** is the best answer inside the current structure. A **Global Maximum** is the best sustainable structure for the real constraints, even when the current structure must change.

Global Maximum does **not** mean maximum abstraction, infrastructure, generality, future-proofing, or redesign. Prefer it only when the current structure preserves the root cause or creates a foreseeable structural dead end.

### Complexity law

Preserve **essential complexity** from the real problem; remove **accidental complexity** introduced by the solution.

YAGNI removes unsupported capability, speculative frameworks, unused extensibility, duplicate authorities, and hypothetical compatibility. It MUST NOT remove a known invariant, safety property, required isolation/recoverability/auditability, Evidence/provenance, or a seam justified by evidenced evolution.

Before adding a material abstraction/mechanism, ask:

1. What concrete consumer, risk, or defect requires it now?
2. What defect class does it eliminate?
3. Is a simpler existing boundary sufficient?
4. Can it be added later without dismantling authority or duplicating semantics?
5. Does it reduce total complexity or only move it?

Future evolution is evidenced by a declared Product objective, accepted requirement, named consumer, or real constraint. Imagined possibility is not Evidence.

**Prepare the seam, not the entire future capability.**

### Authority and mechanism

**Mechanism ≠ Authority.** Shared machinery may centralize retries, scheduling, validation, observability, serialization, caching, or similar mechanics without owning the business/system meaning it supports.

When ownership matters, state who owns meaning and lifecycle, what remains external, what callers may depend on, and what the boundary does not own. Two authorities for the same meaning are presumed wrong until justified.

A material dependency/reuse choice must deliberately preserve ownership: differentiated semantics must not become commodity by accident; commodity machinery must not become authority by convenience.

### Downstream falsification and bounded rebaseline

Accepted upstream authority is **binding for execution and falsifiable for inquiry**.

A downstream activity—frontend planning, realization, implementation, security analysis, integration proof, concurrency testing, recovery testing, or another specialist method—may expose material Evidence that an accepted upstream assumption, capability boundary, or contract is insufficient.

When this occurs:

```text
downstream Evidence
+ accepted upstream authority materially insufficient/contradicted
= UPSTREAM FINDING
```

The downstream actor MUST NOT:

```text
silently override accepted authority
silently invent replacement authority
suppress a proven requirement merely to preserve prior planning
patch around the contradiction while representing the upstream decision as still sufficient
restart unrelated valid work by default
```

Instead:

```text
1. state the Finding and the protected property/user/system outcome;
2. suspend only the affected downstream scope;
3. identify the smallest owning Product/architecture/contract decision;
4. run the Decision Core against current Evidence and credible alternatives;
5. operator/owning authority ratifies, rejects, defers, or restructures;
6. update the owning authority first;
7. boundedly rebaseline only affected downstream artifacts;
8. preserve prior valid locks/decisions unless the new Evidence actually falsifies them;
9. resume from accepted authority.
```

`Current implementation/plan lacks X` is neither automatic authority to invent X nor automatic authority to suppress X. Evidence decides whether X is required, rejected, or deferred.

This law is symmetric across layers. Frontend may falsify backend planning; implementation may falsify architecture assumptions; real provider Evidence may falsify integration planning; recovery/concurrency proof may falsify a previously accepted mechanism. The smallest owning authority reopens—not the entire program by reflex.

### Enforcement

Choose the strongest reasonable enforcement that covers **all paths capable of reaching the protected state**, including paths the boundary structurally admits. Structure, types, schema constraints, runtime fail-closed checks, tests, static guards, and documentation are mechanisms—not a fixed ranking.

Among equally sufficient mechanisms, prefer earlier feedback unless it adds disproportionate complexity.

A control counts only when its firing can be demonstrated or credibly falsified.

### Proof Strategy Before Implementation

Define how the protected claim could be proven false **before** implementing the solution.

Proof must match the claim and maturity level: architecture may require counterexample analysis, independent challenge, coherence review, or a targeted probe; implementation may require compile/type/schema failure, negative fixtures, integration, restart/recovery, concurrency, contract-diff, or end-to-end Evidence.

Artifact existence is not proof. **A control that cannot be shown to fire is not proven.**

### Adversarial challenge and findings

Attack the preferred decision: strongest counterargument, invalidating assumption, duplicate authority, framework/provider overfit, partial failure, concurrency, restart, migration trap, hardest future change.

Self-review is not independent review. Before ratification, use an independent/fresh challenger when a decision creates or moves authority/trust boundaries, has external/irreversible effects, or binds multiple repositories. A repository may require independent challenge more often, not less than this floor.

When independent review runs, use the pinned `ADVERSARIAL-REVIEW-METHOD.md`; load other specialist methods only when the claim under review requires them.

A reviewer Finding or severity is Evidence, not requirement authority. First classify it against current authority. A defect against existing authority may be corrected; a proposal that creates new authority/requirement must return to decision, never enter disguised as a correction.

## 4. Outcomes, stop, and reopen

Every material decision ends as one of:

- **RESTRUCTURE NOW** — implement the Global Maximum now.
- **CURRENT STRUCTURE CONFIRMED** — structure is sound; make the bounded correction.
- **NO CHANGE REQUIRED** — examined Evidence supports no change; record what was examined and what would have falsified the conclusion.
- **TRANSITIONAL SOLUTION** — temporary local maximum; record the property protected now, why the target cannot land now, the successor, and deletion/replacement condition.
- **STOP / SPLIT PREREQUISITE** — unresolved prerequisite blocks correctness.
- **DEFER SAFELY** — current work can proceed; record why deferral is safe, the revisit trigger, and later owner/stage when identifiable.

Stop when Evidence is sufficient for the claim, root cause/invariant are clear, credible alternatives were compared, complexity/authority/proof were checked, strongest objections were addressed, and no material contradiction remains.

Do not reopen accepted decisions for preference or hypothetical futures. Reopen on material Evidence: changed requirement/ownership/scale, a new real consumer, newly reachable failure mode, external change, downstream Evidence that invalidates an assumption, or implementation Evidence that invalidates an assumption.

Under deadline, keep Unknown as Unknown, state residual risk, prefer the safest/reversible option compatible with the invariant, and tighten proof/reopen triggers. Deadline never converts uncertainty into truth.

## 5. Global coherence

Local correctness does not guarantee global coherence.

Run a Global Coherence Review when closing a major design stage, after a `RESTRUCTURE NOW`, before ratifying a decision that binds multiple repositories, after a new organizational specialist method is introduced, or when repeated local exceptions suggest a systemic problem.

Look for duplicate/missing authority, circular ownership, contradictory assumptions, repeated correctness machinery, God components, excessive fragmentation, abstractions caused only by other abstractions, removed necessary seams, speculative extensibility, and specialist methods that silently redefine the reasoning kernel.

A material coherence Finding returns to the Decision Loop and reopens only the decisions it actually implicates.

---

**Namespace note:** `Evidence`, `Finding`, and `UPSTREAM FINDING` in this method are epistemic terms. Repository/domain objects with the same names retain their own scoped semantics.
