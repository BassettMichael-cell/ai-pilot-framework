# Go / No-Go Decision Memo

**Template version:** 1.3
**Use Case ID:** `[Insert]`
**Use Case Name:** `[Insert]`
**Memo date:** `YYYY-MM-DD`
**Prepared by:** `[Name, Title]`
**Distribution:** `[List recipients]`

---

## Decision

> **[ ] GO** — Recommend production deployment as described in the next steps section
> **[ ] NO-GO** — Do not proceed to production. Rationale and re-submission path documented below.
> **[ ] CONDITIONAL GO** — Proceed to production only after all conditions in this memo are verified as complete.

---

## Use Case Summary

**What this AI does:**
> [1–2 sentences. Describe the operational function. What does the AI do, and where does it fit in the workflow?]

**Pilot scope:**
> [Team, record type, volume, time period, systems involved.]

**Pilot dates:**
Start: `__________` End: `__________` Duration: `__________`

**Risk tier:** `[ ] 1  [ ] 2  [ ] 3  [ ] 4`

---

## Evidence Summary

### Performance vs Baseline

| Metric | Baseline | Pilot | Delta | Assessment |
|---|---|---|---|---|
| Average handle time | | | | Met / Not Met / Exceeded |
| Quality / accuracy rate | | | | Met / Not Met / Exceeded |
| Error rate | | | | Met / Not Met / Exceeded |
| Escalation rate | | | | Met / Not Met / Exceeded |
| Volume processed | | | | — |

### Risk Metrics

| Metric | Pilot Result | Threshold | Status |
|---|---|---|---|
| Override rate | | 25% max | Within Bounds / Exceeded |
| Error delta vs baseline | | +5 pts max | Within Bounds / Exceeded |
| Escalation delta | | +10 pts max | Within Bounds / Exceeded |
| User-reported issues | | 3/week max | Within Bounds / Exceeded |
| Model failure rate | | 2% max | Within Bounds / Exceeded |

### ROI Estimate

| Metric | Estimate | Basis |
|---|---|---|
| Time saved per unit | | Measured AHT delta |
| Monthly time saved | | Volume x time saved |
| Estimated monthly cost delta | | Finance model |
| Estimated annual savings | | Monthly x 12 — estimate only |

> *All ROI figures are estimates from a bounded pilot. They are not guaranteed production outcomes.*

---

## Key Findings

*State 3–5 specific, numbered findings that directly support the recommendation. Use the data. Do not use vague language.*

1. [Finding 1 — include numbers. Example: "Average handle time fell from 14.2 to 8.8 minutes, a 38% reduction, exceeding the 10% minimum threshold."]
2. [Finding 2]
3. [Finding 3]
4. [Finding 4 — if applicable]
5. [Finding 5 — if applicable]

---

## Risk Observations

*Document any risks, anomalies, or concerns identified during the pilot. For a Go decision, these become active monitoring items post-deployment.*

| Observation | Severity | Recommended Mitigation |
|---|---|---|
| | Low / Medium / High | |
| | | |

---

## Recommendation Rationale

> [2–4 paragraphs. State why this recommendation was reached. Reference specific data points from the evidence summary. Do not introduce new information here that is not in the evidence tables above.
>
> If Go: state what conditions are required for safe production deployment and what monitoring is expected.
> If No-Go: state precisely what would need to change for a re-submission to succeed.
> If Conditional Go: state each condition clearly, with owner and deadline.]

---

## Conditions *(Conditional Go only)*

*Each condition must have a named owner and a due date. Production deployment does not begin until all conditions are verified by AI Ops.*

| Condition | Owner | Due Date | How AI Ops Will Verify |
|---|---|---|---|
| | | | |
| | | | |

---

## Recommended Next Steps

**If Go or Conditional Go:**

| Action | Owner | Target Date |
|---|---|---|
| Confirm all Conditional Go conditions met (if applicable) | AI Ops Lead | |
| Configure production monitoring and adoption scorecard | AI Ops | |
| Brief production team on oversight responsibilities | Business Owner | |
| Production deployment — defined scope | Business Owner + AI Ops | |
| Schedule 30-day post-deployment review | AI Ops | |

**If No-Go:**

| Action | Owner | Target Date |
|---|---|---|
| Communicate decision and rationale to requestor | AI Ops | |
| Document re-submission conditions in Use Case Registry | AI Ops | |
| Archive all pilot records | AI Ops | |

---

## Sign-Offs

| Role | Name | Date |
|---|---|---|
| AI Ops Lead | | |
| Business Owner | | |
| Executive Sponsor *(Tier 3/4)* | | |
| Legal/Compliance *(Tier 3/4)* | | |

---

*Use Case Registry updated by:* `____________` *on:* `____________`
*Outcome recorded as:* `[ ] Go  [ ] No-Go  [ ] Conditional Go — Pending`

---

*Template version 1.3 — AI Workflow Operations — Michael Bassett*
