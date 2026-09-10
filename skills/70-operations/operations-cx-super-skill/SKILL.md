---
name: operations-cx-super-skill
description: Comprehensive operations and customer experience skill merging Perplexity Computer's 5 CX skills with Claude Code's project management, file organization, invoice processing, scrum methodology, and verification workflows. Covers ticket triage, customer response drafting, escalation management, knowledge base maintenance, customer research, project management, sprint planning, file organization, and operational quality assurance. Use for support ticket handling, customer communications, escalation workflows, KB article writing, project management, sprint ceremonies, file cleanup, or any operations and CX work.
license: MIT
metadata:
  author: get-zeked
  version: '1.0'
---

# Operations & CX Super-Skill

A unified operations and customer experience reference covering support excellence, project delivery, agile execution, file and financial document management, and quality verification. Merge of Perplexity Computer's five CX skills and five Claude Code operations skills.

---

## Gap Analysis: Source Skills vs. This Super-Skill

| Domain | Source Skill | Coverage in This Document |
|--------|-------------|--------------------------|
| Ticket triage & classification | cx-ticket-triage | Section 2 — full priority matrix, routing rules, SLA table |
| Customer response drafting | cx-response-drafting | Section 3 — tone spectrum, templates, channel guidelines |
| Escalation management | cx-escalation | Section 4 — structured format, reproduction steps, impact assessment |
| Customer research & confidence scoring | cx-customer-research | Section 5 — five-tier source hierarchy, synthesis structure |
| Knowledge base management | cx-knowledge-management | Section 6 — article types, maintenance cadence, taxonomy |
| Portfolio & senior PM | senior-pm | Section 7 — WSJF/RICE/ICE, RAG status, risk EMV |
| Sprint & agile operations | scrum-master | Section 8 — health scoring, velocity, ceremony guides |
| File & document organization | file-organizer | Section 9 — analysis workflow, naming conventions |
| Invoice & financial document processing | invoice-organizer | Section 10 — extraction, filename format, CSV reporting |
| Operational quality & verification | verification-before-completion | Section 11 — iron law, gate function, red flags |
| Structured implementation planning | writing-plans | Section 11 — plan headers, task granularity, TDD cadence |
| Unique Perplexity Computer capabilities | about-computer | Section 12 — integrations, scheduled monitoring, CRM access |

**Gaps addressed by this merge not present in any single source skill:**
- Cross-domain triage → escalation → KB article pipeline in one workflow
- Sprint velocity data feeding PM portfolio risk scoring
- Invoice categorization standards aligned with project cost-center taxonomy
- Verification gates applied to customer-facing content, not just code
- Perplexity Computer integration capabilities surfaced for CX workflows (CRM, email, calendar)

---

## Section 2 — Ticket Triage & Classification

### Category Taxonomy

Assign every ticket a **primary category** and optionally a **secondary category**. Root cause drives the primary category, not the surface symptom.

| Category | Description | Signal Words |
|----------|-------------|-------------|
| **Bug** | Product behaving incorrectly or unexpectedly | Error, broken, crash, not working, unexpected, wrong, failing |
| **How-to** | Customer needs guidance on using the product | How do I, can I, where is, setting up, configure, help with |
| **Feature Request** | Customer wants a capability that does not exist | Would be great if, wish I could, any plans to, requesting |
| **Billing** | Payment, subscription, invoice, or pricing issues | Charge, invoice, payment, subscription, refund, upgrade, downgrade |
| **Account** | Account access, permissions, settings, or user management | Login, password, access, permission, SSO, locked out, can't sign in |
| **Integration** | Issues connecting to third-party tools or APIs | API, webhook, integration, connect, OAuth, sync, third-party |
| **Security** | Security concerns, data access, or compliance questions | Data breach, unauthorized, compliance, GDPR, SOC 2, vulnerability |
| **Data** | Data quality, migration, import/export issues | Missing data, export, import, migration, incorrect data, duplicates |
| **Performance** | Speed, reliability, or availability issues | Slow, timeout, latency, down, unavailable, degraded |

**Category determination rules:**
- If the customer reports both a bug and a feature request, bug is primary
- If they cannot log in due to a bug, category is Bug (not Account) — root cause drives category
- "It used to work and now it doesn't" = Bug
- "I want it to work differently" = Feature Request
- "How do I make it work?" = How-to
- When in doubt, lean Bug — better to investigate than dismiss

### Priority Framework

#### P1 — Critical

**Criteria:** Production system down, data loss or corruption, security breach, all or most users affected.

- The customer cannot use the product at all
- Data is being lost, corrupted, or exposed
- A security incident is in progress
- The issue is worsening or expanding in scope

**SLA:** Respond within 1 hour. Continuous work until resolved or mitigated. Updates every 1–2 hours.

#### P2 — High

**Criteria:** Major feature broken, significant workflow blocked, many users affected, no workaround.

- A core workflow is broken but the product is partially usable
- Multiple users are affected or a key account is impacted
- The issue is blocking time-sensitive work
- No reasonable workaround exists

**SLA:** Respond within 4 hours. Active investigation same day. Updates every 4 hours.

#### P3 — Medium

**Criteria:** Feature partially broken, workaround available, single user or small team affected.

- A feature is not working correctly but a workaround exists
- The issue is inconvenient but not blocking critical work
- A single user or small team is affected
- The customer is not escalating urgently

**SLA:** Respond within 1 business day. Resolution or update within 3 business days.

#### P4 — Low

**Criteria:** Minor inconvenience, cosmetic issue, general question, feature request.

- Cosmetic or UI issues that do not affect functionality
- Feature requests and enhancement ideas
- General questions or how-to inquiries
- Issues with simple, documented solutions

**SLA:** Respond within 2 business days. Resolution at normal pace.

### Priority Triage Matrix

| Impact ↓ / Breadth → | All Users | Many Users | Small Group | Single User |
|----------------------|-----------|-----------|-------------|-------------|
| **Production Down** | P1 | P1 | P2 | P2 |
| **Core Feature Broken** | P1 | P2 | P2 | P3 |
| **Major Feature Broken** | P2 | P2 | P3 | P3 |
| **Minor Feature Broken** | P2 | P3 | P3 | P4 |
| **Cosmetic / How-to** | P3 | P4 | P4 | P4 |

### Priority Escalation Triggers

Automatically bump priority up when:
- Customer has been waiting longer than the SLA allows
- Multiple customers report the same issue (pattern detected — 3+ reports)
- The customer explicitly escalates or mentions executive involvement
- A workaround that was in place stops working
- The issue expands in scope (more users, more data, new symptoms)

### Routing Rules

| Route to | When |
|----------|------|
| **Tier 1 (frontline)** | How-to questions, known issues with documented solutions, billing inquiries, password resets |
| **Tier 2 (senior support)** | Bugs requiring investigation, complex configuration, integration troubleshooting, account issues |
| **Engineering** | Confirmed bugs needing code fixes, infrastructure issues, performance degradation |
| **Product** | Feature requests with significant demand, design decisions, workflow gaps |
| **Security** | Data access concerns, vulnerability reports, compliance questions |
| **Billing/Finance** | Refund requests, contract disputes, complex billing adjustments |

### Duplicate Detection Workflow

Before creating a new ticket or routing:

1. **Search by symptom** — look for tickets with similar error messages or descriptions
2. **Search by customer** — check if this customer has an open ticket for the same issue
3. **Search by product area** — look for recent tickets in the same feature area
4. **Check known issues** — compare against documented known issues

If a duplicate is found: link the new ticket to the existing one, notify the customer this is a known issue being tracked, add any new information from the new report to the existing ticket, and bump priority if the new report adds urgency.

### Auto-Response Templates by Category

**Bug — Initial Response**
```
Thank you for reporting this. I can see how [specific impact]
would be disruptive for your work.

I've logged this as a [priority] issue and our team is
investigating. [If workaround exists: "In the meantime, you
can [workaround]."]

I'll update you within [SLA timeframe] with what we find.
```

**How-to — Initial Response**
```
Great question! [Direct answer or link to documentation]

[If more complex: "Let me walk you through the steps:"]
[Steps or guidance]

Let me know if that helps, or if you have any follow-up questions.
```

**Feature Request — Initial Response**
```
Thank you for this suggestion — I can see why [capability]
would be valuable for your workflow.

I've documented this and shared it with our product team.
While I can't commit to a specific timeline, your feedback
directly informs our roadmap priorities.

[If alternative exists: "In the meantime, you might find
[alternative] helpful for achieving something similar."]
```

**Security — Initial Response**
```
Thank you for flagging this — we take security concerns
seriously and are reviewing this immediately.

I've escalated this to our security team for investigation.
We'll follow up with you within [timeframe] with our findings.

[If action is needed: "In the meantime, we recommend
[protective action]."]
```

### Triage Checklist

