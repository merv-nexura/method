---
title: "Decision: Cognitive Composition Thesis — Selective vs Maximal"
status: open
owner: Merv
date: "2026-05-31"
prd_type: research
relates_to: [030, 032, 035, 037, 050, 052]
---

# Decision needed: what is our cognitive-composition thesis?

**Status: OPEN — needs an owner decision this sprint.** This is a roadmap fork, not a doc cleanup.

## The contradiction

The cognitive-architecture PRDs are pulling in opposite directions, and our own best evidence backs only one of them:

- **PRD-035 (the most rigorously validated PRD in the set)** found that stacking metacognitive patterns **degrades** performance: full composition dropped task success **75% → 22%**, and it concluded **"selective > maximal metacognition."**
- **PRD-032** ships and claims "all 8 patterns."
- **PRD-037** ships a `maximalPreset` (everything on).
- **PRDs 050 / 052** then build routers *specifically because* running the cognitive stack unconditionally hurts ~33% of tasks — effectively conceding 035's point.

So we are simultaneously building "more composition" (032/037) and "route around composition because it's harmful" (050/052).

## The fork

Pick one and align the PRDs to it:

- **Option A — Selective (evidence-backed).** Default to flat/minimal cognition; treat each pattern as opt-in and earn it with per-task evidence. Make routing (050/052) first-class. Demote `maximalPreset` (037) to an experiment-only flag. Re-scope 032's "all 8 patterns" claim.
- **Option B — Maximal (current build direction).** Keep full composition as the target and treat 035's collapse as a calibration bug to fix (e.g., the documented `minPredictionError` miscalibration). Requires a concrete plan to reproduce 035 and show composition can be made non-harmful **before** more patterns ship.
- **Option C — Hybrid.** Maximal is research-only (tagged `prd_type: research`); product path is selective + routed. Clear labeling so reporting never conflates the two.

## Recommendation

Option C, leaning A for the product path: the only validated result we have says maximal hurts, so product should default selective/routed; maximal composition continues as explicitly-tagged research until it can beat the flat baseline on the hardened bench (see EVAL-BENCH-HARDENING).

## Decision
_Owner: Merv — record the chosen option, date, and the PRD edits it triggers._
