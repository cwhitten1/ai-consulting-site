# Customer Intelligence Patterns

Use AI to analyze customer behavior, feedback, and interactions to predict outcomes, segment audiences, and surface actionable insights. These patterns require more data maturity than other categories — the company needs clean, accessible customer data before AI can extract value from it.

**Who this applies to:** Companies with existing customer bases generating behavioral data (transactions, support interactions, feedback, usage patterns). B2B and B2C with 500+ customers. Particularly high-value for subscription/recurring revenue businesses, companies with high acquisition costs, and organizations drowning in unstructured customer feedback.

**Data maturity prerequisite:** Most 50–500 person companies underestimate how much data cleanup is needed. Before recommending these patterns, verify: Is customer data centralized in a CRM? Are key events tracked? Is the data clean enough to analyze? If not, scope data readiness as a prerequisite project.

---

## Patterns

### Customer Sentiment Analysis

**What it is:** AI aggregates and analyzes customer feedback across channels — support tickets, reviews, surveys, social media, NPS responses — to identify sentiment trends, emotional drivers, and satisfaction patterns at scale. Turns scattered feedback into a unified voice-of-customer signal.

**When to recommend:**
- Client says: "We get tons of feedback but nobody synthesizes it — we react to the loudest complaints"
- Client says: "We don't know if customers are happy until they leave"
- Client says: "Our NPS is a number but we don't understand *why* it moves"
- Multiple feedback channels generating data nobody has time to read holistically
- Customer-facing teams (support, success, sales) have anecdotal insights but no systematic view
- Leadership makes product/service decisions without understanding customer sentiment drivers
- 500+ customers generating regular feedback (surveys, tickets, reviews)

**ROI framing:**
- Primary metric: Time to insight from feedback + quality of customer understanding
- Typical range: Process 10–100x more feedback signals than manual review; identify emerging issues 2–4 weeks earlier
- Retention impact: Early detection of satisfaction drops enables intervention before churn
- Executive one-liner: "You have thousands of customer signals scattered across 5 channels that nobody has time to read. AI synthesizes them into 'here's what customers are actually saying and here's what's changing' — every week, automatically."

**Implementation complexity:** Standard Pilot
- Timeline: 4–6 weeks (data integration across channels, sentiment model calibration, dashboard/reporting setup)
- Typical stack: LLM for nuanced sentiment analysis (beyond pos/neg — intent, emotion, topic); data connectors to support system (Zendesk, Freshdesk), survey tools (SurveyMonkey, Typeform), review platforms; aggregation layer; reporting dashboard or weekly digest
- Solo consultant role: Build it yourself for the analysis pipeline. May recommend BI tool (Metabase, Looker) for dashboards if client needs ongoing self-service visualization.

**Red flags:**
- Fewer than 100 feedback data points per month (insufficient volume for meaningful trend analysis)
- Client has no action framework — they'll see the sentiment data but won't change behavior (start with "what decisions would this inform?")
- Feedback is primarily from one channel and skews negative (support tickets) — need balanced input sources for accurate picture
- Client expects real-time individual intervention ("alert when any customer is upset") — this is a different pattern (churn prediction), not sentiment analysis
- No CRM or customer identity linking — can't connect feedback across channels to the same customer

**Examples:**
- **SaaS company:** Analyze support tickets + NPS comments + G2 reviews to identify top product friction points and track sentiment by feature area over time. (100–400 employees, 1000+ customers)
- **E-commerce / D2C brand:** Aggregate product reviews, post-purchase survey responses, and social mentions to identify quality issues and feature requests by product line. (50–200 employees, high review volume)
- **Healthcare services:** Analyze patient satisfaction surveys, online reviews, and complaint logs to identify service delivery patterns affecting satisfaction scores. (100–500 employees, regulatory pressure on patient satisfaction metrics)

---

### Churn Risk Prediction

**What it is:** AI identifies at-risk customers by analyzing behavioral signals — declining usage, reduced engagement, support escalations, payment delays, negative sentiment — and scores accounts by likelihood of churning before they actually leave. Enables proactive retention intervention.

