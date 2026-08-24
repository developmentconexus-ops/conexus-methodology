# DevelopmentConexus Frontend Product Experience Method

**Version:** 1.0.0  
**Scope:** reusable frontend/product-experience planning across DevelopmentConexus repositories  
**Lineage:** consolidates the reusable local Frontend Product Experience Planning Method through the operator-ratified MetalDocs v2.3 generation

## 1. Purpose

Make production frontend implementation a realization of already-reviewed Product, UX, interaction, and system decisions instead of a design phase performed while coding.

The frontend is the human-operable projection of accepted Product architecture, but backend coherence does not uniquely determine good UX.

```text
accepted Product/system authority
→ actors + user needs
→ complete user flows
→ frontend coverage
→ candidate information architecture
→ material surface inventory
→ block-by-block design
→ functional low-fidelity HTML
→ operator use / iteration / LOCK
→ exact frontend/backend trace
→ pattern consolidation
→ assembled low-fidelity product
→ adversarial whole-product walkthrough
→ visual handoff
→ implementation readiness
```

Binding distinctions:

```text
backend coherence != UX coherence
accepted backend plan != immutable UX ceiling
static plausibility != interaction coherence
block coherence != whole-product coherence
```

This method specializes `METHOD.md`. It never replaces Product authority, repository status, or the Repository Standard.

## 2. Success condition

Frontend planning is complete only when a production implementer can build without inventing material Product, IA, workflow, interaction, failure, or backend-contract decisions in code.

For each material surface/interaction the team can answer:

```text
who is the user and what outcome do they need?
why does this surface exist and why is information organized this way?
what accepted Product capability does it serve?
what owner/read truth supplies each material fact?
what accepted operation owns each material action?
where does every required identity come from?
what state is authoritative?
what happens on success, stale state, ambiguity, denial, unavailable truth, and material failure?
what must the user understand after failure?
what happens responsively and accessibly?
what may the frontend NOT infer or own?
```

If a material answer is missing, the frontend is not implementation-ready.

## 3. Core laws

### 3.1 Human needs before screens

```text
actor
→ context
→ user need / job
→ desired outcome
→ end-to-end flow
```

Never start from endpoint inventories, database nouns, backend packages, or a preselected component library.

### 3.2 Coverage before layout

```text
accepted capability / human goal
→ semantic owner
→ admitted read/write contract
→ candidate frontend context
```

Coverage determines what must be representable, not how it looks.

### 3.3 IA before screen composition

Navigation, grouping, browse, search, work queues, and cross-links are Product-experience decisions. Backend topology is not a navigation model by default.

### 3.4 References are Evidence, never authority

For unfamiliar or consequential ambiguity, study mature products/design systems by user task and failure pattern, not visual fashion.

Separate:

```text
SOURCE OBSERVATION
INFERENCE
PRODUCT DECISION
```

Stop when new references stop changing the decision space.

### 3.5 Competing hypotheses only when ambiguity is real

Compare 2–3 credible structures only when more than one material structure is plausible. Do not manufacture alternatives for ceremony.

### 3.6 Operator-only LOCK

```text
assistant / reviewer / tool
  may propose CANDIDATE / FINDING / REJECTED / DEFERRED
  MUST NOT set LOCKED

operator / designated human Product decision owner
  alone may set LOCKED
```

Dependent material blocks do not inherit a candidate as baseline unless the operator explicitly authorizes parallel candidate work.

### 3.7 No all-at-once wireframing

For non-trivial products, do not generate the whole UI and seek feedback only at the end. Important blocks are designed, operated, and LOCKED before downstream blocks inherit their structure.

### 3.8 P8 is functional low-fidelity

For a material interactive web block, canonical P8 evidence is a **browser-operable low-fidelity HTML artifact**.

Default medium:

```text
HTML
CSS
vanilla JavaScript where interaction exists
deterministic local fixtures/state simulation
```

Static screenshots, images, ASCII, prose, box diagrams, or non-interactive HTML cannot receive P8 LOCK when the structure can be falsified only by interaction.

P8 code is disposable Evidence. It is not production React, a real API integration, a second Product state authority, a second Authorization engine, or a production design system.

### 3.9 No screen-shaped backend

A difficult screen is not authority for a convenience API.

```text
prove the user need
→ identify missing semantic truth
→ locate the accepted owner
→ classify current authority
→ reopen only the smallest owning decision when Evidence requires it
```

### 3.10 No backend-shaped UX

Accepted pre-implementation Product/backend authority is a **binding but falsifiable baseline**, not an immutable ceiling on Product experience.

