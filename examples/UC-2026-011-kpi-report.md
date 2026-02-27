# KPI Comparison Report — Claims Triage AI, Region 4

**Document type:** Pilot KPI Evaluation Report
**Use Case ID:** `UC-2026-011`
**Report date:** `2026-04-07`
**Prepared by:** Jordan Kim, AI Workflow Operations
**Pilot period:** March 2 – March 28, 2026 (4 weeks)
**Baseline period:** January 6 – February 28, 2026 (8 weeks)

---

## Executive Summary

The 4-week pilot of ClaimAssist TriageAI v2.3 in Region 4 produced measurable improvements across every primary performance metric compared to the 8-week baseline. Average handle time fell 38%, triage accuracy improved by 1.3 percentage points, and the error rate declined slightly. No metric regressed. The override rate of 17.2% is within the 25% threshold, though the pattern of overrides reveals a specific calibration gap in urgency tier assignment on wind damage claims.

Two issues require resolution before production deployment. Both are correctable within a defined timeframe. Recommendation: Conditional Go. See the decision memo (UC-2026-011-go-no-go-memo.md) for the full recommendation.

---

## Measurement Methodology

**Baseline (January 6 – February 28, 2026)**
- Team: Same 4 specialists who participated in the pilot (Region 4)
- Volume: 847 standard FNOL claims over 8 weeks
- AHT measurement: ClaimsMgr time-tracking field — time from claim open to specialist submission
- Accuracy measurement: QA audit sample — 120 claims reviewed by QA Lead using the standard triage accuracy rubric
- Error measurement: ClaimsMgr rework log — claims returned to triage queue with error flag
- Escalation measurement: ClaimsMgr escalation log

**Pilot (March 2 – March 28, 2026)**
- Same 4 specialists. Same measurement methods. Same systems.
- Volume: 394 standard FNOL claims (in-scope per pilot definition)
- QA audit sample: 80 claims reviewed by same QA Lead using the same rubric
- Override measurement: ClaimAssist TriageAI override log (system-generated)

**Volume note:** Pilot volume (98.5/week) is lower than baseline (105.9/week). This reflects the scope exclusions defined in the intake form — CAT claims, litigated claims, and commercial lines were excluded from the pilot but present in the baseline period. This is expected and does not affect the validity of the comparison. Per-claim metrics (AHT, accuracy rate, error rate) are not volume-dependent.

---

## Category 1 — Baseline vs Pilot Performance

| Metric | Baseline (8-wk avg) | Pilot (4-wk) | Delta | Assessment |
|---|---|---|---|---|
| Weekly claims processed | 105.9 / week | 98.5 / week | -7.0% | Expected — scope exclusions applied |
| Average handle time (AHT) | 14.2 min | 8.8 min | **-38.0%** | Exceeded stretch goal (9.0 min target) |
| Triage accuracy rate | 93.5% | 94.8% | **+1.3 pts** | Exceeded — no regression, slight improvement |
| Incorrect routing (error) rate | 2.1% | 1.8% | **-0.3 pts** | Exceeded — error rate declined |
| Escalation rate | 5.4% | 6.1% | +0.7 pts | Met — within +10 pt threshold |
| Staff hours per 100 claims | 23.7 hrs | 14.7 hrs | **-38.0%** | Consistent with AHT reduction |

---

## Category 2 — AI Delta vs Minimum Thresholds

| Metric | Minimum Threshold | Pilot Result | Threshold Met? |
|---|---|---|---|
| AHT improvement | 10% or more | 38.0% improvement | Yes — exceeded |
| Triage accuracy | No regression below 93.5% | 94.8% | Yes — exceeded |
| Error rate | No increase above 2.1% | 1.8% | Yes — declined |
| Escalation rate | No increase above 15.4% (baseline + 10 pts) | 6.1% | Yes — within bounds |

All four minimum thresholds met. Three exceeded.

---

## Category 3 — Risk Metrics

