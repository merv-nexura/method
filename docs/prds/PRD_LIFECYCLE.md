---
title: "PRD Lifecycle & Governance"
status: active
owner: Merv
date: "2026-05-31"
---

# PRD Lifecycle & Governance

This document defines how PRDs in `docs/prds/` are tracked so that **status is a reliable source of truth**. It exists because a 2026-05-31 review of PRD-023→059 found ~6 PRDs whose front-matter status contradicted their own bodies, several "done" PRDs with no recorded metrics, missing/duplicate numbers, and no named owners.

## 1. The five states

PRDs move strictly forward through these states. Every PRD's front-matter `status:` MUST be one of them.

| State | Meaning | Entry criteria (all required) |
|-------|---------|-------------------------------|
| `draft` | Being written / proposed. | Document exists; problem stated. |
| `approved` | Design accepted; build not yet complete. | Reviewed and accepted; scope + success criteria defined; **no claim that code shipped**. Use this for detailed designs whose phases are still pending. |
| `in-progress` | Implementation underway. | At least one phase merged; remaining phases tracked. |
| `implemented` | Built and merged. | Code merged to `master` **and tests green**. Success metrics not necessarily measured yet. |
| `validated` | Proven against its own success criteria. | `implemented` **plus** each success criterion has a **recorded, dated measured outcome** in the doc. |

Legacy alias: `complete` is treated as `implemented` until metrics are recorded (then `validated`). New PRDs must not use `complete`.

## 2. "Implemented" vs "validated" — the bright line

- **`implemented` = merged + tests green.** Nothing more is claimed.
- **`validated` = success metrics measured and recorded.** A PRD cannot be `validated` until every success criterion shows an actual number/result with a date. PRDs that assert success criteria but record no outcomes (e.g. 026, 031, 053 as of this review) stay at `implemented`, not `validated`.

## 3. Required front-matter fields

```yaml
---
title: "PRD NNN: <name>"
status: draft|approved|in-progress|implemented|validated
owner: <name>            # REQUIRED. No PRD ships without an accountable owner. Default: Merv.
prd_type: product|research   # REQUIRED. See §5.
date: "YYYY-MM-DD"
problem_evidence: "<incident/metric/citation>"   # REQUIRED before leaving `draft`. See §4.
depends_on: [..]
---
```

When status is changed by anyone other than the author, add `status_note:` (why) and `status_corrected: YYYY-MM-DD`.

## 4. `problem_evidence` gate (anti "build-ahead-of-need")

A PRD may not leave `draft` until `problem_evidence` cites a **real** signal — an incident, a measured metric, a user/customer report, or a profiled limit. "We might need X at scale" is not evidence. (Example from the review: PRD-039 Bridge Cluster admitted no capacity-blocking incident had occurred, yet shipped in full.)

## 5. `prd_type`: product vs research

- `product` — intended to ship user/operator value. Held to product success criteria.
- `research` — a hypothesis/exploration bet. May ship infrastructure without proving the thesis, **but must be tagged `research`** so "what's shipped" reporting never conflates hypothesis scaffolding with delivered value. (Example: PRD-030 and descendants.)

## 6. Numbering rules

1. Numbers are unique and assigned from a single source (this directory). Check for collisions before claiming a number.
2. Gaps are allowed but must be recorded in `README.md` (what happened to the number).
3. Never reuse a number for two PRDs. The 2026-05-31 review found two PRDs numbered 057; the SLM Cascade PRD was renumbered to 051.

## 7. Ownership

Every PRD has exactly one accountable `owner`. Missing owners default to **Merv** until reassigned. The owner is responsible for keeping status honest.
