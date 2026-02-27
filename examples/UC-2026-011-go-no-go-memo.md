# Go / No-Go Decision Memo

**Template version:** 1.3
**Use Case ID:** `UC-2026-011`
**Use Case Name:** Claims Triage AI — Region 4
**Memo date:** `2026-04-09`
**Prepared by:** Jordan Kim, AI Workflow Operations
**Distribution:** Dana Reyes (Claims Ops), Michael Tran (VP Claims Ops), Michael Bassett (AI Ops)

---

## Decision

> **[x] CONDITIONAL GO** — Proceed to production deployment in Region 4 after both conditions listed in this memo are verified as complete by AI Ops.

---

## Use Case Summary

**What this AI does:**
ClaimAssist TriageAI v2.3 pre-populates claim category, urgency tier, and routing destination for incoming standard FNOL claims. The Claims Specialist reviews and confirms or adjusts the recommendation before the claim routes to an adjuster queue. No claim routes without specialist action.

**Pilot scope:**
4 Claims Specialists, Region 4 (Oklahoma and Kansas), standard FNOL claims only — non-CAT, non-litigated, non-commercial. March 2–28, 2026.

**Pilot dates:** Start: March 2, 2026 — End: March 28, 2026 — Duration: 4 weeks

**Risk tier:** Tier 2 — Moderate

---

## Evidence Summary

### Performance vs Baseline

| Metric | Baseline | Pilot | Delta | Assessment |
|---|---|---|---|---|
| Average handle time | 14.2 min | 8.8 min | -38% | **Exceeded** stretch goal (9.0 min) |
| Triage accuracy rate | 93.5% | 94.8% | +1.3 pts | **Exceeded** minimum (no regression) |
| Incorrect routing (error) rate | 2.1% | 1.8% | -0.3 pts | **Exceeded** minimum (no increase) |
| Escalation rate | 5.4% | 6.1% | +0.7 pts | **Met** — within +10 pt threshold |
| Weekly volume processed | 105.9 | 98.5 | -7.0% | Expected — scope exclusions applied |

### Risk Metrics

| Metric | Pilot Result | Threshold | Status |
|---|---|---|---|
| Override rate | 17.2% | 25% max | Within bounds |
| Error delta vs baseline | -0.3 pts | +5 pts max | Within bounds |
| Escalation delta | +0.7 pts | +10 pts max | Within bounds |
| User-reported issues | 0.75/week avg | 3/week max | Within bounds |
| Model failure rate | 0.5% | 2% max | Within bounds |

### ROI Estimate

| Metric | Estimate | Basis |
|---|---|---|
| Time saved per claim | 5.4 minutes | Measured AHT delta |
| Total monthly time saved | ~39.6 hours | ~440 claims × 5.4 min |
| Estimated monthly cost delta | ~$1,881 | 39.6 hrs × $47.50 loaded rate |
| Estimated annual savings, Region 4 | ~$22,572 | Monthly × 12 — **estimate only** |

*All ROI figures are estimates from a bounded pilot. Not guaranteed production outcomes.*

---

## Key Findings

1. Average handle time dropped from 14.2 to 8.8 minutes — a 38% reduction. This exceeds both the minimum threshold (12.0 minutes) and the stretch goal (9.0 minutes). The result was consistent across all four weeks of the pilot and across all four specialists.

2. Triage accuracy improved from 93.5% to 94.8%. The QA sample methodology was identical in both the baseline and pilot periods. AI-assisted triage did not degrade quality — it improved slightly, which is consistent with the AI handling straightforward categorization and freeing specialist attention for edge cases.

3. The override rate of 17.2% is within threshold and, more usefully, is diagnostic. Analysis of the 68 overrides shows that 45.6% follow a single pattern: the AI assigns urgency Tier 2 to wind damage claims that specialists consistently reassign to Tier 1. This is a calibration gap, not random error, and it has a defined fix.

