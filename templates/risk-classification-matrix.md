# Risk Classification Matrix

**Template version:** 1.4
**Completed by:** AI Ops (not the requestor)
**Use Case ID:** `[Insert]`

---

## Purpose

This matrix scores the risk level of a submitted AI use case. The total score determines the risk tier, which controls: required reviews before any work begins, pilot constraints, oversight levels, and decision authority at the Go/No-Go gate.

---

## Tier Definitions

| Tier | Label | Core Characteristic | Decision Authority |
|---|---|---|---|
| **1** | Low | Advisory or read-only AI output. No regulated data. Human reviews all outputs before any action is taken. | AI Ops Lead |
| **2** | Moderate | AI assists operational tasks. May involve internal PII. Human-in-the-loop required. Customer impact is indirect. | AI Ops Lead + Business Owner |
| **3** | Elevated | AI output influences a consequential decision or customer-facing record. Regulated data likely. Legal/Compliance review required before pilot. | AI Ops Lead + Legal/Compliance + Exec Sponsor |
| **4** | High | AI output directly triggers consequential action. Sensitive regulated data. Material compliance exposure possible. Full governance review required before any pilot activity. | AI Governance Committee |

---

## Scoring Instructions

Score each of the five dimensions from 1 to 4. Sum all five scores. Use the total to assign the tier.

---

### Dimension 1 — Output Consequence

*What is the operational impact if the AI output is wrong?*

| Score | Criteria |
|---|---|
| 1 | Output is reviewed by a human before any action is taken. An error has low operational impact and is caught before it affects anything. |
| 2 | Output influences a human decision but does not trigger action directly. Moderate rework cost if wrong. |
| 3 | Output directly affects a customer record, routing decision, or communication. |
| 4 | Output directly triggers a transaction, decision, or action with no mandatory human review step before it takes effect. |

**Score:** `[ ]`

---

### Dimension 2 — Data Sensitivity

*What data does the AI access, process, or produce?*

| Score | Criteria |
|---|---|
| 1 | Internal, non-sensitive operational data only. No PII of any kind. |
| 2 | Internal PII — employee records, internal contact data, workforce information. |
| 3 | Customer PII. Non-regulated financial or health-adjacent data. |
| 4 | Regulated data: PHI, HIPAA-covered, FINRA-covered, PCI, GDPR-subject, legal hold files, HR investigation records. |

**Score:** `[ ]`

---

### Dimension 3 — Scope of Impact

*How broadly are people or processes affected if the AI makes an error or fails?*

| Score | Criteria |
|---|---|
| 1 | Single team or isolated process. Contained failure surface. |
| 2 | Multiple teams or a regional operation. |
| 3 | A product line, a defined customer segment, or a business-critical operational workflow. |
| 4 | Enterprise-wide exposure or impact across the full customer base. |

**Score:** `[ ]`

---

### Dimension 4 — Reversibility

*Can errors be identified and corrected without material harm?*

| Score | Criteria |
|---|---|
| 1 | Fully reversible. No downstream consequences. An error can be corrected with no lasting impact. |
| 2 | Reversible with moderate effort. Some rework required, but no external notifications needed. |
| 3 | Partially reversible. Correction may require customer notification or a regulatory disclosure. |
| 4 | Difficult or impossible to reverse. Legal, financial, or reputational consequences if wrong. |

**Score:** `[ ]`

---

### Dimension 5 — Vendor and Model Maturity

*How well-validated is this AI system in production environments comparable to ours?*

| Score | Criteria |
|---|---|
| 1 | Approved vendor. Model is production-validated in comparable use cases. Internal team has operational experience with this system. |
| 2 | Approved vendor. Limited production history in this specific use case type. Team is learning the system. |
| 3 | Approved vendor using a new capability or model version not previously deployed here. Or: unapproved vendor currently under evaluation. |
| 4 | Unapproved vendor. Novel model with no internal production history. No comparable deployment data available. |

**Score:** `[ ]`

---

## Tier Assignment

| Total Score | Assigned Tier |
|---|---|
| 5 – 7 | **Tier 1 — Low** |
| 8 – 11 | **Tier 2 — Moderate** |
| 12 – 16 | **Tier 3 — Elevated** |
| 17 – 20 | **Tier 4 — High** |

**Total score:** `[ ]`
**Assigned tier:** `[ ]`

---

## Requirements Triggered by Tier

| Requirement | Tier 1 | Tier 2 | Tier 3 | Tier 4 |
|---|---|---|---|---|
| Standard intake + AI Ops review | Required | Required | Required | Required |
| Business Owner co-sign on intake | — | Required | Required | Required |
| Legal/Compliance written approval before Baseline | — | — | Required | Required |
| Executive Sponsor sign-off at Decision gate | — | — | Required | Required |
| Security assessment before pilot | — | — | — | Required |
| AI Governance Committee approval before any work | — | — | — | Required |
| Weekly risk review during pilot | — | — | Required | Required |
| Maximum pilot duration without re-authorization | 90 days | 90 days | 45 days | 30 days |

---

## Constraints Log

*Document any constraints that apply to this use case beyond the standard tier requirements.*

| Constraint | Source | Owner | Due Date |
|---|---|---|---|
| | Legal / Compliance / Security / AI Ops | | |
| | | | |

---

## Classification Record

| Field | Value |
|---|---|
| Use Case ID | |
| Use Case Name | |
| Classified by | |
| Classification date | |
| Dimension scores (D1/D2/D3/D4/D5) | |
| Total score | |
| Assigned tier | |
| Constraints applied | |
| AI Ops reviewer sign-off | |
| Date | |

---

*Template version 1.4 — AI Workflow Operations — Michael Bassett*