**When to recommend:**
- Client says: "We only know a customer is leaving when they send the cancellation email"
- Client says: "We lose 15% of customers annually and we don't understand why"
- Client says: "Our CSMs manage too many accounts to notice warning signs"
- Subscription or recurring revenue model where retention directly impacts revenue
- Customer data available: usage/login frequency, support interactions, billing history, engagement metrics
- Churn rate is a known problem (10%+ annual) with no early warning system
- Customer success team exists but is reactive rather than proactive

**ROI framing:**
- Primary metric: Early warning lead time + retention rate improvement
- Typical range: Identify at-risk accounts 30–90 days before churn; reduce churn by 10–25% through early intervention
- Revenue impact: For a company with $5M ARR and 15% churn, reducing churn by 5 points = $250K retained revenue/year
- Executive one-liner: "You lose customers you didn't know were unhappy. AI watches 20 behavioral signals and tells your success team exactly which accounts need attention *today* — before the cancellation email arrives."

**Implementation complexity:** Standard Pilot
- Timeline: 6–8 weeks (data integration, feature engineering, model training/calibration, CS workflow integration)
- Typical stack: Data pipeline pulling usage, support, billing signals; ML model (gradient boosted trees or LLM-based scoring) for risk prediction; integration with CRM/CS platform (Gainsight, ChurnZero, or simply HubSpot/Salesforce fields); alerting workflow for CS team
- Solo consultant role: Build the pilot yourself if data is accessible. For ongoing model maintenance, either train client's data team or recommend a platform (ChurnZero, Gainsight) for long-term operation.

