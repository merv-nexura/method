---
title: "Proposal: Harden the cognitive eval bench before trusting further claims"
status: open
owner: Merv
date: "2026-05-31"
prd_type: product
relates_to: [032, 035, 043, 048, 049, 050, 052]
---

# Proposal: harden the eval bench

**Problem.** Almost every cognitive success/regression claim rests on a 6-task suite (T01–T06) at **N=5** runs. That sample cannot separate signal from noise — and the PRDs prove it: PRD-043 shows T02 dropping **80%→40%** and T03 **60%→20%** under its own change, dismissed as "LLM variance at N=5." Either those regressions are real (the change is harmful) or the bench is too noisy to validate anything built on it (every success claim is shaky). Both readings block trustworthy decisions.

## What to do (before trusting any further cognitive claims)

1. **Raise N.** Move from N=5 to a sample that yields usable confidence intervals (target ≥20 runs/condition; justify per-task).
2. **Expand beyond T01–T06.** Add tasks covering the regression-prone cases and the routing decision boundary (050/052). Document each task's intent.
3. **Define signal vs. variance up front.** State the minimum effect size that counts as a real change, and report confidence intervals, not point estimates. No more "dismissed as variance" without the interval to back it.
4. **Re-run the disputed results.** Specifically re-run PRD-043's T02/T03 regression under the hardened protocol before treating it as variance.
5. **Gate `validated`.** A cognitive PRD reaches `validated` only against this hardened bench with recorded outcomes (ties into PRD_LIFECYCLE §2).

## Why now
This is the dependency under the entire cognitive roadmap and the composition-thesis decision. Until the bench is trustworthy, 032/035/037/048/049/050/052 success claims can't be relied on.

## Decision
_Owner: Merv — approve scope, assign build, set the N and effect-size thresholds._