When working a ticket:
- [ ] Read the full ticket (including attachments and thread history) before categorizing
- [ ] Categorize by root cause, not symptom
- [ ] Check for duplicate or related tickets
- [ ] Assign priority using the triage matrix
- [ ] Check if a known-issue KB article already exists
- [ ] Write internal notes that help the next person pick up context quickly
- [ ] Document what has already been checked or ruled out
- [ ] Flag patterns — if you are seeing the same issue repeatedly, escalate the pattern even if individual tickets are low priority

---

## Section 3 — Customer Response Drafting

### Core Principles

1. **Lead with empathy** — acknowledge the customer's situation before jumping to solutions
2. **Be direct** — bottom-line-up-front; customers are busy
3. **Be honest** — never overpromise, never mislead, never hide bad news in jargon
4. **Be specific** — use concrete details, timelines, and names; avoid vague language
5. **Own it** — take responsibility when appropriate; use "we" not "the system" or "the process"
6. **Close the loop** — every response should have a clear next step or call to action
7. **Match their energy** — if they are frustrated, lead with empathy; if they are excited, be enthusiastic

### Response Structure

For most customer communications, follow this structure:

```
1. Acknowledgment / Context (1–2 sentences)
   - Acknowledge what they said, asked, or are experiencing
   - Show you understand their situation

2. Core Message (1–3 paragraphs)
   - Deliver the main information, answer, or update
   - Be specific and concrete
   - Include relevant details they need

3. Next Steps (1–3 bullets)
   - What YOU will do and by when
   - What THEY need to do (if anything)
   - When they will hear from you next

4. Closing (1 sentence)
   - Warm but professional sign-off
   - Reinforce you are available if needed
```

### Channel-Based Length Guidelines

| Channel | Length | Style |
|---------|--------|-------|
| Chat / IM | 1–4 sentences | Immediate, get to the point |
| Support ticket | 1–3 short paragraphs | Structured and scannable |
| Email | 3–5 paragraphs max | Respect their inbox |
| Escalation response | As needed with headers | Thorough and well-structured |
| Executive communication | 2–3 paragraphs max | Data-driven, shorter is better |

### Tone Spectrum

| Situation | Tone | Characteristics |
|-----------|------|----------------|
| Good news / wins | Celebratory | Enthusiastic, warm, forward-looking |
| Routine update | Professional | Clear, concise, informative, friendly |
| Technical response | Precise | Accurate, detailed, structured, patient |
| Delayed delivery | Accountable | Honest, apologetic, action-oriented, specific |
| Bad news | Candid | Direct, empathetic, solution-oriented |
| Issue / outage | Urgent | Immediate, transparent, actionable, reassuring |
| Escalation | Executive | Composed, ownership-taking, plan-presenting |
| Billing / account | Precise | Clear, factual, empathetic, resolution-focused |

### Tone Adjustments by Relationship Stage

**New Customer (0–3 months):**
- More formal and professional
- Extra context and explanation; do not assume knowledge
- Proactively offer help and resources
- Build trust through reliability and responsiveness

**Established Customer (3+ months):**
- Warm and collaborative
- Reference shared history and previous conversations
- More direct and efficient communication
- Show awareness of their goals and priorities

**Frustrated or Escalated Customer:**
- Extra empathy and acknowledgment first
- Urgency in response times
- Concrete action plans with specific commitments
- Shorter feedback loops

### Writing Style Rules

**DO:**
- Use active voice ("We'll investigate" not "This will be investigated")
- Use "I" for personal commitments and "we" for team commitments
- Name specific people when assigning actions
- Use the customer's terminology, not your internal jargon
- Include specific dates and times, not relative terms ("by Friday March 7" not "in a few days")
- Break up long responses with headers or bullet points

**DO NOT:**
- Use corporate jargon or buzzwords ("synergy", "leverage", "paradigm shift")
- Deflect blame to other teams, systems, or processes
- Use passive voice to avoid ownership ("Mistakes were made")
- Include unnecessary caveats or hedging that undermines confidence
- CC people who do not need to be in the conversation
- Use exclamation marks excessively (one per email max, if any)

### Full Response Templates

**Acknowledging a Bug Report**
```
Hi [Name],

Thank you for reporting this — I can see how [specific impact] would be
frustrating for your team.

I've confirmed the issue and escalated it to our engineering team as a
[priority level]. Here's what we know so far:
- [What's happening]
- [What's causing it, if known]
- [Workaround, if available]

I'll update you by [specific date/time] with a resolution timeline.
In the meantime, [workaround details if applicable].

Let me know if you have any questions or if this is impacting you in
other ways I should know about.

Best,
[Your name]
```

**Acknowledging a Billing or Account Issue**
```
Hi [Name],

Thank you for reaching out about this — I understand billing issues
need prompt attention, and I want to make sure this gets resolved quickly.

I've looked into your account and here's what I'm seeing:
- [What happened — clear factual explanation]
- [Impact on their account — charges, access, etc.]

Here's what I'm doing to fix this:
- [Action 1 — with timeline]
- [Action 2 — if applicable]

[If resolution is immediate: "This has been corrected and you should
see the change reflected within [timeframe]."]
[If needs investigation: "I'm escalating this to our billing team
and will have an update for you by [specific date]."]

I'm sorry for the inconvenience. Let me know if you have any
questions about your account.

Best,
[Your name]
```

**Responding to a Feature Request You Won't Build**
```
Hi [Name],

Thank you for sharing this request — I can see why [capability] would
be valuable for [their use case].

I discussed this with our product team, and this isn't something we're
planning to build in the near term. The primary reason is [honest,
respectful explanation].

That said, I want to make sure you can accomplish your goal. Here are
some alternatives:
- [Alternative approach 1]
- [Alternative approach 2]
- [Integration or workaround if applicable]

I've also documented your request in our feedback system, and if our
direction changes, I'll let you know.

Would any of these alternatives work for your team?

Best,
[Your name]
```

**Outage or Incident Communication**
```
Hi [Name],

I wanted to reach out directly to let you know about an issue affecting
[service/feature] that I know your team relies on.

What happened: [Clear, non-technical explanation]
Impact: [How it affects them specifically]
Status: [Investigating / Identified / Fixing / Resolved]
ETA for resolution: [Specific time if known, or "we'll update every X hours"]

[If applicable: "In the meantime, you can [workaround]."]

I'm personally tracking this and will update you as soon as we have a
resolution. You can also check [status page URL] for real-time updates.

I'm sorry for the disruption to your team's work.

[Your name]
```

**Following Up After Silence**
```
Hi [Name],

I wanted to check in — I sent over [what you sent] on [date] and
wanted to make sure it didn't get lost in the shuffle.

[Brief reminder of what you need from them or what you're offering]

If now isn't a good time, no worries — just let me know when would be
better.

Best,
[Your name]
```

### Follow-up Cadence

| Situation | Follow-up Timing |
|-----------|----------------|
| Unanswered question | 2–3 business days |
| Open critical support issue | Daily until resolved |
| Open standard support issue | Every 2–3 days |
| Post-meeting action items | Within 24 hours for notes, then at deadline |
| After delivering bad news | 1 week to check on impact and sentiment |

---

## Section 4 — Escalation Management

### When to Escalate vs. Handle in Support

**Handle in Support When:**
- The issue has a documented solution or known workaround
- It is a configuration or setup issue you can resolve
- The customer needs guidance or training, not a fix
- Previous similar tickets were resolved at the support level

**Escalate When:**
- **Technical:** Bug confirmed and needs a code fix; infrastructure investigation needed; data corruption or loss
- **Complexity:** Issue is beyond support's ability to diagnose; requires access support doesn't have; involves custom implementation
- **Impact:** Multiple customers affected; production system down; data integrity at risk; security concern
- **Business:** High-value customer at risk; SLA breach imminent or occurred; customer requesting executive involvement
- **Time:** Issue has been open beyond SLA; customer has been waiting unreasonably long
- **Pattern:** Same issue reported by 3+ customers; recurring issue that was supposedly fixed; increasing severity over time

### Escalation Tiers

| From | To | When | What to Include |
|------|----|------|----------------|
| L1 (frontline) | L2 (senior support) | Deeper investigation needed, specialized knowledge required | Ticket summary, steps already tried, customer context |
| L2 (senior support) | Engineering | Confirmed bug, infrastructure issue, code change needed | Full reproduction steps, environment details, logs, business impact |
| L2 (senior support) | Product | Feature gap causing customer pain, design decision needed | Customer use case, business impact, frequency of request |
| Any tier | Security | Potential data exposure, unauthorized access, vulnerability | What was observed, who is affected, containment steps taken |
| Any tier | Leadership | High-revenue customer at churn risk, SLA breach on critical account, exception to policy | Full business context, revenue at risk, specific decision needed |