4. The routing destination overrides (17.6% of overrides) trace entirely to a data sync gap — the adjuster assignment table in TriageAI is not current. This is a data maintenance issue, not a model quality issue, and it is resolved by a one-time sync.

5. Specialist feedback was broadly positive. Three of four specialists agreed that AI recommendations are accurate and that the tool made their work easier. The main concern raised by three of four specialists was urgency tier accuracy on wind claims — the same pattern identified in the override analysis.

---

## Risk Observations

| Observation | Severity | Recommended Mitigation |
|---|---|---|
| Urgency tier over-tiering on wind damage claims is a consistent, patterned error | Medium | ClaimAssist calibration update required before production go-live. Verified by AI Ops test run. |
| Adjuster routing table in TriageAI is not current | Low | One-time data sync required. Completed by Claims Ops before production launch. |
| Escalation rate increased by 0.7 percentage points | Low | Monitor for 30 days post-deployment. If delta reaches +3 pts, trigger review. No action needed now. |

---

## Recommendation Rationale

The pilot produced results that meet the evidentiary standard for a production deployment. Every performance threshold was met or exceeded. No metric regressed. The override rate is within bounds. The ROI estimate is conservative and based on measured data, not vendor projections.

Two issues are carried forward as conditions. The urgency tier calibration gap is a medium-severity concern because it is consistent and patterned — left unaddressed, it would erode specialist confidence in the AI's recommendations over time and could drive the override rate toward the threshold. ClaimAssist has reviewed the override data and confirmed a calibration update is feasible within two weeks. The adjuster routing table sync is a straightforward data maintenance task with no model quality implications.

Neither condition suggests the use case has a fundamental problem or that the vendor cannot deliver. Both have clear owners and short timelines. Production deployment is appropriate once both are verified.

The escalation rate increase of 0.7 percentage points is noted but not interpreted as a meaningful signal at this time. It will be tracked on the adoption scorecard for 30 days post-deployment.

---

## Conditions

*Production deployment does not begin until both conditions are verified complete by AI Ops.*

| Condition | Owner | Due Date | How AI Ops Will Verify |
|---|---|---|---|
| ClaimAssist delivers urgency tier calibration update addressing wind damage claim pattern | Jordan Kim (AI Ops) + ClaimAssist Account Team | 2026-04-25 | AI Ops runs validation set of 50 held-out wind damage claims against updated model. Override rate on this set must be below 20%. |
| Adjuster routing table synced between ClaimsMgr and TriageAI — all Region 4 adjusters current | Dana Reyes (Claims Ops) | 2026-04-20 | AI Ops spot-checks 10 routing assignments against current ClaimsMgr adjuster list. All 10 must match. |

---

## Recommended Next Steps

| Action | Owner | Target Date |
|---|---|---|
| Issue calibration task to ClaimAssist in writing | Jordan Kim | 2026-04-11 |
| Adjuster routing table sync complete | Dana Reyes | 2026-04-20 |
| Urgency tier calibration validated by AI Ops | Jordan Kim | 2026-04-28 |
| Both conditions confirmed — production approval issued | Jordan Kim | 2026-04-29 |
| Region 4 production deployment — full standard FNOL volume | Dana Reyes + Jordan Kim | 2026-05-05 |
| Adoption scorecard activated in observability dashboard | Jordan Kim | 2026-05-05 |
| 30-day post-deployment review | Jordan Kim + Dana Reyes | 2026-06-05 |
| Evaluate Region 5 expansion feasibility (if Region 4 post-deployment review is positive) | Jordan Kim | Q3 2026 |

---

## Sign-Offs

| Role | Name | Date |
|---|---|---|
| AI Ops Lead | Jordan Kim | 2026-04-09 |
| Business Owner | Dana Reyes | 2026-04-10 |
| Executive Sponsor | Michael Tran | 2026-04-10 |

---

*AI Use Case Registry updated: 2026-04-10*
*Status: Conditional Go — Pending Conditions*
*Condition tracker: UC-2026-011-conditions*

---

*Template version 1.3 — AI Workflow Operations — Michael Bassett*
