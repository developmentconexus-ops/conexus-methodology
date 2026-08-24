# DevelopmentConexus Independent Adversarial Review Method

**Version:** 1.0.0  
**Scope:** independent challenge of material engineering candidates when `METHOD.md` or repository governance requires it

## 1. Purpose

Independent review tries to **falsify the exact candidate**. It is not agreement theater and does not create a second design/Product authority.

```text
exact candidate
+ current authority
+ independent Challenger
→ strongest credible attack
→ Findings as Evidence
→ Lead adjudication
→ bounded correction/reopen when justified
```

This method specializes `METHOD.md`; it does not own Product semantics, repository status, acceptance, or merge authority.

## 2. Roles and deployment precondition

Roles are semantic:

```text
OPERATOR    human decision/authorization owner
LEAD        primary engineering agent/session that owns candidate analysis/adjudication
CHALLENGER  independent agent/session that attacks the exact candidate
```

`README.md` owns the current tool assignment to these roles.

The canonical `ai-dialog` transport profile requires both Lead and Challenger to have write-capable Git/GitHub access. If either actor lacks it, STOP and explicitly choose a different transport for that review; do not silently mix manual relay into a workflow represented as direct agent-to-agent Git transport.

## 3. Independence

The Challenger reconstructs review context from repository authority and the exact candidate, not from the Lead's hidden reasoning or persuasive narrative.

A compact operator handoff may identify repository, candidate PR/ref, optional expected HEAD, and review focus. It is routing information, not authority. Remote repository state wins over a stale handoff; surviving material ambiguity is surfaced rather than guessed.

The Challenger MUST NOT modify the candidate branch.

## 4. Context loading

Follow the reviewed repository's actual bootstrap shape, then load only the review profile selected by `ROUTER.md`.

Typical Product/platform review:

```text
revalidate repository/remote/PR
→ local AGENTS.md
→ docs/index.md
→ docs/roadmap.md
→ pinned methodology ROUTER.md
→ METHOD.md
→ this review method
→ exact candidate diff
→ 1–2 owning documents
```

For `conexus-methodology` itself:

```text
revalidate repository/PR
→ AGENTS.md
→ ROUTER.md
→ METHOD.md
→ this review method
→ exact candidate diff
```

Load frontend/realization methods, research, Evidence, code, tests, history, or external sources only when the attacked claim requires them. Never recursively ingest the repository or all Methods for ceremony.

## 5. Candidate identity and Git safety

Before reviewing, resolve and record:

```text
repository
candidate PR/ref
candidate base
exact candidate HEAD
methodology pin
review round
```

Refresh remote state with `git fetch`; do not use `git pull` as review bootstrap because it combines fetch with integration into the current checkout.

Prefer an isolated review branch/worktree from the exact candidate. Preserve unowned state; never reset, clean, stash, force-update, or rewrite the candidate merely to prepare review.

Normal naming:

```text
review/<increment>-adversarial-r1
review/<increment>-adversarial-r2   # only when a fresh round is justified
```

## 6. Temporary `ai-dialog.md` transport

Canonical review transport:

```text
docs/work/current/ai-dialog.md
```

The review branch may create this temporary path even when the candidate repository normally has no `docs/` tree. Its existence is a review-branch transport exception only.

`ai-dialog.md` is:

- versioned Lead↔Challenger transport;
- temporary/non-authoritative;
- resumable across sessions;
- never Product/architecture/status authority;
- never merged to the candidate or `main`.

The review branch SHOULD differ from the exact candidate by this file only; the consuming repository's aggregate verification SHOULD prove that isolation when this review profile is used.

Minimum structure:

```text
# AI Dialog
Candidate: <repo / PR / exact SHA>
Round: R1
Methodology: <exact pin>

## Findings
<compact ledger>

## Dialogue
### R1-C1 — CHALLENGER
...
### R1-L1 — LEAD
...
```

Do not copy whole authority documents, Methods, or diffs into the dialogue.

### Why not native PR comments as the canonical transport?

GitHub PR comments/threads were considered during PR #2. For the current deployment they were not selected because the desired property is one branch-isolated, fetchable, versioned transcript available from normal Git worktrees and repository APIs, mechanically absent from the candidate/main, and not mixed with human/bot PR conversation. If a future deployment lacks shared Git write capability, transport selection may be reopened from that Evidence rather than adding a speculative fallback now.

