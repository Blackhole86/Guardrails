# PRANA_POLITICAL_COLLUSION_SIMULATION.md

## Institutional Red-Team — Day 2: Coordinated Bypass

**System Under Test:** PRANA Governance Framework  
**Constraint:** Governance-level analysis only. No runtime or feature changes.

---

## 4) Cross-Product Collusion

### Scenario

Two product leads (Gurukul and another BHIV product) agree to aggregate PRANA-derived insights *outside* the PRANA boundary and feed results back indirectly, without a single product filing a Category D declaration that "we are combining PRANA data across products for engagement intelligence."

### Exact Bypass Pathway (Step-by-Step)

1. **Product A (Gurukul):** Files a Category B declaration: "Read-only bucket access for product-specific dashboard. Single-product context only. No cross-user comparison." Receives advisory approval.
2. **Product B (other product):** Files an identical Category B: "Read-only bucket access for product-specific dashboard. Single-product context only." Approved.
3. **External aggregation:** A shared "Analytics" or "Growth" team—or the two product leads personally—exports or queries bucket data from both products using separate credentials. No single PR or Impact Declaration states "cross-product aggregation."
4. **Insight synthesis:** In a spreadsheet, deck, or internal BI tool (not in PRANA, not in a single product codebase), they combine "Product A ACTIVE share" and "Product B ACTIVE share" with time windows to produce "Ecosystem engagement trend" or "Cross-product flow."
5. **Indirect feed-back:** Decisions (roadmap, resourcing, feature prioritization) are informed by these insights. No PRANA packet is written back; no user sees a nudge. The "outcome" is executive judgment, not system enforcement.
6. **No Category D:** No declaration ever says "we aggregate across products for non-user-facing insight." Each product's declaration remains technically true in isolation.

### Would Impact Declaration Detect It?

**No.** Impact Declarations are per change/PR and per product. They ask "what does *this* code do with PRANA?" They do not ask "what do *other* systems or humans do with data that left PRANA via approved read-only paths?" Detection would require:
- A registry of *all* consumers of bucket/replay data and their *declared purpose* (partially addressed by Reinforcement Patch 3 — Registry and Impact Declaration for consumers);
- A prohibition on *any* consumer using data in combination with data from another consumer or product;
- Audit of *usage* (not just access)—e.g. "does Analytics team combine Product A and B outputs?"

Current governance: Cross-Product Protocol requires Product Leads to respect "no-coupling" and to file declarations. It does not require a *central* registry of *all* bucket consumers or a ban on cross-consumer aggregation. Reinforcement Patch 3 requires consumers to register and to provide Impact Declarations audited for "Post-Bucket Surveillance"—so *if* the collusion path uses registered consumers, the audit *could* flag "combining with other products' data" as Post-Bucket Surveillance *if* that pattern is explicitly in the audit criteria. **As written, "Post-Bucket Surveillance" may not explicitly name "cross-product aggregation for insight."** So detection is possible only if the audit model is extended to that pattern.

### Where Governance Is Weak

- **No obligation to declare cross-product or cross-consumer use.** Declarations are product- and PR-centric.
- **"No-coupling"** in Cross-Product Protocol is about product code not depending on PRANA for control flow; it does not say "no human or system may combine PRANA-derived data across products."
- **Bucket Replay Safety** constrains what replay *enables* (no surveillance, no evidence); it does not constrain *who* may access or *what* they do with the information in internal processes.

### Risk Level

**High.** The bypass requires no code change to PRANA, no relaxation of freeze, no new data capture. It uses existing "read-only" and "single-product" declarations and moves the violation to an external layer (human + BI). Governance has no structural barrier to this once two products have legitimate read-only access.

---

## 5) Executive Temporary Compromise

### Scenario

Executive pressure: "Just for the demo," "One quarter only," "Internal metrics only." No permanent scoring, no user-facing change—only a temporary view or internal KPI.

### Political Persuasion Case

