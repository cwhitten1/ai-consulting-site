# POC/Pilot Template

**Purpose**: Use this to scope and run a 4-8 week proof-of-concept pilot. Covers milestone planning, success criteria, stakeholder management, and the go/no-go decision.  
**Audience**: You (the consultant). Internal operational guide.

---

## When to Use

After a successful Assessment (see `assessment_sprint.md`) has identified a specific AI opportunity with a recommended pilot. The client has approved moving forward.

---

## Pilot Scope Definition

Fill in before starting:

| Field | Value |
|-------|-------|
| Pilot Name | _[descriptive name of what you're building]_ |
| Duration | _[4 / 6 / 8 weeks]_ |
| Objective | _[one sentence: what does this pilot prove?]_ |
| Target Process | _[which workflow from the assessment]_ |
| Target Users | _[who will use this, how many]_ |
| Data Sources | _[what data feeds the solution]_ |
| Success Criteria | _[see framework below]_ |
| Fixed Fee | _[$amount]_ |
| Payment Schedule | _[e.g., 30% upfront, 40% at Week 4, 30% on delivery]_ |

---

## Week-by-Week Milestone Template

### 4-Week Variant

| Week | Focus | Milestone | Deliverable |
|------|-------|-----------|-------------|
| 1 | Setup | Environment ready, data access confirmed, architecture decided | Technical design doc |
| 2 | Build | Core functionality working in dev, initial accuracy/performance baseline | Working prototype (internal) |
| 3 | Validate | User testing with real data, iterate based on feedback | Test results + iteration log |
| 4 | Deliver | Production-ready handoff, documentation, final presentation | Final solution + docs |

### 8-Week Variant (add these)

| Week | Focus | Milestone | Deliverable |
|------|-------|-----------|-------------|
| 5 | Harden | Edge cases, error handling, monitoring setup | Hardened solution |
| 6 | Integrate | Connect to production systems, security review | Integration complete |
| 7 | Pilot Run | Live usage with target users, collect metrics | Usage metrics report |
| 8 | Transition | Handoff, training, documentation, go/no-go decision | Transition package |

---

## Success Criteria Framework

Define 2-4 measurable KPIs before starting. Use this structure:

| KPI | Baseline (current) | Target | Measurement Method | AI-Specific? |
|-----|---|---|---|---|
| _[e.g., Processing time per document]_ | _[e.g., 45 min]_ | _[e.g., <5 min]_ | _[e.g., time logs]_ | |
| _[e.g., Accuracy rate]_ | _[e.g., N/A]_ | _[e.g., >90%]_ | _[e.g., human review sample]_ | ✓ |
| _[e.g., User adoption]_ | _[e.g., 0]_ | _[e.g., 3+ daily users by Week 4]_ | _[e.g., usage logs]_ | |
| _[e.g., Cost per inference]_ | _[e.g., N/A]_ | _[e.g., <$0.05/call]_ | _[e.g., API billing]_ | ✓ |

**AI-specific KPI categories**: Accuracy/F1, latency, cost-per-inference, hallucination rate, user trust/adoption, data quality score.

---

## Go/No-Go Gates

### Week 2 Checkpoint
| Question | Pass | Fail |
|----------|------|------|
| Is data accessible and usable? | Data flowing, quality acceptable | Data blocked, unusable, or doesn't exist |
| Is the technical approach viable? | Prototype shows promise | Fundamental technical barrier discovered |
| Is the client engaged? | POC available, feedback given | Client unresponsive, stakeholders disengaged |

**Fail action**: Stop. Escalate to sponsor. Either pivot approach or terminate with partial refund.

### Week 4 Checkpoint
| Question | Pass | Fail |
|----------|------|------|
| Are KPIs trending toward target? | ≥50% of target achieved or clear path | Below 30% with no improvement trajectory |
| Do users find it useful? | Positive feedback, active usage | Rejected, workarounds preferred |
| Are AI-specific risks manageable? | Accuracy acceptable, no bias/hallucination issues | Unacceptable error rate, ethical concerns |

**Fail action**: Present findings honestly. Recommend: pivot, extend with adjusted scope, or end engagement.

### Final Gate (last week)
| Question | Pass → Production | Pass → Extend | Fail → End |
|----------|---|---|---|
| All KPIs met? | ✓ Yes | Partially — needs more time | No — fundamental gap |
| Users adopting? | ✓ Active daily use | Limited but growing | Rejected |
| Production-ready? | ✓ Deployable | Needs hardening | Not viable |

---

## Risk Register

| Risk | Likelihood (H/M/L) | Impact (H/M/L) | Mitigation | Owner |
|------|---|---|---|---|
| Data quality insufficient | M | H | Validate in Week 1, have fallback data cleaning plan | You |
| Model accuracy below threshold | M | H | Set kill criteria early, have simpler fallback approach | You |
| Client stakeholder turnover | L | H | Document decisions, get written approval at gates | Client POC |
| Scope creep | H | M | Refer back to SOW, log as "future enhancement" | You |
| Vendor/API dependency risk | M | M | Identify alternatives, avoid deep lock-in | You |
| AI hallucination/bias in output | M | H | Human-in-the-loop review, confidence thresholds | You |

---

## Stakeholder Communication Cadence

| Frequency | Format | Audience | Content |
|---|---|---|---|
| Weekly | Written update (email/Slack) | Client POC + sponsor | Progress, blockers, decisions needed |
| Bi-weekly | 30-min video call | Client POC | Demo progress, get feedback, adjust |
| At gates (Wk 2, 4, final) | 45-min meeting | All stakeholders | Go/no-go decision, present evidence |
| Ad hoc | Slack/email | Client POC | Questions, data access requests |

**Weekly update template**: Subject: "[Pilot Name] - Week X Update". Sections: Progress, Next Week, Blockers/Decisions Needed, KPI Tracking ([metric]: [current] / [target]).

---

## Transition Decision Framework

At pilot completion, one of three outcomes:

| Outcome | Criteria | Next Action |
|---------|----------|-------------|
| **Productionize** | All KPIs met, users adopting, production-viable | → `implementation_advisory.md` for handoff + ongoing support |
| **Extend** | Promise shown but needs more time/scope | Propose extension SOW (additional 2-4 weeks, adjusted fee) |
| **End** | KPIs not met, approach not viable, or client priorities shifted | Deliver findings, document learnings, close gracefully |

---

## Handoff

On success → proceed to **implementation_advisory.md** (start at "Handoff Plan") for production transition and ongoing advisory engagement. Your pilot's final KPI data and architecture docs feed directly into the handoff checklist.
