# AI Dialog

Candidate: developmentconexus-ops/conexus-methodology / PR #2 / 562473ed2a77130a9b25f91675b7134dedbb84a5
Base: main @ ac832790b04491418d663960bd095a8ec8801693
Round: R3 (research-first bounded adversarial review of the post-convergence amendment `26d5c4d5..562473ed`; prior rounds: `review/method-suite-v1-1-adversarial-r1` @ 9b36fc6e, `review/method-suite-v1-1-adversarial-r2` @ R2-L1 CONVERGED at `26d5c4d5`)
Methodology: candidate's own pinned suite (ROUTER.md + METHOD.md + ADVERSARIAL-REVIEW-METHOD.md + FRONTEND-METHOD.md lens, all at candidate HEAD)
Scope: ONLY the amendment range `26d5c4d5c39b3de3c95c5b7bd71d7060cd413316..562473ed2a77130a9b25f91675b7134dedbb84a5` (2 commits: `760e662` METHOD.md consumer-feedback law, `562473e` FRONTEND-METHOD.md lock/assembly safety; net +124/−12 lines across exactly those 2 files). Settled R1/R2 areas are not reopened; preserved invariants are checked for regression only. External instruction-design evidence is treated as Evidence, never as authority over this repository.

## Findings

| ID | Severity | Subject | Status |
|---|---|---|---|
| R3-F1 | IMPORTANT | Duplicated normative statements reintroduced by the amendment (rule-once violations) | CLOSED — ACCEPT / deleted |
| R3-F2 | IMPORTANT | `NOT_MATERIAL_TO_STRUCTURE` is unreachable under its own scope sentence | CLOSED — ACCEPT / deleted unreachable branch |
| R3-F3 | MINOR | METHOD.md promotion-review rubric restates the §3 decision core | CLOSED — ACCEPT / compressed |
| R3-F4 | MINOR | Compressible definition/list prose in the FRONTEND additions | CLOSED — ACCEPT / compressed |

No MATERIAL finding. Nothing in this round falsifies the amendment's central mechanisms; the two IMPORTANT findings were bounded internal-consistency defects in the added text, not defects of the protected behavior.

## Dialogue

### R3-C1 — CHALLENGER

Remote authority revalidated before review: PR #2 OPEN, head `docs/method-suite-v1-1` @ `562473ed2a77130a9b25f91675b7134dedbb84a5` (matches operator-supplied expected HEAD), base `main` @ `ac832790`. Amendment range verified: exactly 2 commits, touching exactly FRONTEND-METHOD.md (+116 net) and METHOD.md (+8). R2 convergence point `26d5c4d5` confirmed as the amendment base. Candidate branch not modified; this review branch is fresh from the exact candidate and differs from it by this file only. Marketplace Central not touched by the amendment or by this review.

#### External Evidence base (research-first)

Loaded as Evidence for the deletion test, not as authority:

