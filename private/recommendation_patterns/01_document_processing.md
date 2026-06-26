# Document Processing Patterns

Automate extraction, classification, routing, and summarization of documents. The most universal AI entry point — every company has documents consuming human hours. These patterns require minimal AI maturity and produce measurable time savings immediately.

**Who this applies to:** Any company that processes invoices, contracts, forms, reports, or compliance documents manually. Manufacturing, professional services, healthcare, financial services, logistics — essentially everyone.

---

## Patterns

### Intelligent Document Extraction

**What it is:** AI reads structured and semi-structured documents (invoices, purchase orders, forms, contracts) and extracts key fields into your systems automatically. Combines OCR for scanned documents with LLM-based extraction for understanding context, tables, and variable layouts.

**When to recommend:**
- Client says: "We have people typing data from invoices/POs into our ERP all day"
- Client says: "We get documents in 15 different formats from vendors"
- High volume of inbound documents (50+ per day) with data that needs to enter a system
- Documents are semi-structured (invoices, forms) not completely unstructured (novels)
- Company already has a target system (ERP, database, spreadsheet) where data should land
- Current error rate in manual entry is a pain point (re-work, corrections, customer complaints)

**ROI framing:**
- Primary metric: Time saved on manual data entry
- Typical range: 60–85% reduction in processing time per document
- Error reduction: Manual entry error rates of 2–5% drop to <1% with AI + human review
- Executive one-liner: "Your team processes 200 invoices/day spending 3 minutes each — that's 10 person-hours daily on data entry. AI handles 80% automatically, freeing 8 hours for higher-value work."

**Implementation complexity:** Quick Win
- Timeline: 1–3 weeks for a single document type; add 1 week per additional type
- Typical stack: Azure Document Intelligence, AWS Textract, or Google Document AI for OCR/extraction; LLM layer (GPT-4, Claude) for complex field interpretation; integration script to target system
- Solo consultant role: Build it yourself. Configure extraction service, write integration, set up human-review workflow for low-confidence extractions.

**Red flags:**
- Documents are handwritten (OCR accuracy drops significantly — needs specialized models)
- Fewer than 20 documents/day of a given type (ROI may not justify setup cost)
- No target system — data extracted but nowhere structured to put it
- Client wants 100% automation with no human review (not realistic for high-stakes docs like contracts)
- Documents contain sensitive PII/PHI and client has no data governance framework

**Examples:**
- **Manufacturing (gov-contractor):** Extract line items, quantities, part numbers from purchase orders received via email/PDF. Push into ERP. (50–200 employees, 30–100 POs/week)
- **Accounting firm:** Extract data from client-submitted tax documents, receipts, and bank statements into tax preparation software. (20–100 employees, seasonal spikes)
- **Logistics company:** Extract shipment details from bills of lading and customs forms into TMS. (100–500 employees, 200+ docs/day)

---

### Document Classification & Routing

**What it is:** AI automatically categorizes incoming documents by type (invoice, contract, complaint, application) and routes them to the correct workflow, department, or person. Eliminates the "mailroom sorting" problem where humans triage inbound document streams.

**When to recommend:**
- Client says: "Incoming documents get lost or go to the wrong person"
- Client says: "Someone spends their morning sorting emails/faxes/uploads into folders"
- High volume of mixed-type inbound documents from a single channel (shared inbox, upload portal, fax)
- Multiple departments handle different document types
- Misrouted documents cause delays or compliance issues
- Current triage person is a bottleneck (vacation = backlog)

**ROI framing:**
- Primary metric: Routing time reduced + misroute rate
- Typical range: 90–95% classification accuracy after initial training; routing time from hours/days to seconds
- Downstream impact: Every day of misrouting delay compounds into missed SLAs, late payments, or compliance gaps
- Executive one-liner: "Documents that take 4 hours to reach the right person now arrive in under a minute — and your triage person can focus on exceptions instead of sorting."

**Implementation complexity:** Quick Win
- Timeline: 1–2 weeks for initial classifier; 1 week to integrate with routing (email rules, ticketing system, workflow tool)
- Typical stack: LLM-based classification (GPT-4/Claude with few-shot examples); integration with email system or document management; simple rules engine for routing logic
- Solo consultant role: Build it yourself. Create classification prompt/model, connect to document intake channel, set up routing rules, define escalation path for uncertain classifications.

