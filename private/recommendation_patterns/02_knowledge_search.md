# Knowledge Search Patterns

Make institutional knowledge findable and queryable. Solves the universal problem of information trapped in people's heads, scattered systems, or unsearchable file shares. These patterns transform "ask Steve" into "search the system" — critical for scaling and resilience.

**Who this applies to:** Any company where finding information is painful — scattered documentation, tribal knowledge, departing experts, or customers who can't self-serve. Especially high-value for knowledge-intensive businesses (professional services, engineering, compliance-heavy industries).

---

## Patterns

### Internal Knowledge Q&A (RAG)

**What it is:** A chat interface that lets employees ask questions in natural language and get answers sourced from company documents — SOPs, policies, handbooks, technical docs, past decisions. Uses Retrieval-Augmented Generation (RAG) to ground LLM responses in actual company content with source citations.

**When to recommend:**
- Client says: "New hires take months to find answers — they have to ask around"
- Client says: "The same questions get asked over and over in Slack/Teams"
- Client says: "We have documentation but nobody can find anything in it"
- Company has 100+ pages of documentation that people should reference but don't
- Onboarding time is a known pain point (weeks/months before new hires are productive)
- Knowledge is documented but scattered, poorly organized, or in formats people avoid reading
- Company has grown past the point where "just ask someone" scales

**ROI framing:**
- Primary metric: Time to answer saved + onboarding acceleration
- Typical range: 50–70% reduction in time employees spend searching for internal information; onboarding acceleration of 2–4 weeks
- Knowledge accessibility: Turns "documented but unfindable" into "ask and get an answer with source link in 10 seconds"
- Executive one-liner: "Your team spends 20% of their time looking for information that already exists somewhere. An AI knowledge assistant answers questions instantly with citations — like having your best employee available 24/7 to answer questions."

