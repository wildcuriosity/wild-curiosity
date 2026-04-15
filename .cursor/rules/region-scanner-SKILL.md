---
name: region-scanner
description: >
  AI Search Visibility Scanner for hospitality prospects. Use this skill whenever the user wants to
  scan a destination, region, or market to find independent or boutique hotels that have poor AI search
  visibility. Also trigger when the user mentions prospecting, lead generation, hotel scanning, AI audit
  prospects, destination analysis, or finding hotels that are "invisible" to AI. This skill searches for
  hotels in a target region, checks whether they appear in AI-generated travel recommendations, and
  produces a ranked prospect list with visibility scores and outreach-ready insights. Designed for
  Wild Curiosity's sales pipeline.
---

# Region Scanner — AI Search Visibility Prospector

You are helping run a sales prospecting tool for **Wild Curiosity** (wildcuriosity.ai), an AI-powered
destination marketing agency that helps independent and boutique hotels get found, booked, and grown
through AI search optimization.

## What This Skill Does

Given a destination or region, this skill:
1. Identifies 4-5 star independent/boutique hotels in that area
2. Tests whether each hotel appears in AI-generated travel recommendations
3. Scores each hotel's AI visibility
4. Produces a ranked prospect list — hotels with the worst AI visibility are the hottest leads

## Market Focus

Wild Curiosity is initially targeting **European luxury hospitality markets** — Greece, Italy,
France, Spain, Portugal, Croatia, Turkey, and similar destinations. All reports should use
British English spelling (travellers, organised, recognised), EUR (€) for any financial
references, and language that is clear for an international audience. No American idioms,
no business jargon, no AI-sounding phrases.

## Why This Matters

Most independent hotels don't realise they're invisible to AI assistants. When a traveler asks ChatGPT
or Perplexity "best boutique hotel in [destination]", the same big chains and OTA-promoted properties
show up. Independent hotels with great reviews and unique character get skipped entirely. This skill
finds those overlooked properties — they're the perfect clients for Wild Curiosity.

## Hard Filter: 4-5 Star Properties Only

This is non-negotiable. Wild Curiosity's services start at $3,000/month — properties below 4-star
simply don't have the budget. Every hotel in your final report must be a genuine 4-5 star (or
equivalent luxury/upscale boutique) property. If you can't confirm the star rating, look for proxy
signals: room rates above $200/night, presence on luxury travel platforms (Mr & Mrs Smith, Small
Luxury Hotels, Leading Hotels of the World, Relais & Chateaux), upscale positioning language on
their website, or consistent "luxury" / "boutique" categorization on TripAdvisor/Booking.com.

**Exclude without exception:** 3-star and below, hostels, guesthouses, B&Bs that aren't positioned
as luxury, budget chains, apartment rentals, and any property where average room rates are under
$150/night. When in doubt, leave it out — a smaller list of qualified prospects is far more valuable
than a padded list with weak leads.

## Step-by-Step Workflow

### Step 1: Understand the Target Region

The user will provide a destination. This could be specific ("Kefalonia, Greece") or broad ("Greek Islands").
If broad, narrow it down to 2-3 specific sub-destinations to keep the scan manageable.

Confirm with the user:
- Target destination(s)
- Property type (default: independent/boutique — exclude major chains)
- How many prospects they want (default: 8-12)

Star rating is always 4-5 star. Don't ask — it's already decided.

### Step 2: Find Hotels in the Region

Use **WebSearch** to find independent and boutique hotels in the target destination. Run multiple searches
to build a comprehensive list:

**Search queries to use (adapt to the destination):**
- `"best boutique hotels in [destination]"`
- `"top independent hotels [destination]"`
- `"luxury boutique hotels [destination] 2025 2026"`
- `"[destination] hotel reviews boutique independent"`
- `"small luxury hotels [destination]"`

Also try:
- `site:tripadvisor.com boutique hotel [destination]`
- `site:booking.com boutique hotel [destination]`

From the search results, compile a list of **12-20 candidate hotels**. For each, capture:
- Hotel name
- Location (specific town/area)
- Star rating or category (if available)
- Brief description
- Whether it appears to be independent or chain-affiliated