```text
NO screen-shaped backend
  UI convenience alone does not justify an API.

NO backend-shaped UX
  current API absence alone does not justify suppressing a proven user need.
```

When user, operator, reference, or prototype Evidence exposes a potentially material capability:

```text
prove the human job / outcome
→ test whole-Product value
→ compare credible alternatives + YAGNI pressure
→ identify semantic owner
→ classify current authority

SUFFICIENT
  → continue

INSUFFICIENT + material need proven
  → UPSTREAM FINDING
  → apply METHOD.md downstream-falsification law
  → reopen smallest owning Product/backend/wire authority

useful but unjustified now
  → explicit REJECTED or DEFERRED for Product reasons
```

Forbidden shortcuts:

```text
API lacks X → omit X
reference has X → invent endpoint X
backend plan exists → preserve it despite stronger Evidence
```

### 3.11 Frontend never becomes parallel business authority

Unless explicitly accepted, frontend planning does not own business lifecycle, Authorization evaluation, parallel DTO/schema registries, normalized business truth mirrors, Audit/History as current-resource truth, or provider mechanism state as Product truth.

### 3.12 Shared patterns are derived

Graduate a shared pattern only after repeated LOCKED behavior proves the same protected semantics. Cosmetic similarity is insufficient.

### 3.13 Accessibility and responsive behavior are structural

A block cannot LOCK if its interaction model lacks a plausible accessible/responsive realization. Keyboard path, focus order, semantic controls, labels, non-color meaning, reading order, and responsive priority are part of structure.

### 3.14 Visual design cannot silently redesign UX

Visual design may change aesthetics. Navigation, material fields/actions, reading order, region priority, interaction model, density class, and workflow require return to the smallest affected frontend decision.

### 3.15 P8 proves the block; P11 proves the product

```text
P8  → bounded block + material local interactions + operator LOCK
P11 → assemble already-LOCKED blocks + cross-block journeys
```

P11 is not the first time the Product becomes clickable.

## 4. Evidence and decision vocabulary

Inputs:

```text
ACCEPTED AUTHORITY
USER / OPERATOR EVIDENCE
REFERENCE EVIDENCE
ASSUMPTIONS
```

Material assumptions remain explicit until validated, rejected, deferred, or escalated as a Finding. P8 owns lock-time disposition for any still-OPEN assumption the block materially depends upon.

Statuses:

```text
LOCKED
CANDIDATE
FINDING
UPSTREAM FINDING
REJECTED
DEFERRED
NOT-HUMAN-FACING
```

Reject an artifact and its underlying requirement separately. A bad wireframe does not automatically invalidate the user need.

## 5. Frontend planning program

`P0–P14` defines **how** frontend planning proceeds. The consuming repository roadmap owns **where the product currently is**.

Recommended macro-program:

```text
FP0 — Frontend Foundation                 P0–P5
FP1 — Block-by-block Product Experience   B01...Bnn using P6–P10
FP2 — Integrated Low-Fidelity Product     P11
FP3 — Whole-Product Adversarial Review    P12
FP4 — Visual Handoff + Readiness          P13–P14
```

`FP*` and `Bxx` are recommended planning vocabulary, not universal Product ontology.

For a non-trivial product, enumerate knowable material blocks before deep execution. Avoid opaque `B04+` placeholders when the real inventory is already knowable.

The repository roadmap should identify:

```text
current FP stage
current Bxx block
LOCKED blocks
blocking findings
next exact gate
implementation allowed/blocked
```

### Bounded rebaseline and LOCK impact sweep

Whenever an accepted upstream authority change is material to frontend planning:

```text
changed authority
→ determine the plausible impact boundary
→ disposition every LOCKED block inside that boundary
→ boundedly update only affected foundation/block artifacts
→ resume from current accepted authority
```

Each plausibly affected LOCKED block receives exactly one disposition:

```text
UNAFFECTED
  changed authority does not alter the block's protected structure,
  Screen Contract, or dependency

REVALIDATE
  protected structure is expected to remain valid but must be explicitly
  rechecked against the changed authority before dependent progression

REOPEN
  the LOCK is materially falsified; return only to the smallest required
  earlier frontend phase or upstream owner
```

If the impact boundary cannot be bounded safely, sweep all currently LOCKED blocks. Record the result as a compact **LOCK impact matrix** inside the existing rebaseline/decision artifact; this method does not require a new file for the matrix.

Do not restart the entire frontend or invalidate unrelated LOCKs by reflex.

