# Risk Classification Matrix — Completed

**Template version:** 1.4
**Use Case ID:** `UC-2026-011`
**Use Case Name:** Claims Triage AI — Region 4
**Classified by:** Jordan Kim, AI Workflow Operations
**Classification date:** 2026-01-13

---

## Scoring

### Dimension 1 — Output Consequence

**Score selected: 2**

Rationale: The AI pre-populates three fields (category, urgency tier, routing destination). The specialist reviews these before submitting. The AI output does not take any action without specialist confirmation. An incorrect AI recommendation that the specialist accepts would result in a misrouted claim — moderate rework, no customer-facing consequence before it is caught in the adjuster queue. The specialist is explicitly in the loop for every claim.

---

### Dimension 2 — Data Sensitivity

**Score selected: 3**

Rationale: The AI processes customer PII — names, addresses, and narrative descriptions of loss events. This is customer PII. The data is not regulated under HIPAA, FINRA, or PCI, but it is customer-identifiable and classified as Confidential under the data classification policy. A current DPA is in place with ClaimAssist.

---

### Dimension 3 — Scope of Impact

**Score selected: 2**

Rationale: The pilot is scoped to Region 4 (Oklahoma and Kansas), a single regional operation. Failure or poor performance would affect a regional claims queue, not a product line or the full customer base. The pilot involves 4 specialists and 80–110 claims per week.

---

### Dimension 4 — Reversibility

**Score selected: 2**

Rationale: Routing errors are correctable. If a claim is misrouted, the adjuster can return it to the correct queue. This creates rework but does not require customer notification or regulatory disclosure. Override logging provides a full audit trail.

---

### Dimension 5 — Vendor and Model Maturity

**Score selected: 2**

Rationale: ClaimAssist is an approved vendor on the AI Vendor Registry. TriageAI v2.3 is a production-deployed product. However, the company has not previously deployed ClaimAssist for FNOL triage specifically — this is the first internal use case of this type. The team is learning the system. Score 2 reflects approved vendor with limited internal production history for this specific use case.

---

## Tier Assignment

| Dimension | Score |
|---|---|
| D1 — Output Consequence | 2 |
| D2 — Data Sensitivity | 3 |
| D3 — Scope of Impact | 2 |
| D4 — Reversibility | 2 |
| D5 — Vendor Maturity | 2 |
| **Total** | **11** |

**Assigned tier: Tier 2 — Moderate**

Score 11 falls within the Tier 2 range (8–11).

---

## Requirements Triggered

| Requirement | Required? | Status |
|---|---|---|
| Standard intake + AI Ops review | Yes | Complete — UC-2026-011 intake reviewed 2026-01-10 |
| Business Owner co-sign on intake | Yes (Tier 2) | Complete — Michael Tran signed 2026-01-09 |
| Legal/Compliance written approval before Baseline | No (Tier 3/4 only) | Not required |
| Security assessment | No (Tier 4 only) | Not required |
| Weekly risk review during pilot | No (Tier 3/4 standard — optional for Tier 2) | Recommended given customer PII involvement — added to pilot plan |

---

## Constraints Log

| Constraint | Source | Owner | Notes |
|---|---|---|---|
| Customer PII processed by external vendor — DPA must be current at time of pilot launch | AI Ops / Legal | Jordan Kim | DPA reviewed November 2025. Confirm still current before March 2 pilot start. |
| Override logging must be system-enforced, not manual | AI Ops | Jordan Kim | Confirmed with ClaimAssist integration team 2026-01-13. Override logging is automatic in v2.3. |

---

## Classification Record

| Field | Value |
|---|---|
| Use Case ID | UC-2026-011 |
| Use Case Name | Claims Triage AI — Region 4 |
| Classified by | Jordan Kim |
| Classification date | 2026-01-13 |
| Dimension scores (D1/D2/D3/D4/D5) | 2 / 3 / 2 / 2 / 2 |
| Total score | 11 |
| Assigned tier | Tier 2 — Moderate |
| Constraints applied | 2 — see constraints log above |
| AI Ops reviewer sign-off | Jordan Kim |
| Date | 2026-01-13 |

---

*Approved to proceed to Baseline gate.*
*AI Use Case Registry updated: 2026-01-13*

---

*Template version 1.4 — AI Workflow Operations — Michael Bassett*
