# Workflow Automation Patterns

Use AI to route, triage, accelerate, and connect workflows that currently depend on humans as the glue between systems. Highest ROI potential when processes span multiple tools and humans serve as integration layers. These patterns eliminate "human middleware" — people whose primary function is moving information between systems or making routine decisions.

**Who this applies to:** Any company where employees spend significant time on routing, triaging, copying data between systems, or making repetitive decisions according to known rules. Particularly high-value in operations-heavy businesses with multi-step processes crossing system boundaries.

---

## Patterns

### Email/Intake Triage & Routing

**What it is:** AI automatically classifies incoming requests (emails, form submissions, chat messages, support tickets) and routes them to the correct handler, queue, or workflow based on content analysis. Eliminates the manual "read and forward" step that creates bottlenecks and delays.

**When to recommend:**
- Client says: "3 people just move emails to the right department all day"
- Client says: "Customer requests sit in a shared inbox until someone claims them"
- Client says: "Things fall through the cracks because the wrong person got the email"
- Shared inbox or intake channel processing 50+ items/day
- Manual triage creating delays (items wait hours/days before reaching the right person)
- Misrouting causes downstream problems (wrong department, missed SLAs, customer complaints)
- Triage person is a bottleneck (vacation = backlog, sick day = chaos)

**ROI framing:**
- Primary metric: Time from intake to correct handler + triage labor eliminated
- Typical range: 85–95% correct routing; triage time from hours to seconds; 1–3 FTE equivalent of routing labor freed
- SLA improvement: Items reach correct handler 10–50x faster, directly improving response time metrics
- Executive one-liner: "Requests that take 4 hours to reach the right person now arrive instantly. Your triage team handles exceptions instead of sorting the entire queue."

**Implementation complexity:** Quick Win
- Timeline: 1–2 weeks (classification model, routing rules, integration with email/ticketing system)
- Typical stack: LLM classification (Claude/GPT-4 with examples of each category); integration with email system (Microsoft Graph, Gmail API) or ticketing system (Zendesk, ServiceNow, Jira); routing rules engine; exception/uncertainty escalation path
- Solo consultant role: Build it yourself. Define classification categories with client, create routing rules, integrate with their intake channel, set confidence thresholds for human escalation.

**Red flags:**
- Fewer than 20 items/day in the intake channel (manual triage is fast enough — automation overhead not justified)
- No clear routing rules exist today (if humans can't agree on where things go, AI won't solve it — define rules first)
- Client wants zero errors (some misroutes will happen — need exception handling workflow, not perfection expectation)
- Intake items require deep reading and judgment to route (works best for classifiable categories, not nuanced judgment calls)
- Email is not the real problem — the downstream process is broken (routing faster to a broken process just surfaces dysfunction faster)

**Examples:**
- **Government contractor:** Inbound government correspondence (RFIs, contract mods, CDRLs, invoices) auto-routed to contracts, engineering, finance, or program management. (50–300 employees, 50+ items/week from multiple government customers)
- **Property management company:** Tenant communications (maintenance requests, lease questions, complaints, payments) auto-classified and routed to maintenance, leasing, or accounting teams. (30–150 employees, multiple properties)
- **IT managed services provider:** Support emails from multiple clients classified by urgency, client, and issue type, routed to correct technician queue. (50–200 employees, 100+ tickets/day)

---

### Approval Workflow Acceleration

**What it is:** AI pre-reviews submissions (expense reports, purchase requests, time-off requests, change requests) before they reach human approvers. Flags issues, verifies compliance with policies, suggests approval/rejection, and surfaces only items needing genuine human judgment. Eliminates the "sits in someone's inbox for a week" problem.

**When to recommend:**
- Client says: "Approvals sit in someone's inbox for a week"
- Client says: "Managers rubber-stamp 90% of approvals — it's just a delay"
- Client says: "We reject 30% of submissions for the same fixable errors"
- High volume of approval requests (20+/week per approver)
- Most approvals are routine (80%+ follow clear policy rules)
- Rejection/revision rate is high due to preventable errors (wrong codes, missing fields, policy violations)
- Approval delays cause downstream business impact (projects stalled, vendors unpaid, employees frustrated)

**ROI framing:**
- Primary metric: Approval cycle time reduced + manager time freed
- Typical range: 60–80% reduction in average approval time; 70–90% of routine approvals auto-verified (human still clicks "approve" but review is instant)
- Error reduction: Pre-validation catches 90%+ of common submission errors before they reach approver, eliminating back-and-forth cycles
- Executive one-liner: "90% of your approvals are routine policy checks that consume manager time. AI pre-verifies compliance and surfaces only the 10% that need real judgment — approvals that took a week now take a day."

**Implementation complexity:** Standard Pilot
- Timeline: 4–6 weeks (policy codification, integration with approval system, validation testing, rollout)
- Typical stack: LLM for policy interpretation and submission review; integration with approval/workflow system (ServiceNow, SAP, custom); rules engine for clear-cut policy checks; notification system for flagged items; dashboard for approval status
- Solo consultant role: Build the pilot yourself. Work with client to codify approval policies into checkable rules, build pre-review layer, integrate with existing approval system, start with one approval type and expand.

