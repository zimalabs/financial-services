# Best Practices, Examples, and Quality Guidelines

This document provides examples, tips for success, common mistakes to avoid, and comprehensive quality checklists.

## Example Headlines

### Good Earnings Update Headlines:
- "Nike Q2 FY24: DTC Strength Offsets Wholesale Weakness - Maintaining OW, PT $95"
- "Tesla Q3'24: Cybertruck Ramp Ahead of Plan - Raising Estimates, PT to $285"
- "LVMH Q4'24: Fashion & Leather Resilient, Wines Weak - In-Line, Reiterating Buy"
- "Apple Q1 FY24: Services Beat, iPhone Miss - Mixed Quarter, Lowering PT to $185"

### Bad Headlines (Avoid):
- "Nike Quarterly Update" (too generic, no takeaway)
- "Company Reports Earnings" (states obvious, no analysis)
- "Q3 Results Analysis" (no company name, no view)

## Tips for Success

1. **Speed matters**: Published 24-48hrs post-earnings, not days later

2. **Lead with conclusion**: Beat or miss? Up or down estimates?

3. **Quantify everything**: "Strong" means nothing, "$150M beat on $1.2B revenue" is clear

4. **Focus on drivers**: Don't just say "revenue beat", explain WHY

5. **Show the work**: Old estimates → New estimates with reasons

6. **Update price target if material**: If estimates change >5%, usually PT changes too

7. **Acknowledge the call**: Reference management commentary, don't just analyze the press release

8. **Compare to peers**: If similar companies reported, note relative performance

9. **Be concise**: This is NOT a comprehensive report, stay focused on quarterly results

10. **Chart the trends**: Quarterly progression charts are most valuable

## Common Mistakes to Avoid

❌ **Too comprehensive**: Don't write an initiation-length report for quarterly results

❌ **Missing beat/miss**: Lead with whether results beat or missed expectations

❌ **Not updating estimates**: Must provide updated forward estimates

❌ **Vague language**: "Strong performance" without quantification

❌ **Ignoring guidance**: If company guides, analyze it thoroughly

❌ **Too slow**: Publishing 5+ days after earnings loses relevance

❌ **Rehashing basics**: Don't spend 3 pages explaining what the company does

❌ **Missing price target update**: If estimates changed materially, PT should too

❌ **No investment impact**: Must connect results to thesis and rating

❌ **Missing citations**: Every number needs a source naming a local file in CWD

❌ **Fabricated URLs / EDGAR links**: This skill is local-only — never invent URLs or hyperlinks to external sources

❌ **Web-searching for "latest" data**: Use only the files the user has placed in the working directory

## Comprehensive Quality Control Checklist

Before delivering earnings update, verify all items below:

### Content & Analysis Checklist

**Beat/Miss Analysis:**
- [ ] Beat/miss analysis leads the report
- [ ] Specific variances quantified (e.g., "beat by $120M or 3%")
- [ ] Explanation of WHY results differed from expectations
- [ ] Analysis of each key metric (revenue, EPS, margins, etc.)

**Metrics & Performance:**
- [ ] All key metrics discussed with YoY comparisons
- [ ] QoQ comparisons included where relevant
- [ ] Segment/geographic/product breakdowns provided
- [ ] Operating metrics analyzed (customers, ARPU, units, etc.)

**Guidance & Estimates:**
- [ ] Guidance changes analyzed and quantified (if provided)
- [ ] If no guidance, this is explicitly noted
- [ ] Updated estimates provided for current year
- [ ] Updated estimates provided for next year
- [ ] Old vs. new estimates clearly shown
- [ ] Explanation of what changed and why

**Valuation & Rating:**
- [ ] Price target updated (if warranted by results)
- [ ] If PT unchanged, explicitly maintained
- [ ] Valuation methodology explained
- [ ] Rating confirmed or changed with clear rationale
- [ ] Investment thesis assessed and updated if needed

### Format & Length Checklist

**Overall Structure:**
- [ ] Report is 8-12 pages (not shorter, not longer)
- [ ] Page 1 has earnings summary format
- [ ] Page 1 has "EARNINGS UPDATE" in title (NOT "Initiating Coverage")
- [ ] Event-driven title (e.g., "Strong Q3 Results...")

**Tables:**
- [ ] 1-3 summary tables included (NOT comprehensive tables)
- [ ] All tables have clear column headers
- [ ] All tables have header row shading
- [ ] All tables have source lines at bottom
- [ ] Estimates table shows old vs. new with change column

**Charts:**
- [ ] 8-12 charts embedded throughout document
- [ ] All charts have "Figure X - [Title]" caption above
- [ ] All charts have "Source: [Source]" line below
- [ ] Charts focus on quarterly trends
- [ ] Charts highlight changes (beat/miss, revisions)
- [ ] Charts use professional styling

### Citations & Sources Checklist ⭐⭐⭐ MANDATORY

