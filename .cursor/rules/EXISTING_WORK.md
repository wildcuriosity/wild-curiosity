# Wild Curiosity — Existing Work Brief
## For Cursor: Build on this foundation, not from scratch

This document captures everything already built for Wild Curiosity's AI Visibility Scan reports.
These HTML reports are the core deliverable of the region-scanner sales prospecting workflow.

---

## 1. Brand Colors

These are the two sources of truth. The logo brief (aspirational brand direction) and the report
palette (what's already built) differ slightly. Reports use the darker palette.

### Report HTML Palette (currently implemented)

| Token            | Hex       | Usage                                          |
|------------------|-----------|------------------------------------------------|
| Background       | `#1E2926` | Page background — deep sage green-black        |
| Surface / Cards  | `#2A3533` | All card and panel backgrounds                 |
| Card Hover       | `#354440` | Hover state on prospect cards                  |
| Border           | `#3D4B47` | All dividers, card borders, table lines        |
| Primary Accent   | `#CBA27D` | Gold/camel — brand color, headings, scores, links |
| Text Primary     | `#F5F0E8` | Warm cream — main body text, hotel names       |
| Text Secondary   | `#D8D3CB` | Field content, slightly dimmed                 |
| Text Muted       | `#7B7670` | Labels, metadata, subtitles, section notes     |
| Score Hot        | `#8B4D3B` | Muted terracotta — Score 1 and 2 badges, hot card border |
| Score Hot Label  | `#C47A5A` | Lighter terracotta for score label text        |
| Score Warm       | `#6B5A2E` | Dark amber — Score 3 badge background          |
| Score Cool       | `#3D4B47` | Score 4–5 badge (same as border color)         |
| Score Cool Label | `#7B8176` | Sage — Score 4–5 text                         |
| Hot Tag BG       | `#8B4D3B` | "Hot Lead" inline tag                          |
| Warm Tag BG      | `#5A4A1E` | "Warm Lead" inline tag                         |
| Location Tag BG  | `#1E2926` | Location pill (same as background)             |
| Insight Border   | `#CBA27D` | Gold border on insight/pattern observation box |
| Status Pill BG   | `#354440` | "Scanned" status in pipeline table             |
| Verified Badge   | `#3D5A3E` bg / `#7BB87F` text | Green — Verified contact           |
| Likely Badge     | `#4A4020` bg / `#CBA27D` text | Amber — Likely contact             |
| Generic Badge    | `#3D4B47` bg / `#7B7670` text | Grey — Generic/info@ contact      |

### Logo Brief Palette (brand identity direction — may diverge from reports)

| Token       | Hex       | Notes                                |
|-------------|-----------|--------------------------------------|
| Primary     | `#3A9BBE` | Bright Mediterranean ocean blue      |
| Dark        | `#1A2520` | Deep earth green-black (close to report bg) |
| Accent      | `#C8923A` | Warm ochre gold (close to report accent) |
| Background  | `#F5F0E8` | Warm cream (same as report text primary) |

Note: The report cream (`#F5F0E8`) used as text-on-dark in reports is the same value as the logo
brief's light background. The ocean blue (`#3A9BBE`) does not currently appear in any reports —
it is a logo-only color. The gold is slightly different (`#C8923A` brief vs `#CBA27D` reports).

---

## 2. Prospect Card Data Structure

Every hotel prospect card contains the following fields. This is the full schema.

### Card Header (always visible)
| Field         | Content                                                              |
|---------------|----------------------------------------------------------------------|
| Rank          | `#1`, `#2`, etc. — position in the ranked list                      |
| Hotel Name    | Full property name                                                   |
| Priority Tag  | Inline badge: `HOT LEAD` (terracotta) or `WARM LEAD` (amber)        |
| Location Tag  | Inline pill: specific area/village (e.g., "Adamas", "Pollonia")     |
| Card Location | Subtitle line: village, island, key descriptors, room type, features |
| AI Score Badge | Circle badge (1–5) with color-coded background                     |
| Score Label   | Text label below badge: "Invisible", "Barely Visible", etc.         |

### Card Body (two-column grid, some fields full-width)
| Field                    | Format          | Notes                                                  |
|--------------------------|-----------------|--------------------------------------------------------|
| Key Finding              | Paragraph (col) | 2–4 sentences. What the property is, what's missing.  |
| Review Strength          | Rating + source | Numeric rating (e.g., "4.8 / 5"), platform, contextual note |
| Contact                  | Contact block   | See Contact Block spec below                          |
| Website                  | Link            | Hotel URL, styled in gold                             |
| Unique Angle             | Paragraph (col) | The hook: founding story, setting, differentiator     |
| Wild Curiosity Opportunity | Paragraph (full-width) | Specific pitch angle and how to approach |

### Contact Block (nested inside card body)
| Sub-field        | Format                                                              |
|------------------|---------------------------------------------------------------------|
| Contact Name     | Name or descriptor (e.g., "Family Founders"), styled gold          |
| Confidence Badge | Inline pill: `VERIFIED`, `LIKELY`, or `GENERIC`                   |
| Contact Role     | Job title or ownership type (e.g., "Owner-operators", "General Manager") |
| Contact Email    | Monospace font. May also include website domain after `·`          |

Confidence badge semantics:
- `VERIFIED` — name/email confirmed on official hotel website or team page (green)
- `LIKELY` — found via LinkedIn, guest reviews, or pattern inference (amber)
- `GENERIC` — only info@, contact form, or no contact found (grey)

### Card Visual Logic
- Hot Lead cards: left border `3px solid #8B4D3B` (terracotta)
- Warm Lead cards: left border `3px solid #CBA27D` (gold/amber)
- Cards hover to `#354440` (slightly lighter than resting `#2A3533`)
- Score badges: circular 32x32px, Score 1 and 2 share the same terracotta; Score 3 is amber; Score 4-5 are sage/grey

---

## 3. AI Visibility Scoring System

| Score | Label          | Color        | Meaning                                                               | Pipeline Priority |
|-------|----------------|--------------|-----------------------------------------------------------------------|-------------------|
| 1     | Invisible      | Terracotta   | Not found in any AI recommendation context. Only on OTAs or own site. | HOT — highest priority |
| 2     | Barely Visible | Terracotta   | Mentioned once in a minor list or only in niche long-tail searches.   | HOT               |
| 3     | Partially Visible | Amber     | Appears in some AI-curated content but not consistently.              | WARM              |
| 4     | Moderately Visible | Sage    | Shows up in several recommendation contexts. Deprioritize.            | LOW               |
| 5     | Well Visible   | Sage/grey    | Consistently recommended. Not a Wild Curiosity prospect.              | EXCLUDED          |

Scoring is based on web search simulations that replicate what AI assistants (ChatGPT, Perplexity,
Gemini) return for typical traveler queries. A property appearing only on Booking.com or Expedia
listing pages — regardless of review quality — is treated as Invisible (Score 1).

The "golden combination" that makes the strongest pitch: **high review score + low AI visibility**.
A hotel with a 4.8 TripAdvisor rating and Score 1–2 is the easiest sell.

---

## 4. Report Sections (in order)

Every report contains the following sections in this exact sequence:

### 4.1 Page Header
- Wild Curiosity wordmark top-left: `WILD CURIOSITY` in gold uppercase, letter-spaced
- Tagline below: `wildcuriosity.ai — AI Visibility for Independent Hotels` in muted text
- Scan date top-right + `Region Scanner v1.0` version note
- H1 title: `AI Visibility Scan: [Destination, Country]` — "Destination" portion in gold
- Subtitle (italic serif): e.g., "Independent & boutique hotels · 4–5 star & equivalent luxury · [Region] prospecting"
- Stats bar (4–5 counters): Hotels Evaluated · Qualified Prospects · Hot Leads (Score 1–2) · Warm Leads (Score 3) · Excluded / Low Priority

### 4.2 Market Context Note (optional but used in all current reports)
- A short boxed paragraph (styled with gold border, slightly lighter background) that sets the
  scene for the destination — market dynamics, recent growth, why now, the specific opportunity.
- Formatted with a `Market Context:` bold label.

### 4.3 Executive Summary
- Section header: "Executive Summary" + italic note "Top prospects & regional insight"
- Numbered list of the top 3–5 hottest prospects — each as a two-column item:
  - Large light number (1, 2, 3)
  - Hotel name bold + italic description paragraph explaining why it's a top lead
- Regional Pattern Observation box (gold-bordered insight box):
  - Small uppercase label: "REGIONAL PATTERN OBSERVATION"
  - Italic serif paragraph describing the macro pattern (e.g., one property dominating AI,
    geographic blind spots, market structural issues)

### 4.4 Ranked Prospect List
- Section header: "Ranked Prospect List" + "Sorted by opportunity score"
- All prospect cards sorted: Score 1 first (most invisible = hottest), then Score 2, then Score 3
- Within same score, sorted by review strength (higher reviews = higher priority)
- At the end of the list: an "Excluded / Low Priority" note listing properties screened out and why

### 4.5 Ready to Act (Pipeline Actions)
- Section header: "Ready to Act" + "Copy-paste prompts for hot leads"
- One action card per Hot Lead (Score 1–2 only)
- Each action card contains:
  - Hotel name as H3
  - Action tag: score, label, key descriptors, contact email
  - Two prompt blocks (dark background, gold label):
    - **Skill 2 prompt** labeled "→ Skill 2: Run Quick Audit" — ready-to-paste audit trigger
    - **Skill 3 prompt** labeled "→ Skill 3: Draft Outreach" — ready-to-paste outreach trigger
  - Each prompt block ends with a copy hint: "↑ Paste into a new chat to trigger the [skill] skill"

### 4.6 Pipeline Summary Table
- Section header: "Pipeline Summary" + "All prospects · Status: Scanned"
- Full-width table with columns: # · Hotel · Area · AI Score · Priority · Contact · Status
- Every prospect listed (hot and warm)
- AI Score cells: colored text ("1 — Invisible" in terracotta, "3 — Partial" in gold)
- Priority cells: emoji indicator — red circle for Hot, yellow circle for Warm
- Status column: all set to `Scanned` pill

### 4.7 Methodology Note
- Small italic serif text at the bottom, separated by a top border
- Explains: how AI visibility scores are derived, the proxy method, what "invisible" means,
  any region-specific caveats (e.g., which property dominates), and the scan date

---

## 5. Outreach Prompt Format

### Skill 2 — Run Quick Audit
```
"Run a top-line AI audit for [Hotel Name] in [Location], [Country].
Their website is [domain.com].
[1–2 sentences describing the property: type, key feature, founding story or USP.]
[Review score if available, e.g., "4.8 TripAdvisor rating."]
Scored [X]/5 on AI visibility — [Invisible/Barely Visible/etc.] — [specific gap description]."
```

### Skill 3 — Draft Outreach
```
"Draft outreach for [Hotel Name], [Destination].
Contact: [Name or role description] — email [email@domain.com].
Key finding: [1–2 sentence property description with review score + visibility gap].
Angle: [The specific emotional/narrative hook — the founder story, the product paradox,
the traveler mismatch. This is the headline pitch sentence.]"
```

The angle is always a direct, human statement — not a feature list. It speaks to the founder's
emotional investment or articulates the paradox ("You built X. Travelers who want X are asking AI
— and getting someone else.").

---

## 6. Typography System

| Element              | Font                            | Weight / Style            |
|----------------------|---------------------------------|---------------------------|
| Brand wordmark       | System sans-serif               | 600, uppercase, letter-spaced |
| H1 title             | System sans-serif               | 300 (light)               |
| H2 section headers   | System sans-serif               | 400                       |
| Body / card fields   | System sans-serif               | 400                       |
| Italic descriptions  | Georgia, serif                  | Italic                    |
| Contact email        | 'Courier New', monospace        | 400                       |
| Labels / tags        | System sans-serif               | Uppercase, letter-spaced, small |

The serif (Georgia italic) is used specifically for:
- Subtitle line in the header
- Executive summary description paragraphs
- Regional Pattern Observation body text
- Prompt block body text in action cards
- Methodology note
- Section notes next to section headers

This creates a two-voice system: sans-serif for data and structure, serif italic for narrative
and insight.

---

## 7. Visual Logic Summary

### Dark-on-dark hierarchy (3 levels)
1. `#1E2926` — page background (darkest)
2. `#2A3533` — card/panel surface (mid)
3. `#354440` — hover state and some nested elements (lightest dark)

The contact block inside cards inverts this — it uses `#1E2926` (darkest) as a nested inner
block, creating depth within a card.

### Color as signal
- Gold (`#CBA27D`) = brand, positive, actionable, primary emphasis
- Terracotta (`#8B4D3B` / `#C47A5A`) = urgent, invisible, hot prospect
- Sage/grey (`#7B8176` / `#7B7670`) = secondary, deprioritized, already visible
- Border (`#3D4B47`) = structural only, never decorative

### What makes it feel premium
- Light font weight on large headings (300) — confident restraint
- Generous spacing between cards and sections
- No gradients, no shadows, no rounded corners on functional elements (only cards get 10px radius)
- Monospace contact email — signals data precision
- Italic serif for narrative voice — editorial rather than corporate
- Stats bar with large light numbers — like a dashboard, not a table

---

## 8. Hard Business Rules (baked into scan logic)

- **4–5 star only.** Average nightly rate must be above €150–200/night minimum.
  Proxy signals: Mr & Mrs Smith, Small Luxury Hotels, Leading Hotels of the World, Relais &
  Chateaux membership, or luxury/boutique positioning on TripAdvisor/Booking.com.
- **No major chains.** Marriott, Hilton, IHG, Accor, Hyatt, Best Western, Wyndham, Radisson
  excluded without exception. Includes soft brands (e.g., Autograph Collection, MGallery).
- **Design Hotels members** are borderline — they are independently owned but Marriott-distributed.
  Included if the property is owner-operated and independently run in practice.
- **Small Greek collection brands** (Lesante Collection, Andronis Collection, Contessina
  Collection) are included — these are independent Greek family/founder operators, not global
  chains, even though they operate multiple properties.
- **Properties scoring 5** (Well Visible) are excluded from the prospect list — they're already
  doing something right. They appear in the Excluded section at most.
- **Wild Curiosity's engagement starts at $3,000/month.** Every prospect must be a property that
  could realistically afford this. A 6-suite hotel at €400+/night qualifies; a 6-room guesthouse
  at €100/night does not.

---

## 9. Files Produced So Far

All files saved to: `~/LocalOnly/WildCuriosity/`

| File                                        | Destination      | Prospects | Hot | Warm |
|---------------------------------------------|------------------|-----------|-----|------|
| AI_Visibility_Scan_SantaMonica_2026-03-05.html | Santa Monica, CA | 5         | 3   | 2    |
| AI_Visibility_Scan_Athens_2026-03-05.html   | Athens, Greece   | 10        | 6   | 4    |
| AI_Visibility_Scan_Zakynthos_2026-03-05.html | Zakynthos, Greece | 6        | 3   | 3    |
| AI_Visibility_Scan_Milos_2026-03-06.html    | Milos, Greece    | 8         | 5   | 3    |

Total: 29 prospects identified across 4 markets. 17 hot leads (Score 1–2). 12 warm leads (Score 3).

---

## 10. What Cursor Should Know

- **Do not redesign.** The visual system is intentional and already working. Extend it, don't replace it.
- **The brand is aspirational travel, not tech.** No charts, no bar graphs, no dashboard-style data
  visualization. The reports look like editorial hotel guides, not SaaS analytics.
- **Gold is the primary action color.** Links, scores, badges, labels — all gold. Reserve terracotta
  exclusively for urgency (Score 1–2, hot leads).
- **Serif italic is for voice, not decoration.** Only use Georgia italic for narrative text, never
  for structural elements.
- **The contact block is a key design element.** It's a nested dark card-within-a-card. The
  confidence badge (Verified / Likely / Generic) is critical data — don't strip it.
- **Pipeline actions are part of the document.** The "Ready to Act" section is not an appendix —
  it's the handoff point to the next stage of the sales workflow (Skill 2 and Skill 3).
- **Exclusions should always be documented.** The "Excluded / Low Priority" note at the end of
  the prospect list shows the user what was considered and filtered out. This builds trust in the
  scan quality.