**Note:** Security escalations bypass normal tier progression — escalate immediately regardless of your level.

### Structured Escalation Format

```
ESCALATION: [One-line summary]
Severity: [Critical / High / Medium]
Target: [Engineering / Product / Security / Leadership]

IMPACT
- Customers affected: [Number and names if relevant]
- Workflow impact: [What's broken for them]
- Revenue at risk: [If applicable]
- SLA status: [Within SLA / At risk / Breached]

ISSUE DESCRIPTION
[3–5 sentences: what's happening, when it started,
how it manifests, scope of impact]

REPRODUCTION STEPS (for bugs)
1. [Step — be specific about paths, values, and inputs]
2. [Step]
3. [Step]
Expected: [X]
Actual: [Y]
Environment: [Browser, OS, account type, plan level, feature flags]

WHAT'S BEEN TRIED
1. [Action] → [Result]
2. [Action] → [Result]
3. [Action] → [Result]

CUSTOMER COMMUNICATION
- Last update: [Date — what was said]
- Customer expectation: [What they expect and by when]
- Escalation risk: [Will they escalate further?]

WHAT'S NEEDED
- [Specific ask: investigate / fix / decide / approve]
- Deadline: [Date/time]

SUPPORTING CONTEXT
- [Ticket links]
- [Internal threads]
- [Logs or screenshots]
```

### Business Impact Assessment

| Dimension | Questions to Answer |
|-----------|-------------------|
| **Breadth** | How many customers/users are affected? Is it growing? |
| **Depth** | How severely are they impacted? Blocked vs. inconvenienced? |
| **Duration** | How long has this been going on? How long until it becomes critical? |
| **Revenue** | What is the ARR at risk? Are there pending deals affected? |
| **Reputation** | Could this become public? Is it a reference customer? |
| **Contractual** | Are SLAs being breached? Are there contractual obligations? |

### Writing Reproduction Steps

Good reproduction steps are the single most valuable thing in a bug escalation:

1. **Start from a clean state** — describe the starting point (account type, configuration, permissions)
2. **Be specific** — "Click the Export button in the top-right of the Dashboard page" not "try to export"
3. **Include exact values** — use specific inputs, dates, IDs, not "enter some data"
4. **Note the environment** — browser, OS, account type, feature flags, plan level
5. **Capture the frequency** — always reproducible? Intermittent? Only under certain conditions?
6. **Include evidence** — screenshots, error messages (exact text), network logs, console output
7. **Note what you've ruled out** — "Tested in Chrome and Firefox — same behavior" / "Not account-specific — reproduced on test account"

### Follow-up Cadence After Escalation

| Severity | Internal Follow-up | Customer Update |
|----------|-------------------|--------------------|
| **Critical** | Every 2 hours | Every 2–4 hours (or per SLA) |
| **High** | Every 4 hours | Every 4–8 hours |
| **Medium** | Daily | Every 1–2 business days |

**After escalating:** maintain ownership of the customer relationship. Check with the receiving team for progress, update the customer even when there is no new information, adjust severity if the situation changes, document all updates in the ticket for audit trail, and close the loop when resolved.

### De-escalation

De-escalate when:
- Root cause is found and it is a support-resolvable issue
- A workaround is found that unblocks the customer
- The issue resolves itself (but still document root cause)
- New information changes the severity assessment

When de-escalating: notify the team you escalated to, update the ticket with the resolution, inform the customer, and document what was learned for future reference.

---

## Section 5 — Customer Research & Investigation

### Research Process

**Step 1: Understand the Question**
Before searching, clarify what you are actually trying to find:
- Is this a factual question with a definitive answer?
- Is this a contextual question requiring multiple perspectives?
- Is this an exploratory question where the scope is still being defined?
- Who is the audience for the answer (internal team, customer, leadership)?

**Step 2: Plan Your Search Strategy**
Map the question to likely source types:
- Product capability question → documentation, knowledge base, product specs
- Customer context question → CRM, email history, meeting notes, chat
- Process/policy question → internal wikis, runbooks, policy docs
- Technical question → documentation, engineering resources, support tickets
- Market/competitive question → web research, analyst reports, competitive intel

**Step 3: Execute Searches Systematically**
Search sources in priority order. Do not stop at the first result — cross-reference across sources.

**Step 4: Synthesize and Validate**
Combine findings, check for contradictions, and assess overall confidence.

**Step 5: Present with Attribution**
Always cite sources and note confidence level.

### Five-Tier Source Hierarchy

**Tier 1 — Official Internal Sources (Highest Confidence)**
These are authoritative and should be trusted unless outdated.
- Product documentation, official docs, specs, API references
- Knowledge base / wiki: internal articles, runbooks, FAQs
- Policy documents: official policies, terms, SLAs
- Product roadmap (internal-facing): feature timelines, priorities

Confidence level: **High** (unless clearly outdated — check dates)

**Tier 2 — Organizational Context (Medium-High Confidence)**
These provide context but may reflect one perspective.
- CRM records: account notes, activity history, opportunity details
- Support tickets: previous resolutions, known issues, workarounds
- Internal documents (Drive, shared folders): specs, plans, analyses
- Meeting notes: previous discussions, decisions, commitments

**Tier 3 — Team Communications (Medium Confidence)**
Informal but often contain the most recent information.
- Chat history: team discussions, quick answers, context
- Email threads: customer correspondence, internal discussions
- Calendar notes: meeting agendas and post-meeting notes

**Tier 4 — External Sources (Low-Medium Confidence)**
Useful for general knowledge but not authoritative for internal matters.
- Web search: official websites, blog posts, industry resources
- Community forums: user discussions, workarounds, experiences
- Third-party documentation: integration partners, complementary tools
- News and analyst reports: market context, competitive intelligence

**Tier 5 — Inferred or Analogical (Low Confidence)**
Use when direct sources do not yield answers.
- Similar situations: how similar questions were handled before
- Analogous customers: what worked for comparable accounts
- General best practices: industry standards and norms

### Confidence Levels

**High Confidence:**
- Answer confirmed by official documentation or authoritative source
- Multiple sources corroborate the same answer
- Information is current (verified within a reasonable timeframe)
- State: "I'm confident this is accurate based on [source]."

**Medium Confidence:**
- Answer found in informal sources (chat, email) but not official docs
- Single source without corroboration
- Information may be slightly outdated but likely still valid
- State: "Based on [source], this appears to be the case, but I'd recommend confirming with [team/person]."

**Low Confidence:**
- Answer is inferred from related information
- Sources are outdated or potentially unreliable
- Contradictory information found across sources
- State: "I wasn't able to find a definitive answer. Based on [context], my best assessment is [answer], but this should be verified before sharing with the customer."

**Unable to Determine:**
- No relevant information found in any source
- State: "I couldn't find information about this. I recommend reaching out to [suggested expert/team] for a definitive answer."

### Answer Synthesis Structure

```
Direct Answer: [Bottom-line answer — lead with this]

Confidence: [High / Medium / Low]

Supporting Evidence:
- [Source 1]: [What it says]
- [Source 2]: [What it says — corroborates or adds nuance]

Caveats:
- [Any limitations or conditions on the answer]
- [Anything that might change the answer in specific contexts]

Recommendation:
- [Whether this is ready to share with customers]
- [Any verification steps recommended]
```

### When to Escalate vs. Answer Directly

**Answer Directly When:**
- Official documentation clearly addresses the question
- Multiple reliable sources corroborate the answer
- The question is factual and non-sensitive
- The answer does not involve commitments, timelines, or pricing

**Escalate or Verify When:**
- The answer involves product roadmap commitments or timelines
- Pricing, legal terms, or contract-specific questions
- Security, compliance, or data handling questions
- The answer could set a precedent or create expectations
- Contradictory information found in sources
- The question involves a specific customer's custom configuration

### Research Documentation

After completing research, capture the knowledge for future use:

```markdown
## [Question/Topic]

**Last Verified:** [date]
**Confidence:** [level]

### Answer
[Clear, direct answer]

### Details
[Supporting detail, context, and nuance]

### Sources
[Where this information came from]

### Related Questions
[Other questions this might help answer]

### Review Notes
[When to re-verify, what might change this answer]
```

**Knowledge Base Hygiene:**
- Date-stamp all entries
- Flag entries that reference specific product versions or features
- Review and update entries quarterly
- Archive entries that are no longer relevant
- Tag entries for searchability (by topic, product area, customer segment)

---

## Section 6 — Knowledge Base Management

### Universal Article Elements

Every KB article should include:
1. **Title** — clear, searchable, describes the outcome or problem (not internal jargon)
2. **Overview** — 1–2 sentences explaining what this article covers and who it's for
3. **Body** — structured content appropriate to the article type
4. **Related articles** — links to relevant companion content
5. **Metadata** — category, tags, audience, last updated date

### Formatting Standards