### Small bounded delta

For a genuinely small single-block delta on an otherwise valid foundation:

```text
reuse valid P0–P5
→ run P6/P7 only when triggered
→ render/operate the affected P8 block
→ run P9 only for changed material contracts
→ run the LOCK impact sweep only across plausibly affected LOCKs
→ run P11 only when cross-block integration is implicated
→ run affected proof/review
```

Do not repeat unrelated Product-wide discovery for ceremony. A change is **not** small merely because its diff is small; changes to Product meaning, authority, IA, cross-block state, or semantic ownership follow the normal bounded-rebaseline laws.

## 6. P0 — Recover accepted authority

Load only the smallest task-relevant authority pack, including as applicable:

```text
Product scope
actors/capabilities
semantic owners
state/lifecycle
identity
permissions/disclosure
API/read models
concurrency/idempotency
external-effect/runtime constraints
accepted route/lens constraints
```

Exit: every known frontend requirement traces to authority or is explicitly unknown/assumed.

## 7. P1 — Actors, jobs, user needs

Recommended form:

```text
When <context>,
I need to <goal>,
so that <outcome>.
```

Capture frequency/urgency, decision information, friction, and handoffs. Goals must remain independent from proposed components/pages.

Accepted Product/domain authority may seed candidate human jobs, but authority-derived jobs are hypotheses about human operation until supported by proportionate user/operator, workflow/process, or reference/domain Evidence. Unsupported material human-operation details remain explicit assumptions.

Formal user research is not a prerequisite for every frontend program; use the strongest Evidence proportional to the uncertainty and materiality.

## 8. P2 — End-to-end flows

For every accepted human goal:

```text
entry
→ understand state
→ decide
→ act
→ system response
→ handoff if any
→ outcome
→ next likely task
```

Capture material alternate/failure branches. Do not split planning at a boundary that leaves a real human goal incoherent.

## 9. P3 — Frontend coverage

Minimum mapping:

| User need/capability | Owner | Flow | Candidate context | Reads | Writes | Access/security | UX obligations | Disposition |
|---|---|---|---|---|---|---|---|---|

Cross-cutting obligations may include:

```text
unknown != known-empty
projection != mutation authority
hidden control != Authorization
ambiguous outcome != known failure
stale write != silent overwrite
provider success != Product success
```

A human-class backend operation with no user need must be mapped, explicitly NOT-HUMAN-FACING/DEFERRED, or raised as an excess-capability upstream Finding.

A material human need with insufficient backend capability becomes an UPSTREAM FINDING. Never invent UI to reach zero backend orphans, and never suppress a proven need to reach zero backend gaps.

## 10. P4 — Candidate information architecture

Design intentionally:

```text
global navigation
context navigation
home/default landing
work queues
browse hierarchy
search/filter entry
cross-links
breadcrumbs only when real hierarchy exists
```

Maintain a user-language terminology glossary. P4 exits `CANDIDATE`; global IA becomes LOCKED through an operated global-frame P8 block.

## 11. P5 — Material surface inventory

Derive surfaces from flows + IA, not endpoints. Distinguish route/page, sub-surface, drawer/modal, inline region, alternate collection view, and material state variant.

Split a material surface when semantic truth, safe action, write owner, required identity, concurrency, disclosure, recovery, or editor/viewer mode materially changes.

## 12. P6 — Reference study, conditional per block

Use references when uncertainty justifies them. Analyze user problem, hierarchy, action priority, collection representation, search/filter strategy, progressive disclosure, selection, failure states, responsive behavior, density, and mismatch risk.

Every materially relevant reference capability gets one disposition:

```text
IRRELEVANT TO USER JOB
PRESENT-IN-AUTHORITY
REJECTED — Product reason
DEFERRED — justified scope reason
UPSTREAM FINDING — authority insufficient
```

`Current backend does not provide it` is not a valid Product rejection reason by itself.

## 13. P7 — Layout hypotheses + feasibility

When ambiguity is real, compare alternatives against task completion, scanability, recognition/comparison, density, cognitive load, context preservation, accessibility, responsive viability, scale, preview needs, recovery, and backend-truth fit.

Before P8, state required fields/summaries, identity sources, pagination/scale, sort/filter needs, preview/content truth, and material writes. Each is:

```text
PRESENT-IN-AUTHORITY
UPSTREAM FINDING
REJECTED — evidence-backed Product reason
DEFERRED — evidence-backed scope reason
```

Blocking law:

```text
material user need
+ current authority insufficient
= blocking UPSTREAM FINDING
```

P8 does not begin until the Finding is ratified into authority, explicitly REJECTED, or explicitly DEFERRED by the Product decision owner.

## 14. P8 — Functional low-fidelity HTML

P8 is the design-learning loop for one block:

```text
leading hypothesis
→ functional low-fi HTML
→ operator operates it
→ discuss friction/failure
→ revise
→ operate again
→ repeat
→ operator LOCK
```

Material controls capable of falsifying structure must work: open/close, tabs/lenses, drawers/modals, progressive disclosure, selection, local forms, typeahead, deep-link/anchor, viewer entry/exit, state switching, and responsive menus/sheets where relevant.

A future unopened block may terminate at an explicit boundary; do not secretly design downstream work.

P8 does not freeze final palette, typography, spacing, tokens, iconography, component architecture, or production animation.

### Lock-time assumption disposition

Before a material P8 LOCK, every still-OPEN assumption that the block's structure materially depends upon records:

```text
assumption ID
structural dependency
risk if false
operator disposition
```

Disposition is exactly one of:

```text
ACCEPT_FOR_LOCK_WITH_LATER_PROBE
  operator explicitly accepts the known assumption debt for this LOCK

BLOCK_LOCK
  uncertainty is too material; LOCK cannot occur yet
```

Only the operator may select `ACCEPT_FOR_LOCK_WITH_LATER_PROBE`. Do not enumerate unrelated assumptions merely to satisfy a template.

### Operator walkthrough evidence

For a material LOCK, keep the walkthrough record falsifiable but small:

```text
OPERATED
actual task attempted
material issues found
final disposition: LOCK | REVISE | UPSTREAM FINDING
```

When relevant, use §2's success questions to probe context, consequential actions, material states, architecture gaps, and responsive meaning. Do not turn them into a mandatory questionnaire for trivial blocks.

Exit:

```text
functional HTML exists
material local interactions work
important states are inspectable
responsive/accessibility structure is plausible
no blocking Finding remains
materially depended-upon OPEN assumptions have lock-time disposition
operator walkthrough evidence exists
operator explicitly LOCKS
```

## 15. P9 — Screen Contract + bidirectional backend trace

After LOCK, bind each material region/control:

```text
GOAL / FLOW
ROUTE / SURFACE
INFORMATION ROLE
OWNER + READ TRUTH
WRITE CONTROL
IDENTITY SOURCE
CLIENT STATE CLASS
WIRE MECHANICS
MATERIAL FAILURES
FAILURE MESSAGE INTENT
SUCCESS CONSEQUENCE
AUTHZ / DISCLOSURE
FORBIDDEN FRONTEND AUTHORITY
BACKEND SUFFICIENCY
```

Trace both directions:

```text
Product/backend → capability → owner → contract → screen/control
frontend        → screen/control → contract/read truth → owner → capability
```

A P9 contradiction reopens the smallest affected P7/P8 scope; an upstream authority contradiction invokes the Method rather than weakening the user need by default.

## 16. P10 — Pattern consolidation

After each block LOCK, compare its protected behavior with prior LOCKED blocks and graduate only real repeated semantics. Reconcile duplicate or false abstractions before final closure.

## 17. P11 — Assembled interactive low-fidelity product

P11 creates a **new assembled prototype artifact** from already-LOCKED blocks. Canonical P8 LOCK artifacts remain immutable review Evidence; P11 does not rewrite them. P11 assembly code remains disposable prototype Evidence and never becomes production/component architecture authority.

Prove cross-block navigation, complete journeys, deep links, shared shell/overlay behavior, negative/recovery flows, and responsive behavior.

Every retained LOCKED block receives an assembled-fidelity check. The assembled artifact must preserve the block's material locked invariants, including as applicable:

```text
shell / region relationship
material states
action availability and material ordering
context and identity meaning
responsive transformations
accessibility interaction laws
important negative controls
```

Where an executable structural verifier already exists, reuse the same invariant against P11. Do not build a new verification framework solely for ceremony. Record `PASS FIDELITY` or `REOPEN` for each assembled LOCKED block.

If integration falsifies a lock:

```text
FINDING
→ smallest affected block/phase or upstream owner
→ adjudicate
→ revise
→ operator re-LOCK
→ reassemble affected path
```

P11 exits only when all retained assembled LOCKED blocks pass fidelity verification.

## 18. P12 — Adversarial UX + architecture walkthrough

Attack the assembled product from target-user, Product, design, IA, frontend, backend/domain, accessibility, and adversarial-architecture perspectives.