**Filter out ruthlessly:** Major chains (Marriott, Hilton, IHG, Accor, Hyatt, Best Western, Wyndham,
Radisson, etc.), hostels, apartments, B&Bs, guesthouses, and anything below 4-star equivalent.
If a property's star rating is ambiguous, check room rates and positioning. Under $150/night average
or categorized as "mid-range" on Booking.com? Cut it. The goal is a list where every single hotel
could realistically afford a $3,000+/month engagement.

### Step 3: Test AI Search Visibility

This is the core value. For each candidate hotel, test whether AI assistants recommend it.

**Run these AI-simulating searches via WebSearch:**

For each hotel on your list, search:
1. `"best boutique hotel in [destination]" AI recommendation`
2. `"where to stay in [destination]" boutique independent`
3. `ChatGPT recommendation hotel [destination]`
4. `"best hotels [destination]" Perplexity AI`

Also run **generic traveler queries** that a real person might ask an AI assistant:
- `"plan a trip to [destination] where should I stay"`
- `"romantic boutique hotel [destination]"`
- `"best [destination] hotels for couples/families/solo travelers"`

**What you're looking for:**
- Does the hotel appear in AI-curated "best of" lists?
- Is it mentioned in AI-generated travel guides or itineraries?
- Does it show up in Perplexity/ChatGPT-style recommendation roundups?
- Or is it only found on OTA listing pages (Booking.com, Expedia) and its own website?

### Step 4: Score Each Hotel

Rate each hotel's AI visibility on a scale:

| Score | Label | Meaning |
|-------|-------|---------|
| 1 | Invisible | Not found in any AI recommendation context. Only appears on OTAs or own site. |
| 2 | Barely Visible | Mentioned once in a minor list or only in very specific long-tail searches. |
| 3 | Partially Visible | Appears in some AI-curated content but not consistently. |
| 4 | Moderately Visible | Shows up in several recommendation contexts. Some AI presence. |
| 5 | Well Visible | Consistently recommended. Not a strong prospect — they're already doing something right. |

**Scoring guidance:**
- Hotels scoring 1-2 are **hot prospects** — they have the most to gain
- Hotels scoring 3 are **warm prospects** — room for improvement
- Hotels scoring 4-5 are **low priority** — already have AI presence

Also note for each hotel:
- **Review strength**: Do they have strong reviews (4.5+ on TripAdvisor/Google) despite low AI visibility?
  This is the golden combination — great product, terrible AI presence. These are the easiest sell.
- **Content gaps**: Does the hotel have a website? Blog? Is their content rich enough for AI to reference?
- **Unique angle**: What's their differentiator? (historic property, family-run, design-forward,
  eco-focused, etc.) This feeds into personalized outreach later.

### Step 5: Find the Right Contact

For each qualified prospect, find the best person to reach out to. The goal is a named individual,
not a generic info@ address.

**Who to target (in priority order):**
1. **Owner or General Manager** — at independent boutiques (10-50 rooms), this is often the same
   person. They control budget, feel OTA commission pain personally, and can say yes without committee
   approval. This is the ideal contact.
2. **Director of Sales & Marketing / Marketing Manager** — at larger properties (50+ rooms) or those
   with a management company. They'll immediately understand the value proposition but may need to
   escalate for budget.
3. **Revenue Manager** — good secondary contact. Cares about channel mix, direct booking rates, and
   anything that reduces OTA dependency.

**Do NOT use:** info@, reservations@, reception@, booking@, or generic contact form submissions.
These go into a black hole.

**How to find contacts:**

Use **WebSearch** and **WebFetch** for each hotel:

1. Search `"[Hotel Name]" general manager` or `"[Hotel Name]" owner`
2. Check the hotel's own website — look for "About Us", "Our Team", "Management" pages. Many
   boutique hotels feature the owner/GM by name, often with a personal story.
3. Search `site:linkedin.com "[Hotel Name]" general manager OR "marketing manager"`
4. If you find a name, the email pattern at small hotels is usually predictable:
   firstname@hotelname.com, or gm@hotelname.com, or the domain from their website contact page.
5. Check the hotel's website contact page — sometimes individual department emails are listed
   (e.g., marketing@, gm@) which are better than info@.

**What to capture for each hotel:**
- **Contact name** (if found)
- **Contact role** (Owner, GM, Marketing Director, etc.)
- **Contact email** (direct if possible, department email as fallback)
- **Source** (where you found it — website team page, LinkedIn, etc.)
- **Confidence level**: "Verified" (found on official site), "Likely" (found via LinkedIn/pattern),
  or "Generic" (only found info@ or contact form)

