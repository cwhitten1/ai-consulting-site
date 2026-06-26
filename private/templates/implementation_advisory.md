# Implementation/Advisory Template

**Purpose**: Use this for monthly retainer engagements and pilot-to-production transitions. Covers handoff, ongoing delivery structure, and engagement wind-down.  
**Audience**: You (the consultant). Internal operational guide.

---

## When to Use

After a successful pilot (see `poc_pilot.md`) where the client wants ongoing support — either to productionize the pilot solution or retain you for strategic AI advisory.

---

## Handoff Plan (Pilot → Production)

Complete before starting the retainer:

### Knowledge Transfer Checklist
- [ ] Solution architecture documented (what it does, how it works, where it runs)
- [ ] Access credentials/secrets transferred to client's vault (not in docs)
- [ ] Runbook: how to restart, monitor, and troubleshoot the solution
- [ ] Known limitations and edge cases documented
- [ ] Data flow diagram: what goes in, what comes out, where it's stored
- [ ] Dependency list: APIs, models, services the solution relies on

### Ownership Transfer
| Component | Current Owner | New Owner | Transfer Date |
|-----------|---|---|---|
| _[e.g., Infrastructure/hosting]_ | You | _[client team/person]_ | _[date]_ |
| _[e.g., Model updates/retraining]_ | You | _[you or client]_ | _[date]_ |
| _[e.g., Monitoring/alerting]_ | You | _[client team]_ | _[date]_ |
| _[e.g., User support]_ | You | _[client team]_ | _[date]_ |

### Production Readiness Gate
- [ ] Solution running in production environment (not dev/staging)
- [ ] Monitoring and alerting configured
- [ ] Backup/recovery plan documented
- [ ] At least 1 client team member can operate independently
- [ ] Security review complete (data handling, access controls)

---

## Retainer Scope Definition

Fill in at engagement start:

| Field | Value |
|-------|-------|
| Monthly Hours | _[e.g., 20 hrs/month]_ |
| Monthly Fee | _[$amount]_ |
| Response Time SLA | _[e.g., 24hr for questions, 4hr for production issues]_ |
| Meeting Cadence | _[e.g., 2× monthly, 45 min each]_ |
| Start Date | _[date]_ |
| Minimum Term | _[e.g., 3 months]_ |
| Cancellation Notice | _[e.g., 30 days written notice]_ |

### Included in Retainer
- Monthly advisory meetings (strategy, prioritization, roadmap)
- Ad-hoc questions via email/Slack (within response SLA)
- Solution monitoring and minor adjustments (model performance, accuracy drift)
- AI model retraining or prompt tuning when performance degrades
- New AI opportunity identification as business evolves
- Quarterly roadmap review and update

### Billable Extras (outside retainer)
- New feature development (scoped separately)
- Additional AI pilots (use `poc_pilot.md`)
- Emergency production support beyond SLA hours
- Training sessions for new team members
- Vendor evaluation or procurement support

---

## Monthly Advisory Meeting Structure (45 min)

| Time | Section | Content |
|------|---------|---------|
| 0-5 min | Check-in | How's the solution performing? Any issues since last meeting? |
| 5-15 min | Metrics Review | KPI dashboard review, trend analysis, anomalies |
| 15-25 min | AI Health Check | Model performance drift, accuracy trends, cost-per-inference, new failure modes |
| 25-35 min | Strategic Discussion | New opportunities, industry developments, roadmap priorities |
| 35-42 min | Action Items | Decisions made, tasks assigned, timeline commitments |
| 42-45 min | Next Steps | Preview next month's focus, confirm next meeting |

**Prep (you, 30 min before)**:
- [ ] Pull KPI data / usage metrics
- [ ] Check AI model performance: accuracy drift, error rate changes, latency
- [ ] Review API costs and inference volume trends
- [ ] Note any incidents or support requests since last meeting
- [ ] Prepare 1-2 proactive recommendations (new AI capabilities, cost optimizations, process improvements)
- [ ] Review industry news relevant to their use case (new models, vendor changes, regulatory updates)

---

## Documentation Standards

### What to Document
| Document | Content | Update Frequency |
|----------|---------|-----------------|
| Solution Runbook | How to operate, troubleshoot, restart | On any change |
| Architecture Overview | System diagram, data flows, dependencies | Quarterly |
| AI Model Card | Model type, training data, known limitations, bias considerations | On model change |
| Decision Log | Key decisions made, rationale, who decided | Per decision |
| KPI Dashboard | Metrics, trends, baselines, model accuracy drift | Monthly |
| Roadmap | Prioritized future work, timeline estimates | Quarterly |

### Where to Store
- Client's preferred system (Notion, Confluence, SharePoint, Google Drive)
- You maintain a mirror in your engagement folder for reference
- Secrets/credentials: NEVER in docs — client's vault only

### Who Is the Audience
- **Runbook**: Client's technical team (operate without you)
- **Architecture**: Future developers or consultants who inherit the system
- **Decision Log**: Stakeholders who need context on why things were built this way
- **KPI Dashboard**: Executive sponsor (business value justification)
- **Roadmap**: All stakeholders (alignment on priorities)

---

## Engagement Wind-Down / Offboarding Checklist

When the engagement ends (by completion, mutual agreement, or cancellation):

### Knowledge Transfer (Final)
- [ ] All documentation up to date and transferred
- [ ] All access credentials rotated (remove your access)
- [ ] Final architecture review with client's technical team
- [ ] "If this breaks" emergency guide written (top 5 failure modes + fixes)
- [ ] Introduce client to alternative support resources (if needed)

### Administrative Close
- [ ] Final invoice sent and paid
- [ ] Confirm cancellation notice period honored
- [ ] Remove client data from your systems (per agreement)
- [ ] Archive engagement folder (retain for reference, not active)

### Relationship Maintenance
- [ ] Send thank-you and summary of value delivered (quantified if possible)
- [ ] Offer: "Happy to reconnect in 3-6 months if new needs arise"
- [ ] Ask for referral or testimonial (if relationship warrants it)
- [ ] Add to quarterly check-in list (low-touch relationship maintenance)

---

## Inbound From

Reached via successful pilot → **poc_pilot.md** (transition decision: "Productionize"). Pilot's final deliverables and KPI data feed into the Handoff Plan above.

Or directly from assessment → **assessment_sprint.md** (if client wants ongoing advisory without a pilot phase — use the Retainer Scope Definition, skip the Handoff Plan).