Look for findability failure, unnecessary depth, hidden decision facts, wrong density/pattern, local optimum that fails globally, missing source/identity, screen-shaped API, backend-shaped UX, frontend Authorization, fixture state masquerading as Product truth, and broken concurrency/idempotency/recovery semantics.

Material assumptions become VALIDATED, REJECTED, DEFERRED, or FINDING.

## 19. P13 — Visual handoff + conformance

Handoff includes locked IA, functional P8 blocks, P11 prototype, terminology, graduated patterns, Screen Contracts, failure intent, and responsive structure.

After visual design, verify no silent change to reading order, region priority, action placement, interaction model, density class, navigation meaning, material visibility, or responsive behavior.

## 20. P14 — Implementation-readiness closure

Close only when applicable obligations are satisfied:

```text
accepted human goals complete
end-to-end flows complete
IA locked where applicable
block inventory dispositioned
functional P8 blocks operator-LOCKED
Screen Contracts complete
material controls bound
navigation identities sourced
patterns reconciled
P11 complete
negative/material states represented
failure message intent defined
frontend ↔ backend trace complete
backend human ops without disposition = 0
material human needs suppressed by API absence = 0
invented Product operations = 0
screen-shaped APIs = 0
material assumptions OPEN = 0
unresolved material UX/architecture findings = 0
post-design conformance defects = 0
```

## 21. Block operating protocol

For each `Bxx`, preserve proportionately:

```text
stable block ID
user goals
authority pack
dependencies
assumptions
lock-time material-assumption dispositions
reference evidence when triggered
hypotheses when ambiguity is real
data/backend feasibility disposition
Global-Maximum check
canonical functional P8 HTML
material interactions
operator walkthrough evidence
Findings
LOCK/CANDIDATE disposition
LOCK impact disposition after a material upstream rebaseline when applicable
P9 Screen Contract
P10 pattern pass
P11 integration path + fidelity result when applicable
```

The method does not require one file per artifact.

## 22. Git / acceptance increment boundary

Frontend decision granularity and Git integration granularity should align.

For FP1, a normal coherent acceptance increment is one material `Bxx` through the smallest stable LOCK + P9/P10 closure that can be independently accepted and leaves the repository valid.

```text
Bxx P6/P7 as triggered
→ P8 operator LOCK
→ P9 trace
→ P10 bounded pattern pass
→ one acceptance-increment PR by default
→ integrate
→ next dependent block starts from updated main
```

Do not create one PR per mechanical P-step. Conversely, do not keep an entire multi-block frontend program in one PR merely because the roadmap stage remains open.

A material UPSTREAM FINDING should normally be resolved in its own owning acceptance increment when separable, then the frontend block rebases/rebaselines on the integrated authority.

Repository Standard v1.1 governs exceptions and parallel work.

## 23. Independent review

Use independent adversarial review when required by `METHOD.md` or repository governance. Reviewer output is Evidence, never authority.

Attack at least:

```text
missing user-centered discovery
weak IA
static approval before interaction learning
all-at-once generation
screen-shaped API
backend-shaped UX
frontend authority duplication
stale LOCK after material upstream change
hidden structural assumption debt at LOCK
P11 assembled-fidelity drift
YAGNI / overengineering
untracked assumptions
accessibility/responsive deferral
visual-design drift
program/roadmap ambiguity
```

## 24. Adoption by repositories

A consuming repository:

1. pins the exact `conexus-methodology` commit containing this method;
2. keeps mutable Product/frontend status in its own `docs/roadmap.md`;
3. defines FP0–FP4 or a justified equivalent;
4. enumerates real material blocks;
5. uses functional HTML/CSS/JS as canonical P8 evidence for interactive web blocks;
6. requires explicit operator LOCK;
7. treats prototype code/fixtures as Evidence only;
8. treats accepted Product/backend authority as binding but falsifiable during pre-implementation inquiry;
9. routes material missing-capability Findings through `METHOD.md` before P8;
10. records justified local specialization instead of silently forking this method.

## 25. Final principle

A strong frontend plan makes production coding almost boring:

```text
realize operator-LOCKED interaction structure
→ bind accepted contracts
→ implement reviewed patterns
→ preserve responsive/accessibility behavior
→ prove states and failures
```

not:

```text
invent navigation/screens in production
→ discover interaction after static approval
→ invent missing APIs
→ let API absence suppress proven Product needs
→ redesign workflows while coding
→ reconcile backend/frontend after the fact
```
