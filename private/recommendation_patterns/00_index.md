# AI Transformation Recommendation Patterns

Quick-reference index for identifying which AI solutions fit a client's situation. Use during or immediately after a discovery call: find the client's pain signals in the matrix below, then drill into the relevant category file for talking points, scoping guidance, and red flags.

This knowledge base covers 6 categories with 25+ patterns accessible to companies with 50–500 employees.

---

## Quick Decision Matrix

When a client says something like the signal below, recommend the corresponding pattern.

| Client Pain Signal | Category | Pattern | Complexity |
|---|---|---|---|
| "We spend days manually entering data from invoices/forms" | Document Processing | Intelligent Document Extraction | Quick Win |
| "Incoming documents get lost or go to the wrong person" | Document Processing | Document Classification & Routing | Quick Win |
| "Contract review takes weeks and we still miss clauses" | Document Processing | Contract/Compliance Review | Standard Pilot |
| "No one reads the 40-page reports we produce" | Document Processing | Document Summarization | Quick Win |
| "We generate the same reports manually every month" | Document Processing | Automated Report Generation | Quick Win |
| "New hires take months to find answers in our docs" | Knowledge Search | Internal Knowledge Q&A (RAG) | Standard Pilot |
| "Our search never finds what people are looking for" | Knowledge Search | Semantic Document Search | Standard Pilot |
| "When [expert] retires, we lose everything they know" | Knowledge Search | Expert Knowledge Capture | Standard Pilot |
| "Customers call support for things that are in our docs" | Knowledge Search | Customer-Facing Knowledge Base | Standard Pilot |
| "Information is scattered across 5 different systems" | Knowledge Search | Cross-System Knowledge Federation | Significant Build |
| "3 people just move emails to the right department all day" | Workflow Automation | Email/Intake Triage & Routing | Quick Win |
| "Approvals sit in someone's inbox for a week" | Workflow Automation | Approval Workflow Acceleration | Standard Pilot |
| "We have people who just copy data between systems" | Workflow Automation | Data Entry & Reconciliation | Quick Win |
| "We don't know where things get stuck in our process" | Workflow Automation | Process Bottleneck Detection | Standard Pilot |
| "Every order touches 4 systems and someone manually connects them" | Workflow Automation | Multi-Step Orchestration | Significant Build |
| "Each proposal takes 3 days and we rewrite 80% from scratch" | Proposal/Content Generation | Proposal/RFP Draft Generation | Standard Pilot |
| "We need to send personalized outreach but can't scale it" | Proposal/Content Generation | Personalized Outreach at Scale | Quick Win |
| "Monthly reports take a full day to compile from spreadsheets" | Proposal/Content Generation | Template-Based Report Generation | Quick Win |
| "Marketing can't produce content fast enough" | Proposal/Content Generation | Marketing Content Acceleration | Quick Win |
| "SOWs take forever and have inconsistent terms" | Proposal/Content Generation | SOW/Contract Drafting | Standard Pilot |
| "We don't know which customers are about to leave" | Customer Intelligence | Churn Risk Prediction | Standard Pilot |
| "We get hundreds of reviews/tickets but can't see trends" | Customer Intelligence | Customer Sentiment Analysis | Standard Pilot |
| "We treat all customers the same regardless of value" | Customer Intelligence | Customer Segmentation | Standard Pilot |
| "Our devs spend too much time on boilerplate code" | Code/Engineering | AI Coding Copilot Adoption | Quick Win |
| "We have no tests and can't refactor safely" | Code/Engineering | Automated Test Generation | Quick Win |
| "Code reviews are a bottleneck — PRs sit for days" | Code/Engineering | Code Review Augmentation | Quick Win |
| "Nobody knows how the legacy system works anymore" | Code/Engineering | Legacy Code Comprehension | Standard Pilot |

---

## Category Summaries

### 1. Document Processing
**File:** `01_document_processing.md`

Automate the extraction, classification, routing, and summarization of documents. The most universal AI entry point — every company has documents that consume human time.

**Patterns:**
- Intelligent Document Extraction
- Document Classification & Routing
- Contract/Compliance Review
- Document Summarization
- Automated Report Generation

**Accessibility for 50–500 person companies:** ⬆️ High
**Typical entry point:** "We have people who spend hours copying data from documents into systems"

---

### 2. Knowledge Search
**File:** `02_knowledge_search.md`

Make institutional knowledge findable and queryable. Solves the universal problem of information trapped in people's heads, scattered systems, or unsearchable file shares.