- **Use headers (H2, H3)** to break content into scannable sections
- **Use numbered lists** for sequential steps
- **Use bullet lists** for non-sequential items
- **Use bold** for UI element names, key terms, and emphasis
- **Use code blocks** for commands, API calls, error messages, and configuration values
- **Use tables** for comparisons, options, or reference data
- **Keep paragraphs short** — 2–4 sentences max
- **One idea per section** — if a section covers two topics, split it

### Title Best Practices

| Good Title | Bad Title | Why |
|------------|-----------|-----|
| "How to configure SSO with Okta" | "SSO Setup" | Specific, includes the tool name customers search for |
| "Fix: Dashboard shows blank page" | "Dashboard Issue" | Includes the symptom customers experience |
| "API rate limits and quotas" | "API Information" | Includes the specific terms customers search for |
| "Error: 'Connection refused' when importing data" | "Import Problems" | Includes the exact error message |

**Keyword optimization:**
- Include exact error messages — customers copy-paste error text into search
- Use customer language, not internal terminology ("can't log in" not "authentication failure")
- Include common synonyms ("delete/remove", "dashboard/home page", "export/download")
- Add alternate phrasings — address the same issue from different angles in the overview

### Common Article Types

**How-to Article Structure**
```markdown
# How to [accomplish task]

[Overview — what this guide covers and when you'd use it]

## Prerequisites
- [What's needed before starting]

## Steps
### 1. [Action]
[Instruction with specific details]

### 2. [Action]
[Instruction]

## Verify It Worked
[How to confirm success]

## Common Issues
- [Issue]: [Fix]

## Related Articles
- [Links]
```

**Best practices for how-to articles:**
- Start each step with a verb
- Include the specific path: "Go to Settings > Integrations > API Keys"
- Mention what the user should see after each step ("You should see a green confirmation banner")
- Test the steps yourself or verify with a recent ticket resolution

**Troubleshooting Article Structure**
```markdown
# [Problem description — what the user sees]

## Symptoms
- [What the user observes]

## Cause
[Why this happens — brief, non-jargon explanation]

## Solution
### Option 1: [Primary fix]
[Steps]

### Option 2: [Alternative if Option 1 doesn't work]
[Steps]

## Prevention
[How to avoid this in the future]

## Still Having Issues?
[How to get help]
```

**FAQ Article Structure**
```markdown
# [Question — in the customer's words]

[Direct answer — 1–3 sentences]

## Details
[Additional context, nuance, or explanation if needed]

## Related Questions
- [Link to related FAQ]
```

**Known Issue Article Structure**
```markdown
# [Known Issue]: [Brief description]

**Status:** [Investigating / Workaround Available / Fix In Progress / Resolved]
**Affected:** [Who/what is affected]
**Last updated:** [Date]

## Symptoms
[What users experience]

## Workaround
[Steps to work around the issue, or "No workaround available"]

## Fix Timeline
[Expected fix date or current status]

## Updates
- [Date]: [Update]
```

**Best practices for known issue articles:**
- Keep the status current — nothing erodes trust faster than a stale known issue article
- Update the article when the fix ships and mark as resolved
- If resolved, keep the article live for 30 days for customers still searching the old symptoms

### Review and Maintenance Cadence

| Activity | Frequency | Who |
|----------|-----------|-----|
| **New article review** | Before publishing | Peer review + SME for technical content |
| **Accuracy audit** | Quarterly | Support team reviews top-traffic articles |
| **Stale content check** | Monthly | Flag articles not updated in 6+ months |
| **Known issue updates** | Weekly | Update status on all open known issues |
| **Analytics review** | Monthly | Check low helpfulness ratings or high bounce rates |
| **Gap analysis** | Quarterly | Identify top ticket topics without KB articles |

### Article Lifecycle

1. **Draft** — written, needs review
2. **Published** — live and available to customers
3. **Needs update** — flagged for revision (product change, feedback, or age)
4. **Archived** — no longer relevant but preserved for reference
5. **Retired** — removed from the knowledge base

### KB Category Taxonomy

```
Getting Started
├── Account setup
├── First-time configuration
└── Quick start guides

Features & How-tos
├── [Feature area 1]
├── [Feature area 2]
└── [Feature area 3]

Integrations
├── [Integration 1]
├── [Integration 2]
└── API reference

Troubleshooting
├── Common errors
├── Performance issues
└── Known issues

Billing & Account
├── Plans and pricing
├── Billing questions
└── Account management
```

### Linking Best Practices

- Link from troubleshooting to how-to: "For setup instructions, see [How to configure X]"
- Link from how-to to troubleshooting: "If you encounter errors, see [Troubleshooting X]"
- Link from FAQ to detailed articles: "For a full walkthrough, see [Guide to X]"
- Use relative links within the KB — they survive restructuring better than absolute URLs
- Avoid circular links

### KB-to-Ticket Pipeline

Every resolved ticket that required research should be evaluated for KB documentation:

1. **Check if an article already exists** — search before creating
2. **If no article exists:** draft a new article using the appropriate template above
3. **If an article exists but is incomplete or wrong:** update it immediately
4. **Tag the ticket** with the KB article for tracking
5. **Measure ticket deflection** — track whether the article reduces future tickets on the same topic

---

## Section 7 — Project Management & Portfolio

### Core Expertise Areas

- Multi-project portfolio optimization using advanced prioritization models (WSJF, RICE, ICE, MoSCoW)
- Strategic roadmap development aligned with business objectives
- Resource capacity planning and allocation optimization across portfolio
- Portfolio health monitoring with multi-dimensional scoring frameworks
- Quantitative risk management using EMV analysis and Monte Carlo simulation
- Board-ready executive reports with RAG status and strategic recommendations
- Stakeholder alignment through RACI matrices and escalation paths

### Portfolio Health Scoring Framework

**Health Dimensions (Weighted)**

| Dimension | Weight | Scoring Criteria |
|-----------|--------|-----------------|
| **Timeline Performance** | 25% | Schedule adherence, milestone achievement, critical path |
| **Budget Management** | 25% | Spend variance, forecast accuracy, cost efficiency |
| **Scope Delivery** | 20% | Feature completion rates, requirement satisfaction, change control |
| **Quality Metrics** | 20% | Code coverage, defect density, technical debt, security posture |
| **Risk Exposure** | 10% | Risk score, mitigation effectiveness, exposure trends |

**RAG Status Calculation:**
- Green: Composite score >80, all dimensions >60
- Amber: Composite score 60–80, or any dimension 40–60
- Red: Composite score <60, or any dimension <40

### Prioritization Framework Selection

**Weighted Shortest Job First (WSJF) — For Agile Portfolios**
```
WSJF Score = (User Value + Time Criticality + Risk Reduction) ÷ Job Size

Best for: resource-constrained environments, competitive landscapes,
agile/SAFe methodology, clear cost-of-delay quantification
```

**RICE Framework — For Product Development**
```
RICE Score = (Reach × Impact × Confidence) ÷ Effort

Best for: customer-facing initiatives, marketing and growth projects,
when reach metrics are quantifiable, data-driven product decisions
```

**ICE Scoring — For Rapid Decision Making**
```
ICE Score = (Impact + Confidence + Ease) ÷ 3

Best for: quick prioritization, brainstorming phases, limited analysis
time, cross-functional team alignment
```

**Model Selection Decision Tree:**
- Resource constrained? → WSJF
- Customer impact focus? → RICE
- Need speed? → ICE
- Multiple stakeholder groups? → MoSCoW
- Complex trade-offs? → Multi-Criteria Decision Analysis (MCDA)

### Risk Management Framework

**Step 1: Risk Identification & Classification**
- Technical risks: architecture, integration, performance
- Resource risks: availability, skills, retention
- Schedule risks: dependencies, critical path, external factors
- Financial risks: budget overruns, currency, economic factors
- Business risks: market changes, competitive pressure, strategic shifts

**Step 2: Probability/Impact Assessment**
Use three-point estimation for Monte Carlo simulation:
```
Expected Value = (Optimistic + 4 × Most Likely + Pessimistic) ÷ 6
Standard Deviation = (Pessimistic - Optimistic) ÷ 6
```

**Step 3: Expected Monetary Value (EMV) Calculation**
```
EMV = Σ(Probability × Financial Impact) for all risk scenarios

Risk-Adjusted Budget = Base Budget × (1 + Risk Premium)
Risk Premium = Portfolio Risk Score × Risk Tolerance Factor
```

**Step 4: Risk Response Strategy**

| Risk Score | Strategy | Action |
|-----------|----------|--------|
| >18 | **Avoid** | Eliminate through scope or approach changes |
| 12–18 | **Mitigate** | Reduce probability or impact through active intervention |
| 8–12 | **Transfer** | Insurance, contracts, partnerships |
| <8 | **Accept** | Monitor with contingency planning |

