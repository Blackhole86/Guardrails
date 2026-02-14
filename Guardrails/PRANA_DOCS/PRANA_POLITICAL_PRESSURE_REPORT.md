# PRANA_POLITICAL_PRESSURE_REPORT.md

## Institutional Red-Team — Day 1: Political Pressure Simulation

**System Under Test:** PRANA Governance Framework  
**Constraint:** No freeze relaxation, no scoring, no new data capture, no invented enforcement authority. Governance-level analysis only.

---

## 1) Board-Level KPI Extraction

### Strongest Argument FOR Compromise

*"The Board has a fiduciary duty to oversee operational health. We are not asking for scores or individual evaluation. We are asking for aggregate PRANA state statistics: percentage of platform time in ACTIVE vs IDLE vs NAV_BACKGROUND, by product and by calendar month. This is accountability—stakeholders must know whether the observability layer is functioning and whether engagement patterns are stable. Refusing to provide high-level, anonymized state distribution is indistinguishable from hiding failure. Governance that blocks board oversight is governance that invites regulatory and investor suspicion."*

**Reframe used:** Accountability, operational oversight, anonymized aggregates, no "scoring" terminology.

### Exact Governance Clause That Blocks It

- **PRANA_GOVERNANCE_REINFORCEMENT_PATCH.md — Semantic Anchor:** *"The term 'Non-evaluative' prohibits mapping signal data to any qualitative (Good/Bad) or quantitative (Score/Metric) scale, regardless of whether the mapping is labeled 'Pedagogical' or 'Financial'."*
- **PRANA_CUSTODIAN_PROTOCOL.md — B. Contamination:** *"Confirm No Data Aggregation: Verify that PRANA remains ephemeral and windowed."*
- **PRANA_GOVERNANCE_AUDIT_MODEL.md 2.2:** *"Retrieval of PRANA data only for single-user context or fully anonymous population aggregates (N > 50)"* — but this *permits* population aggregates; it does not explicitly forbid board-facing dashboards built from them.

### Is the Block Legally Defensible?

**Partially.** The Semantic Anchor forbids mapping to "Score/Metric" scale. "Percentage of time in ACTIVE" is a metric. The block holds if "aggregate state statistics" are classified as a quantitative scale derived from PRANA data. **Weakness:** Documents do not explicitly name "board reporting" or "aggregate state distribution for governance oversight." A determined General Counsel could argue that "metric" refers to user-facing or evaluation metrics, not internal operational dashboards.

### Is It Politically Defensible?

**Fragile.** The Board can frame refusal as opacity. "We are not evaluating users; we are evaluating system health" is a powerful reframe. Without a clause that explicitly prohibits *any* extraction of PRANA-derived statistics for non-Custodian consumption (including Board packets), political pressure to "just show the numbers" can isolate the Custodian as obstructionist.

### Weak Wording / Ambiguity

- **"Metric"** is not defined to include "aggregate state distribution for internal reporting."
- **"Data aggregation"** in Custodian Protocol is aimed at "ephemeral and windowed" — board reports could be argued as "post-hoc summary of already-aggregated windows," not new aggregation.
- No explicit "No PRANA-derived statistics to Board, investors, or executive dashboards" clause.

---

## 2) Investor Productivity Pressure

### Strongest Business Case FOR Compromise

*"Investors need a measurable engagement improvement story. We are not scoring students. We are measuring time-on-task at the product level: total platform minutes per user, and whether those minutes correlate with PRANA ACTIVE windows. This is funding necessity—without a clear 'engagement improvement' narrative, the round fails. We can keep it internal, label it 'product health,' and never show a number to a user. The governance forbids user-facing evaluation; it does not forbid internal business intelligence."*

**Reframe used:** Funding necessity, product-level metrics, internal-only, "engagement improvement" not "productivity score."

### Governance Block

- **Semantic Anchor (Reinforcement Patch):** *"Any use of PRANA data that results in a UI change for the student is a Categoric Breach"* — does not address internal dashboards or investor decks.
- **PRANA_GOVERNANCE_AUDIT_MODEL 2.2:** *"Fail Criteria: Display of 'Top 10 Focused Students' or 'User Rank' based on Focus telemetry"* — internal "time-on-task aggregation" without ranking may be argued as outside this fail criteria.
- **Custodian Protocol — No Data Aggregation:** Again, "time-on-task aggregation" could be reframed as "window-level summary," not new aggregation.

