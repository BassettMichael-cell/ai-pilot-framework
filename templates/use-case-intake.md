# Use Case Intake Form

**Template version:** 2.1
**Use Case ID:** `[Assigned by AI Ops on receipt — do not fill in]`
**Submission date:** `YYYY-MM-DD`
**Status:** Pending Review

---

## Section 1 — Requestor Information

| Field | Value |
|---|---|
| Business Unit | |
| Requestor Name | |
| Requestor Title | |
| Executive Sponsor | |
| Sponsor Title | |
| Primary Contact Email | |
| Date Submitted | |

---

## Section 2 — Use Case Description

**Problem statement**
*What operational problem or inefficiency are you solving? Be specific. Include volume, frequency, and business impact.*

> [Your answer here]

**Proposed AI solution**
*What tool, model, or capability is being proposed? Name the vendor and product if known.*

> [Your answer here]

**Current process**
*How is this task performed today? Who does it, how long does it take, and how often does it occur?*

> [Your answer here]

**Expected change**
*What will be concretely different if AI is introduced? Avoid vague claims. Specify what changes, by how much, and how you will know.*

> [Your answer here]

---

## Section 3 — Scope Definition

**Pilot scope**
*Define the specific, bounded subset of work that will be included in the pilot.*

> [Example: "Standard FNOL claims received in Region 4 between March 1-28, 2026. Excludes CAT claims, litigated claims, and commercial lines."]

**Volume estimate**

| Metric | Estimated Value |
|---|---|
| Weekly transaction volume (in scope) | |
| Monthly transaction volume (in scope) | |
| Number of users participating in pilot | |
| Number of systems involved | |

**Explicitly excluded from the pilot**

> [List everything that will NOT be tested. Defines clean measurement boundaries.]

---

## Section 4 — Data and Systems

**Data sources the AI will access or process**

| Data Source | Data Type | Contains PII? | Classification |
|---|---|---|---|
| | | Yes / No | Public / Internal / Confidential / Restricted |
| | | Yes / No | |

**Systems the AI will interact with**

| System Name | Access Type | Integration Method |
|---|---|---|
| | Read / Write / Both | API / Direct / Manual |
| | | |

**Data handling notes**

> [Residency requirements, regulatory classification, DPA status if vendor involved, retention schedule.]

---

## Section 5 — Human Oversight Plan

**Who reviews AI outputs before they take effect?**
*Name the role, not the individual.*

> [Example: "Claims Specialist reviews AI-generated triage recommendation before the claim routes."]

**Override mechanism**

> [How can a human reject or modify an AI output? Is this enforced by the system?]

**Escalation path if AI fails or produces unexpected output**

> [Who is notified? What is the response SLA?]

---

## Section 6 — Success Criteria

*Define what success looks like before the pilot begins. These become the Go/No-Go basis. Do not revise after the pilot starts.*

| Metric | Baseline (to be measured) | Minimum Acceptable AI Result | Stretch Goal |
|---|---|---|---|
| Accuracy / quality rate | | No regression vs baseline | |
| Average handle time | | 10% improvement | |
| Override / rejection rate | N/A | 25% or below | 15% or below |
| Error rate | | No increase vs baseline | |
| [Use case specific metric] | | | |

---

## Section 7 — Risk Self-Assessment

*Check all that apply. Full risk classification is completed separately by AI Ops.*

- [ ] Use case involves regulated data (PHI, financial records, legal records, HR records)
- [ ] AI output directly triggers a customer-facing action without human review
- [ ] AI output influences a consequential decision (credit, benefits, safety, compliance)
- [ ] Proposed vendor is not yet in the approved AI vendor registry
- [ ] Integration requires write access to a production system
- [ ] Use case involves any form of customer communication

**Additional concerns:**

> [Optional]

---

## Section 8 — Requestor Sign-Off

| Role | Name | Date |
|---|---|---|
| Requestor | | |
| Executive Sponsor | | |

---

*AI Ops use only:*
Use Case ID: `____________` | Received by: `____________` | Date: `____________`

---

*Template version 2.1 — AI Workflow Operations — Michael Bassett*