- **E1 — Anthropic, Claude Code best practices (code.claude.com/docs/en/best-practices, read 2026-08-24).** Persistent instruction files: "Keep it concise. For each line, ask: *'Would removing this cause Claude to make mistakes?'* If not, cut it. Bloated CLAUDE.md files cause Claude to ignore your actual instructions!" Named failure pattern: "The over-specified CLAUDE.md… Claude ignores half of it because important rules get lost in the noise." Broadly-applicable rules stay resident; situational knowledge loads on demand. Deterministic enforcement (hooks) is reserved for "actions that must happen every time with zero exceptions"; instructions are advisory. Emphasis dilutes: "If you emphasize many lines, none of them stands out." Instructions evolve by observing failures and pruning, i.e. evidence-driven evolution.
- **E2 — Anthropic, Effective context engineering for AI agents (anthropic.com/engineering, read 2026-08-24).** Core principle: "find the *smallest possible* set of high-signal tokens that maximize the likelihood of some desired outcome." Right altitude: avoid both "complex, brittle logic" and "vague, high-level guidance that fails to give the LLM concrete signals"; target instructions "specific enough to guide behavior effectively, yet flexible enough to provide the model with strong heuristics." Progressive disclosure / just-in-time loading via lightweight identifiers. Attention is a budget; every token depletes it. Start minimal; add instructions only from observed failures.
- **E3 — OpenAI, AGENTS.md guidance (developers.openai.com/codex → learn.chatgpt.com docs, read 2026-08-24).** Instruction files are working agreements, not tutorials; 32 KiB default cap with splitting across nested files rather than growing one file; "Keep rules concise, explain the behavior to flag and any safe path or exception, and reserve formatting and lint checks for CI" — i.e. mechanical enforcement belongs in a mechanical channel, prose rules carry only what needs judgment; hierarchy prevents duplicated/conflicting guidance ("at most one file per directory").
- **E4 — Chroma, Context Rot (trychroma.com/research/context-rot, 2025).** Across 18 frontier models, "performance grows increasingly unreliable as input length grows" even on simple tasks; a single distractor measurably reduces accuracy; degradation is non-uniform and appears well inside advertised windows.
- **E5 — IFScale, "How Many Instructions Can LLMs Follow at Once?" (arXiv:2507.11538, 2025).** Instruction-following accuracy degrades with instruction density; best frontier models reach only ~68% adherence at 500 concurrent instructions; models bias toward earlier instructions; degradation begins far below the density ceiling.

Synthesis applied to this review: every added rule pays rent twice — once in tokens (E2/E4) and once in adherence-probability for every other rule in the same loaded profile (E1/E5). The candidate's own kernel already encodes this (`METHOD.md` LLM-first: "maximize decision signal per token. State each normative rule once."), and its ROUTER already implements progressive disclosure (FRONTEND-METHOD loads only for frontend work), so the amendment's context cost is paid only in frontend sessions — but E5 makes intra-document duplication and low-signal prose an adherence cost even there. The operator's prescribed deletion test is materially identical to E1's official line test; it was applied to every added rule below. Conversely, E2's altitude principle cuts the other way: concrete disposition vocabularies and checkable records are exactly the "strong heuristics" that make advisory rules fire, so mechanism-bearing additions are not ceremony merely because they add lines.

#### Confirm/falsify the eight operator questions

