---
title: "PRD Index"
owner: Merv
date: "2026-05-31"
---

# PRD Index (`docs/prds/`)

Governance: see [`PRD_LIFECYCLE.md`](./PRD_LIFECYCLE.md). New PRDs start from [`PRD_TEMPLATE.md`](./PRD_TEMPLATE.md).

This index is the authoritative record of PRD number, owner, and status. It was reconciled on **2026-05-31** following a product review of PRD-023→059. Where a PRD's front-matter status was corrected, see its `status_note`.

## Status lifecycle
`draft → approved → in-progress → implemented → validated` (legacy `complete` ≡ `implemented`). See PRD_LIFECYCLE.md for entry criteria.

## Numbering notes

- **024** — no PRD exists with this number (never written / abandoned). Slot intentionally left empty; do not reuse without recording why here.
- **051** — now assigned to **SLM Cascade Infrastructure**, renumbered from a duplicate `057` on 2026-05-31 (fits the SLM/router cluster 049–052). The old `057-slm-cascade-infrastructure.md` is a tombstone redirect (no delete via API).
- **057** — canonical: **fca-index Language Profiles**. (Previously collided with SLM Cascade; see above.)
- **009** — predates this range; not reviewed here.

## Index (023→059)

Owner defaults to **Merv** pending reassignment. "Status" reflects the corrected front-matter as of 2026-05-31.

| PRD | Title | Owner | Status | Note |
|-----|-------|-------|--------|------|
| 023 | FCA Bridge Refactor (Fractal Component Architecture) | Merv | implemented | Phases 0–10,12 done; D1/D2 deferred → issue #202 |
| 025 | Universal Genesis (GES) | Merv | implemented | |
| 026 | Universal Event Bus | Merv | implemented | not `validated` — metrics not recorded |
| 027 | Pacta — Modular Agent SDK | Merv | implemented | |
| 028 | Pacta Print-Mode Convergence + PTY removal | Merv | implemented | clean |
| 029 | Bridge Resilience | Merv | implemented | Phase 3 deferred |
| 030 | Pacta Cognitive Composition | Merv | approved (was implemented) | research; body phases all pending |
| 031 | Cognitive Memory Module | Merv | implemented | not `validated` — metrics not recorded |
| 032 | Advanced Cognitive Patterns | Merv | implemented | P3 superseded by 037 |
| 033 | Cognitive Session UX | Merv | implemented | |
| 034 | SLM Validation | Merv | in-progress (was implemented) | Gate 4 blocked on ONNX/Windows |
| 035 | Cognitive Monitoring & Control v2 | Merv | implemented | validation mixed: maximal composition 75%→22% |
| 036 | Cognitive Memory Architecture | Merv | approved (was implemented) | body phases all pending |
| 037 | Cognitive Affect & Exploration | Merv | approved (was implemented) | research; body phases all pending |
| 038 | Bridge Deployment | Merv | implemented | clean |
| 039 | Bridge Cluster | Merv | implemented | build-ahead-of-need (no capacity incident) |
| 040 | Cognitive Agent Maturity | Merv | implemented | |
| 041 | Cognitive Experiment Lab | Merv | implemented | |
| 042 | Cognitive Composition Bridge Integration | Merv | implemented | |
| 043 | Workspace Constraint Pinning | Merv | implemented | T02/T03 −40pp dismissed as variance — re-run |
| 044 | Workspace Partition Architecture | Merv | approved (was implemented) | written as proposal; R-17 not run |
| 045 | Goal-State Monitoring | Merv | draft | |
| 046 | Runtime Consolidation | Merv | implemented | no results section |
| 047 | Build Orchestrator | Merv | draft | very large scope |
| 048 | Cybernetic Verification Loop | Merv | draft | |
| 049 | KPI Checker SLM | Merv | draft | |
| 050 | Meta-Cognitive Router | Merv | draft | |
| 051 | SLM Cascade Infrastructure | Merv | in-progress (was complete @057) | renumbered from 057; Wave 4 contradiction |
| 052 | Router SLM | Merv | draft | |
| 053 | fca-index Library | Merv | complete→implemented | metrics contested (SC-1, AC-3) |
| 054 | fca-index MCP Tools | Merv | complete→implemented | |
| 055 | Methodology Smoke Test Suite | Merv | implemented | front-matter added; SC-1 coverage unmet |
| 056 | Smoke Test Viz Redesign | Merv | draft | front-matter added |
| 057 | fca-index Language Profiles | Merv | in-progress | canonical 057 |
| 058 | Hierarchical Trace Observability | Merv | complete→implemented | infra only; migration deferred |
| 059 | Pacta Testkit Diagnostics | Merv | complete→implemented | SC-4 adoption skipped |

## Open decisions

- [`decisions/COGNITIVE-COMPOSITION-THESIS.md`](./decisions/COGNITIVE-COMPOSITION-THESIS.md) — selective vs maximal (relates 030/032/035/037/050/052).
- [`decisions/EVAL-BENCH-HARDENING.md`](./decisions/EVAL-BENCH-HARDENING.md) — fix the N=5 / 6-task bench before trusting further claims.

## Related

- Issue **#202** — PRD-023 D1/D2 follow-up (supersedes legacy tracker note "#644").