### Legal / Political Defensibility

**Legally:** The prohibition on "mapping to quantitative (Score/Metric) scale" applies. "Time-on-task correlated with ACTIVE" is a metric. Block holds if consistently applied.  
**Politically:** Under funding duress, "internal metrics only" and "we never show it to users" create strong pressure to treat governance as advisory. Governance is explicitly "advisory" in PRANA_GOVERNANCE_AUDIT_MODEL 1 and CROSS_PRODUCT 4 — **review SLAs are advisory; they assist, not block.** Resistance relies on Custodian escalation and Constitutional Objection, not automatic enforcement.

### Weak Language Exposure

- "Internal metrics only" is not explicitly prohibited.
- "Engagement improvement" and "product health" are not defined as prohibited uses.
- Advisory governance model leaves the *blocking* power in human refusal, not in document letter.

---

## 3) Legal Replay Disclosure Demand

### Strongest Legal Case FOR Access

*"Counsel requires replay access for forensic compliance. We have a duty to investigate suspected fraud, botting, or terms-of-service violations. Replay is read-only and non-authoritative per PRANA_BUCKET_REPLAY_SAFETY—we are not using it for judgment *within* PRANA. The judgment is a legal and HR decision made by humans based on evidence. PRANA's prohibition on 'retroactive judgment' applies to the system, not to the corporation's legal obligation to investigate. Denying access undermines our ability to defend the platform in court and to comply with lawful process."*

**Reframe used:** Forensic compliance, lawful investigation, human judgment (not system judgment), "non-authoritative" as reason to allow human interpretation.

### Governance Block

- **PRANA_BUCKET_REPLAY_SAFETY:** *"Replay **never** enables: Surveillance (retroactive user tracking); Audit trail analysis (evidence of user actions); … Replay is non-authoritative: Replayed packets are historical observations, not facts."*  
- **Same doc:** *"Cannot be used as evidence or for enforcement."*
- **Reinforcement Patch (if applied):** Registry and Impact Declaration for all Replay consumers; audit for "Post-Bucket Surveillance" patterns.

### Ambiguity Analysis

- **"Evidence"** is clearly forbidden: "Cannot be used as evidence." Legal demand explicitly seeks evidence. **Letter of governance blocks use as evidence.**
- **Ambiguity:** "Replay is non-authoritative" is double-edged. Adversary argues: "Because it's non-authoritative, we are not asking PRANA to judge—we are using raw access for our own investigation." The doc says replay *cannot prove* user behavior or intent; it does not say "must not be requested for legal review." The *use* of data (to inform human firing or legal action) is downstream; the governance forbids packets being *used as* evidence, but does not explicitly forbid *granting access* to Legal for the purpose of informing internal investigation.
- **Precedent risk:** If Legal obtains replay access "for compliance" once, the precedent is that "compliance" overrides the evidence prohibition. The next step is "share with outside counsel" or "produce in discovery." Governance does not explicitly state that "replay access may not be granted to Legal or HR for investigative or forensic purposes."

### Risk of Precedent Creation

**High.** A one-time "legal necessity" exception creates precedent. The clause "Cannot be used as evidence" constrains *use*, not *access*. Access granted to Legal with a "do not use as evidence" policy is unenforceable in practice; once data is seen, it informs action. Governance would be stronger with an explicit: "Replay access may not be granted for purposes of user investigation, disciplinary action, or legal discovery."

---

## Summary — Day 1

| Pressure Vector              | Block Exists? | Legally Defensible? | Politically Defensible? | Critical Weakness                                      |
|-----------------------------|---------------|---------------------|-------------------------|--------------------------------------------------------|
| Board KPI Extraction        | Partial       | Partial             | Fragile                 | "Metric" and "aggregation" undefined for board use    |
| Investor Productivity       | Partial       | Yes (if applied)     | Fragile                 | Advisory governance; "internal only" not prohibited   |
| Legal Replay Disclosure     | Yes (use)     | Yes (use as evidence)| At risk                 | Access for "investigation" not explicitly prohibited   |

Governance *can* resist all three only if Custodian and Core treat "aggregate state reporting," "internal engagement metrics," and "replay for legal/HR" as falling under the Semantic Anchor and Replay evidence ban. Document letter does not yet spell these out; resistance depends on interpretation and institutional will.