This skill is **local-only**: every citation must name a file that actually exists in the working directory. No URLs, no EDGAR links, no external hyperlinks.

**Figure & Table Citations:**
- [ ] Every figure names a local source file in CWD with the document date
- [ ] Every table names a local source file in CWD
- [ ] Source citations include page numbers or slide numbers where applicable

**Beat/Miss Citations:**
- [ ] Beat/miss analysis cites a local consensus file (e.g., `*consensus*.xlsx`), or is marked N/A if no consensus file is provided
- [ ] Consensus source includes "as of" date taken from inside the file
- [ ] Company reported results cited to the local earnings release or 10-Q file

**Guidance Citations:**
- [ ] Current guidance cited to the local earnings call transcript, release, or presentation file
- [ ] Prior guidance cited to a local prior-period file, or noted as "prior guidance not available locally"

**Statistics & Metrics:**
- [ ] Key statistics have footnotes naming the local source file
- [ ] Footnotes reference specific documents and page/slide numbers where applicable
- [ ] Management quotes cite the speaker name and the local transcript filename

**Sources Section:**
- [ ] "Sources & References" section included at end of report
- [ ] Section lists every local file used, with its filename and the date taken from inside the document
- [ ] Missing materials are explicitly listed under a "Not provided locally" subsection
- [ ] No URLs, EDGAR links, or external hyperlinks anywhere in the document
- [ ] Every cited filename exactly matches a file present in CWD

### Accuracy Checklist

**Numerical Accuracy:**
- [ ] Numbers match company's reported results exactly
- [ ] Math checks out in all calculations
- [ ] Estimate changes calculated correctly
- [ ] Valuation math is accurate
- [ ] Charts match text descriptions

**Factual Accuracy:**
- [ ] No typos in ticker symbol
- [ ] No typos in company name
- [ ] Dates are current and accurate
- [ ] Quarter/year references are correct
- [ ] Year notation correct (A for actual, E for estimate)

### Sourcing Discipline Checklist

**Local-only sourcing:**
- [ ] All data sourced from local files in the working directory
- [ ] No web searches, no WebFetch calls, no IR / EDGAR / Seeking Alpha access
- [ ] No supplementation from training-data recollection of past quarters
- [ ] Consensus estimates (if a local file is provided) are pre-earnings; otherwise beat/miss-vs-consensus is marked N/A
- [ ] Missing-material gaps flagged in the report's Sources section
- [ ] Whatever quarter and dates are stamped on the local documents is the period being analyzed — no recency gating

### Writing Style Checklist

**Clarity & Directness:**
- [ ] Lead with numbers ("Revenue grew 15% to $1.2B" not "Strong revenue")
- [ ] Use "vs." not "versus"
- [ ] Be direct and concise throughout
- [ ] Focus on what's NEW (not rehashing company basics)
- [ ] Avoid vague language ("strong performance" without quantification)

**Professional Standards:**
- [ ] Institutional tone maintained
- [ ] Consistent terminology throughout
- [ ] No informal language
- [ ] Proper financial notation

## Pre-Delivery Final Check

Run through this quick final check before sending report to user:

### 5-Minute Final Review:
1. **Page 1**: Rating clear? Price target updated? Key takeaways compelling?
2. **Numbers**: Do reported results match the local press release file exactly?
3. **Citations**: Spot check 3-4 figures/tables — every source names a local file actually present in CWD?
4. **Estimates**: Old vs. new clearly shown? Changes explained?
5. **Charts**: All 8-12 embedded? All numbered and captioned?
6. **Length**: Is it 8-12 pages (not 6, not 15)?
7. **Sources section**: Lists every local file used, plus "Not provided locally" gaps?
8. **No external links**: Document contains no URLs, EDGAR links, or external hyperlinks?

If all items check out, the report is ready for delivery.

## Summary Delivery Format

When delivering the completed report to the user, provide this summary:

```
[Company] Q[X] [Year] Earnings Update Complete

Results: [BEAT / INLINE / MISS]
- Revenue: $X.XB ([beat/missed] by $XXM or X%)
- EPS: $X.XX ([beat/missed] by $X.XX)

Key Takeaways:
■ [Takeaway 1]
■ [Takeaway 2]
■ [Takeaway 3]

Updated Estimates:
- FY[Year]E Revenue: $XX.XB (prior: $XX.XB, [+/-]X%)
- FY[Year]E EPS: $X.XX (prior: $X.XX, [+/-]X%)

Rating: [MAINTAINED / RAISED / LOWERED] [RATING]
Price Target: $XXX (prior: $XXX) - [+/-]XX% upside

Deliverables:
✓ 8-12 page earnings update report (DOCX)
✓ 8-12 embedded charts
✓ Updated estimates with old/new comparison
✓ Sources section listing every local file used (plus any missing materials flagged)
✓ [Optional: Updated XLS financial model]

File: [Company]_Q[X]_[Year]_Earnings_Update.docx
```