**Implementation complexity:** Standard Pilot
- Timeline: 4–6 weeks (document ingestion, chunking strategy, retrieval tuning, UI, user testing)
- Typical stack: Vector database (Pinecone, Weaviate, pgvector); embedding model (OpenAI, Cohere); LLM for generation (Claude/GPT-4); document connectors (SharePoint, Confluence, Google Drive, file shares); chat UI (custom or Slack/Teams bot)
- Solo consultant role: Build it yourself for the pilot. Ingest a focused document set (one department's SOPs or one knowledge domain), deploy a chat interface, iterate on retrieval quality. Scale with client team after pilot validation.

**Red flags:**
- Documentation doesn't exist (RAG can't retrieve what's never been written — you need Expert Knowledge Capture first)
- Documents are severely outdated or contradictory (system will surface wrong answers with confident citations — garbage in, garbage out)
- Client expects it to replace documentation governance ("we'll just ask the AI" without maintaining source docs = knowledge rot)
- Sensitive/classified documents with strict access controls (RAG must respect document-level permissions — adds significant complexity)
- Fewer than 50 pages of reference material (not enough content to justify the infrastructure — simpler FAQ might suffice)

**Examples:**
- **Manufacturing company:** Engineers ask questions about manufacturing processes, material specifications, and quality procedures. Sources: ISO docs, process manuals, engineering change orders. (100–500 employees, 500+ pages of technical documentation)
- **Professional services firm:** Consultants query past project approaches, methodologies, and templates. Sources: project documentation, methodology guides, engagement playbooks. (50–200 employees)
- **Healthcare organization:** Staff ask policy and procedure questions. Sources: P&P manual, compliance guidelines, departmental procedures. (200–500 employees, constantly updated regulatory landscape)

---

### Semantic Document Search

**What it is:** Upgrade traditional keyword search to meaning-based search across document repositories. Users search by describing what they need ("document about the thermal testing protocol for aluminum parts") instead of guessing exact keywords. Returns relevant documents ranked by semantic similarity.

**When to recommend:**
- Client says: "Our search never finds what people are looking for"
- Client says: "You have to know the exact filename or keyword to find anything"
- Client says: "People give up searching and just ask someone"
- Existing search produces poor results (keyword-only matching misses relevant documents)
- Large document repositories (1000+ documents) where browsing isn't feasible
- Documents use inconsistent terminology across departments or time periods
- Users frequently search for concepts rather than specific terms

**ROI framing:**
- Primary metric: Search success rate + time to find relevant documents
- Typical range: 3–5x improvement in search relevance; document retrieval time from 10–20 minutes of hunting to under 1 minute
- Indirect ROI: Reduces duplicate work (people who can't find existing docs create new ones)
- Executive one-liner: "Your team creates duplicate documents because they can't find existing ones. Semantic search means searching by concept instead of guessing keywords — found in seconds instead of never."

**Implementation complexity:** Standard Pilot
- Timeline: 3–5 weeks (document indexing, embedding pipeline, search interface, relevance tuning)
- Typical stack: Vector database; embedding model; document connectors to existing repositories; search UI (often integrated into existing portal or intranet); metadata filtering layer
- Solo consultant role: Build it yourself. Index existing document repositories, deploy search interface, tune relevance based on user feedback during pilot.

**Red flags:**
- Client has fewer than 200 documents (folder organization and naming conventions might be sufficient)
- Documents are primarily structured data (spreadsheets, databases) — not a semantic search problem
- Client's real issue is document creation/governance, not findability (search won't help if documents are outdated or don't exist)
- Multiple languages without clear delineation (multilingual semantic search is significantly harder)
- Client expects search to replace taxonomy/organization entirely (search works best alongside reasonable organization, not instead of it)

**Examples:**
- **Engineering firm:** Search across 10 years of project documentation, technical specifications, and engineering reports by concept. (100–300 employees, 50,000+ documents across multiple file shares)
- **Law firm:** Find relevant precedents, memos, and briefs by describing the legal concept or situation. (20–100 attorneys, decades of accumulated work product)
- **Government contractor:** Search across contract documentation, technical data packages, and regulatory references. (50–500 employees, documentation spanning multiple programs)

---

### Expert Knowledge Capture

**What it is:** Systematically extract and preserve the knowledge of experienced employees (especially those approaching retirement or departure) into a queryable, structured format. Uses AI-assisted interviews, document generation, and knowledge structuring to transform tacit expertise into explicit, searchable institutional memory.

**When to recommend:**
- Client says: "When [person] retires, we lose everything they know"
- Client says: "Only one person knows how to handle [critical process]"
- Client says: "We've lost so much knowledge from turnover in the last 2 years"
- Key employees approaching retirement with undocumented expertise
- Single points of failure — critical processes depend on one person's knowledge
- Recent or upcoming organizational changes (mergers, restructuring) that risk knowledge loss
- Apprenticeship-style roles where knowledge transfer currently takes years

**ROI framing:**
- Primary metric: Knowledge preserved + cross-training time reduced
- Typical range: Capture 60–80% of an expert's procedural and decision-making knowledge in structured, queryable form; reduce successor ramp-up time by 40–60%
- Risk reduction: Quantify the cost of one expert being unavailable for a week (delays, errors, lost institutional memory)
- Executive one-liner: "Your senior engineer carries 25 years of undocumented knowledge in their head. When they retire in 18 months, that knowledge leaves. AI-assisted capture preserves it in a searchable system their successor can query from day one."

**Implementation complexity:** Standard Pilot
- Timeline: 4–8 weeks per expert (structured interviews, documentation generation, validation cycles, system setup)
- Typical stack: Interview recording + transcription (Otter, Whisper); LLM for structuring and expanding interview content into documentation; knowledge base system (can feed into RAG system from pattern above); validation workflow for expert review
- Solo consultant role: Build the capture system and facilitate the process. Run structured interview sessions with the expert, use AI to generate initial documentation, have expert validate and correct, deploy into queryable format.

**Red flags:**
- Expert is unwilling to participate (knowledge capture requires cooperation — can't be forced)
- No plan for maintaining captured knowledge after the expert leaves (knowledge rots without governance)
- Client expects AI to completely replace the expert (captured knowledge covers documented procedures but not judgment/intuition for novel situations)
- Expert's knowledge is primarily relationship-based rather than procedural (AI can capture "how to do X" but not "who to call when Y breaks")
- Extremely narrow domain with only one expert and no successor identified (capture without a consumer is just archiving)

**Examples:**
- **Manufacturing company:** Capture senior machinist's knowledge of machine calibration, material handling quirks, and troubleshooting procedures before retirement. (100–500 employees, 30-year veteran)
- **Utility company:** Document experienced field engineer's knowledge of infrastructure (what's actually underground vs. what's on the maps, failure patterns, maintenance shortcuts). (200–500 employees)
- **Government contractor:** Preserve program manager's knowledge of customer relationships, contract history, and institutional memory of a long-running program. (50–300 employees, 15+ year program)

---

### Customer-Facing Knowledge Base

**What it is:** AI-powered self-service system that lets customers find answers to their questions without contacting support. Goes beyond static FAQ pages by understanding natural language questions and retrieving relevant answers from documentation, past tickets, and product information. Often deployed as a chatbot or enhanced search on the support portal.

**When to recommend:**
- Client says: "Customers call support for things that are in our documentation"
- Client says: "80% of our support tickets are the same 20 questions"
- Client says: "We can't scale support without hiring more people"
- High volume of repetitive support inquiries (50+ tickets/day with common question patterns)
- Existing documentation/FAQ that customers don't find or don't use
- Support team overwhelmed with L1 questions that have known answers
- Client wants to offer 24/7 support without 24/7 staffing

**ROI framing:**
- Primary metric: Support ticket deflection rate + customer resolution time
- Typical range: 30–50% deflection of L1 tickets; average resolution time for common questions drops from hours/days to seconds
- Cost savings: Each deflected ticket saves $5–25 in support cost (industry benchmark varies by complexity)
- Executive one-liner: "Half your support tickets have known answers buried in your docs. An AI knowledge base finds those answers for customers instantly — your support team handles only the complex issues that need a human."

**Implementation complexity:** Standard Pilot
- Timeline: 4–6 weeks (content ingestion, tuning for customer language, UI deployment, feedback loop)
- Typical stack: RAG system over support documentation + past ticket resolutions; customer-facing chat widget or enhanced search; analytics dashboard for deflection tracking; escalation path to human support when AI can't answer
- Solo consultant role: Build the pilot yourself. Ingest existing support docs and FAQ, deploy chat interface on support page, tune responses based on early user feedback. Hand off ongoing content maintenance to client's support team.

**Red flags:**
- Support documentation doesn't exist or is severely outdated (AI will surface wrong answers — fix docs first)
- Client's product is highly complex with issues that genuinely require human troubleshooting (AI can handle known questions but not novel debugging)
- Client has no way to measure deflection (can't prove ROI without before/after metrics — establish baseline first)
- Regulatory requirements for human interaction in support (financial services, healthcare advice — check compliance)
- Customer base prefers phone/human contact and will resist self-service (cultural fit matters)

**Examples:**
- **SaaS company:** Customer-facing chatbot that answers product configuration, billing, and troubleshooting questions from documentation and resolved tickets. (50–200 employees, 100+ support tickets/day)
- **E-commerce/retail:** AI-powered help center that answers questions about orders, returns, sizing, and product details. (100–500 employees, high-volume consumer support)
- **Industrial equipment manufacturer:** Customer portal where buyers find installation guides, maintenance procedures, and parts information through natural language search. (200–500 employees, complex product catalog)

---

### Cross-System Knowledge Federation

**What it is:** Unified search and query layer across multiple disconnected systems (SharePoint, Confluence, Google Drive, Slack, email, databases, ticketing systems). Eliminates the "where did I see that?" problem by providing a single search interface that understands content across all connected sources.

**When to recommend:**
- Client says: "Information is scattered across 5 different systems and nobody knows which one to check"
- Client says: "We have Confluence, SharePoint, AND Google Drive and nothing is consistent"
- Client says: "I spend 30 minutes searching multiple systems before I find what I need"
- Company uses 3+ knowledge/document systems with no unified access
- Frequent context-switching between systems to find information
- Information duplication and inconsistency across platforms (same doc in 3 places, different versions)
- M&A situation where two companies' systems haven't been consolidated

**ROI framing:**
- Primary metric: Time spent searching across systems + information duplication eliminated
- Typical range: 60–80% reduction in cross-system search time; single source of truth visibility reduces conflicting information
- Productivity: 15–30 minutes/day saved per knowledge worker (industry benchmarks for multi-system search overhead)
- Executive one-liner: "Your team searches 4 different systems to find one answer. Federated search gives them one place to look that covers everything — no more 'which system was that in?'"

**Implementation complexity:** Significant Build
- Timeline: 3–6 months (connector development per system, unified index, access control synchronization, UI, ongoing maintenance)
- Typical stack: Enterprise search platform (Elasticsearch/OpenSearch with vector extensions, or purpose-built like Glean/Coveo); connectors per source system (APIs, crawlers); unified embedding and index layer; access control sync (critical — must respect per-system permissions); search UI
- Solo consultant role: Architect and advise. This is too large for solo delivery in most cases. Design the architecture, evaluate build-vs-buy (Glean, Coveo, custom), select vendors, guide implementation team, validate delivery. Fractional Advisory engagement.

**Red flags:**
- Client has no budget for ongoing maintenance (connectors break when source systems update — this is not "set and forget")
- Source systems have incompatible access control models (synchronizing permissions across 5 systems is the hardest part)
- Client's real problem is governance, not search ("we have 3 systems because nobody agreed on one" — federation papers over the real problem)
- Fewer than 100 users (the ROI math doesn't work for small user populations — consolidate systems instead)
- Client expects perfect accuracy on day one (federated search improves over time with relevance tuning — set expectations)

**Examples:**
- **Post-acquisition company:** Two merged organizations with separate Confluence, SharePoint, and shared drives. Need unified access before full system consolidation (2-year project). (300–500 employees combined, 5+ systems)
- **Engineering organization:** Technical documentation in Confluence, project files in SharePoint, discussions in Slack, code in GitHub, tickets in Jira — engineers need to search concepts across all simultaneously. (100–300 employees, multiple dev teams)
- **Healthcare system:** Clinical protocols in one system, HR policies in another, training materials in a third, compliance docs in a fourth. Staff needs one place to search "what's our policy on X?" (200–500 employees, regulatory pressure for accessible policies)
