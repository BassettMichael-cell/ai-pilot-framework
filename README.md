# ai-pilot-framework

**Measured AI Implementation Framework**
*AI Workflow Operations — Michael Bassett*

---

## What This Repository Is

This is the operational framework I use to evaluate, pilot, and gate AI use cases before production deployment. It answers one question directly: **how do you implement AI safely and measure whether it actually works?**

The answer is structured gating, baseline-first measurement, and risk-adjusted decision logic. Not vendor benchmarks. Not internal enthusiasm. Documented evidence collected the same way before and after.

Every use case that moves through this framework either earns a production deployment with evidence behind it, or receives a No-Go with a clear rationale and a path to resubmission. Nothing skips the process.

---

## The Pilot Lifecycle

All use cases move through six gates in sequence. No gate is skipped. Each gate produces a signed artifact before the next gate opens.

```
Intake → Risk Classify → Baseline → Pilot → Evaluate → Decision
```

| Gate | Owner | Output Artifact |
|---|---|---|
| Intake | Requestor + AI Ops | Completed intake form, Use Case ID assigned |
| Risk Classify | AI Ops | Risk tier assignment, constraints log |
| Baseline | Operations + AI Ops | Baseline metrics snapshot, signed by Business Owner |
| Pilot | AI Ops + Business Owner | Execution log, weekly monitoring records |
| Evaluate | AI Ops | KPI comparison report |
| Decision | AI Ops Lead + Stakeholders | Go / No-Go / Conditional Go memo |

**Hard rules:**
- Tier 3 or Tier 4 risk classifications require Legal/Compliance written approval before Baseline begins.
- Minimum pilot duration is 2 weeks. Maximum is 90 days without re-authorization.
- Override rate exceeding 25% during a pilot triggers an automatic pause and documented root cause review.
- No metric is introduced after the pilot starts. The KPI table is locked at Baseline.

---

## Repository Structure

```
ai-pilot-framework/
├── README.md
├── templates/
│   ├── use-case-intake.md
│   ├── risk-classification-matrix.md
│   ├── pilot-gating-checklist.md
│   ├── kpi-model.md
│   └── go-no-go-decision.md
└── examples/
    ├── UC-2026-011-intake.md
    ├── UC-2026-011-risk-classification.md
    ├── UC-2026-011-kpi-report.md
    └── UC-2026-011-go-no-go-memo.md
```

The `/templates` folder contains blank, reusable versions of every document in the lifecycle.

The `/examples` folder contains a fully worked pilot evaluation for **Use Case UC-2026-011: Claims Triage AI, Region 4** — a complete end-to-end example from intake through a Conditional Go decision.

---

## KPI Framework Summary

Metrics are organized into four categories. Every category is populated at Baseline before the pilot begins. No category is optional.

| Category | Purpose |
|---|---|
| Baseline Metrics | Establish current-state performance before AI is introduced |
| AI Delta Metrics | Measure change attributable to the AI system |
| Risk Metrics | Track override rate, error rate, escalation frequency, model failure rate |
| ROI Metrics | Quantify time saved, cost delta, and capacity shift |

**Variance thresholds:**

| Signal | Threshold | Response |
|---|---|---|
| Performance improvement | < 10% vs baseline | Flagged in evaluation report |
| Override rate | > 25% | Pilot pause + root cause analysis |
| Error rate increase | > 5 percentage points vs baseline | Same-day escalation to AI Ops Lead |
| Quality rate below baseline | Any regression | Mandatory No-Go consideration |

---

## How to Use This Framework

1. Business owner submits the **Use Case Intake** form.
2. AI Ops completes the **Risk Classification Matrix** and assigns a tier.
3. AI Ops and Business Owner agree on KPIs before baseline collection begins.
4. Baseline data is collected for a minimum of two weeks using documented methods.
5. Pilot runs in the defined, bounded scope. AI Ops monitors weekly.
6. AI Ops completes the **KPI Comparison Report** at the Evaluate gate.
7. AI Ops issues the **Go/No-Go Decision Memo** with an explicit recommendation.

---

## Governance Notes

- All use cases are assigned a Use Case ID and tracked in the central AI Use Case Registry.
- Pilot records are retained for a minimum of 12 months regardless of decision outcome.
- No-Go decisions include documented rationale and re-submission conditions.
- Tier 3 and Tier 4 decisions require executive sponsor sign-off at the Decision gate.
- This framework version-controls all templates. Each document includes a version number. Outdated template versions are not accepted at gate reviews.

---

*Maintained by Michael Bassett — AI Workflow Operations*
*Last updated: Q1 2026*
