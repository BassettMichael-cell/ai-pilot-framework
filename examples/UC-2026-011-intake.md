# Use Case Intake Form — Completed

**Template version:** 2.1
**Use Case ID:** `UC-2026-011`
**Submission date:** `2026-01-08`
**Status:** Approved — Routed to Risk Classification

---

## Section 1 — Requestor Information

| Field | Value |
|---|---|
| Business Unit | Claims Operations — Regional Processing |
| Requestor Name | Dana Reyes |
| Requestor Title | Claims Operations Manager |
| Executive Sponsor | Michael Tran |
| Sponsor Title | VP, Claims Operations |
| Primary Contact Email | d.reyes@company.com |
| Date Submitted | 2026-01-08 |

---

## Section 2 — Use Case Description

**Problem statement**

Claims specialists in Regional Processing manually triage all incoming first-notice-of-loss (FNOL) claims before they are routed to an adjuster. Each triage review requires reading the customer narrative, selecting a claim category from a 14-item taxonomy, assigning an urgency tier (1–3), and routing to the correct adjuster queue. The team currently handles between 280 and 340 claims per week. Average triage time is 14.2 minutes per claim. During high-volume periods — post-storm events and Q4 — the team regularly builds a 2–3 day backlog. This backlog delays first customer contact and increases complaint rates tracked in the QA reporting dashboard.

**Proposed AI solution**

Deploy ClaimAssist TriageAI v2.3 to pre-populate the claim category, urgency tier, and routing destination fields before the specialist opens each claim. ClaimAssist is an approved vendor on the company AI Vendor Registry. The specialist reviews the pre-populated recommendation and confirms or adjusts before the claim routes. The AI does not route anything without explicit specialist confirmation.

**Current process**

1. FNOL claim is logged in ClaimsMgr by an intake CSR via web portal or phone.
2. Claim enters the triage queue assigned to the specialist team.
3. Specialist opens the claim record and reads the customer narrative and loss details.
4. Specialist manually selects claim category, urgency tier, and routing destination.
5. Claim is submitted to the adjuster queue.
6. Current average time: 14.2 minutes per claim based on Q4 2025 ClaimsMgr time-tracking data.

**Expected change**

AI pre-populates all three fields before the specialist opens the claim. The specialist reads the narrative, reviews the pre-populated values, and either confirms or adjusts. Based on ClaimAssist vendor benchmarks from comparable deployments, expected time reduction is 5–7 minutes per claim. We will measure this independently in the pilot and will not cite vendor benchmarks as the basis for any Go decision.

---

## Section 3 — Scope Definition

**Pilot scope**

Standard FNOL claims (non-catastrophe, non-litigated, non-commercial lines) received in Region 4 (Oklahoma and Kansas) between March 2 and March 28, 2026. Estimated 80–110 claims per week.

**Volume estimate**

| Metric | Estimated Value |
|---|---|
| Weekly transaction volume (in scope) | 80–110 claims |
| Monthly transaction volume (in scope) | 320–440 claims |
| Number of users participating in pilot | 4 Claims Specialists |
| Number of systems involved | 2 (ClaimsMgr, ClaimAssist TriageAI) |

**Explicitly excluded from the pilot**

- Claims with an active CAT flag (catastrophe designation)
- Litigated or attorney-represented claims
- Commercial lines claims
- Claims submitted via the legacy fax intake process
- Any claim received outside the March 2–28 window, even if in Region 4

---

## Section 4 — Data and Systems

**Data sources the AI will access or process**

| Data Source | Data Type | Contains PII? | Classification |
|---|---|---|---|
| FNOL customer narrative (free text) | Unstructured | Yes — name, address, event description | Confidential |
| Claim metadata (type, date of loss, location code) | Structured | Yes — address fields | Confidential |
| ClaimsMgr claim record | Structured | Yes | Confidential |

**Systems the AI will interact with**

| System Name | Access Type | Integration Method |
|---|---|---|
| ClaimsMgr | Read and Write | API — ClaimAssist certified integration, version 4.1 |
| ClaimAssist TriageAI | Read and Write (API call and response) | SaaS — vendor-hosted, US infrastructure only |

**Data handling notes**

ClaimAssist is on the approved AI Vendor Registry. A current Data Processing Agreement is in place, reviewed by Legal in November 2025. Customer PII is not retained by ClaimAssist beyond the active session per DPA Section 4.2. All data processing occurs within US infrastructure. Retention schedule for pilot records: 12 months per AI Ops policy OP-07.

---

## Section 5 — Human Oversight Plan

**Who reviews AI outputs before they take effect?**

The Claims Specialist reviews every AI-generated recommendation within ClaimsMgr before any action is taken. The AI populates the claim category, urgency tier, and routing destination fields in a review panel. The specialist must click Confirm or manually edit the fields before the claim routes to an adjuster queue. The AI cannot route a claim without specialist action.

**Override mechanism**

All three AI-populated fields are editable by the specialist at any time before submission. If the specialist changes an AI-populated value, ClaimsMgr logs an override event capturing: original AI value, specialist-entered value, specialist ID, and timestamp. Override logging is system-enforced and auditable.

**Escalation path if AI fails or produces unexpected output**

If ClaimAssist returns an error or a confidence score below the configured threshold, the claim is flagged in the queue with status "AI Review Needed" and remains unrouted until the specialist triages it manually. Systemic issues escalate as follows: Claims Ops Manager (Dana Reyes) → AI Ops on-call (ai-ops@company.com, SLA 4 hours) → ClaimAssist Support (SLA 4 hours per contract).

---

## Section 6 — Success Criteria

| Metric | Baseline (to be measured) | Minimum Acceptable AI Result | Stretch Goal |
|---|---|---|---|
| Average handle time | To be measured in baseline period | 12.0 minutes or below | 9.0 minutes or below |
| Triage accuracy rate | To be measured via QA audit in baseline period | No regression below baseline | 95.0% or above |
| Override / rejection rate | N/A (new metric) | 25% or below | 15% or below |
| Incorrect routing (error) rate | To be measured in baseline period | No increase above baseline | 1.5% or below |
| Specialist satisfaction | N/A | Neutral or positive on end-of-pilot survey | — |

---

## Section 7 — Risk Self-Assessment

- [x] Use case involves regulated data — customer PII (names, addresses, loss details)
- [ ] AI output directly triggers a customer-facing action without human review — *No. Specialist confirms before routing.*
- [ ] AI output influences a consequential decision (credit, benefits, safety, compliance) — *No. Internal routing only.*
- [ ] Proposed vendor is not yet in the approved AI vendor registry — *No. ClaimAssist is approved.*
- [ ] Integration requires write access to a production system — *Write is to routing and category fields in ClaimsMgr. Specialist-confirmed only.*
- [ ] Use case involves any form of customer communication — *No. Internal routing only.*

**Additional concerns:**

Customer PII is processed by the vendor. DPA is current. Legal reviewed in November 2025 — no new concerns identified at that time. No additional flags.

---

## Section 8 — Requestor Sign-Off

| Role | Name | Date |
|---|---|---|
| Requestor | Dana Reyes | 2026-01-08 |
| Executive Sponsor | Michael Tran | 2026-01-09 |

---

*AI Ops use only:*
Use Case ID: `UC-2026-011` | Received by: `Jordan Kim` | Date: `2026-01-10`
Routed to Risk Classification: `2026-01-10`

---

*Template version 2.1 — AI Workflow Operations — Michael Bassett*