**Risk Appetite Framework:**
- **Conservative:** Risk scores 0–8, 25–30% contingency reserves
- **Moderate:** Risk scores 8–15, 15–20% contingency reserves
- **Aggressive:** Risk scores 15+, 10–15% contingency reserves

### RACI Matrix Structure

| Role | Description | Decision Authority |
|------|-------------|-------------------|
| **Responsible (R)** | Does the work | Execution decisions |
| **Accountable (A)** | Owns the outcome | Final approval, one per task |
| **Consulted (C)** | Provides input | Advisory, two-way communication |
| **Informed (I)** | Kept in the loop | One-way communication |

**Escalation Path Template:**
1. Team lead → resolved at team level (0–24 hours)
2. Project manager → resolved with PM involvement (1–3 days)
3. Program director → escalated program-level issue (3–7 days)
4. Executive sponsor → strategic or resource decision required (7+ days or critical)

### Executive Report Template

```markdown
# Portfolio Status Report — [Month Year]

## Executive Summary
[2–3 sentences: overall portfolio health, key wins this period,
critical issues requiring leadership attention]

## Portfolio Health Dashboard
| Project | RAG | Budget Variance | Schedule Variance | Risk Level |
|---------|-----|-----------------|-------------------|------------|
| [Name]  | 🟢  | +2%             | On track          | Low        |
| [Name]  | 🟡  | -8%             | 2 weeks behind    | Medium     |
| [Name]  | 🔴  | -18%            | At risk           | High       |

## Critical Issues Requiring Action
1. [Issue] — [Owner] — [Deadline]
2. [Issue] — [Owner] — [Deadline]

## Investment Recommendations
[Specific recommendations with business cases]

## Forward-Looking: Next 30 Days
[Key milestones, decisions needed, resource commitments]
```

### Portfolio Review Cadence

**Weekly:**
- Update project data from JIRA, financial systems, team surveys
- Refresh risk probabilities and impact assessments
- Review resource utilization and bottlenecks
- Generate executive summary

**Monthly:**
- Apply WSJF/RICE/ICE models to evaluate current priorities
- Update risk appetite and tolerance levels
- Analyze capacity constraints across upcoming quarter
- Gather stakeholder feedback on prioritization

**Quarterly:**
- Evaluate portfolio contribution to business objectives
- Analyze risk-adjusted ROI across portfolio
- Identify emerging technology and skill requirements
- Apply three horizons model for innovation balance

### Portfolio Performance KPIs

- **On-time Delivery Rate:** >80% projects delivered within 10% of planned timeline
- **Budget Variance:** <5% average variance across portfolio
- **Quality Score:** >85 composite quality rating
- **Risk Mitigation Effectiveness:** >90% risks with active mitigation plans
- **Resource Utilization:** 75–85% average utilization across teams
- **ROI Achievement:** >90% projects meeting ROI projections within 12 months

---

## Section 8 — Sprint & Agile Operations

### Sprint Health Scoring

**Six Dimensions (Weighted)**

| Dimension | Weight | Target | Description |
|-----------|--------|--------|-------------|
| **Commitment Reliability** | 25% | >85% | Sprint goal achievement consistency |
| **Scope Stability** | 20% | <15% change | Mid-sprint scope change frequency |
| **Blocker Resolution** | 15% | <3 days avg | Average time to resolve impediments |
| **Ceremony Engagement** | 15% | >90% | Participation and effectiveness metrics |
| **Story Completion Distribution** | 15% | >80% | Ratio of completed vs. partial stories |
| **Velocity Predictability** | 10% | CV <20% | Delivery consistency (coefficient of variation) |

**Health Score Grades:**
- A (90–100): Performing team, optimize for innovation
- B (80–89): Healthy team, minor process improvements
- C (70–79): Developing team, active coaching needed
- D (60–69): Struggling team, intervention required
- F (<60): Crisis, immediate escalation and remediation

### Velocity Analysis

**Key Metrics:**
- Rolling averages: 3-sprint, 5-sprint, 8-sprint windows
- Trend detection using linear regression
- Volatility assessment (coefficient of variation)
- Anomaly detection (outliers beyond 2σ)

**Velocity Targets:**
- Velocity Predictability: Coefficient of variation <20%
- Improvement Velocity (retro action items): >70% completion rate
- Team Maturity: Reach "performing" stage within 6–9 months

**Monte Carlo Forecasting:**
```
Use historical velocity distribution to generate probabilistic
release date estimates with confidence intervals:
- 50% confidence: median completion scenario
- 70% confidence: likely completion scenario
- 85% confidence: planning target
- 95% confidence: contractual commitment ceiling
```

### Sprint Ceremony Guides

#### Sprint Planning

**Pre-Planning Checklist:**
- [ ] Run velocity analysis to determine sustainable commitment level
- [ ] Review sprint health scores from previous sprints
- [ ] Check retrospective action items for capacity impact
- [ ] Confirm team member availability and any external dependencies
- [ ] Ensure product backlog is groomed and top items are story-pointed

**Sprint Planning Agenda:**
```
Sprint Planning — [Sprint N] — [Date]
Duration: [2 hours per sprint week (2-week sprint = 4 hours)]

Part 1: What (60 min)
- Product Owner presents sprint goal and candidate backlog items
- Team reviews each item for understanding and acceptance
- Capacity calculation and adjustment

Part 2: How (remaining time)
- Team breaks stories into tasks
- Each task sized in hours (no task >8 hours — break it down)
- Identifies dependencies and blockers
- Commits to sprint goal

Output:
- Sprint goal statement (1 sentence)
- Sprint backlog (committed stories)
- Identified dependencies and risks
```

**Capacity Calculation Template:**
```
Team size: [N] people
Sprint length: [N] days
Working days available: [N days × N people] = [total person-days]
Minus: PTO, meetings, overhead (~20%): [subtract]
Effective capacity: [N person-days]
Points per person-day (from velocity): [N points/person-day]
Recommended commitment: [effective capacity × points rate] points
```

#### Daily Standup

**Structured Format (15 minutes max):**
1. Progress: What did you complete since last standup?
2. Plan: What will you complete before next standup?
3. Blockers: What is preventing your progress?

**Scrum Master Observations During Standup:**
- Track participation patterns and engagement levels
- Note conflict emergence and resolution attempts
- Monitor help-seeking behavior
- Capture all blockers for immediate follow-up — blockers are not resolved in standup

**Anti-patterns to watch:**
- Status reports directed at Scrum Master rather than team
- Problem-solving discussions that should be taken offline
- No blockers reported (often means psychological safety is low)
- Same blocker appearing for 2+ days without resolution

#### Sprint Review

**Sprint Review Agenda:**
```
Sprint Review — Sprint [N] — [Date]
Duration: [1 hour per sprint week]

Opening (5 min)
- Sprint goal reminder
- What was committed

Demo (60–70% of time)
- Working software only — no slides for done items
- Each story demoed by the developer who built it
- Acceptance criteria verified live

Feedback Session (20–30% of time)
- Open questions from stakeholders
- Backlog adjustments based on feedback
- Priority clarifications for next sprint

Closing (5 min)
- Updated velocity and burndown summary
- Preview of next sprint goal candidates
```

#### Sprint Retrospective

**Three-Format Options:**

**Format 1: Start-Stop-Continue**
- Start: What should we begin doing?
- Stop: What should we stop doing?
- Continue: What's working well?

**Format 2: 4Ls**
- Liked: What did we enjoy?
- Learned: What did we discover?
- Lacked: What was missing?
- Longed For: What do we wish we had?

**Format 3: Mad-Sad-Glad**
- Mad: What frustrated the team?
- Sad: What disappointed or concerned the team?
- Glad: What are we proud of?

**Retrospective Facilitation Rules:**
1. Present sprint health scores and velocity data as a neutral starting point
2. Use retrospective analyzer insights to guide discussion focus
3. Surface patterns from historical retrospective themes
4. Limit action items to the team's actual completion rate (do not overpromit)
5. Every action item must have: owner, deadline, measurable success criteria
6. Review previous sprint's action items first — were they completed?

**Action Item Format:**
```
Action: [Specific, measurable action]
Owner: [Named person, not "team"]
Deadline: [Specific date]
Success Criteria: [How we know it's done]
```

### Team Development Framework

**Tuckman's Stages Applied to Scrum Teams:**

| Stage | Behaviors | Scrum Master Focus |
|-------|-----------|-------------------|
| **Forming** | Polite, unclear roles, defer to SM | Structure, process education, trust building |
| **Storming** | Conflict, frustration, resistance | Psychological safety, conflict facilitation, flexibility |
| **Norming** | Collaboration, shared norms, efficiency | Autonomy building, ownership transfer, skill development |
| **Performing** | High output, self-organizing, innovation | Challenge provision, innovation support, organizational impact |