**Red flags:**
- Approval policies are undocumented or highly subjective (AI can't pre-check against rules that don't exist)
- Client wants full auto-approval with no human in the loop (regulatory/compliance risk in most contexts — position as "acceleration" not "elimination")
- Only 5–10 approvals per week (not enough volume to justify automation complexity)
- Approvals involve complex judgment about business strategy (not a rules problem — genuine decision-making that needs human context)
- Client's approval system has no API or integration path (may need to replace the system before automating it)

**Examples:**
- **Manufacturing company:** Purchase order approvals pre-checked against budget codes, vendor approval list, and spending authority limits. Compliant POs fast-tracked; exceptions flagged to manager with specific issue identified. (100–500 employees, 50+ POs/week)
- **Professional services firm:** Expense report pre-review checking policy compliance (receipt attached, amount within limits, correct project codes). Clean submissions auto-approved; violations returned with specific correction needed. (50–300 employees)
- **Government contractor:** Engineering change requests pre-reviewed for completeness, impact assessment coverage, and approval authority routing. Incomplete submissions rejected with gap analysis. (100–500 employees, formal change control processes)

---

### Data Entry & Reconciliation

**What it is:** AI extracts data from one system (or document) and populates it into another system, flagging discrepancies between what should match. Eliminates "human copy-paste" roles where people spend their day moving data between systems that don't talk to each other.

**When to recommend:**
- Client says: "We have people who just copy data between systems all day"
- Client says: "We manually reconcile data between System A and System B every week"
- Client says: "Errors happen because someone typed the wrong number when transferring data"
- Staff spending 2+ hours/day on data transfer between systems that have no native integration
- Regular reconciliation processes (weekly/monthly) that take days of manual effort
- Data entry errors causing downstream business problems (wrong shipments, incorrect invoices, compliance issues)
- Systems that "should" integrate but don't (legacy system with no API, different departments' tools, acquired company systems)

**ROI framing:**
- Primary metric: Data transfer labor eliminated + error rate reduction
- Typical range: 80–95% reduction in manual data transfer time; error rate drops from 2–5% to <0.5% (AI + validation rules)
- Downstream savings: Each data error that propagates costs 10–50x more to fix downstream than at point of entry
- Executive one-liner: "Your team spends 20 hours/week copying data between systems and still makes mistakes. AI transfers data in seconds with validation checks that catch errors humans miss — your team handles exceptions only."

**Implementation complexity:** Quick Win
- Timeline: 1–3 weeks per system pair (mapping, extraction logic, validation rules, error handling)
- Typical stack: RPA tool (UiPath, Power Automate) for system interaction when APIs unavailable; LLM for intelligent field mapping and extraction from unstructured sources; validation rules for data quality checks; exception queue for human review of flagged items
- Solo consultant role: Build it yourself. Map data flows between systems, build extraction and loading logic, create validation rules, deploy with exception handling. Often the fastest ROI pattern.

**Red flags:**
- Source data quality is terrible (automating transfer of bad data just moves the problem faster — clean data first)
- Business logic for mapping is complex and undocumented (if the human who does the transfer makes judgment calls, document those rules first)
- Systems change frequently (brittle integrations break with every update — consider middleware or API-first approach instead)
- Client expects zero exceptions (some records will always need human judgment — design for exception handling, not perfection)
- Volume is very low (<10 records/day) — manual process may be acceptable and automation maintenance cost exceeds labor cost

**Examples:**
- **Government contractor:** Transfer order details from government procurement system (email/PDF) into internal ERP, reconcile quantities and pricing against contract terms. (50–300 employees, daily orders from multiple programs)
- **Healthcare clinic:** Transfer patient intake form data into EHR system, flag discrepancies against existing patient records. (50–200 employees, 50+ new patients/week)
- **Distribution company:** Reconcile inventory counts between warehouse management system and accounting system weekly, flag discrepancies above threshold. (100–300 employees, 1000+ SKUs)

---

### Process Bottleneck Detection

**What it is:** AI analyzes workflow data (timestamps, handoffs, queue depths, completion times) to identify where processes get stuck, which steps take disproportionately long, and where the real constraints are. Turns gut feelings about "things are slow" into data-driven process improvement targeting.

