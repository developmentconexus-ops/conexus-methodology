# DevelopmentConexus Evidence-Grounded Realization Method

**Version:** 1.0.0  
**Status:** CANDIDATE FOR ORGANIZATIONAL RATIFICATION  
**Scope:** material technology selection, production implementation, integration, dependency, and proof work across DevelopmentConexus repositories  
**Lineage:** consolidates reusable production-engineering/realization guidance proven in Marketplace Central and Conexus OS

## 1. Purpose

Turn accepted Product/system authority into production software without allowing technology, framework defaults, model memory, examples, or current implementation to become a second authority.

The target is the smallest sustainable realization that preserves accepted meaning and failure properties while reusing standards and mature mechanisms when they genuinely fit.

```text
accepted authority / protected property
→ exact engineering question
→ current Evidence
→ credible alternatives
→ ADOPT | ADAPT | BUILD | DEFER | STOP
→ proof strategy before implementation
→ exact version/dependency admission when needed
→ implementation
→ claim-matched proof
→ durable result / residual risk / reopen trigger
```

This method specializes `METHOD.md`. It does not own Product semantics, architecture, status, implementation authorization, or repository-local technology decisions.

## 2. Epistemic discipline

For every material conclusion classify the basis:

```text
KNOWN
  current repository authority, normative/official source,
  exact source/version Evidence, or executed proof

INFERRED
  reasoned from cited Evidence with assumptions visible

UNKNOWN
  Evidence insufficient; no convenient default

DEFERRED
  a named later consumer/stage owns the question;
  safety basis + reopen trigger remain explicit
```

Never convert:

```text
latest → compatible
popular → fit
example → production contract
current code → target authority
framework/provider behavior → Product authority
mock success → real dependency proof
unknown/partial → zero/success/safe
reference implementation → required dependency
```

For unstable external facts, current APIs, security guidance, version support, provider behavior, or framework semantics, re-check current primary sources. Model memory is discovery help, never deciding Evidence.

## 3. Property before technology

Research starts from the protected property or failure class, not a preferred tool.

Bad:

```text
Which auth framework should we use?
Which queue should we use?
Which React state library is best?
```

Good:

```text
How do we authenticate humans without owning password/MFA machinery
while preserving Product-owned identity and Authorization?

How do we make a committed owner mutation trigger durable asynchronous work
without making an event bus a second source of truth?

How do we prevent an ambiguous external write from being blindly replayed?
```

A technology search without an invariant is solution shopping.

## 4. Claim-relative source hierarchy

Use the strongest source required by the claim:

1. current repository Product/architecture/decision authority;
2. normative specifications and standards;
3. official documentation for the exact selected technology/provider version;
4. official source repositories, release notes, migrations, and security advisories;
5. mature reference implementations with comparable failure properties;
6. peer-reviewed or well-documented production engineering references;
7. community material only for discovery/corroboration.

A reference may be `REFERENCE_ONLY`: useful to learn a failure-handling or design pattern without becoming a dependency.

Research is complete when the property and constraints are clear, primary sources establish relevant behavior, credible alternatives were compared, fit/failure modes are understood, a proportional falsifier exists, and additional research no longer changes the decision space.

## 5. ADOPT / ADAPT / BUILD / DEFER / STOP

Use this outcome vocabulary for material realization choices:

| Outcome | Select when |
|---|---|
| `ADOPT` | a standard/native/mature mechanism satisfies the invariant without moving Product authority or adding disproportionate operations |
| `ADAPT` | a proven mechanism fits behind one bounded repository-owned adapter/boundary |
| `BUILD` | a real evidenced gap remains and the smallest custom surface can be bounded and falsified |
| `DEFER` | no current consumer/failure class needs it and the seam can be added later without structural rework |
| `STOP` | a prerequisite or external behavior required for correctness remains unproven |

Before `BUILD`, answer:

1. What exact gap defeats `ADOPT`/`ADAPT`?
2. What defect class remains reachable otherwise?
3. What is the smallest custom surface?
4. Who owns its meaning/lifecycle?
5. How can it be removed/replaced?
6. What falsifier proves the custom mechanism is necessary and correct?

Prepare the seam, not the speculative platform.

## 6. Dependency admission

A production dependency is architecture even when introduced by one import.

For a material library/service/generator/framework evaluate proportionately:

| Dimension | Questions |
|---|---|
| Authority | official/reference/maintained independent source? |
| Problem fit | protects the actual invariant or merely resembles the use case? |
| Exact version fit | compatible with adopted runtime/language/database/browser/toolchain? |
| Maintenance/security | releases, advisories, policy, response path? |
| Correctness Evidence | tests, conformance, fuzzing, source, production use? |
| Operations | state, processes, upgrades, backups, metrics, failure modes? |
| Supply chain | transitive dependencies, binaries, build/install surface? |
| License | compatible with intended use/distribution? |
| Lock-in | bounded replacement interface and data/protocol migration cost? |
| Reversibility | removable without rewriting Product meaning? |
| Total complexity | reduces system complexity or only moves it into configuration/operations? |

Stars, download counts, benchmark screenshots, and brand reputation are discovery signals, not deciding proof.

Prefer native/standard behavior when sufficient, narrow dependencies over broad frameworks, bounded external interfaces, reproducible pins, and deliberate upgrades.

Do not fork casually: a fork transfers security, compatibility, and release ownership to the repository.

## 7. Exact-version law

Do not freeze volatile `latest` choices during early planning when the exact version is not yet decision-relevant.

When implementation reaches the dependency admission point:

```text
current official supported releases
→ exact compatibility/security/migration review
→ exact source/configuration pin
→ bounded negative/real probe where material
→ accepted execution pin
```