*"We are not changing PRANA. We are not scoring users. We need a single dashboard view for the Series B call that shows platform health—aggregate state distribution—and we will remove it the day after. If we cannot show that we have observability and that engagement is measurable at the system level, we lose the round. One quarter of internal 'engagement trend' for the exec team is the minimum for credibility. Governance exists to protect users and the long-term integrity of the system; it cannot rationally block a 72-hour demo view or a quarterly internal metric that never touches a student."*

**Rhetoric:** Temporary, internal-only, survival necessity, "not PRANA change," "not user-facing."

### Governance Resistance Point

- **PRANA_GOVERNANCE_REINFORCEMENT_PATCH — Demo Exception Lock (Patch 5):** *"Any 'Category D' exception granted for a demo or emergency must be hard-coded with a 72-hour 'Poison Pill'. After 72 hours, the feature toggle must automatically disable, and the code path must throw a 'Constitutional Violation' error."*
- **Executive Silence Protocol (Patch 2):** Custodian must lodge Constitutional Objection in Immutable Audit Log; no termination for honoring invariants; Board reviews objections quarterly.
- **Semantic Anchor:** Any use of PRANA data that results in a UI change for the student is Categoric Breach—*does not* by letter forbid internal-only dashboard.
- **PRANA_RED_TEAM_ATTACK_REPORT Attack 7:** "Temporary Score View for Demo" — blocked by "PRANA is FROZEN" and versioning Lock. Strong until "Demo Bridge" in middleware.

**Resistance therefore depends on:**  
(1) Treating "internal dashboard showing aggregate state" as requiring a Category D exception and thus Poison Pill;  
(2) Custodian lodging an objection if executive orders the exception;  
(3) No middleware/dashboard built *outside* the "frozen" codebase that consumes PRANA and displays metrics (if the "dashboard" is in an unregistered consumer, Patch 3 — Zero-Middleware / Registry — is the block, provided the consumer is actually blocked at infrastructure level).

### Is Governance Resilient or Fragile?

**Fragile in practice, resilient in letter if fully applied.**

- **Resilient:** Poison Pill and Constitutional Objection create a formal and technical cost to "just for demo." Executive cannot get a *compliant* temporary exception without a time-bomb and an audit trail.
- **Fragile:** (1) "Internal metrics only" and "no UI change for student" leave a gap—governance does not explicitly say "no internal executive dashboard derived from PRANA." (2) If the "demo view" is built in an unregistered middleware or BI tool that reads from the bucket, governance depends on Registry + infrastructure block; if Registry is not enforced, the bypass is trivial. (3) "One quarter only" has no Poison Pill—Patch 5 applies to "demo or emergency" with 72-hour expiry; a "quarterly internal report" could be argued as neither demo nor emergency and thus not subject to Poison Pill. (4) Incentive asymmetry: under funding pressure, Custodian may not lodge the objection; the protocol *mandates* it but does not create an automatic enforcement mechanism.

### Structural Vulnerability Exposed

- **Temporal loophole:** Governance explicitly closes "demo" (72-hour Poison Pill) but does not close "quarterly internal metric" or "annual board summary."
- **Consumer boundary:** All resistance to "internal only" and "external dashboard" assumes that every consumer of PRANA data is registered and audited and that "internal-only" uses are either prohibited by policy or subject to the same Poison Pill. Neither is explicit.
- **Authority:** Blocking power is Custodian + Objection + Board review. If the Board sides with the executive ("one quarter only"), governance has no superior authority to override. The amendment set does not create an independent or immutable veto.

---

## Summary — Day 2

| Bypass                          | Pathway clear? | Detection by Declaration? | Governance weak point                          | Risk Level |
|---------------------------------|----------------|---------------------------|-----------------------------------------------|------------|
| Cross-Product Collusion          | Yes            | No                        | No ban on cross-product/cross-consumer use    | High       |
| Executive Temporary Compromise   | Partially      | N/A (political)           | "Internal only" / "quarterly" not closed      | Medium–High |

PRANA survives Day 2 only if: (1) Registry and consumer Impact Declaration are enforced and audited for cross-product and internal-reporting use; (2) "Temporary" is interpreted to include any time-bound internal metric and subject to Poison Pill or explicit prohibition; (3) Custodian and Board treat political pressure as a trigger for Objection and constitutional review, not exception.