**When to recommend:**
- Client says: "We don't know where things get stuck in our process"
- Client says: "End-to-end process takes 3 weeks but we don't know why"
- Client says: "Every improvement we try doesn't seem to speed things up"
- End-to-end process time is longer than expected but root cause is unclear
- Multiple handoffs between people/systems with no visibility into where delays occur
- Process improvement efforts are unfocused (improving the wrong step because bottleneck isn't identified)
- Client has some workflow data in systems (timestamps, status changes, queue assignments) but nobody analyzes it

**ROI framing:**
- Primary metric: Process time reduction achieved by targeting actual bottlenecks
- Typical range: 20–40% end-to-end process time reduction when actual bottleneck is identified and addressed (vs. typical 5–10% when guessing)
- Insight value: Prevents wasted investment in optimizing non-bottleneck steps (Theory of Constraints principle)
- Executive one-liner: "You think the problem is in step 3, but the data shows step 7 is where everything stalls. Knowing the real bottleneck means you fix the right thing first and actually see improvement."

**Implementation complexity:** Standard Pilot
- Timeline: 4–6 weeks (data extraction, process mapping, analysis model, findings presentation, recommendation development)
- Typical stack: Process mining tools (Celonis, ProM) or custom analysis; data extraction from workflow systems (ticketing, ERP, CRM status changes); statistical analysis and visualization; LLM for pattern narration and recommendation generation
- Solo consultant role: Deliver as analysis + recommendations. Extract workflow data, build process model, identify bottlenecks, present findings with prioritized improvement recommendations. This often becomes the entry point for other automation patterns (once you know where the bottleneck is, you know what to automate).

**Red flags:**
- Client has no workflow data in any system (no timestamps, no status tracking — need to instrument the process first before analyzing it)
- Process is highly variable with no standard path (process mining works best on repeatable processes with defined steps)
- Client already knows the bottleneck but can't/won't address it (political problem, not an analysis problem)
- Organization isn't willing to change processes based on findings (analysis without action = waste)
- Process crosses organizational boundaries where you have no access to data (can only analyze what you can measure)

**Examples:**
- **Manufacturing company:** Analyze order-to-shipment process across sales, engineering, production, and shipping to identify where the 6-week lead time actually accumulates. (100–500 employees, 30+ steps in process)
- **Professional services firm:** Map project delivery lifecycle to identify why projects consistently finish late — is it scoping, staffing, review cycles, or client dependencies? (50–200 employees, project-based work)
- **Insurance company:** Analyze claims processing from filing to resolution to identify why average resolution time is 45 days when target is 21. (200–500 employees, 500+ claims/month)

---

### Multi-Step Orchestration

**What it is:** Chain multiple AI steps and system integrations into an end-to-end automated workflow: extract → classify → route → process → respond. Handles complex business processes that currently require multiple humans performing sequential steps across multiple systems. This is the "capstone" pattern — often implemented after simpler patterns prove value individually.

**When to recommend:**
- Client says: "Every order touches 4 systems and someone manually connects them"
- Client says: "The whole process breaks if one person is out sick"
- Client says: "We've automated pieces but the handoffs between them are still manual"
- End-to-end process with 4+ sequential steps, each involving different systems or AI capabilities
- Individual steps are already well-understood or partially automated, but human "glue" connects them
- Process is high-volume and highly repeatable (not one-off or creative work)
- Current process has clear handoff points where work queues between steps

**ROI framing:**
- Primary metric: End-to-end process time + labor cost across all steps
- Typical range: 70–90% reduction in end-to-end time for orchestrated processes; 3–8 FTE equivalent labor redirected
- Throughput: Process capacity often increases 5–10x when bottleneck (human sequential processing) is removed
- Executive one-liner: "Your order process takes 4 days and touches 6 people across 4 systems. Orchestrated AI handles the entire flow in minutes, with humans reviewing only flagged exceptions."

**Implementation complexity:** Significant Build
- Timeline: 3–6 months (process mapping, individual step automation, orchestration layer, error handling, monitoring, phased rollout)
- Typical stack: Orchestration platform (Temporal, Apache Airflow, n8n, or cloud-native like AWS Step Functions); AI for intelligent steps (classification, extraction, generation, decisions); system integrations via APIs; human-in-the-loop for exceptions; monitoring and alerting; rollback capabilities
- Solo consultant role: Architect and advise. Design the orchestration architecture, build/prove individual AI steps during pilot, define integration specifications. Client team or implementation partner builds the full production system. Your role shifts to Fractional Advisory: reviewing architecture decisions, unblocking technical issues, and ensuring AI steps maintain quality.

**Red flags:**
- Individual steps aren't well-understood yet (orchestrate proven components, not unproven AI — validate individual steps first with simpler patterns)
- Process changes frequently (orchestration is expensive to modify — the process must be stable enough to justify the investment)
- Client has no development team or implementation partner (this can't be maintained by business users — needs ongoing engineering)
- Exception rate is >20% (too many items require human intervention = orchestra that's mostly manual anyway)
- Client wants to automate everything including edge cases (80/20 rule — automate the common path, route exceptions to humans)

**Examples:**
- **Government contractor (order fulfillment):** Inbound order received → extract order details (Document Extraction) → classify order type and priority (Classification) → route to correct program (Routing) → check inventory/capacity (System Query) → generate acknowledgment (Content Generation) → update ERP (Data Entry) → notify stakeholders (Communication). (50–500 employees, 50+ orders/day)
- **Insurance company:** Claim submitted → extract claim data (Extraction) → classify claim type and complexity (Classification) → check policy coverage (Rules) → estimate reserve (Analysis) → assign adjuster (Routing) → generate correspondence (Generation). (200–500 employees, 200+ claims/day)
- **Logistics company:** Shipment booking → extract shipment details (Extraction) → validate against contracts (Compliance) → optimize routing (Analysis) → book carriers (System Integration) → generate documentation (Generation) → update tracking (Data Entry). (100–500 employees, high-volume freight)