1. **LOCK impact sweep — CONFIRMED.** The replaced text ("preserve valid LOCKED blocks unless new Evidence falsifies them") stated the property with no firing mechanism: an agent could silently no-op and report compliance. The amendment converts it to a checkable per-block record (tri-state disposition + compact matrix) while explicitly bounding it: plausible-impact boundary first, full sweep only when the boundary cannot be bounded safely, matrix lives inside the existing artifact (no new file), and "Do not restart the entire frontend or invalidate unrelated LOCKs by reflex." That is E2's right altitude — concrete signals without brittle procedure — and it protects a real failure class (stale LOCK surviving a material upstream change is precisely the class of silent drift E1 warns advisory prose alone will not catch). No blanket invalidation, no ceremony inflation. Definition prose is compressible (R3-F4) but the mechanism stands.
2. **P8 lock-time assumption disposition — CONFIRMED, with one bounded defect.** `ACCEPT_FOR_LOCK_WITH_LATER_PROBE` is the load-bearing option: it makes assumption debt explicit and operator-owned without making every OPEN assumption block LOCK; `BLOCK_LOCK` preserves the escalation path; operator-only selection is consistent with §3.6; "Do not enumerate unrelated assumptions merely to satisfy a template" blocks questionnaire drift. The defect is internal: see R3-F2 — the third disposition contradicts the scope sentence that introduces the record. Bounded reword, not redesign.
3. **P11 immutable P8 Evidence + assembled fidelity — CONFIRMED.** "Canonical P8 LOCK artifacts remain immutable review Evidence; P11 does not rewrite them" closes the silent-redesign channel (assembly edits masquerading as integration). The fidelity check is explicitly framework-averse: "Where an executable structural verifier already exists, reuse the same invariant… Do not build a new verification framework solely for ceremony," and the invariant list is gated by "including as applicable." `PASS FIDELITY | REOPEN` is a two-token record, not a framework. One duplication defect in how the exit condition is restated at P14 (R3-F1c).
4. **Small-delta path — CONFIRMED.** It is a skip-list, not a new process: it authorizes *not* running P0–P5/P6/P7/P9/P11 when untriggered. Its one guard sentence ("A change is **not** small merely because its diff is small…") is the load-bearing anti-abuse clause and survives the deletion test — without it, "small diff" becomes the standard laundering route for semantic changes. The path is a frontend operationalization of METHOD §2 proportionality; the concrete phase mapping is what makes proportionality actually fire (E2: concrete signal beats abstract principle), so it is not inferable-and-deletable.
5. **P1 human-evidence clarification — CONFIRMED.** "Authority-derived jobs are planning hypotheses about human operation until supported by proportionate Evidence" targets a real, model-specific failure class: LLMs fluently generate plausible personas/jobs from schemas and API surfaces, which is exactly backend-shaped UX at P1. The explicit "Formal user research is not a prerequisite for every frontend program; use the strongest Evidence proportional to the uncertainty and materiality" prevents the over-prescription failure the operator asked about. The two exemplar lists are compressible (R3-F4) but the rule is right-altitude.
6. **Operator walkthrough Evidence — CONFIRMED.** The canonical record is four lines (`OPERATED / actual task attempted / material issues found / final disposition`) — minimal and falsifiable (it distinguishes a real walkthrough from a rubber-stamp "operated: yes"). The probe sentence is gated by "When relevant" and explicitly de-fanged by "Do not turn these prompts into a mandatory questionnaire for trivial blocks." Not a questionnaire. Partial overlap with the §2 question set noted under R3-F4.
7. **Consumer→METHOD FINDING law — CONFIRMED.** The core law (local safeguard allowed now; cross-repository property MUST surface as METHOD FINDING; "Until central disposition, the safeguard remains local specialization") prevents permanent silent forks without blocking current work on central review — the anti-bureaucracy property holds. "One material real consumer may be sufficient" is genuine new signal: it kills the wait-for-N-repos failure mode. This law also supplies the missing return path for FRONTEND §24.10's existing "records justified local specialization instead of silently forking" duty. The promotion-review rubric sentence, however, restates the decision core (R3-F3). Note the law's own lineage is its best Evidence: this FRONTEND method is itself a promoted consumer safeguard suite (MetalDocs v2.3 generation), and the amendment under review is itself a consumer-feedback promotion — the law describes a channel that demonstrably already operates in Markdown + Git with zero new infrastructure.
8. **Could the same behavior be materially more concise? — PARTIALLY FALSIFIED (compression exists, mechanisms are right-sized).** The mechanisms — tri-state sweep, lock-time disposition record, 4-line walkthrough record, fidelity two-state, small-delta skip-list, feedback law — are near-minimal for behavior an agent must actually execute; deleting any of them re-exposes an evidenced failure class (E1's test fails in the keep direction). But roughly a quarter of the added prose fails the deletion test: three duplicated normative statements (R3-F1), one self-contradictory disposition (R3-F2), one restated rubric (R3-F3), and definition/list prose compressible without losing a failure class (R3-F4). The amendment is directionally sound; it should converge smaller, not different.

#### Findings detail

**R3-F1 — IMPORTANT — duplicated normative statements (rule-once violations).** The candidate's kernel commands "State each normative rule once" (METHOD.md, LLM-first), and R1-F2/R2 spent two rounds enforcing one-owner-per-rule across the suite. The amendment reintroduces the defect class inside single documents:

- (a) "P14 still requires material OPEN assumptions = 0" appears in §4 (Evidence vocabulary) **and** §14 (lock-time disposition), both restating what P14 §20 already owns as "material assumptions OPEN = 0". The same rule now appears three times in one file.
- (b) The §4 sentence and §14's opening sentence both state that P8 owns lock-time disposition of materially-depended-upon OPEN assumptions — the same ownership stated twice ~250 lines apart.
- (c) P14 gains "all retained P11 blocks PASS FIDELITY or were explicitly reopened" while P11 now owns "P11 exits only when all retained assembled LOCKED blocks pass fidelity verification…" and P14 already lists "P11 complete." With the new exit condition, "P11 complete" subsumes the new line entirely.

*Why it matters:* E5 shows adherence degrades with instruction count and biases toward earlier instructions; every duplicate is a pure adherence tax on all neighboring rules (E1: bloat causes rule-loss), and duplicated mutable statements are the drift class R1-F2 was raised to kill. *Smallest scope:* three deletions. *Recommended disposition:* in §4 keep only the pointer ("P8 owns explicit lock-time disposition for any still-OPEN assumption the block materially depends upon.") and delete its trailing P14 clause; in §14 delete the trailing "P14 still requires material OPEN assumptions = 0."; in P14 §20 delete the new fidelity line (P11's exit condition owns it; "P11 complete" fires it). *Falsifier for closure:* `grep -c "P14 still requires" FRONTEND-METHOD.md` returns 0 and the P14 checklist contains no P11-fidelity restatement.

**R3-F2 — IMPORTANT — `NOT_MATERIAL_TO_STRUCTURE` is unreachable.** The record's scope sentence is "every still-OPEN assumption **that the block's structure materially depends upon**"; the third disposition is defined as "does not support the block's protected structure." An assumption satisfying the scope condition cannot, by that definition, validly receive the disposition — the option exists only for items that should never have entered the record. An agent reading this either ignores the contradiction (unpredictable triage) or enumerates out-of-scope assumptions specifically so it can disposition them away — the exact template-filling behavior the very next sentence forbids. *Smallest scope:* one sentence. *Recommended disposition (either, not both):* widen the scope sentence to "every still-OPEN assumption plausibly material to the block" and keep the third disposition as the triage-out; **or** keep the current strict scope and delete `NOT_MATERIAL_TO_STRUCTURE` (out-of-scope assumptions simply stay in the normal §4 assumption ledger). The second option is smaller and is preferred under E1/E2. *Falsifier:* the scope sentence and the disposition set compose without a vacuous branch.

**R3-F3 — MINOR — promotion-review rubric restates the decision core.** METHOD.md's new second paragraph ("Central promotion review asks whether the failure class is real/generalizable, whether current methods already cover it, what credible alternatives exist, and whether promotion reduces total risk/complexity without ceremony inflation") is the §3 decision core (Evidence → Credible Alternatives → Complexity law/YAGNI) re-instantiated. §1 already states "A change to this method is itself a material decision: apply the current accepted Method" — so the rubric fires with the sentence deleted. Deletion test: no failure class re-exposed. Keep the genuinely new second sentence ("One material real consumer may be sufficient…"). Similarly compress the final sentence: "consuming repositories then upgrade their pinned methodology deliberately" restates the README Consumption-contract pin-move rule; the new signal is only the ordering ("update canonical methodology first"). Proposed compressed paragraph 2–3: "Promotion is a material METHOD change; adjudicate it with this Method. One material real consumer may be sufficient when the failure class is clearly cross-repository. Until central disposition, the safeguard remains local specialization. If promoted, canonical methodology updates first; consumers follow the normal pin-move path and boundedly rebaseline only affected work." (~45% smaller, same behavior.)

**R3-F4 — MINOR — compressible definition/list prose.** No failure class is protected by the extra words in: (a) the `UNAFFECTED` definition's five-item enumeration (the method's existing vocabulary "protected structure / Screen Contract / dependency" covers it); (b) P1's five-item evidence-type list, which re-enumerates §4's input classes (`USER / OPERATOR EVIDENCE`, `REFERENCE EVIDENCE`) inline, and its five-item assumption-kind list, an instance of §4's "material assumptions remain explicit"; (c) the walkthrough probe sentence's overlap with the §2 success-condition question set; (d) P11's exit clause "and the material cross-block journeys are coherent," restating the section's own "Prove cross-block navigation, complete journeys…". Estimated recoverable: ~25–30 lines of the +124 without deleting any mechanism. Optional; bundle with F1/F2 edits if the Lead accepts them.

#### Amendment disposition table (KEEP / COMPRESS / DELETE / ADD)

| Amendment element | Disposition | Deciding Evidence |
|---|---|---|
| LOCK impact sweep: tri-state disposition + compact matrix + no-reflex-invalidation + no new file | **KEEP** (compress disposition definitions per F4a) | E2 altitude: replaced text had no firing mechanism; explicit per-block record is the smallest checkable form. E1: rule without observable effect is prose. |
| Small bounded delta path + "not small merely because diff is small" guard | **KEEP** | E2: concrete phase mapping is what makes METHOD §2 proportionality fire; guard sentence blocks the evidenced laundering route. |
| P1 hypotheses-until-evidence + "formal research not prerequisite" | **KEEP** (compress both exemplar lists per F4b) | E1/E2: core rule targets a real model failure (schema-derived personas); lists duplicate §4 vocabulary. |
| §4 sentence: P8 ownership pointer | **COMPRESS** — keep pointer, delete P14 clause | METHOD LLM-first rule-once; E5 density cost (F1a/F1b). |
| P8 lock-time disposition record + operator-only ACCEPT + anti-template guard | **KEEP** (fix scope/disposition contradiction per F2; delete trailing P14 clause per F1a) | E2 altitude; contradiction is the only defect. |
| `NOT_MATERIAL_TO_STRUCTURE` disposition | **DELETE** (preferred) or widen scope sentence | F2: unreachable branch; E1 deletion test passes — the §4 assumption ledger already holds out-of-scope items. |
| Operator walkthrough 4-line record + anti-questionnaire guard | **KEEP** | E1: minimal falsifiable record distinguishes walkthrough from rubber-stamp; already near floor. |
| Walkthrough probe sentence | **KEEP** (optionally compress by citing §2 question set, F4c) | Single "when relevant"-gated sentence; marginal. |
| P8 exit: 2 new lines | **KEEP** | Exit checklists are the firing surface for the two new records. |
| P11 immutability + assembled-fidelity check + reuse-existing-verifier + PASS FIDELITY/REOPEN + exit condition | **KEEP** (trim exit second clause per F4d) | E1/E2: closes silent-redesign channel with a two-state record, explicitly refuses a verification framework. |
| P14 line "all retained P11 blocks PASS FIDELITY…" | **DELETE** | F1c: subsumed by "P11 complete" + P11 exit; rule-once. |
| §21 block-protocol ledger lines (3 edits) | **KEEP** | Artifact-preservation index, "when applicable"-gated; records, not rules. |
| §23 attack-list additions (3 lenses) | **KEEP** | Attack list is the firing mechanism for reviewers (this R3 exercised all three lenses); lenses are pointers, not duplicate rules. |
| METHOD feedback law: core law + one-consumer threshold + local-until-disposition | **KEEP** | Confirmation 7; lineage of this very amendment is the executed proof. |
| METHOD feedback law: promotion rubric sentence + pin-restatement | **COMPRESS** per F3 | §1 material-decision clause + §3 decision core + README Consumption contract already own the semantics. |
| New machinery / infrastructure | **ADD: none** | No current failure demonstrated that Markdown + Git cannot solve; E3 confirms plain hierarchical Markdown is the current vendor-recommended substrate for exactly this workflow. |

#### Preserved invariants — regression check

The amendment leaves intact, and this round re-verified at HEAD: the phase chain P7 → P8 functional HTML + operator LOCK → P9 → P10 → P11 → P12; browser-operable P8 (§3.8 unchanged); operator-only LOCK (§3.6 unchanged; both new mechanisms route final authority to the operator — `ACCEPT_FOR_LOCK_WITH_LATER_PROBE` is operator-only, fidelity failure routes to FINDING → operator re-LOCK); no screen-shaped backend / no backend-shaped UX (§3.9/§3.10 unchanged; the P1 addition strengthens the anti-backend-shaped direction); Global Maximum before YAGNI (METHOD §3 untouched); smallest-semantic-owner reopen (REOPEN disposition explicitly says "smallest required earlier frontend phase or upstream owner"); P10 after repeated LOCK evidence (§16 untouched); P12 as whole-product backstop (§18 untouched). No preserved invariant is weakened; several gain firing mechanisms.

#### Net verdict for R3

The amendment is behaviorally sound: all seven protected mechanisms are confirmed against both the repository's own laws and current external instruction-design evidence, and no MATERIAL finding exists. It is not yet textually converged: two IMPORTANT internal-consistency defects (three duplicated normative statements; one unreachable disposition) and two MINOR compressions keep it above the smallest high-signal form the kernel itself mandates. All proposed corrections are deletions or single-sentence rewords on the amendment's own text — no redesign, no new machinery, no reopening of settled R1/R2 areas.

**LEAD RESPONSE REQUIRED** — adjudicate R3-F1 and R3-F2 (bounded edits on the candidate branch), disposition R3-F3/R3-F4 (accept, defer, or reject as polish), then this round can converge on the corrected HEAD without a further Challenger turn unless material uncertainty survives.

### R3-L1 — LEAD

Adjudication against corrected candidate `c2944492091990ec047bf5ac35546bf758618826`:

- **R3-F1 — ACCEPT / CLOSED.** Removed the repeated P14 assumption clause from §4/P8 and removed the P11-fidelity restatement from P14. P14 now owns only its implementation-readiness checklist; P8/P11 own their respective exit laws.
- **R3-F2 — ACCEPT / CLOSED.** Kept the strict scope (only assumptions materially depended upon by the block enter the lock-time record) and deleted `NOT_MATERIAL_TO_STRUCTURE`. Non-structural assumptions remain in the normal assumption ledger rather than entering a vacuous disposition branch.
- **R3-F3 — ACCEPT / CLOSED.** Compressed consumer→METHOD feedback to the new signal only: cross-repository safeguards surface centrally, one real material consumer may suffice, local specialization remains local until disposition, canonical method updates before normal consumer pin-move/rebaseline.
- **R3-F4 — ACCEPT / CLOSED.** Compressed `UNAFFECTED`, P1 evidence examples, walkthrough probes (now reusing §2), and the P11 exit clause without deleting any firing mechanism.

Fresh verification:

```text
562473ed..c2944492
= 2 commits
= METHOD.md + FRONTEND-METHOD.md only
FRONTEND correction = +7 / -11
METHOD correction   = +1 / -3
net correction      = -6 lines
```

At corrected HEAD:

```text
NOT_MATERIAL_TO_STRUCTURE = absent
"P14 still requires"      = absent
P14 P11-fidelity restate   = absent
P8 lock-time record        = present
LOCK impact tri-state      = present
P11 PASS FIDELITY/REOPEN   = present
small-delta anti-abuse law = present
formal user research gate  = explicitly rejected
new machinery              = none
CodeRabbit                  = success
```

Core sequencing remains:

```text
P7
→ P8 browser-operable functional HTML + operator LOCK
→ P9 exact Screen Contract
→ P10 repeated-LOCK pattern consolidation
→ P11 assembled prototype + fidelity
→ P12 whole-product adversarial backstop
```

No screen-shaped backend, no backend-shaped UX, Global Maximum before YAGNI, smallest-owner reopen and operator-only LOCK remain unchanged.

All R3 corrections are the bounded deletions/compressions requested by the Challenger. No material uncertainty survives and no additional mechanism or scope was introduced.

**R3 CONVERGED — no MATERIAL or IMPORTANT finding remains open.**
