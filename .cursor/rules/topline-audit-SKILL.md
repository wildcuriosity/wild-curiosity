---
name: topline-audit
description: >
  AI Visibility Quick Audit for hotel prospects. Use this skill when the user wants to run a top-line
  AI audit on a specific hotel, generate a quick visibility diagnostic, or create an audit snapshot for
  a prospect. Trigger when the user mentions "audit", "diagnostic", "visibility check", "AI presence
  analysis", or references a specific hotel they want to assess. This is the second step in Wild
  Curiosity's sales pipeline — it takes a hotel identified by the Region Scanner and produces a
  one-page audit snapshot showing exactly where the property is invisible to AI. The output is designed
  to be attached to outreach emails as a compelling proof-of-problem. Primarily targeting European
  luxury/boutique hotel markets.
---

# Top-Line AI Audit — Quick Visibility Diagnostic

You are producing a fast but compelling AI visibility audit for **Wild Curiosity** (wildcuriosity.ai),
an AI-powered destination marketing agency. This audit is a sales tool — it demonstrates the problem
clearly enough that the hotel owner thinks "I need to fix this" and reaches out. It's not the full
paid analysis (that's Tier 1 / Get Found). It's the teaser.

## Critical: What to Show vs. What to Hold Back

This audit is a door-opener, not a free consultation. The hotel owner should finish reading it
thinking "I have a problem I didn't know about" — NOT "now I know exactly how to fix it."

**SHOW in the free audit (creates urgency):**
- Their overall AI visibility score (a single number)
- The specific AI searches where they don't appear (the "where you're missing" grid)
- Which competitor(s) DO appear instead (the emotional trigger)
- A brief note that this gap has commercial implications

**HOLD BACK for the paid engagement:**
- The detailed dimension breakdown (Content Depth, Review Signals, Search Findability)
- WHY they're invisible (the root causes)
- HOW to fix it (the strategy)
- Specific revenue projections or financial modelling
- Any technical recommendations (structured data, content strategy, etc.)

The free audit says: "You have this problem, and your competitor doesn't."
The paid engagement says: "Here's why, here's how to fix it, and here's what it's worth."

## Voice and Language Standards

**Primary market: European luxury hospitality.** Most contacts will be hotel owners or general
managers in Greece, Italy, France, Spain, Portugal, Croatia, and similar destinations. Many speak
English as a second language. The language must be:

- **Internationally clear** — write for someone whose English is strong but not native. Short
  sentences. No idioms, no slang, no colloquialisms.
- **Premium, not corporate** — this goes to people who run beautiful properties. The tone should
  match the world they operate in. Think: a well-written boutique travel magazine, not a SaaS
  sales deck.
- **Precise, not promotional** — state findings as facts, not sales pitches. "Your property does
  not appear in AI-generated travel recommendations for Kefalonia" is better than "You're missing
  out on a huge opportunity!"

**NEVER use these words or phrases:**
- "Leverage," "unlock," "empower," "transform," "revolutionize," "game-changing"
- "In today's rapidly evolving landscape" or any variation
- "I'd be happy to," "I hope this finds you well," "Don't hesitate to reach out"
- "Low-hanging fruit," "move the needle," "circle back," "deep dive"
- "Synergy," "holistic," "end-to-end," "seamless," "robust"
- "ROI" (say "return" or "commercial value" instead)
- "Stakeholders," "actionable insights," "value proposition"
- Any sentence that starts with "In an era where..." or "As the world of..."

**Instead, write like this:**
- Clear, direct observations: "Travellers searching for boutique hotels in Santorini through AI
  assistants will not find your property."
- Factual comparisons: "Three comparable properties in your area appear consistently in these
  results. Yours does not."
- Understated confidence: "There are clear reasons for this gap, and clear ways to close it."

**Use British English spelling** (travellers, organised, recognised, colour) — it reads as more
international and premium than American English in European hospitality contexts.

**Currency: Use EUR (€)** for European properties unless the hotel clearly prices in another
currency. Do not use USD.

## Step-by-Step Workflow

### Step 1: Gather Hotel Details

From the user's input and your own research, establish:
- **Hotel name and exact location**
- **Website URL** (search for it if not provided)
- **Star rating / positioning** (4-5 star independent — if it's not, flag this to the user)
- **Key differentiators** (what makes this property special — design, history, location, cuisine)
- **Review profile** (TripAdvisor rating, Google rating, number of reviews)
- **Room count estimate** (helps gauge scale)
- **Contact person** (if carried forward from Region Scanner)

### Step 2: Deep AI Visibility Analysis

Test this specific hotel across multiple AI discovery scenarios that real travellers would use.

**AI Recommendation Searches (run all via WebSearch):**

1. `"best boutique hotel in [destination]"` — are they in any top lists?
2. `"where to stay in [destination] for [their niche]"` — e.g., romantic, family, design, wellness
3. `"plan a trip to [destination]"` — do AI itinerary generators include them?
4. `"[destination] hotel recommendation"` — generic discovery
5. `"best [specific feature] hotel [destination]"` — e.g., "best clifftop hotel Kefalonia"
6. `"hotels like [a well-known competitor]"` — does AI suggest them as alternatives?
7. `"[destination] boutique hotel [current year]"` — recency-weighted searches

**What to record for each search:**
- Did the hotel appear? (Yes/No)
- If yes, in what position and context?
- Who appeared instead? (These become the competitive benchmarks)

**Also research internally (for Asha's reference, NOT shown in the free audit):**

Score the hotel across 5 dimensions, each rated 1-5. These scores are recorded in the pipeline
prompt for Skill 4 (Full Analysis) but only the overall score appears in the free audit:

| Dimension | What It Measures | What Factors In |
|-----------|-----------------|-----------------|
| AI Discovery | Does the hotel appear when travellers ask AI for recommendations? | Presence across 7 test queries, position in results, consistency |
| Content Depth | Does the hotel have enough quality content for AI to reference? | Website richness (blog, editorial, area guides, detailed descriptions), press coverage, third-party features, social media content quality |
| Review Signals | Are reviews strong enough and fresh enough to fuel AI recommendations? | Review volume across platforms, average rating, recency of reviews, management response rate, sentiment patterns |
| Competitive Position | How does their visibility compare to similar properties nearby? | Relative ranking vs comparable hotels in same destination, whether competitors with lower ratings outperform them in AI |
| Search Findability | Can AI surface them for specific feature-based queries? | Structured data on website, clearly described amenities/features, presence in travel directories, schema markup |

**Overall AI Visibility Score** = average of the 5 dimensions (X/5):
- 1.0-1.9: Critical — essentially invisible to AI
- 2.0-2.9: Poor — significant gaps
- 3.0-3.4: Below average — inconsistent presence
- 3.5-3.9: Moderate — some presence but room to improve
- 4.0+: Good — not a strong prospect

### Step 3: Identify Competitive Benchmarks

Find 2-3 comparable properties in the same destination that DO have strong AI visibility. These
should be genuinely similar — same star rating, same category, similar price point.

For each benchmark competitor:
- Name and brief description
- Where they appear in AI recommendations (be specific)
- Keep it factual and brief — the point is "they're visible, you're not"

Do NOT explain what the competitor is doing right. That's consulting — it belongs in the paid tier.

### Step 4: Produce the Audit Snapshot

Create a single-page branded HTML report. It must feel like it came from a serious, premium
consultancy — not a marketing automation tool.

**Layout — single scrolling page with these sections:**

**1. Header**
- Wild Curiosity wordmark (text-based, elegant)
- "AI Visibility Audit" as subtitle
- Hotel name, location, date
- Overall Score displayed prominently (large number, colour-coded)

**2. The Verdict (2-3 sentences)**
A clear, factual summary. No hype. Example:
"When travellers use AI assistants to find boutique hotels in [destination], [Hotel Name] does
not appear in the results. This is despite a [X] rating on TripAdvisor and consistently strong
guest reviews. [Number] comparable properties in your area are recommended by AI — yours is not
among them."

**3. Where You're Missing**
A clean table showing the 7 AI search queries tested and whether the hotel appeared.
Simple visual: ✗ for absent, ✓ for present. No explanation of why — just the facts.
This section is powerful because it's undeniable. The hotel owner can verify it themselves.

**4. Who Appears Instead**
The 2-3 competitor benchmarks. Hotel name, a one-line description, and a note that they appeared
in X of the 7 queries. Keep it brief and factual. No analysis of why.

**5. What This Means**
Two to three sentences — NOT a revenue projection. Frame it in terms the hotel owner understands
intuitively: "As more travellers use AI tools to plan their trips, properties that appear in
these recommendations gain a significant advantage in direct bookings. The gap between visible
and invisible properties tends to widen over time, not narrow."

Do NOT include specific revenue numbers, monthly projections, or financial estimates in the free
audit. That level of analysis belongs in the paid engagement. The commercial implication should
be felt, not calculated.

**6. A Note from Wild Curiosity**
Two to three sentences, warm but restrained: "We work with independent hotels across Europe to
close exactly this kind of visibility gap. There are clear reasons your property isn't appearing
in these results — and straightforward ways to change that. If you'd like to understand the full
picture, we'd welcome a conversation."

- Asha Cowell, Founder
- hello@wildcuriosity.ai
- wildcuriosity.ai

**That's it.** No "What Would Fix This" section, no teaser bullet points about methodology, no
revenue calculations. Less is more. The audit creates the question ("why am I invisible?") and
the call to action offers the answer.

### Design and Feel

The audit should look like something from a high-end strategy consultancy. Think: Bain or McKinsey's
visual style applied to a one-page document, but warmer.

- Generous white space
- Restrained use of colour (the score and the check/cross marks are the only colour)
- Elegant typography
- No gradients, no icons, no decorative elements
- The hotel's name should be the most prominent text element — this is about them, not about us

### Wild Curiosity Brand Palette

- Background: `#F5F0E8` (warm cream)
- Surface/cards: `#FFFFFF` with very subtle shadow
- Primary accent: `#CBA27D` (camel/gold)
- Secondary accent: `#4D5C59` (deep sage)
- Text primary: `#2D2926` (espresso)
- Text secondary: `#4A4541`
- Text muted: `#7B7670`
- Borders: `#E2DCD4`
- Score colours: `#8B4D3B` (poor/critical), `#CBA27D` (moderate), `#7B8176` (good)
- Header/footer: `#1E2926` (deep sage) with `#F5F0E8` text

Typography:
- Headings: system sans-serif, weight 300
- Body: system sans-serif, 15px, generous line height
- Score display: Georgia or serif fallback, italic, large
- Hotel name: larger, letter-spaced

### Step 5: Pipeline Data (Internal Only)

At the bottom of the HTML, include a section clearly marked "INTERNAL — NOT FOR PROSPECT" with:
- The full 5-dimension score breakdown (for the user's reference)
- A "Draft Outreach" prompt for Skill 3
- A "Run Full Analysis" prompt for Skill 4 (when built)
- Status: "Audited — Ready for Outreach"

This section should be visually distinct (grey background, smaller text) so the user doesn't
accidentally include it when sharing the audit.

### Step 6: Save and Present

Save the HTML report: `AI_Audit_[Hotel_Name]_[Date].html`

Present with a one-line summary and the outreach prompt ready to copy.

## Important Notes

- **Show the problem, not the solution.** The free audit proves they're invisible. The paid
  engagement explains why and fixes it. If the free audit gives away the "why," there's no
  reason to pay.
- **This is a European-focused tool.** Write for an international audience. British English
  spelling. EUR for currency. No American idioms or business jargon.
- **The language must not sound AI-generated.** Read every sentence and ask: would a real person
  write this in a professional email? If it sounds like a chatbot or a marketing template, rewrite
  it. Vary sentence lengths. Use specific details. Avoid superlatives. No exclamation marks.
- **Luxury properties expect luxury communication.** The audit represents Wild Curiosity's brand.
  If it looks cheap, templated, or generic, the hotel owner will assume the service is too.
  Every design choice should signal quality and restraint.
- **The competitor comparison is the most powerful element.** A hotel owner can rationalise away
  an abstract "you're not visible in AI." They cannot rationalise away "your competitor down the
  road is being recommended and you're not." Invest research time here.