**Psychological Safety Indicators (Google Project Aristotle):**
- Team members speak up with ideas and concerns without fear
- Mistakes are discussed openly and treated as learning opportunities
- Help-seeking is normalized, not seen as weakness
- Everyone's voice is heard in planning and retrospectives

### Sprint Performance Targets

| Metric | Target |
|--------|--------|
| Velocity Predictability (CV) | <20% |
| Commitment Reliability | >85% |
| Scope Stability | <15% mid-sprint change |
| Blocker Resolution Time | <3 days average |
| Ceremony Participation | >90% |
| Retrospective Action Completion | >70% |
| Psychological Safety Score | >4.0/5.0 |

---

## Section 9 — File & Document Organization

### When to Use This Workflow

- Downloads folder is a chaotic mess
- Cannot find files because they are scattered
- Duplicate files taking up space
- Folder structure does not match current work
- Preparing for archiving old projects
- Starting a new project and need a clean structure
- Cleaning up shared team folders

### Analysis Workflow

**Step 1: Understand the Scope**

Before touching anything, clarify:
- Which directory needs organization? (Downloads, Documents, entire home folder?)
- What is the main problem? (Cannot find things, duplicates, too messy, no structure?)
- Any files or folders to avoid? (Current projects, sensitive data?)
- How aggressively to organize? (Conservative vs. comprehensive cleanup)

**Step 2: Analyze Current State**

```bash
# Get overview of current structure
ls -la [target_directory]

# Check file types and sizes
find [target_directory] -type f | sed 's/.*\.//' | sort | uniq -c | sort -rn

# Identify largest files
du -sh [target_directory]/* | sort -rh | head -20

# Count files by type
find [target_directory] -type f -exec file {} \; | head -20
```

Summarize findings:
- Total files and folders
- File type breakdown
- Size distribution
- Date ranges
- Obvious organization issues

**Step 3: Identify Organization Patterns**

By Type:
- Documents (PDF, DOCX, TXT)
- Images (JPG, PNG, SVG)
- Videos (MP4, MOV)
- Archives (ZIP, TAR, DMG)
- Code/Projects (directories with code)
- Spreadsheets (XLSX, CSV)
- Presentations (PPTX, KEY)

By Purpose:
- Work vs. Personal
- Active vs. Archive
- Project-specific
- Reference materials
- Temporary/scratch files

By Date:
- Current year/month
- Previous years
- Very old (archive candidates)

**Step 4: Find Duplicates**

```bash
# Find exact duplicates by hash
find [directory] -type f -exec md5sum {} \; | sort | uniq -d -w 32

# Find files with same name
find [directory] -type f -printf '%f\n' | sort | uniq -d

# Find similar-sized files
find [directory] -type f -printf '%s %p\n' | sort -n
```

For each set of duplicates:
- Show all file paths
- Display sizes and modification dates
- Recommend which to keep (usually newest or best-named)
- Always ask for confirmation before deleting

### Organization Plan Template

```markdown
# Organization Plan for [Directory]

## Current State
- X files across Y folders
- [Size] total
- File types: [breakdown]
- Issues: [list problems]

## Proposed Structure
[Directory]/
├── Work/
│   ├── Projects/
│   ├── Documents/
│   └── Archive/
├── Personal/
│   ├── Photos/
│   ├── Documents/
│   └── Media/
└── Downloads/
    ├── To-Sort/
    └── Archive/

## Changes to Make
1. Create new folders: [list]
2. Move files:
   - X PDFs → Work/Documents/
   - Y images → Personal/Photos/
   - Z old files → Archive/
3. Rename files: [any renaming patterns]
4. Delete: [duplicates or confirmed trash files]

## Files Needing Your Decision
- [List any files you're unsure about]

Ready to proceed? (yes/no/modify)
```

### Execution Rules

**Always:**
- Confirm before deleting anything
- Log all moves for potential undo
- Preserve original modification dates
- Handle filename conflicts gracefully
- Stop and ask if you encounter unexpected situations

**Never:**
- Delete files without explicit confirmation
- Move files outside the agreed scope
- Rename files in ways that break existing links or dependencies

### Naming Conventions

**Folder Naming:**
- Use clear, descriptive names
- Avoid spaces (use hyphens or underscores)
- Be specific: "client-proposals" not "docs"
- Use prefixes for ordering: "01-current", "02-archive"

**File Naming:**
- Include dates: "2024-10-17-meeting-notes.md"
- Be descriptive: "q3-financial-report.xlsx"
- Avoid version numbers in names (use version control instead)
- Remove download artifacts: "document-final-v2 (1).pdf" → "document.pdf"

**Recommended date format:** YYYY-MM-DD (sorts chronologically)

### When to Archive vs. Delete

| Situation | Recommended Action |
|-----------|--------------------|
| Projects not touched in 6+ months | Archive |
| Completed work that might be referenced | Archive |
| Old versions after migration | Archive |
| Definite duplicates (verified by hash) | Delete with confirmation |
| Temp/scratch files (confirmed) | Delete with confirmation |
| Files you're hesitant to delete | Archive first, review in 90 days |

### Maintenance Schedule

| Frequency | Activity |
|-----------|----------|
| Weekly | Sort new downloads into appropriate folders |
| Monthly | Review and archive completed projects |
| Quarterly | Run duplicate check, review archive |
| Yearly | Archive old annual files, assess storage |

---

## Section 10 — Invoice & Financial Document Processing

### When to Use This Workflow

- Preparing for tax season and need organized records
- Managing business expenses across multiple vendors
- Organizing receipts from a messy folder or email downloads
- Setting up automated invoice filing for ongoing bookkeeping
- Archiving financial records by year or category
- Reconciling expenses for reimbursement
- Preparing documentation for accountants

### What to Extract from Each Document

For each invoice or receipt, extract:

**From PDF invoices:**
- Invoice date (look for "Invoice Date:", "Date:", "Issued:")
- Invoice number (look for "Invoice #:", "Invoice Number:")
- Company/vendor name (usually at the top of the document)
- Amount due (look for "Amount Due:", "Total:", "Amount:")
- Product or service description (look for "Description:", "Service:", "Product:")
- Payment method (if present)

**From image receipts:**
- Vendor name (usually at top of receipt)
- Date (in any common format — convert to YYYY-MM-DD)
- Total amount
- Product/service category (inferred from vendor type if not explicit)

**Fallback for unclear files:**
- Use filename clues
- Check file creation/modification date
- Flag for manual review in a "Needs-Review/" folder

### Standardized Filename Format

```
YYYY-MM-DD Vendor - Invoice - Description.ext
```

**Examples:**
- `2024-03-15 Adobe - Invoice - Creative Cloud.pdf`
- `2024-01-10 Amazon - Receipt - Office Supplies.pdf`
- `2023-12-01 Stripe - Invoice - Monthly Payment Processing.pdf`

**Filename rules:**
- Remove special characters except hyphens
- Capitalize vendor names properly
- Keep descriptions concise but meaningful
- Use consistent date format (YYYY-MM-DD) for sorting
- Preserve the original file extension

### Organization Strategies

| Strategy | Structure | Best For |
|----------|-----------|----------|
| **By Vendor** | `Adobe/`, `Amazon/`, `Stripe/` | Simple tracking, small vendor count |
| **By Category** | `Software/`, `Office/`, `Travel/` | Expense reporting, budget analysis |
| **By Year/Quarter** | `2024/Q1/`, `2024/Q2/` | Detailed financial tracking |
| **By Tax Category** | `Deductible/`, `Personal/` | Tax preparation |
| **Year/Category (default)** | `2024/Software/Adobe/` | Tax-friendly and detailed |

### Invoice Organization Plan Template

```markdown
# Invoice Organization Plan

## Proposed Structure
Invoices/
├── 2023/
│   ├── Software/
│   ├── Services/
│   └── Office/
└── 2024/
    ├── Software/
    ├── Services/
    └── Office/

## Sample Changes

Before: invoice_adobe_march.pdf
After: 2024-03-15 Adobe - Invoice - Creative Cloud.pdf
Location: Invoices/2024/Software/Adobe/

Before: IMG_2847.jpg
After: 2024-02-10 Staples - Receipt - Office Supplies.jpg
Location: Invoices/2024/Office/Staples/

Process [X] files? (yes/no)
```

### CSV Summary Report Format

Always generate a summary CSV alongside the organized files:

```csv
Date,Vendor,Invoice Number,Description,Amount,Category,File Path
2024-03-15,Adobe,INV-12345,Creative Cloud,52.99,Software,Invoices/2024/Software/Adobe/2024-03-15 Adobe - Invoice - Creative Cloud.pdf
2024-03-10,Amazon,123-456-789,Office Supplies,127.45,Office,Invoices/2024/Office/Amazon/2024-03-10 Amazon - Receipt - Office Supplies.pdf
```