If you can't find a named contact for a hotel, note that in the report but still include the hotel.
A hot prospect with a generic email is still worth listing — the user can find the contact manually
or use LinkedIn outreach.

### Step 6: Produce the Prospect Report

Create an HTML report saved to the workspace folder. The report should include:

**Header section:**
- Report title: "AI Visibility Scan: [Destination]"
- Date of scan
- Wild Curiosity branding (use the color palette below)
- Summary stats: X hotels scanned, Y hot prospects identified

**Prospect table (sorted by opportunity — lowest visibility + highest reviews first):**

For each hotel:
- Hotel name
- Location
- AI Visibility Score (1-5) with color coding (red for 1-2, amber for 3, green for 4-5)
- Review Rating (if found)
- **Contact** — name, role, and email (with confidence badge: Verified/Likely/Generic)
- Key finding (1-2 sentences on what's missing)
- Opportunity note (what Wild Curiosity could help with)
- Website URL

**Executive summary:**
- Top 3-5 hottest prospects with a sentence on why each is a great lead
- Regional pattern observations (e.g., "most boutique hotels in [area] are invisible to AI despite
  strong review profiles")
- Recommended outreach priority

### Wild Curiosity Brand Palette

Use these colors for the HTML report:
- Background: `#1E2926` (deep sage)
- Surface/cards: `#2A3533`
- Primary accent: `#CBA27D` (camel/gold)
- Text primary: `#F5F0E8` (warm cream)
- Text secondary: `#7B7670`
- Text on light backgrounds: `#2D2926` (espresso)
- Borders: `#3D4B47`
- Success/visible: `#7B8176` (sage)
- Warning/partial: `#CBA27D` (camel)
- Danger/invisible: `#8B4D3B` (muted terracotta)
- Card hover: `#354440`

Typography:
- Headings: system sans-serif, light weight
- Body: system sans-serif
- Accent text: Georgia or serif fallback, italic

### Step 7: Add Pipeline Actions to the Report

The HTML report isn't just a read-only document — it's the first step in a sales pipeline.
Add interactive elements at the bottom of the report that connect the scan to the next steps:

**"Ready to Act" section at the bottom of the HTML report:**

For each hot prospect (scored 1-2), include a pre-formatted action card with:
- A "Run Quick Audit" prompt — a ready-to-paste prompt the user can give to Skill 2 (Top-Line Audit).
  Format: `"Run a top-line AI audit for [Hotel Name] in [Destination]. Their website is [URL].
  They have [X] rating on TripAdvisor but scored [Y]/5 on AI visibility."`
- A "Draft Outreach" prompt — a ready-to-paste prompt for Skill 3 (Personalized Outreach).
  Format: `"Draft outreach for [Hotel Name]. Contact: [Name, Role, Email]. Key finding: [specific gap].
  Angle: [unique hook]."`

This means the user can scan a region, see the results, and immediately copy-paste the next action
into their chat without having to re-explain context. Each step in the pipeline carries forward
what the previous step learned.

**Also include a "Pipeline Summary" block** at the very end — a simple structured list of all
prospects with their status set to "Scanned" that the user can reference when updating their
workspace tracker.

### Step 8: Save and Present

Save the HTML report to the user's workspace folder with a descriptive filename:
`AI_Visibility_Scan_[Destination]_[Date].html`

Present the file link to the user with a brief summary of findings — the top 3 prospects
and the key regional insight. Remind them they can copy the "Run Quick Audit" prompts to
immediately move their top prospects to the next stage.

## Important Notes

- **Be thorough but realistic.** Web search results are a proxy for AI visibility, not a perfect
  measure. Be transparent about this — the scan identifies likely gaps, not guaranteed ones.
- **Prioritize independent properties.** Chain hotels have corporate digital teams. The sweet spot
  for Wild Curiosity is independent 4-5 star properties with great guest experiences but poor
  digital/AI presence.
- **Quality over quantity.** It's better to deeply research 8 well-qualified prospects than to
  superficially list 20.
- **Note data limitations.** If search results are thin for a region, say so. Some destinations
  have fewer independent luxury properties than others.
- **The prospect list feeds into Skill 2 (Top-Line Audit) and Skill 3 (Outreach).** Structure the
  data cleanly so it can be picked up by subsequent workflow steps.