Version-sensitive claims resolve against the exact selected artifact/source/configuration, not generic documentation for the project name.

## 8. Proof before implementation

For every material realization claim define how it could be proven false before implementing.

Proof strength matches the claim:

| Claim | Suitable proof |
|---|---|
| pure/value behavior | table/property/fuzz/boundary tests |
| type/API contract | compile/type/schema failure, contract diff, generated projection conformance |
| DB invariant | real constraint/transaction/migration/concurrency proof |
| concurrency | deterministic race/linearization/invariant/stress proof as applicable |
| idempotency | duplicate + changed-request + concurrent/restart proof |
| browser/session | real browser/server integration when browser behavior is claimed |
| tenant/security | cross-tenant/permission/abuse negative controls |
| external integration | controlled real dependency Evidence for real provider claims |
| external effect | ambiguity injection + authoritative reread/reconciliation |
| recovery | crash/restart/loss/redelivery/restore Evidence at the owning stage |
| performance | representative dataset/load/query plan/resource proof |
| observability | prove the signal fires, attributes the failure, and does not leak data |
| deployment/migration | exact build/deploy/migration/recovery rehearsal proportional to claim |

A mock proves the local mock boundary only. Artifact existence is not proof. A guard that cannot be demonstrated to fire is not proven.

## 9. Before production code

A material realization increment begins with:

```text
repository/ref/current authority revalidated
→ implementation authorization confirmed
→ scope + acceptance increment identified
→ materiality/root cause/invariant stated
→ current Evidence + unknowns classified
→ standards/reference research as needed
→ credible alternatives compared
→ ADOPT/ADAPT/BUILD/DEFER/STOP disposition
→ proof strategy + falsifier
→ dependency/version admission if triggered
→ write scope
```

Do not implement from chat history alone when repository authority can reconstruct the decision.

If realization Evidence falsifies accepted upstream architecture/Product assumptions, do not silently patch around them. Emit an upstream Finding and apply the downstream-falsification law in `METHOD.md`.

## 10. During implementation

Preserve one authority for each material meaning.

As applicable:

- keep provider/framework wire objects behind bounded adapters;
- use explicit types/contracts rather than ambiguous property bags;
- make illegal states structurally difficult where reasonable;
- use database constraints for database-owned invariants;
- fail closed at identity, tenant, security, authorization, and consequential-effect ambiguity boundaries;
- propagate cancellation/deadlines across blocking/remote work;
- bound concurrency, memory, payloads, retries, queues, and external calls;
- distinguish safe retry from idempotency and from ambiguous external acceptance;
- preserve sufficient historical/provenance Evidence without creating generic payload archives;
- keep generated code derived from one source authority with drift mechanically detectable;
- update contract + implementation + proof together when one material contract changes;
- avoid unrelated refactoring, compatibility tax without a consumer, and speculative extensibility.

Never add silent fallback, fake success, hard-coded production answers, or tests that only imitate the dependency whose behavior is claimed.

## 11. External effects and integrations

For each material external read/write establish, as applicable:

```text
correct Organization/tenant
correct installation/source namespace
current credential capability
semantic owner + operation authority
source time/freshness/coverage meaning
idempotency/duplicate protection
ambiguous acceptance behavior
reconciliation/reread path
audit/provenance
PII/secret minimization
```

Provider success does not automatically mean Product success.

For potentially accepted consequential writes:

```text
unknown acceptance
-X-> blind retry
→ reconcile authoritative provider/business truth
→ decide from evidence
```

A provider API convenience does not become a Product capability by existence.

## 12. AI/LLM-assisted implementation law

Agents accelerate generation, not authority.

- repository authority and exact current Evidence outrank model memory;
- generated code is reviewed/proved by the same claim-relative standards as human code;
- prompts, examples, agent plans, scratchpads, and reviewer prose are not Product authority;
- use current official docs/source when library behavior is version-sensitive;
- keep task context selective instead of recursively loading the repository;
- prefer small coherent acceptance increments that a fresh reviewer/agent can hold in context;
- material uncertainty remains explicit rather than being completed by plausible inference;
- reviewer/agent findings are Evidence and may not smuggle new requirements into implementation.

## 13. Verification and closure

Before claiming an acceptance increment complete:

```text
inspect final diff
→ scope COBRE / FALTA / EXCEDE review
→ focused falsifier/proof
→ repository-prescribed aggregate gate
→ exact-head CI/check revalidation where applicable
→ real-dependency proof for real-dependency claims
→ residual Unknown/risk/reopen trigger recorded
```

A skipped/unavailable proof remains unproven; say so explicitly.

A large diff is not automatically wrong, but when one PR contains multiple independently acceptable outcomes, split it. Diff size is a review signal; semantic coherence is the boundary.

## 14. Technology-specific specialization

This organizational method deliberately does **not** prescribe Go, PostgreSQL, React, OpenAPI, Keycloak, Mastra, a queue, a cloud, or any other stack.

A consuming repository may keep concise technology-specific guidance when it has a real consumer. Such guidance:

- cites this method and current Product/architecture authority;
- remains repository-specific;
- uses exact official version documentation/source when material;
- cannot silently become Product/status authority;
- is removed or revised when the technology/consumer disappears.

## 15. Final principle

Reuse proven engineering when it preserves repository meaning. Adapt only across a bounded evidenced gap. Build custom machinery only for a real unresolved property. Prove real claims against the real dependency.

```text
maximum generation speed
-X-> maximum engineering quality

accepted authority
+ current Evidence
+ smallest sustainable mechanism
+ falsifiable proof
= production realization
```