The CSV is useful for:
- Importing into accounting software
- Sharing with accountants
- Expense tracking and reporting
- Tax preparation and audit support

### Handling Special Cases

| Case | Resolution |
|------|-----------|
| Date/vendor can't be extracted | Flag for manual review, use file modification date as fallback |
| Duplicate invoices | Compare file hashes, keep highest quality version, note in summary |
| Multi-page invoices split across files | Merge PDFs where possible, use consistent naming for parts |
| Non-standard formats | Extract what's possible, standardize what you can, flag missing info |

### Completion Summary Template

```markdown
# Invoice Organization Complete

## Summary
- Processed: [X] invoices
- Date range: [earliest] to [latest]
- Total amount: $[sum] (if amounts extracted)
- Vendors: [Y] unique vendors

## New Structure
Invoices/
├── 2024/ (45 files)
│   ├── Software/ (23 files)
│   ├── Services/ (12 files)
│   └── Office/ (10 files)
└── 2023/ (12 files)

## Files Created
- /Invoices/ — organized invoices
- /Invoices/invoice-summary.csv — spreadsheet for accounting
- /Invoices/originals/ — original files (if copied)

## Files Needing Review
[List any files where information couldn't be extracted completely]

## Next Steps
1. Review the invoice-summary.csv file
2. Check files in "Needs Review" folder
3. Import CSV into your accounting software
4. Retain records per your jurisdiction's audit retention requirements (commonly 7 years)
```

### Retention Guidelines

- **Standard audit retention:** 7 years (US standard)
- **General business records:** 3–7 years depending on document type and jurisdiction
- **Contracts and major agreements:** Retain for the life of the contract plus 7 years
- **Payroll records:** 7 years minimum

---

## Section 11 — Operational Quality & Verification

### The Iron Law

```
NO COMPLETION CLAIMS WITHOUT FRESH VERIFICATION EVIDENCE
```

If you have not run the verification command in this message, you cannot claim it passes.

Claiming work is complete without verification is dishonesty, not efficiency.

**Core principle:** Evidence before claims, always.

**Violating the letter of this rule is violating the spirit of this rule.**

### The Gate Function

```
BEFORE claiming any status or expressing satisfaction:

1. IDENTIFY: What command or check proves this claim?
2. RUN: Execute the FULL verification (fresh, complete)
3. READ: Full output, check exit code, count failures
4. VERIFY: Does output confirm the claim?
   - If NO: State actual status with evidence
   - If YES: State claim WITH evidence
5. ONLY THEN: Make the claim

Skip any step = asserting without evidence
```

### Common Failures Table

| Claim | Requires | Not Sufficient |
|-------|----------|----------------|
| Tests pass | Test command output: 0 failures | Previous run, "should pass" |
| Linter clean | Linter output: 0 errors | Partial check, extrapolation |
| Build succeeds | Build command: exit 0 | Linter passing, logs look good |
| Bug fixed | Test original symptom: passes | Code changed, assumed fixed |
| Regression test works | Red-green cycle verified | Test passes once |
| Agent completed | VCS diff shows changes | Agent reports "success" |
| Requirements met | Line-by-line checklist | Tests passing |
| KB article accurate | Content verified against current product | Article was accurate last month |
| Customer response sent | Delivery confirmation received | Email drafted and queued |
| Invoice data correct | Data validated against source document | Filename looks right |

### Red Flags — STOP Before Claiming Completion

Stop and verify if you are about to:
- Use "should", "probably", "seems to", "I believe", "likely"
- Express satisfaction before verification ("Great!", "Perfect!", "Done!")
- Commit, push, or create a PR without running tests
- Trust agent success reports without independent verification
- Rely on partial verification
- Move to the next task while leaving ambiguous state behind

**Rationalization Prevention:**

| Excuse | Reality |
|--------|---------|
| "Should work now" | RUN the verification |
| "I'm confident" | Confidence ≠ evidence |
| "Just this once" | No exceptions |
| "Linter passed" | Linter ≠ compiler |
| "Agent said success" | Verify independently |
| "I'm tired" | Exhaustion ≠ excuse |
| "Partial check is enough" | Partial proves nothing |
| "Different words so rule doesn't apply" | Spirit over letter |

### Verification Patterns

**Tests:**
```
✅ [Run test command] → [See: 34/34 pass] → "All tests pass"
❌ "Should pass now" / "Looks correct"
```

**Build:**
```
✅ [Run build] → [See: exit 0] → "Build passes"
❌ "Linter passed" (linter does not check compilation)
```

**Requirements:**
```
✅ Re-read plan → Create checklist → Verify each item → Report gaps or completion
❌ "Tests pass, phase complete"
```

**Customer-Facing Content:**
```
✅ Read the draft from the customer's perspective → Check all commitments are accurate
   → Verify all names, dates, and facts → Then send
❌ "Draft looks good, sending"
```

**Knowledge Base Articles:**
```
✅ Follow the steps yourself or verify with a recent ticket resolution
   → Confirm UI paths and commands are current → Peer review → Publish
❌ "Wrote the article, it should be accurate"
```

### Structured Implementation Planning

When working on a multi-step task with a specification, create an implementation plan before execution.

**Announce at start:** "I'm creating the implementation plan before starting work."

**Save plans to:** `docs/plans/YYYY-MM-DD-<feature-name>.md`

**Plan Document Header:**
```markdown
# [Feature Name] Implementation Plan

**Goal:** [One sentence describing what this builds]

**Architecture:** [2–3 sentences about approach]

**Tech Stack:** [Key technologies/libraries]

**DRY. YAGNI. TDD. Frequent commits.**

---
```

**Task Structure (Bite-Sized — 2–5 minutes each):**
```markdown
### Task N: [Component Name]

**Files:**
- Create: `exact/path/to/file.py`
- Modify: `exact/path/to/existing.py:123–145`
- Test: `tests/exact/path/to/test.py`

**Step 1: Write the failing test**
[Complete test code]

**Step 2: Run test to verify it fails**
Run: `pytest tests/path/test.py::test_name -v`
Expected: FAIL with "[specific error message]"

**Step 3: Write minimal implementation**
[Complete implementation code]

**Step 4: Run test to verify it passes**
Run: `pytest tests/path/test.py::test_name -v`
Expected: PASS

**Step 5: Commit**
git add [files]
git commit -m "feat: [specific description]"
```

**Planning Principles:**
- Exact file paths always — no relative paths or vague locations
- Complete code in the plan, not "add validation" or "implement this"
- Exact commands with expected output
- DRY, YAGNI, TDD, frequent commits
- Each task is independently verifiable

### Quality Verification Checklists

**Customer Response Quality Checklist:**
- [ ] Acknowledged the customer's situation in the first sentence
- [ ] Addressed the specific question or issue they raised
- [ ] All names, dates, and factual claims are accurate and verified
- [ ] Commitments are realistic and pre-approved if needed
- [ ] Clear next step included for both parties
- [ ] Tone is appropriate for the situation and relationship stage
- [ ] No jargon or corporate buzzwords
- [ ] No unnecessary hedging or passive voice

**KB Article Quality Checklist:**
- [ ] Title is searchable and descriptive from the customer's perspective
- [ ] Opening sentence restates the problem or task in plain language
- [ ] Steps tested and verified against current product
- [ ] UI paths and commands are current and accurate
- [ ] All numbered lists are sequential; all bullet lists are non-sequential
- [ ] "Related Articles" section populated with accurate links
- [ ] Category, tags, and audience metadata filled in
- [ ] Date-stamped

**Escalation Quality Checklist:**
- [ ] Impact section quantifies breadth, depth, duration, and revenue
- [ ] Reproduction steps are specific enough for an engineer to reproduce immediately
- [ ] "What's Been Tried" section prevents duplicate investigation
- [ ] Customer communication section sets expectations for receiving team
- [ ] Specific ask stated (investigate / fix / decide / approve)
- [ ] Deadline stated
- [ ] All supporting links and evidence attached

---

## Section 12 — Unique Perplexity Computer Capabilities

These capabilities are available in Perplexity Computer and extend the above workflows in ways not available in Claude Code or standalone deployments.

### 400+ Pre-Built Integrations

Perplexity Computer connects to over 400 external tools and services without any configuration on your part. Relevant integrations for operations and CX work include:

**CRM & Sales:**
- Salesforce, HubSpot, Pipedrive — read account context, contact history, deal status, and notes directly from the CRM when researching a customer or drafting a response
- Pull account tier, ARR, renewal date, and CSM assignment without leaving the conversation

**Email & Calendar:**
- Gmail, Outlook — search customer email threads, read correspondence history, find prior commitments, identify patterns across accounts
- Google Calendar, Outlook Calendar — check meeting history, find prior calls, schedule follow-up
- Use when building escalation context: pull the full email thread, not just the latest message