## 7. Challenger attack protocol

Attack the strongest form of the candidate. As applicable test:

```text
root cause solved?
target invariant protected on every reachable path?
strongest credible alternative considered?
Local Maximum preserved despite a better Global Maximum?
YAGNI / speculative machinery?
underengineering / missing necessary seam?
duplicate or missing authority?
mechanism accidentally owning semantics?
hidden assumption converted to fact?
provider/framework behavior mistaken for Product authority?
partial failure / concurrency / restart / recovery?
security/trust boundary gap?
external-effect ambiguity / blind retry?
migration/compatibility trap?
proof weaker than claim?
control cannot be shown to fire?
downstream Evidence suppressed to preserve upstream planning?
review/PR scope too large for coherent adjudication?
```

Load frontend or realization specialist lenses only when those concerns are actually implicated.

## 8. Findings contract

Severity:

```text
MATERIAL
IMPORTANT
MINOR
UNSUPPORTED PREFERENCE
```

- `MATERIAL` can invalidate correctness, authority/boundary, accepted outcome, or ratifiability.
- `IMPORTANT` is substantive but does not currently falsify the central decision.
- `MINOR` is bounded quality/clarity/proof precision.
- `UNSUPPORTED PREFERENCE` lacks sufficient authority/Evidence and must not enter disguised as a defect fix.

For each non-trivial finding record:

```text
ID
severity
claim under attack
Evidence/counterexample
why it matters
smallest implicated authority/scope
recommended disposition or falsifier
```

Reviewer severity is Evidence, never final requirement authority.

## 9. Lead adjudication

The Lead reads the Challenger turn from `ai-dialog.md`, evaluates each material/important finding against repository reality, and appends one technical response to the same temporary channel.

Disposition vocabulary:

```text
ACCEPT  defect confirmed; bounded correction/reopen required
REFINE  concern valid but proposed remedy/extent is wrong
REJECT  not supported against current authority/Evidence
DEFER   real but safely owned by a later consumer/stage
```

Do not accept performatively or reject merely because a finding reopens work. New requirements return to the owning decision under `METHOD.md`.

Candidate corrections land separately on the candidate branch after adjudication, never through the review branch.

## 10. Convergence and rounds

Intended exchange:

```text
CHALLENGER turn
→ LEAD adjudication
→ CHALLENGER confirmation/counterchallenge only if material uncertainty survives
```

Do not create rounds for wording polish or agreement theater.

A fresh Round 2 is justified only when a materially corrected candidate benefits from independent confirmation or a real material contradiction survived R1. It starts from the exact corrected candidate on a fresh review branch; never keep reviewing a stale SHA.

## 11. Publication protocol

Typical Challenger turn:

```text
git fetch origin
→ resolve exact candidate
→ isolated review branch/worktree
→ read current ai-dialog if present
→ append Challenger turn only
→ verify isolation
→ commit
→ push review branch
```

The Lead uses its write-capable Git/GitHub path to fetch/read that review state, append the adjudication turn, and publish it to the same review branch without mutating the candidate through that branch.

## 12. Minimal operator handoff

Because repository state owns the workflow, the handoff stays small:

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

The expected HEAD is optional. If stale, report the mismatch and resolve current authority from the remote repository rather than reviewing old bytes blindly.

A completed Challenger turn may return only:

```text
Review published
review branch/ref
review HEAD
LEAD RESPONSE REQUIRED | CONVERGED
```

The substantive exchange remains in Git.

## 13. Session recovery

A fresh Lead or Challenger session resumes without chat history:

```text
revalidate candidate/review refs
→ local repository bootstrap
→ ROUTER review profile
→ exact candidate
→ current ai-dialog
→ implicated owners only
→ continue next turn
```

Git/repository state is continuity infrastructure; chat handoffs are convenience.

## 14. Closure

When review converges:

```text
accepted consequences absorbed into candidate/durable authority
→ candidate verified
→ review PR/branch closed unmerged
→ ai-dialog absent from candidate/main
→ preserve only future-useful durable decision/proof
```

Do not preserve permanent dialogue archives in the working tree. Git history/closed review PR is review provenance when needed.

> Independent review should increase decision quality while adding the minimum context and ceremony required to falsify a material candidate.