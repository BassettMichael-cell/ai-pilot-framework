# Pilot Gating Checklist

**Template version:** 2.0
**Use Case ID:** `[Insert]`
**Use Case Name:** `[Insert]`
**AI Ops Owner:** `[Insert]`
**Risk Tier:** `[ ] 1  [ ] 2  [ ] 3  [ ] 4`

---

## Instructions

Complete each gate in sequence. Every item must be checked before moving to the next gate.

If a gate item cannot be completed, document the blocker in writing and escalate to AI Ops Lead before proceeding. Do not skip gates. Do not back-fill artifacts after the fact.

---

## Gate 1 — Intake

- [ ] Intake form submitted using current template (v2.1 or later)
- [ ] Use Case ID assigned and logged in AI Use Case Registry
- [ ] Executive Sponsor confirmed in writing
- [ ] AI Ops acknowledgment sent to requestor within 5 business days of submission

**Blocker notes (if any):**
> [Document any delays or issues here before escalating]

**Gate 1 sign-off**
AI Ops Reviewer: `_______________________` Date: `____________`

---

## Gate 2 — Risk Classification

- [ ] Risk Classification Matrix completed using current template (v1.4 or later)
- [ ] All five scoring dimensions documented with rationale
- [ ] Risk tier assigned and recorded
- [ ] Constraints log populated (write "none" if no additional constraints)

**Tier 3 and Tier 4 additional requirements:**
- [ ] Legal/Compliance review formally initiated
- [ ] Legal/Compliance written approval received and filed in pilot record
- [ ] Security review initiated *(Tier 4 only)*
- [ ] AI Governance Committee notified *(Tier 4 only)*
- [ ] AI Governance Committee approval received *(Tier 4 only)*

**Blocker notes (if any):**
> [Document here]

**Gate 2 sign-off**
AI Ops Reviewer: `_______________________` Date: `____________`
Legal/Compliance *(Tier 3/4)*: `_______________________` Date: `____________`

---

## Gate 3 — Baseline

- [ ] Baseline measurement period defined — minimum 2 weeks
- [ ] All KPIs from the intake success criteria table are included in baseline collection
- [ ] Data source documented for every metric (system name, report name, or manual log method)
- [ ] Baseline measurement methodology documented — this same method must be used during the pilot
- [ ] Baseline data stored in the pilot record folder with file path noted here: `____________`
- [ ] Baseline snapshot reviewed and signed by Business Owner

**Baseline measurement period**
Start date: `____________`
End date: `____________`
Total records/transactions captured: `____________`

**Blocker notes (if any):**
> [Document here]

**Gate 3 sign-off**
AI Ops Reviewer: `_______________________` Date: `____________`
Business Owner: `_______________________` Date: `____________`

---

## Gate 4 — Pilot Execution

*Complete before pilot begins:*
- [ ] Pilot scope confirmed in writing — matches intake form exactly
- [ ] Human oversight roles and responsibilities confirmed in writing with pilot team
- [ ] Override mechanism is tested and functional before Day 1
- [ ] Escalation path documented and distributed to all pilot participants
- [ ] Execution logging is active and confirmed
- [ ] Override logging is active and confirmed
- [ ] Error logging is active and confirmed
- [ ] Pilot start date recorded: `____________`
- [ ] Pilot end date defined: `____________`
- [ ] Weekly check-in with Business Owner scheduled — cadence: `____________`

**Scope verification**
Scope as approved in intake: `_____________________________________________`
Scope as actually deployed: `_____________________________________________`
Variance from approved scope: `[ ] None  [ ] Yes — documented below`

> [If variance, describe here and obtain AI Ops Lead approval before proceeding]

**Ongoing during pilot — Tier 2/3/4 weekly checks:**
- [ ] Week 1: Override rate reviewed — value: `____` % — within bounds: `[ ] Yes  [ ] No`
- [ ] Week 2: Override rate reviewed — value: `____` % — within bounds: `[ ] Yes  [ ] No`
- [ ] Week 3: Override rate reviewed — value: `____` % — within bounds: `[ ] Yes  [ ] No`
- [ ] Week 4: Override rate reviewed — value: `____` % — within bounds: `[ ] Yes  [ ] No`
- [ ] Error rate reviewed each week — no escalation trigger fired unresolved: `[ ] Confirmed`

**Blocker notes or mid-pilot issues:**
> [Document any pauses, scope changes, or escalations here]

**Gate 4 sign-off**
AI Ops Reviewer: `_______________________` Date: `____________`
Business Owner: `_______________________` Date: `____________`

---

## Gate 5 — Evaluate

- [ ] KPI Comparison Report completed using current template (v1.6 or later)
- [ ] Every baseline metric compared to pilot metric using the same measurement method
- [ ] Variance threshold logic applied to every metric in the KPI table
- [ ] Override rate calculated and documented
- [ ] Error rate calculated and compared to baseline delta
- [ ] ROI estimate calculated and labeled as estimate
- [ ] User feedback collected and documented (write "not applicable" if not collected)
- [ ] All flags and open items listed in the report
- [ ] Report reviewed and signed by AI Ops Lead

**Evaluation summary (carry over from KPI report)**

| Metric | Baseline | Pilot | Delta | Flagged? |
|---|---|---|---|---|
| Average handle time | | | | Yes / No |
| Quality / accuracy rate | | | | Yes / No |
| Error rate | | | | Yes / No |
| Override rate | N/A | | — | Yes / No |
| Escalation rate | | | | Yes / No |

**Blocker notes (if any):**
> [Document here]

**Gate 5 sign-off**
AI Ops Lead: `_______________________` Date: `____________`

---

## Gate 6 — Decision

- [ ] Go/No-Go Decision Memo completed using current template (v1.3 or later)
- [ ] Recommendation is explicitly stated: Go, No-Go, or Conditional Go
- [ ] If Conditional Go: each condition has a named owner and a due date
- [ ] Decision reviewed by all required stakeholders for this risk tier
- [ ] Decision communicated to requestor and Business Owner in writing
- [ ] Decision logged in AI Use Case Registry with date and outcome

**Final decision:** `[ ] Go   [ ] No-Go   [ ] Conditional Go`

**If Conditional Go — conditions required before production deployment:**

| Condition | Owner | Due Date | How Verified |
|---|---|---|---|
| | | | |
| | | | |

**Blocker notes (if any):**
> [Document here]

**Gate 6 sign-off**
AI Ops Lead: `_______________________` Date: `____________`
Business Owner: `_______________________` Date: `____________`
Executive Sponsor *(Tier 3/4)*: `_______________________` Date: `____________`
Legal/Compliance *(Tier 3/4)*: `_______________________` Date: `____________`

---

*Template version 2.0 — AI Workflow Operations — Michael Bassett*
