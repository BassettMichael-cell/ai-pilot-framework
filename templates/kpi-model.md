# KPI Model — AI Pilot Measurement Framework

**Template version:** 1.6
**Applies to:** All AI pilots in this framework

---

## Measurement Principles

Before using this template, confirm the following:

1. Every metric listed below is populated at **Baseline** before the pilot begins. No exceptions.
2. The same measurement method used at Baseline is used during the Pilot. If the method changes, the comparison is invalid and the gate will not pass.
3. No new metrics are added after the pilot starts. The KPI table is locked at the Baseline gate.
4. ROI figures from a pilot are **estimates**. They come from a bounded scope and a controlled time window. They are not guaranteed production outcomes. Label them as estimates everywhere.

---

## Category 1 — Baseline Metrics

*Establish current-state performance. These are the denominator for all delta calculations.*

| Metric | Definition | Unit | How to Measure | Frequency |
|---|---|---|---|---|
| Task volume | Total units processed per period | Count / week | System report or manual log | Weekly |
| Average handle time (AHT) | Mean time to complete one task unit from start to finish | Minutes | Time-tracking system or structured log | Weekly |
| Quality / accuracy rate | Percentage of outputs that meet the defined quality standard | % | QA sample audit or error log review | Weekly |
| Error rate | Percentage of outputs that required correction or rework | % | Error log or rework tracker | Weekly |
| Escalation rate | Percentage of tasks escalated to a senior reviewer or manager | % | Escalation log | Weekly |
| Staff hours per 100 units | FTE hours consumed to process 100 units of output | Hours | Time-tracking system | Monthly |
| Cost per unit | Fully-loaded cost to complete one task unit | $ | Finance capacity model | Monthly |

---

## Category 2 — AI Delta Metrics

*Measure change attributable to the AI. Each metric maps directly to a baseline metric.*

| Metric | Definition | Unit | Minimum Threshold to Pass |
|---|---|---|---|
| AI-assisted AHT | Mean time to complete task with AI in the loop | Minutes | At least 10% improvement vs baseline AHT |
| AI accuracy rate | Percentage of AI-assisted outputs meeting quality standard | % | Must not fall below baseline accuracy rate |
| AI error rate | Percentage of AI-assisted outputs requiring correction | % | Must not exceed baseline error rate |
| AI escalation rate | Percentage of AI-assisted tasks escalated | % | Must not exceed baseline escalation rate by more than 10 percentage points |
| AI-assisted volume | Total units processed during the pilot period | Count | Track for throughput signal — no pass/fail threshold |

---

## Category 3 — Risk Metrics

*Detect signals that the AI may be underperforming, creating operational risk, or requiring recalibration.*

| Metric | Definition | Alert Threshold | Response if Threshold Exceeded |
|---|---|---|---|
| Override rate | Percentage of AI outputs rejected or manually corrected by a human reviewer | **> 25%** | **Pilot pause.** Root cause analysis required within 3 business days before pilot may resume. |
| Error delta | Change in error rate compared to baseline, measured in percentage points | **> +5 pts** | **Same-day escalation** to AI Ops Lead. Evaluate pilot pause. |
| Escalation delta | Change in escalation rate compared to baseline | **> +10 pts** | Business Owner notified within 24 hours. Weekly review required. |
| User-reported issues | Count of issues flagged directly by pilot users, per week | **> 3/week** (rolling average) | Weekly review meeting with Business Owner. Log and categorize every issue. |
| Model failure rate | Percentage of AI requests that return an error, null output, or timeout | **> 2%** | AI Ops technical review within 48 hours. Evaluate pilot pause if rate is sustained. |

---

## Category 4 — ROI Metrics

*Quantify the business value case for a Go decision. Complete this section at the Evaluate gate.*

| Metric | Definition | Unit | How to Calculate |
|---|---|---|---|
| Time saved per unit | Baseline AHT minus AI-assisted AHT | Minutes / unit | Direct subtraction from AHT comparison |
| Total monthly time saved | Time saved per unit multiplied by monthly AI-assisted volume | Hours / month | Calculation |
| Staff hours reallocated | FTE hours freed from AI-assisted tasks | Hours / month | Total time saved expressed in FTE hours |
| Cost delta per unit | Baseline cost per unit minus AI-assisted cost per unit | $ / unit | Finance model input |
| Total monthly cost delta | Cost delta per unit multiplied by monthly volume | $ / month | Calculation |
| Estimated annual savings | Total monthly cost delta multiplied by 12 | $ / year | **Projection — label as estimate in all documents** |
| Capacity gain | Percentage of total FTE capacity freed within pilot team | % | Staff hours reallocated divided by total available FTE hours |

> **Required caveat in every report that includes ROI figures:**
> *"ROI figures are estimates derived from a bounded pilot. They reflect the pilot scope, time window, and team composition. They are not guaranteed production performance. All projections are estimates pending a 90-day post-deployment review."*

---

## KPI Tracking Table — Blank

*Populate the Baseline column before the pilot begins. Populate the Pilot column at the Evaluate gate.*

| Metric | Category | Baseline Value | Pilot Value | Delta | Threshold | Flag? |
|---|---|---|---|---|---|---|
| Weekly volume | Baseline | | | | — | — |
| Average handle time | Baseline | | | | — | — |
| Quality / accuracy rate | Baseline | | | | — | — |
| Error rate | Baseline | | | | — | — |
| Escalation rate | Baseline | | | | — | — |
| Staff hrs / 100 units | Baseline | | | | — | — |
| Override rate | Risk | N/A | | — | 25% max | Yes / No |
| Error delta | Risk | N/A | | | +5 pts max | Yes / No |
| Escalation delta | Risk | N/A | | | +10 pts max | Yes / No |
| User-reported issues | Risk | N/A | | | 3/wk max | Yes / No |
| Model failure rate | Risk | N/A | | | 2% max | Yes / No |
| Time saved per unit | ROI | N/A | | | — | — |
| Total monthly time saved | ROI | N/A | | | — | — |
| Estimated monthly cost delta | ROI | N/A | | | — | — |

---

## Variance Threshold Quick Reference

| Metric | Threshold | If Exceeded |
|---|---|---|
| AHT improvement | Less than 10% improvement | Flag in evaluation report |
| Override rate | Above 25% | Pilot pause + root cause analysis |
| Error rate increase | More than 5 percentage points above baseline | Same-day AI Ops Lead escalation |
| Escalation rate increase | More than 10 percentage points above baseline | 24-hour Business Owner notification |
| Quality rate below baseline | Any regression | Mandatory consideration in No-Go logic |
| Model failure rate | Above 2% | Technical review, evaluate pause |

---

*Template version 1.6 — AI Workflow Operations — Michael Bassett*