| Metric | Pilot Result | Threshold | Status | Notes |
|---|---|---|---|---|
| Override rate | **17.2%** (68 of 394 claims) | 25% max | Within bounds | Pattern analysis below — calibration issue identified |
| Error delta vs baseline | -0.3 pts | +5 pts max | Within bounds | No escalation required |
| Escalation delta | +0.7 pts | +10 pts max | Within bounds | Monitoring recommended post-deployment |
| User-reported issues | 0.75 / week avg (3 total) | 3 / week max | Within bounds | All 3 issues logged and resolved — see below |
| Model failure / timeout rate | 0.5% (2 of 394 requests) | 2% max | Within bounds | Both occurred Days 1–2 (config issue, resolved March 4) |

### Override Pattern Analysis

68 overrides across 394 claims. AI Ops reviewed override log with QA Lead to identify patterns.

| Override Type | Count | % of Overrides | Pattern Assessment |
|---|---|---|---|
| Urgency tier adjusted (AI: Tier 2 → Specialist: Tier 1) | 31 | 45.6% | Consistent pattern — AI is over-tiering standard wind damage claims. Calibration issue, not random error. |
| Claim category adjusted | 22 | 32.4% | Primarily water damage vs storm damage boundary cases. Category overlap issue in taxonomy. |
| Routing destination adjusted | 12 | 17.6% | Adjuster table in TriageAI is not synced with current ClaimsMgr adjuster assignments. Data issue, not model issue. |
| Other | 3 | 4.4% | One-off cases, no pattern identified. |

**Finding:** 45.6% of overrides follow the same pattern — urgency tier on wind damage claims. This is a model calibration gap, not random noise. ClaimAssist has been notified. The routing overrides are a data sync issue that is straightforward to resolve. Neither issue is a blocker to production if resolved before go-live.

### User-Reported Issues

| Issue # | Description | Resolution |
|---|---|---|
| 1 | UI display bug — confidence score not rendering on some claims | Resolved March 6 by ClaimAssist — v2.3.1 patch deployed |
| 2 | Low-confidence flag on legitimate claim — specialist confused about next step | Process clarification sent to all 4 specialists March 10 |
| 3 | Category taxonomy question — specialist unsure which category applies to a dual-peril claim | Escalated to QA Lead — guidance added to the triage reference guide March 14 |

---

## Category 4 — ROI Estimate

*All figures are estimates from a bounded 4-week pilot. Not guaranteed production outcomes.*

| Metric | Calculation | Estimate |
|---|---|---|
| Time saved per claim | 14.2 – 8.8 min | **5.4 minutes / claim** |
| Monthly claims (Region 4, production estimate) | ~440 claims / month (in-scope types only) | — |
| Total monthly time saved | 440 × 5.4 min | **~39.6 hours / month** |
| FTE equivalent | 39.6 hrs ÷ 160 hrs/FTE | **~0.25 FTE / month** |
| Loaded cost per specialist hour | $47.50 (HR-provided rate, Q1 2026) | — |
| Estimated monthly cost delta | 39.6 hrs × $47.50 | **~$1,881 / month** |
| Estimated annual savings — Region 4 | $1,881 × 12 | **~$22,572 / year (estimate)** |

**Capacity note:** The 0.25 FTE freed per month does not automatically translate to a headcount reduction. At current Region 4 volume, this represents capacity available for backlog clearance during high-volume periods, complex claim support, or QA review work. It is not an immediate savings realization.

---

## Flags and Open Items

| Item | Severity | Status | Recommended Action |
|---|---|---|---|
| Urgency tier over-tiering on wind damage claims | Medium | Open | ClaimAssist calibration update required before production deployment |
| Adjuster routing table not synced between ClaimsMgr and TriageAI | Low | Open | Data sync required before production deployment |
| Escalation rate marginal increase (+0.7 pts) | Low | Monitoring | Track for 30 days post-deployment — no action needed now |

---

## Conclusion

The pilot met or exceeded every minimum performance threshold. No metric regressed. The override rate and risk metrics are within acceptable bounds. Two specific, correctable issues were identified through override pattern analysis — a model calibration gap and a data sync issue. Neither reflects a fundamental problem with the use case or the vendor. Both have defined resolution paths and a short resolution timeline.

This report supports a Conditional Go recommendation pending resolution of the two open items. See the decision memo for conditions, owners, and verification method.

---

*Report prepared by Jordan Kim, AI Workflow Operations*
*Reviewed by: Michael Bassett — 2026-04-07*

---

*Template version 1.6 — AI Workflow Operations — Michael Bassett*
