# DevelopmentConexus Independent Adversarial Review Method

**Version:** 1.0.0  
**Status:** CANDIDATE FOR ORGANIZATIONAL RATIFICATION  
**Scope:** independent challenge of material engineering candidates before ratification/closure where `METHOD.md` or repository governance requires it

## 1. Purpose

Independent review exists to **try to falsify the candidate**, not to validate the Lead's confidence or create a second design authority.

```text
exact candidate
+ current authority
+ independent challenger
→ strongest credible attack
→ Findings as Evidence
→ Lead adjudication
→ bounded correction/reopen when justified
```

The review method specializes `METHOD.md`. It does not own Product semantics, repository status, acceptance, or merge authority.

## 2. Actors

Roles are semantic, not vendor identities:

```text
OPERATOR
  human decision/authorization owner

LEAD
  primary engineering agent/session that owns candidate analysis and adjudication

CHALLENGER
  independent agent/session that attacks the exact candidate
```

Current DevelopmentConexus operating deployment:

```text
LEAD        = ChatGPT
CHALLENGER  = Claude Code
OPERATOR    = human operator
```

Changing the model/tool assigned to a role does not change this method.

## 3. Independence law

The Challenger MUST reconstruct the review from repository authority and the exact candidate, not from the Lead's hidden reasoning or a persuasive narrative.

The Challenger may receive a compact handoff identifying the repository, candidate PR/ref, expected HEAD, and review focus. That handoff is routing information, not authority.

If handoff and remote repository state differ, repository state wins. A material ambiguity is surfaced; it is never silently guessed.

The Challenger MUST NOT modify the candidate branch.

## 4. Review context loading

Start with progressive disclosure:

```text
repository/remote revalidation
→ AGENTS.md
→ docs/index.md
→ docs/roadmap.md
→ pinned methodology ROUTER.md
→ METHOD.md
→ this review method
→ exact candidate diff
→ 1–2 candidate owning documents
```

Load `FRONTEND-METHOD.md`, `REALIZATION-METHOD.md`, research, Evidence, code, tests, history, or external sources only when the claim under attack requires them.

Do not recursively ingest the repository or all Methods for ceremony.

## 5. Candidate identity and Git safety

Before review, resolve and record:

```text
repository
candidate PR/ref
candidate base
exact candidate HEAD
methodology pin
review round
```

Use `git fetch` to refresh remote state. Do not use `git pull` as the review bootstrap because it combines fetch with integration into the current checkout.

Prefer an isolated review branch/worktree from the exact candidate. Preserve unowned state; never reset, clean, stash, force-update, or rewrite the candidate merely to prepare review.

Recommended review branch:

```text
review/<increment>-adversarial-r1
```

Round 2, if actually justified, starts from the exact corrected candidate and uses a fresh review branch:

```text
review/<increment>-adversarial-r2
```

## 6. Temporary `ai-dialog.md` transport

The canonical temporary cross-agent review channel is:

```text
docs/work/current/ai-dialog.md
```

It is:

- versioned review transport;
- temporary non-authoritative work;
- a resumable conversation between Lead and Challenger;
- never Product/architecture/status authority;
- never merged to the candidate or `main`.

The review branch SHOULD differ from the exact candidate by this file only. Repository verification SHOULD prove that isolation mechanically.

Minimal structure:

```text
# AI Dialog

Candidate: <repo / PR / exact SHA>
Round: R1
Methodology: <exact pin>

## Findings
<compact current finding ledger>

## Dialogue
### R1-C1 — CHALLENGER
...

### R1-L1 — LEAD
...
```

Do not copy entire authority documents, diffs, or Methods into the dialogue. Link/identify them and record only the reasoning needed for the review exchange.

## 7. Challenger attack protocol

Attack the preferred candidate, not a straw man.

As applicable, test:

```text
root cause actually solved?
target invariant protected on every reachable path?
strongest credible alternative considered?
Local Maximum preserved when a better Global Maximum exists?
YAGNI / speculative machinery?
underengineering / missing necessary seam?
duplicate or missing authority?
mechanism accidentally owning semantics?
hidden assumption converted to fact?
provider/framework behavior mistaken for Product authority?
partial failure / concurrency / restart / recovery?
security/trust boundary gap?
external-effect ambiguity or blind retry?
migration/compatibility trap?
proof weaker than the claim?
control exists but cannot be shown to fire?
downstream evidence suppressed to preserve upstream planning?
review or PR scope too large for coherent adjudication?
```