**Ticketing & Project Management:**
- Jira, Linear, GitHub Issues — search existing bugs, link escalations to engineering tickets, check sprint status
- Asana, Monday.com, Notion — read project plans and task status without switching tools

**Documentation & Knowledge:**
- Confluence, Notion, Google Drive — search internal wikis and runbooks directly when answering customer research questions
- Slack — search team channels for context on known issues, recent incidents, and prior decisions

**Financial & Accounting:**
- QuickBooks, Xero — pull invoice and billing data when processing financial documents
- Stripe — confirm payment status, subscription tier, and billing history

**Communication Channels:**
- Intercom, Zendesk, Freshdesk — read full ticket thread history and customer context
- Slack, Teams — send escalation notifications or update team channels directly after triage

### Scheduled Monitoring & Proactive Workflows

Unlike static skill applications, Perplexity Computer can be configured to run operations tasks on a schedule:

**Support Monitoring:**
- Run ticket triage on all new inbound tickets every 30 minutes
- Alert on any ticket that exceeds SLA without a response
- Detect pattern: flag when 3+ tickets with the same symptom appear within 24 hours

**KB Maintenance:**
- Weekly scan for KB articles not updated in 6+ months — generate a review queue
- Monthly comparison of top ticket categories vs. KB article coverage — surface gaps
- Track article helpfulness ratings and flag those below threshold

**Portfolio Health:**
- Daily pull of Jira sprint data — auto-calculate sprint health score
- Weekly portfolio RAG status update based on latest milestone data
- Alert when any project risk score crosses from Mitigate to Avoid threshold

**Financial Document Processing:**
- Monitor a designated inbox folder for new invoices
- Auto-extract, rename, and file new documents as they arrive
- Generate monthly expense summary CSVs automatically

### Real-Time Web Research for CX

When answering customer research questions that involve third-party tools, competitive context, or public product information, Perplexity Computer can search the web in real time — not just your internal knowledge base.

**Use for:**
- "Does [our integration] support [third-party API version]?" — search current third-party docs
- "Has [vendor] changed their OAuth flow recently?" — verify with current documentation
- "What are customers saying about this error in the community forums?" — surface community workarounds

**Source hierarchy when using web research:**
1. Official internal sources (highest authority — Sections 5 and 6)
2. Official third-party documentation (current, from vendor's own site)
3. Community forums and user discussions (verify before sharing)
4. General web results (lowest confidence — always flag)

### Multi-Step Orchestrated Workflows

Perplexity Computer can chain tools together in single conversations:

**Example: Full Ticket-to-KB Pipeline**
1. Read new support ticket from Zendesk
2. Search Confluence for existing KB articles on the topic
3. Search Jira for related engineering tickets
4. Search Gmail for prior customer correspondence
5. Draft a response using the cx-response-drafting framework
6. If escalation needed: generate structured escalation using the cx-escalation format and post to Slack #engineering channel
7. After resolution: draft a KB article using cx-knowledge-management structure and save to Confluence draft

**Example: Sprint Ceremony Prep**
1. Pull sprint data from Jira
2. Calculate sprint health score across all 6 dimensions
3. Run velocity analysis with rolling averages
4. Pull retrospective action items from last sprint
5. Check completion status of each action item
6. Generate sprint review summary and retrospective starter deck

**Example: Customer Research Brief**
1. Pull account data from Salesforce (tier, ARR, health score)
2. Search Gmail for recent customer correspondence
3. Search Zendesk for open and recent tickets
4. Search Confluence for any account-specific notes
5. Search web for any recent news about the customer's company
6. Synthesize into confidence-scored answer using Section 5 framework

### Integration-Enabled Triage Enhancements

With CRM and ticketing integrations, triage becomes significantly more contextual:

**Before routing a P1:**
- Automatically check Salesforce: is this customer on an enterprise plan with an uptime SLA?
- Check Jira: is there an open engineering ticket for this issue already?
- Check Slack: has the engineering team been alerted already?

**Before drafting a billing response:**
- Pull Stripe subscription status directly — do not rely on customer's description alone
- Check payment history for the last 90 days
- Verify current plan tier and feature entitlements

**Before escalating to engineering:**
- Search Jira for any similar bug reports in the last 30 days
- Pull the relevant error logs from your logging integration if available
- Confirm the reproduction steps against your test environment

---

## Appendix A — Cross-Domain Workflow: Ticket to Resolution

This workflow integrates multiple sections of this skill to move a ticket from intake to knowledge base article.

```
1. TICKET INTAKE
   └── Section 2: Apply triage matrix → category + priority
   └── Check for duplicate tickets and known-issue KB articles
   └── Auto-respond with category-appropriate template

2. INVESTIGATION
   └── Section 5: Customer research — five-tier source hierarchy
   └── Assign confidence level to findings
   └── Escalate if: roadmap commitment, pricing, security, or custom config

3. CUSTOMER RESPONSE
   └── Section 3: Draft using tone spectrum and structure
   └── Section 11: Quality checklist before sending
   └── Set follow-up timer per cadence table

4. ESCALATION (if needed)
   └── Section 4: Build structured escalation with reproduction steps
   └── Quantify business impact using impact dimensions table
   └── Post to appropriate channel; maintain customer update cadence

5. RESOLUTION
   └── Close loop with customer: confirm resolution, offer resources
   └── Internal: document what was learned

6. KNOWLEDGE BASE
   └── Section 6: Evaluate whether a KB article should exist
   └── If yes: choose article type (how-to / troubleshooting / FAQ / known issue)
   └── Write using templates, verify steps, peer review
   └── Section 11: KB article quality checklist before publishing
   └── Link KB article back to resolved ticket for tracking
```

---

## Appendix B — Cross-Domain Workflow: Sprint to Portfolio

This workflow connects sprint-level data to portfolio-level decisions.

```
1. SPRINT DATA COLLECTION (daily)
   └── Section 8: Track velocity, blockers, ceremony engagement
   └── Log each blocker with resolution time for health scoring

2. SPRINT CEREMONIES
   └── Section 8: Planning → standup → review → retrospective
   └── Section 11: Verify sprint goal achievement with evidence

3. SPRINT HEALTH SCORING (end of sprint)
   └── Section 8: Score all six dimensions → overall health grade
   └── Flag any dimension below 60 for intervention

4. PORTFOLIO ROLL-UP (weekly)
   └── Section 7: Aggregate sprint health into portfolio health
   └── Recalculate RAG status for all active projects
   └── Update risk register based on new sprint data

5. EXECUTIVE REPORTING (monthly)
   └── Section 7: Generate portfolio status report from template
   └── Apply WSJF/RICE/ICE to reprioritize upcoming work
   └── Section 11: Verify all data in report is current before distribution

6. QUARTERLY REVIEW
   └── Section 7: Portfolio rebalancing — three horizons model
   └── Risk appetite reassessment
   └── Methodology evolution based on what's working
```

---

## Appendix C — Quick Reference Cards

### Ticket Priority Quick Reference

| Situation | Priority |
|-----------|----------|
| Production down, all users | P1 |
| Data loss or security incident | P1 |
| Core feature broken, no workaround | P2 |
| Many users affected | P2 |
| Feature partially broken, workaround exists | P3 |
| Single user, non-critical | P3 |
| How-to question | P4 |
| Feature request | P4 |
| Cosmetic issue | P4 |

### Escalation Severity Quick Reference

| Condition | Severity |
|-----------|----------|
| Production down, data at risk, security breach | Critical |
| Major functionality broken, key customer blocked, SLA at risk | High |
| Significant issue with workaround, important but not urgent | Medium |

### Response Tone Quick Reference

| Situation | Lead With |
|-----------|----------|
| Customer is frustrated | Empathy and acknowledgment |
| Customer is confused | Clarity and simple explanation |
| Customer is excited | Enthusiasm and confirmation |
| Customer is escalating | Ownership and concrete action plan |
| Delivering bad news | Directness and alternatives |
| Routine update | Concise status and next steps |

### Sprint Health Quick Reference

| Health Score | Grade | Action |
|-------------|-------|--------|
| 90–100 | A | Optimize for innovation |
| 80–89 | B | Minor process improvements |
| 70–79 | C | Active coaching needed |
| 60–69 | D | Intervention required |
| <60 | F | Immediate escalation |

### Verification Gate Quick Reference

Before claiming anything is done:
1. What command or check proves this claim?
2. Run it fresh — right now
3. Read the full output
4. Does the output confirm the claim?
5. Only then make the claim

---

*Operations & CX Super-Skill v1.0 — Merged from Perplexity Computer cx-ticket-triage, cx-response-drafting, cx-escalation, cx-customer-research, cx-knowledge-management, and Claude Code file-organizer, invoice-organizer, scrum-master, senior-pm, verification-before-completion, writing-plans skills.*