**Red flags:**
- Fewer than 200 customers or fewer than 50 historical churn events (insufficient data to train meaningful predictions)
- No customer usage/behavioral data tracked (only billing data = limited signals; need engagement data)
- Client has no customer success team or retention process (predictions without intervention capability = wasted effort)
- Client expects 100% prediction accuracy (no model catches every churner — position as "prioritization tool" not "crystal ball")
- Churn is driven primarily by external factors (market shifts, budget cuts) not satisfaction/engagement (model can't predict external events)
- Short customer lifecycle (<3 months average) — insufficient time for early warning to matter

**Examples:**
- **B2B SaaS:** Score customer accounts weekly based on login frequency decline, support ticket volume spike, feature adoption stalls, and contract renewal proximity. Surface top-10 at-risk accounts to CS team. (100–300 employees, 500+ B2B customers)
- **Subscription services company:** Predict subscriber churn from usage pattern changes, billing failures, and engagement decline. Trigger automated re-engagement campaigns + CSM outreach for high-value accounts. (50–200 employees, 5000+ subscribers)
- **Professional services firm:** Identify client accounts showing reduced engagement (fewer meetings, slower response to proposals, declining project scope) as early signals of switching firms. (50–150 employees, relationship-driven revenue)

---

### Customer Segmentation

**What it is:** AI-driven clustering that groups customers by behavior, value, needs, or lifecycle stage — going beyond basic demographic segmentation to discover natural groupings the business hasn't seen. Enables differentiated treatment: messaging, pricing, service levels, product development prioritization.

**When to recommend:**
- Client says: "We treat all customers the same but they clearly have different needs"
- Client says: "We know our top 10 accounts but have no strategy for the other 500"
- Client says: "Our marketing messages feel generic because they go to everyone"
- Growing customer base (200+) where one-size-fits-all approach is losing effectiveness
- Customer data available: purchase history, product mix, engagement levels, demographics, support patterns
- Business decisions currently made without segment understanding (pricing, marketing, product roadmap)
- Revenue concentration risk — top 10% of customers = 50%+ of revenue, no strategy for developing mid-tier

**ROI framing:**
- Primary metric: Revenue per customer segment + marketing efficiency
- Typical range: 15–30% improvement in campaign response rates through segment-targeted messaging; identification of underserved segments representing 10–20% revenue growth opportunity
- Strategic impact: Data-driven resource allocation — invest in segments with growth potential, manage at-risk segments differently
- Executive one-liner: "You have 500 customers and treat them all identically. AI reveals 4–6 natural segments with different needs — so you can target your limited resources where they'll generate the most growth."

**Implementation complexity:** Standard Pilot
- Timeline: 4–6 weeks (data integration, exploratory analysis, clustering, validation with business stakeholders, operationalization)
- Typical stack: Customer data warehouse or CRM export; clustering algorithms (k-means, DBSCAN) or LLM-based behavioral grouping; visualization for stakeholder alignment; CRM tagging for operationalization; optional: LLM for generating segment narratives/personas
- Solo consultant role: Build the analysis yourself. Critical to involve business stakeholders in interpreting and naming segments — AI clusters, humans assign meaning and strategy.

**Red flags:**
- Fewer than 200 customers (insufficient data for meaningful clustering — manual segmentation is fine at this scale)
- Customer data is sparse or incomplete (clustering on bad data produces meaningless segments)
- Client has no capacity to act differently per segment (segmentation without differentiated treatment is an academic exercise)
- Business is purely transactional with no ongoing relationship (limited behavioral data to cluster on)
- Client expects segments to be permanent (segments shift over time — needs periodic refresh)

**Examples:**
- **B2B services company:** Segment accounts by engagement level, growth trajectory, service mix, and support needs. Discover "at risk" segment (declining engagement, single product), "growth opportunity" segment (expanding but under-served), and "anchor" segment (stable, high-value). (50–200 employees, 300+ accounts)
- **E-commerce company:** Cluster customers by purchase frequency, average order value, category preferences, and return rates. Discover high-value loyalists, bargain hunters, seasonal buyers, and one-time purchasers for differentiated retention strategies. (50–300 employees, 5000+ customers)
- **SaaS platform:** Segment users by feature adoption patterns, login frequency, support needs, and expansion signals. Identify power users (upsell candidates), at-risk users (intervention needed), and new users (onboarding optimization). (100–400 employees, 1000+ accounts)

---

### Voice of Customer Synthesis

**What it is:** AI summarizes themes, patterns, and insights across hundreds or thousands of customer interactions — synthesizing what customers are *really* asking for versus what individual conversations surface. Transforms scattered qualitative data into structured strategic input for product, service, and business decisions.

**When to recommend:**
- Client says: "We have 10,000 support tickets but no idea what the top themes are"
- Client says: "Product decisions are based on who yells loudest, not systematic customer input"
- Client says: "We do quarterly surveys but the free-text responses just pile up unread"
- Large volume of qualitative customer data accumulating unprocessed (tickets, calls, chat logs, survey comments)
- Product/leadership team makes decisions without systematic customer input
- Customer-facing teams have tribal knowledge about what customers want but can't quantify it
- No current process for synthesizing feedback into product/strategy decisions

**ROI framing:**
- Primary metric: Coverage of customer feedback analyzed + time from feedback to decision input
- Typical range: Analyze 100% of feedback (vs. manual sampling of 5–10%); identify emerging themes 4–8 weeks earlier
- Decision quality: Product roadmap decisions backed by systematic customer evidence rather than anecdote
- Executive one-liner: "You have 10,000 data points about what customers want, buried in tickets and surveys nobody reads completely. AI reads all of them and tells you the top 5 themes every month — so product decisions are based on evidence, not guesswork."

**Implementation complexity:** Standard Pilot
- Timeline: 4–6 weeks (data integration, theme extraction pipeline, validation, reporting cadence)
- Typical stack: LLM for theme extraction and summarization (Claude/GPT-4); data connectors to ticket system, survey platform, call transcripts; aggregation and trend tracking; output as periodic report or dashboard
- Solo consultant role: Build it yourself. Create the extraction pipeline, define taxonomy with product/leadership, deliver as periodic synthesis reports. Train product team to interpret and act on outputs.

**Red flags:**
- Fewer than 500 feedback data points available (manual reading is feasible and often richer at this scale)
- Client has no product management or decision-making process to consume the insights (insights without action = waste)
- Feedback is primarily from support (skewed negative) with no positive signal sources (satisfaction surveys, reviews, usage data) — need balanced picture
- Client expects AI to make product decisions (AI synthesizes and surfaces themes — humans decide priorities)
- No feedback collection in place yet (start with collecting, not analyzing — you can't synthesize what doesn't exist)

**Examples:**
- **SaaS company:** Monthly synthesis of all support tickets, NPS verbatims, and sales call notes into top feature requests, friction points, and emerging needs by customer segment. Fed directly into quarterly product planning. (100–400 employees, high feedback volume)
- **Healthcare organization:** Synthesize patient feedback across satisfaction surveys, complaint logs, and online reviews into actionable themes for service improvement. (200–500 employees, regulatory incentives for patient experience)
- **Financial services:** Aggregate client feedback from advisor notes, service calls, and digital banking reviews to identify service gaps and product opportunities. (100–500 employees, relationship-driven business)

---

### Sales Intelligence & Lead Scoring

**What it is:** AI enriches leads with contextual signals (company growth, tech stack, recent events, fit indicators) and scores them by likelihood to convert based on historical patterns. Enables sales teams to focus effort on highest-probability opportunities instead of working leads sequentially.

**When to recommend:**
- Client says: "Our reps work leads in the order they come in, not by quality"
- Client says: "We can't tell which leads are serious until we've spent time on them"
- Client says: "We generate 500 leads a month but close 10 — most are unqualified"
- Lead volume exceeds sales capacity (more leads than reps can effectively work)
- Historical conversion data exists (which leads became customers? what did they look like?)
- Sales cycle is long enough that prioritization matters (>2 weeks from lead to close)
- Current lead qualification is manual, inconsistent, or based on single criteria (company size only)

**ROI framing:**
- Primary metric: Conversion rate + rep productivity (deals per rep)
- Typical range: 20–40% improvement in lead-to-opportunity conversion by focusing on high-scoring leads; reps spend 30–50% less time on unqualified leads
- Efficiency gain: Same team, more revenue — not by working harder, by working smarter
- Executive one-liner: "Your reps spend half their time on leads that will never close. AI scores every lead based on 20 signals and tells them which 50 to call today — same team, 30% more pipeline."

**Implementation complexity:** Standard Pilot
- Timeline: 4–8 weeks (historical data analysis, feature engineering, model training, CRM integration, rep workflow design)
- Typical stack: CRM data (Salesforce, HubSpot) for historical patterns; enrichment APIs (Clearbit, ZoomInfo, Apollo) for lead signals; ML model (logistic regression or gradient boosted trees) or LLM-based scoring; CRM integration for score display and prioritization views
- Solo consultant role: Build the scoring model yourself. For enrichment, recommend and configure existing tools (ZoomInfo, Apollo, Clearbit) rather than building custom scrapers. Ongoing model retraining may require client data team or scheduled consultant updates.

**Red flags:**
- Fewer than 100 historical conversions to learn from (insufficient data for meaningful scoring — use manual ICP criteria instead)
- Sales process has no CRM discipline (data not captured consistently — scoring can't work without input data)
- Lead source is primarily inbound with high intent already (all leads are warm — scoring adds little value)
- Client expects scoring to replace qualification conversations (score prioritizes, humans still qualify through conversation)
- Single-product company with simple ICP (company size + industry = sufficient criteria; ML scoring is overkill)

**Examples:**
- **B2B SaaS:** Score inbound demo requests and marketing qualified leads by company fit (size, industry, tech stack), behavioral signals (pages visited, content downloaded), and enrichment data (growth rate, funding). Route top scores to senior reps. (50–300 employees, 200+ leads/month)
- **Professional services firm:** Score prospect companies by engagement signals (event attendance, content consumption, referral source) and firmographic fit. Alert partners when high-score prospects show buying intent. (50–200 employees, relationship-driven sales)
- **Insurance/financial services:** Score and prioritize renewal leads and cross-sell opportunities by customer lifetime value, policy complexity, and engagement patterns. (100–500 employees, large book of business)
