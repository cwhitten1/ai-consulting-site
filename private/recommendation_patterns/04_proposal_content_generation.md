# Proposal & Content Generation Patterns

Use AI to draft, personalize, and accelerate the creation of business documents — proposals, outreach, reports, contracts, and marketing content. These patterns turn "staring at a blank page" into "editing a solid first draft." Most accessible when the company already has templates, past examples, or repeatable formats.

**Who this applies to:** Any company that produces recurring written deliverables — RFP responses, sales proposals, SOWs, monthly reports, client communications, or marketing content. Particularly high-value for professional services, government contractors, agencies, and B2B companies with heavy proposal workloads.

---

## Patterns

### Proposal/RFP Draft Generation

**What it is:** AI generates first-draft proposals or RFP responses by combining RFP requirements with the company's past proposals, capability statements, case studies, and boilerplate. Produces a structured response that humans refine rather than write from scratch.

**When to recommend:**
- Client says: "We spend 3 days on every proposal and we respond to 5 a month"
- Client says: "Our best proposal writer is a bottleneck — nothing ships without them"
- Client says: "We keep rewriting the same capability descriptions for every RFP"
- Company responds to 4+ RFPs/proposals per month
- Proposals follow predictable structures (government RFPs with section requirements, industry-standard formats)
- Existing library of past proposals, capability statements, and boilerplate sections
- Win rate suffering because team can't respond to enough RFPs or responses feel rushed

**ROI framing:**
- Primary metric: Time to produce first draft + proposal volume capacity
- Typical range: 50–70% reduction in first-draft creation time; capacity to respond to 2–3x more RFPs without adding staff
- Quality uplift: Consistent messaging, no forgotten sections, compliance matrix auto-populated
- Executive one-liner: "Your team spends 3 days writing each proposal from scratch. AI produces an 80% complete first draft in hours using your past wins — your experts spend time refining strategy, not rewriting boilerplate."

**Implementation complexity:** Standard Pilot
- Timeline: 4–6 weeks (ingest past proposals, build retrieval system, create generation pipeline, calibrate quality)
- Typical stack: RAG system over past proposals and capability library; LLM (Claude/GPT-4) for draft generation; RFP parser to extract requirements and compliance matrices; output templates matching client's proposal format
- Solo consultant role: Build it yourself. Ingest client's proposal library, build retrieval + generation pipeline, deliver review workflow. Ongoing tuning as win/loss data comes in.