**Red flags:**
- Fewer than 5 document types (simple rules might suffice — don't over-engineer)
- Document types are ambiguous even to humans (classification accuracy will plateau)
- No clear routing rules exist today (AI can't route if humans don't agree on where things go)
- Client has no centralized intake channel (documents arrive via 10 different paths — fix intake first)

**Examples:**
- **Insurance company:** Incoming claims documents (medical records, police reports, photos, invoices) automatically classified and routed to correct adjuster queue. (100–400 employees, 500+ docs/day)
- **Government contractor:** Inbound correspondence (RFIs, contract modifications, compliance requests, invoices) sorted and routed to contracts, finance, or program management. (50–300 employees)
- **Property management:** Tenant submissions (maintenance requests, lease applications, complaints, payments) auto-classified and routed to correct team. (20–100 employees, multiple properties)

---

### Contract/Compliance Review

**What it is:** AI assists human reviewers by scanning contracts or regulatory documents to flag specific clauses, identify deviations from standard terms, detect missing required provisions, and highlight risk areas. Augments (not replaces) human legal/compliance review.

**When to recommend:**
- Client says: "Contract review takes weeks and we still miss things"
- Client says: "We're reviewing the same boilerplate changes across 50 vendor contracts"
- High volume of contracts to review (10+/month) with standard-vs-custom clause detection needed
- Compliance requirements that demand every document is checked for specific provisions
- Review bottleneck on one or two people (lawyer, compliance officer) who can't keep up
- Client has existing "standard" templates they can compare against

**ROI framing:**
- Primary metric: Review time per document + risk reduction
- Typical range: 40–60% reduction in initial review time; reviewer focuses on flagged sections rather than reading cover-to-cover
- Risk reduction: Catch 95%+ of standard deviations vs. human fatigue-driven miss rate of 5–15% on long documents
- Executive one-liner: "Your legal team reviews every page of every contract. AI pre-screens and highlights only the sections that deviate from your standards — cutting review time in half and catching things tired eyes miss."

**Implementation complexity:** Standard Pilot
- Timeline: 4–6 weeks (includes building clause library, testing against historical contracts, calibrating sensitivity)
- Typical stack: LLM (Claude/GPT-4) with retrieval over client's standard templates and clause library; custom prompting for clause detection; UI layer (can be as simple as annotated PDF output or integration with contract management system)
- Solo consultant role: Build the pilot yourself. Work with client's legal/compliance team to define "standard" clauses and risk flags. Deploy as a review assistant, not a replacement.

**Red flags:**
- Client wants AI to make legal decisions or sign off on compliance (liability issue — AI assists, humans decide)
- No existing standard templates or clause libraries to compare against (you'd be building the baseline from scratch — scope carefully)
- Low contract volume (<5/month) — manual review may be faster than building and maintaining the system
- Highly regulated industry where AI-assisted review may face regulatory scrutiny (check with client's legal counsel first)
- Client expects perfection — contracts require 100% accuracy; position this as "catches more than humans alone" not "catches everything"

**Examples:**
- **Government contractor:** Review subcontractor agreements against FAR/DFAR clause requirements, flag missing flow-down provisions. (50–500 employees, 20+ subcontracts/quarter)
- **SaaS company:** Review vendor DPAs and security addenda against internal security requirements checklist. (100–300 employees, scaling vendor relationships)
- **Healthcare organization:** Check vendor BAAs for HIPAA compliance provisions, flag non-standard liability terms. (200–500 employees, dozens of vendor relationships)

---

### Document Summarization

**What it is:** AI condenses long documents (meeting transcripts, reports, legal filings, research papers) into structured summaries with key points, action items, and decisions highlighted. Turns "40 pages nobody reads" into "2 pages everyone acts on."

**When to recommend:**
- Client says: "No one reads the reports we produce — they're too long"
- Client says: "I spend an hour after every meeting writing up notes"
- Client says: "We need to review 20 vendor proposals and compare them"
- Long documents produced regularly that have a defined audience who needs key information but not full text
- Meeting-heavy culture with poor follow-through on decisions/action items
- Information overload: staff drowning in documents they should read but don't have time for

**ROI framing:**
- Primary metric: Time saved reading/processing documents + improved information retention
- Typical range: 80–90% reduction in reading time; key information actually reaches decision-makers
- Indirect ROI: Decisions made faster when leaders don't have to read 40-page reports to extract 5 key findings
- Executive one-liner: "Your team produces excellent analysis that nobody reads because it's buried in 30-page reports. AI creates executive summaries so the right information reaches the right people in the format they'll actually consume."

**Implementation complexity:** Quick Win
- Timeline: 1–2 weeks (often the simplest pattern to deploy — LLM + prompt engineering + output template)
- Typical stack: LLM API (Claude/GPT-4) with custom summarization prompts; output templates defining summary structure; optional integration with document management or meeting recording tool (Otter, Fireflies, Teams transcription)
- Solo consultant role: Build it yourself. Define summary templates with client, connect to document/meeting sources, deliver working automation.

**Red flags:**
- Documents contain highly sensitive information (legal privilege, M&A confidential, classified) — check data handling policies before sending to LLM APIs
- Summaries will be used for compliance purposes where full text review is legally required (AI summary ≠ legal review)
- Client has no consistent document format or structure (summarization works best with predictable document types)
- Client expects summaries to be 100% accurate with zero hallucination — always position with human spot-check workflow

**Examples:**
- **Professional services firm:** Summarize meeting transcripts into action items, decisions, and owner assignments. Distributed to attendees within 1 hour of meeting end. (50–200 employees, 20+ meetings/week producing action items)
- **Manufacturing company:** Summarize lengthy supplier quality audit reports into pass/fail with key findings for plant managers. (200–500 employees, monthly audit cycles)
- **Financial services:** Condense quarterly earnings transcripts and analyst reports into key takeaways for portfolio managers. (50–150 employees, research-heavy workflow)

---

### Automated Report Generation

**What it is:** AI generates standardized reports by pulling data from source systems and composing narrative sections following defined templates. Turns "someone spends a day compiling the monthly report" into a draft that needs 30 minutes of human review.

**When to recommend:**
- Client says: "We generate the same reports every month and most of it is copy-paste from dashboards"
- Client says: "Report day is everyone's least favorite day — it takes the whole team"
- Recurring reports with predictable structure (monthly business reviews, compliance reports, status updates)
- Data already exists in systems but requires human effort to compile, format, and narrate
- Reports have a defined audience and template (not ad-hoc analysis)
- Multiple people contribute sections that get assembled manually

**ROI framing:**
- Primary metric: Time to produce recurring reports
- Typical range: 70–90% reduction in report compilation time; from 1–2 days to 1–2 hours of review
- Quality improvement: Consistent formatting, no forgotten sections, data always current
- Executive one-liner: "Your team spends 2 days every month assembling the same report format with updated numbers. AI drafts it in minutes — your people review and refine instead of compile."

**Implementation complexity:** Quick Win
- Timeline: 1–3 weeks per report type (template definition + data source integration + narrative generation)
- Typical stack: LLM for narrative generation; data connectors to source systems (APIs, database queries, spreadsheet reads); templating engine for structure; output format (PDF, DOCX, email)
- Solo consultant role: Build it yourself. Map report structure, connect data sources, create generation prompts, deliver review workflow.

**Red flags:**
- Report contents vary dramatically month-to-month with heavy manual analysis (not a templating problem — needs human judgment)
- Data quality issues in source systems (garbage in = garbage out; fix data first)
- Client wants AI to generate insights/recommendations, not just compile data (different pattern — closer to analysis than report generation)
- No agreed-upon report template today (define the template with stakeholders first, then automate it)
- Report is the only time certain data gets reviewed — removing compilation may mean issues go unnoticed (maintain human review step)

**Examples:**
- **Manufacturing (gov-contractor):** Generate monthly contract status reports pulling from ERP (deliverables, milestones, spend) and composing narrative summaries for government program managers. (50–300 employees, multiple active contracts)
- **Managed services provider:** Generate weekly client status reports from ticketing system data (tickets opened/closed, SLA compliance, major incidents). (50–200 employees, 20+ client accounts)
- **Real estate firm:** Generate quarterly property performance reports from property management system data (occupancy, rent collections, maintenance spend, NOI). (30–150 employees, multiple properties)