For frontend candidates additionally attack user need, IA, backend-shaped UX, screen-shaped backend, interaction truthfulness, accessibility/responsive structure, and screen/backend trace when implicated.

For realization candidates additionally attack source quality, exact-version fit, dependency/operational cost, real-dependency proof, reversibility, and `ADOPT/ADAPT/BUILD` reasoning when implicated.

## 8. Findings contract

Use a small stable severity vocabulary:

```text
MATERIAL
IMPORTANT
MINOR
UNSUPPORTED PREFERENCE
```

`MATERIAL` means the finding could invalidate the candidate's correctness, authority/boundary, accepted outcome, or ratifiability.

`IMPORTANT` means a substantive defect/precision gap should be corrected before closure but does not currently falsify the candidate's central decision.

`MINOR` means bounded quality/clarity/proof precision with no material decision effect.

`UNSUPPORTED PREFERENCE` records a proposed change lacking sufficient authority/Evidence; it must not enter disguised as a defect fix.

For each non-trivial finding state:

```text
ID
severity
claim under attack
Evidence/counterexample
why it matters
smallest authority/scope implicated
recommended disposition or falsifier
```

Reviewer severity is Evidence, not final requirement authority.

## 9. Lead adjudication

The Lead reads the Challenger turn from `ai-dialog.md`, confronts each material/important finding technically, and appends its response to the same temporary channel.

For each finding the Lead resolves one of:

```text
ACCEPT — defect confirmed; bounded correction/reopen required
REFINE — core concern valid but proposed remedy/extent is wrong
REJECT — finding not supported against current authority/Evidence
DEFER — real but safely owned by a later consumer/stage
```

Do not accept findings performatively. Do not reject them merely because they reopen prior work.

If a finding introduces a new Product requirement rather than exposing a defect against current authority, return it to the owning decision under `METHOD.md`.

## 10. Dialogue and convergence

The intended exchange is short:

```text
CHALLENGER turn
→ LEAD adjudication
→ CHALLENGER confirmation/counterchallenge only when material uncertainty survives
```

Do not create repeated rounds for agreement theater or wording polish.

Round 2 is justified only when:

- the candidate changed materially to close a material review finding and independent confirmation is useful; or
- a real material contradiction survives Lead adjudication.

A fresh exact candidate is required for a new round. Do not keep reviewing a stale SHA.

## 11. Publication protocol

The Challenger publishes only the review transport branch/file authorized by the review task.

Typical current Claude Code turn:

```text
git fetch origin
→ resolve exact candidate
→ enter/create isolated review branch/worktree
→ read current ai-dialog if present
→ append Challenger turn only
→ verify review isolation
→ commit
→ push review branch
```

The Lead then fetches the published review branch, reads `ai-dialog.md`, appends its adjudication turn in the authorized review transport, and publishes that turn without mutating the candidate through the review branch.

Candidate corrections are applied separately by the Lead to the candidate branch after adjudication.

## 12. Minimal handoff contract

Because repository state and methodology own the workflow, the operator handoff SHOULD remain small.

Minimum useful handoff:

```text
Repository: <owner/repo>
Candidate PR: #<n>
Expected HEAD: <optional stale-state falsifier>

Perform the independent adversarial review for the current gate.
Revalidate remote authority first.
Use the repository's pinned DevelopmentConexus methodology.
Publish your review turn only through the temporary ai-dialog channel and push it.
Do not modify the candidate.
```

The expected HEAD is optional. If supplied and stale, report the mismatch and resolve current authority from the remote repository rather than blindly reviewing old bytes.

A completed Challenger turn can return to the operator with only:

```text
Review published
review branch/ref
review HEAD
LEAD RESPONSE REQUIRED | CONVERGED
```

The substantive conversation remains in `ai-dialog.md`.

## 13. Session recovery

A new Lead or Challenger session can resume an active review without chat history:

```text
revalidate remote candidate/review refs
→ repository bootstrap + roadmap
→ ROUTER review profile
→ exact current candidate
→ current ai-dialog
→ implicated owner docs only
→ continue next review turn
```

Chat handoffs are convenience. Git/repository state is continuity infrastructure.

## 14. Closure

When review converges:

```text
Lead absorbs accepted consequences into candidate/durable authority
→ candidate verified
→ review PR/branch closed unmerged
→ ai-dialog disappears from live candidate/main
→ durable decision/proof retains only what future work actually needs
```

Do not preserve permanent dialogue archives in the working tree. Git history/closed review PR provides review provenance when needed.

## 15. Final principle

> Independent review should increase decision quality while adding the minimum context and ceremony required to falsify a material candidate.