**Red flags:**
- Client has fewer than 10 past proposals to learn from (insufficient reference material — build the library first)
- Every proposal is highly custom with little reuse (AI adds less value when there's no boilerplate to leverage)
- Client expects AI-generated proposals to go out without human review (proposals are brand-critical — always human-finalized)
- No consistent proposal structure or template today (define the template first, then automate filling it)
- Heavily classified or ITAR-restricted content that can't be processed by commercial LLM APIs (on-premise deployment required — significantly increases complexity)

**Examples:**
- **Government contractor:** Generate first drafts of technical volumes for DoD RFPs by pulling relevant past performance, capability descriptions, and technical approaches from proposal library. (50–300 employees, 5–15 proposals/quarter)
- **IT services company:** Auto-draft managed services proposals using client discovery notes, standard service descriptions, and pricing templates. (100–400 employees, 8+ proposals/month)
- **Engineering/architecture firm:** Generate qualifications packages and proposal narratives from project history database and staff resumes. (50–200 employees, responding to public RFQs)

---

### Personalized Outreach at Scale

**What it is:** AI generates tailored emails, messages, or communications by combining prospect/customer research with templates and value propositions. Each message is customized to the recipient's industry, role, pain points, or recent activity — without manually researching and writing each one.

**When to recommend:**
- Client says: "Our sales team sends generic emails and gets 2% response rates"
- Client says: "We know personalization works but we can't afford the time for 200 prospects"
- Client says: "Our best rep personalizes everything and gets 3x the meetings — we can't scale that"
- Sales/BD team sending 50+ outreach messages per week
- Clear value propositions that map to different segments, industries, or roles
- CRM or prospect data available (company size, industry, role, recent activity)
- Response rates below industry benchmarks due to generic messaging

**ROI framing:**
- Primary metric: Response/reply rate improvement + time per personalized message
- Typical range: 2–4x improvement in response rates; personalization time from 15–20 min/message to 1–2 min (review only)
- Pipeline impact: More meetings booked per rep without increasing headcount
- Executive one-liner: "Your reps either send generic emails that get ignored or spend 20 minutes personalizing each one. AI personalizes at scale — every prospect gets a relevant message, and your team books 2–3x more meetings."

**Implementation complexity:** Quick Win
- Timeline: 1–2 weeks (template creation, prospect data integration, generation workflow)
- Typical stack: LLM (Claude/GPT-4) for personalization; CRM data (HubSpot, Salesforce) for prospect context; LinkedIn/web scraping for research signals; email sequencing tool integration (Outreach, Apollo, HubSpot Sequences)
- Solo consultant role: Build it yourself. Create prompt templates, connect prospect data sources, deliver generation workflow that sales team can operate independently.

**Red flags:**
- Client has no clear ideal customer profile or value propositions (AI can't personalize without knowing what to personalize toward — fix messaging first)
- Outreach volume is <20/week (manual personalization is feasible and often better at this scale)
- Client expects AI to replace relationship-building (personalization ≠ authenticity — works for initial outreach, not deep relationship comms)
- Industry/audience where AI-generated content is easily detected and negatively perceived (executive selling, high-touch enterprise sales)
- No CRM or prospect data to personalize from (garbage in, generic out)

**Examples:**
- **B2B SaaS company:** Generate personalized demo request follow-ups and cold outreach based on prospect's company size, tech stack, and recent funding/hiring signals. (50–200 employees, 3–10 reps)
- **Staffing agency:** Personalize candidate outreach based on their resume, recent job changes, and skill match to open roles. (50–300 employees, high-volume outreach)
- **Consulting firm:** Generate tailored thought leadership follow-ups to event attendees based on their industry and stated challenges. (20–100 employees, business development driven)

---

### Template-Based Report Generation

**What it is:** AI auto-populates recurring reports by pulling data from source systems and composing narrative sections following defined templates. Differs from Document Summarization (Category 1) in that it *creates new content* from structured data rather than condensing existing text.

**When to recommend:**
- Client says: "The monthly report takes the whole team a day to compile"
- Client says: "We pull the same numbers from 5 systems every week and paste them into a deck"
- Client says: "Our client reports are always late because they're manual"
- Recurring reports on predictable schedules (weekly, monthly, quarterly)
- Report structure is standardized (same sections, same metrics, same format every period)
- Data already exists in systems — the work is compilation, formatting, and narrative, not analysis
- Multiple people contribute sections or the same person does it repeatedly

**ROI framing:**
- Primary metric: Report compilation time + delivery consistency
- Typical range: 70–90% reduction in compilation time; from 1–2 days to 1–2 hours of review
- Reliability: Reports never late, never missing sections, always formatted consistently
- Executive one-liner: "Your team spends 2 days every month assembling reports from 5 systems. AI compiles the draft in minutes — your team reviews and adds insight instead of copying data."

**Implementation complexity:** Quick Win
- Timeline: 1–3 weeks per report type (template definition, data connectors, narrative generation)
- Typical stack: Data connectors (APIs, database queries, spreadsheet reads); LLM for narrative sections; templating engine for structure; output format (PDF, DOCX, slides, email)
- Solo consultant role: Build it yourself. Map report structure with client, connect data sources, build generation pipeline, deliver review workflow.

**Red flags:**
- Report content requires significant human judgment or interpretation each period (AI can compile but can't do novel analysis)
- Data quality issues in source systems — automation amplifies bad data
- No agreed-upon report template today (define the template first with stakeholders)
- Report only produced a few times per year (ROI of automation may not justify setup for infrequent reports)
- Client wants to eliminate the report entirely (maybe the right answer is a live dashboard, not an automated report)

**Examples:**
- **Managed services provider:** Generate weekly client status reports from ticketing data (SLA compliance, incident summaries, open issues). (50–200 employees, 15+ client accounts)
- **Manufacturing company:** Generate monthly production reports from ERP data (output volumes, quality metrics, downtime analysis, narrative commentary). (100–500 employees, multiple product lines)
- **Real estate / property management:** Generate quarterly investor reports from property management data (occupancy, rent rolls, maintenance spend, NOI). (30–150 employees, multiple properties)

---

### Marketing Content Acceleration

**What it is:** AI generates marketing content drafts — blog posts, case studies, social media content, newsletters — from seed material like interviews, product releases, customer conversations, or data. Accelerates the content pipeline without requiring more writers.

**When to recommend:**
- Client says: "We know we should be publishing content but we don't have time to write"
- Client says: "We have one marketing person doing everything — they can't keep up"
- Client says: "Our subject matter experts won't write but they'll talk for 30 minutes"
- Content strategy exists but execution is bottlenecked on writing capacity
- Subject matter expertise exists internally but isn't captured in written form
- Publishing cadence goals are missed regularly (blog target: 4/month, actual: 1/month)
- Seed material exists: customer conversations, product docs, internal presentations, data

**ROI framing:**
- Primary metric: Content production velocity + cost per piece
- Typical range: 3–5x increase in content output with same team; draft time from 4–8 hours to 1–2 hours of editing
- Pipeline impact: Consistent publishing cadence builds organic visibility and inbound leads over 6–12 months
- Executive one-liner: "Your marketing team has a backlog of 30 content ideas they'll never get to. AI generates first drafts from your experts' knowledge — they publish 4x more without hiring another writer."

**Implementation complexity:** Quick Win
- Timeline: 1–2 weeks (workflow setup, prompt engineering, brand voice calibration)
- Typical stack: LLM (Claude/GPT-4) for draft generation; transcription tool (Otter, Fireflies) for interview-to-content pipeline; style guide and brand voice examples for calibration; CMS integration for publishing workflow
- Solo consultant role: Build it yourself. Create content generation workflows (interview→draft, data→post, product update→announcement), calibrate brand voice, train team to operate independently.

**Red flags:**
- No content strategy or topic plan (AI can't decide what to write about — strategy comes first)
- Brand voice is highly distinctive and nuanced (heavy editing may negate time savings — test early)
- Industry requires high technical accuracy where hallucination risk is unacceptable (medical, legal, financial — heavier review needed)
- Client expects AI content to be publish-ready without human editing (always position as "draft acceleration" not "auto-publishing")
- SEO is the primary goal but no keyword strategy exists (AI content without SEO direction won't rank)

**Examples:**
- **B2B technology company:** Generate blog posts from product release notes, customer success stories from support tickets, and LinkedIn posts from executive talking points. (50–200 employees, marketing team of 1–3)
- **Professional services firm:** Generate thought leadership articles from partner interviews and conference presentations. (50–300 employees, reputation-driven business development)
- **E-commerce company:** Generate product descriptions, seasonal campaign copy, and email newsletters from product data and promotional calendars. (30–150 employees, 100+ SKUs)

---

### SOW/Contract Drafting

**What it is:** AI generates scoping documents, statements of work, and contract drafts from discovery notes, templates, and project parameters. Turns "2 days of document assembly" into "review and customize a pre-built draft" for standard engagement types.

**When to recommend:**
- Client says: "Every SOW takes 2 days to write and we're always behind on getting them out"
- Client says: "We have standard services but every SOW is written from scratch"
- Client says: "Prospects go cold while we're still writing the SOW"
- Standard service offerings with repeatable scoping parameters
- Discovery/sales process produces structured notes about client needs
- SOW creation is a bottleneck between verbal agreement and signed contract
- Library of past SOWs/contracts available to learn patterns from

**ROI framing:**
- Primary metric: SOW turnaround time + deal cycle acceleration
- Typical range: 60–80% reduction in drafting time; SOW delivered in hours instead of days
- Revenue impact: Faster SOW = shorter sales cycle = faster revenue recognition
- Executive one-liner: "Every day between 'yes' and a signed SOW is a day the client might change their mind. AI drafts the SOW same-day from your discovery notes — you close faster."

**Implementation complexity:** Standard Pilot
- Timeline: 3–5 weeks (template ingestion, parameter extraction from notes, generation pipeline, legal review workflow)
- Typical stack: RAG over past SOWs and contract templates; LLM for draft generation; structured extraction from discovery notes (key parameters: scope, timeline, pricing, assumptions); output in client's document format; review/approval workflow
- Solo consultant role: Build it yourself. Ingest past SOWs, create generation pipeline from discovery notes, establish legal/leadership review workflow before send.

**Red flags:**
- No standard service offerings or pricing (every engagement is truly custom — AI adds less value without patterns to leverage)
- Legal/compliance team requires every SOW to be drafted by legal (AI draft won't be accepted into their workflow)
- Client has fewer than 10 past SOWs to learn from (insufficient pattern base)
- SOW complexity varies enormously between engagements (works best for standardized services, not bespoke projects)
- No discovery process producing structured notes (input quality determines output quality)

**Examples:**
- **IT services company:** Generate managed services SOWs from pre-sales assessment findings — scope, SLAs, pricing tiers, transition plan. Delivered same-day after assessment call. (50–300 employees, 10+ new clients/quarter)
- **Consulting firm:** Draft engagement letters and SOWs from discovery call notes using standard engagement type templates (advisory, assessment, implementation). (20–100 employees, project-based revenue)
- **Government contractor:** Generate task order responses from teaming agreements and BOE templates, pulling relevant past performance and labor categories. (50–500 employees, IDIQ contract holders)