**Patterns:**
- Internal Knowledge Q&A (RAG)
- Semantic Document Search
- Expert Knowledge Capture
- Customer-Facing Knowledge Base
- Cross-System Knowledge Federation

**Accessibility for 50–500 person companies:** ⬆️ High
**Typical entry point:** "New employees take months to get up to speed because knowledge lives in people's heads"

---

### 3. Workflow Automation
**File:** `03_workflow_automation.md`

Use AI to route, triage, accelerate, and connect workflows that currently depend on humans as the glue between systems. Highest ROI potential when processes span multiple tools.

**Patterns:**
- Email/Intake Triage & Routing
- Approval Workflow Acceleration
- Data Entry & Reconciliation
- Process Bottleneck Detection
- Multi-Step Orchestration

**Accessibility for 50–500 person companies:** ⬆️ High
**Typical entry point:** "We have people whose entire job is moving information between systems"

---

### 4. Proposal/Content Generation
**File:** `04_proposal_content_generation.md`

Generate first drafts of proposals, reports, outreach, and contracts from templates and data. High-value for companies that produce repetitive written output at volume.

**Patterns:**
- Proposal/RFP Draft Generation
- Personalized Outreach at Scale
- Template-Based Report Generation
- Marketing Content Acceleration
- SOW/Contract Drafting

**Accessibility for 50–500 person companies:** ⬆️ High
**Typical entry point:** "We respond to RFPs constantly and every proposal starts from scratch"

---

### 5. Customer Intelligence
**File:** `05_customer_intelligence.md`

Analyze customer behavior, feedback, and interactions to predict churn, identify segments, and surface actionable trends. Requires existing customer data — check data maturity first.

**Patterns:**
- Customer Sentiment Analysis
- Churn Risk Prediction
- Customer Segmentation
- Voice of Customer Synthesis
- Sales Intelligence & Lead Scoring

**Accessibility for 50–500 person companies:** ➡️ Medium
**Typical entry point:** "We're losing customers and don't know why until it's too late"
**⚠️ Prerequisite:** Company must have 12+ months of customer interaction data in a queryable format (CRM, support system, or structured export).

---

### 6. Code/Engineering Acceleration
**File:** `06_code_engineering_acceleration.md`

Accelerate software development through AI coding assistants, automated testing, and documentation generation. Only applicable to companies with in-house dev teams.

**Patterns:**
- AI Coding Copilot Adoption
- Automated Test Generation
- Code Review Augmentation
- Technical Documentation Generation
- Legacy Code Comprehension

**Accessibility for 50–500 person companies:** ➡️ Medium
**Typical entry point:** "Our dev team is too small for the backlog we have"
**⚠️ Prerequisite:** Company has an in-house development team (even 3–5 engineers).

---

## Implementation Complexity Legend

| Level | Timeline | Typical Cost | Consultant Role | Service Mapping |
|---|---|---|---|---|
| **Quick Win** | 1–2 weeks | <$10k | Build and deliver yourself | Delivered within Assessment Sprint or small add-on |
| **Standard Pilot** | 4–8 weeks | $10–50k | Build MVP yourself, client validates | Pilot Development service |
| **Significant Build** | 3–6 months | $50–200k | Architect + advise, client team or vendor implements | Fractional Advisory + implementation partner |

**Cost note:** Ranges reflect total implementation cost including your fees. For Quick Wins, your Assessment Sprint ($1.5–5k) often covers it. For Standard Pilots, your Pilot Development fee is the majority. For Significant Builds, your advisory role is a fraction of total project cost.

---

## How to Use This Reference

**During/after a discovery call:**

1. **Listen for pain signals** — Client describes a frustration or time sink
2. **Find the signal in the matrix** — Match their language to the closest row
3. **Note the pattern + complexity** — This tells you what to recommend and how to scope it
4. **Open the category file** — Get detailed talking points, ROI framing, red flags, and examples
5. **Map to your services** — Quick Win = can include in Assessment Sprint; Standard Pilot = propose Pilot Development; Significant Build = propose Fractional Advisory engagement

**Before a discovery call:**

1. Research the client's industry
2. Scan the matrix for signals likely in their domain
3. Pre-load 2–3 category files so you have talking points ready
4. Listen for those signals but hold recommendations loosely — let the client's actual pain guide you

**Red flag check:** Always read the "Red Flags" section in the category file before recommending. Some patterns look attractive but fail without prerequisites (data maturity, system access, executive sponsorship).
