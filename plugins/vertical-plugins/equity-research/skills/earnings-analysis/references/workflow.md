# Detailed Workflow for Earnings Updates

This document provides detailed step-by-step instructions for each phase of the earnings update process.

## ⚠️ LOCAL-ONLY: USE FILES IN THE WORKING DIRECTORY ⚠️

This skill uses **only local files** in the working directory. Do not web-search for earnings materials, IR pages, EDGAR filings, or transcripts. Do not call WebSearch or WebFetch. If a needed document is not present locally, flag the gap in the report and proceed with what is available.

The "latest" earnings period is whichever period is stamped on the documents the user has placed in CWD — never override that with a guess based on today's date or training-data recollection.

## Phase 1: Earnings Data Collection (15-30 minutes)

### Step 1: Inventory Local Earnings Materials

**Step 1a: List files in the working directory**

Use the LS / Glob / Read tools to enumerate every file in CWD (and any subdirectory the user explicitly points to). Do not look outside CWD.

**Step 1b: Classify each file by document type**

Match filenames against these patterns, then peek at the first ~50 lines of each candidate to confirm the content type and read the actual release/quarter date stamped inside the document.

| Document type | Filename patterns |
|---|---|
| Earnings release | `*release*`, `*earnings*`, `*press*`, `*Q[1-4]*results*` |
| 10-Q / 10-K | `*10-Q*`, `*10-K*`, `*10Q*`, `*10K*` |
| Earnings call transcript | `*transcript*`, `*call*`, `*conference*` |
| Investor presentation | `*presentation*`, `*slides*`, `*investor*deck*` |
| Supplemental data | `*supplemental*`, `*data*sheet*`, `*financials*.xlsx` |
| Consensus estimates | `*consensus*`, `*estimates*`, `*street*` |
| Prior period materials | filenames mentioning a prior quarter (`*Q2*` when current is Q3, etc.) |

Filenames vary. Trust content over filename — if a file with no obvious name turns out (on read) to be the earnings release, classify it as such.

**Step 1c: Read the quarter and dates from inside each document**

For each classified file, record:
- The quarter / fiscal period stamped in the document (e.g., "Q3 FY2024")
- The release / filing / transcript date stamped in the document
- The reporting company name and ticker

These dates and identifiers will be used in citations and in the report header. **Use whatever dates appear in the files** — do not gate on whether they are "recent enough".

**Step 1d: Build a present / missing inventory**

Produce a small table for your own reference and for the report's Sources section:

```
PRESENT (local files in CWD):
- Q3_2024_earnings_release.pdf — release dated Nov 7, 2024
- Q3_2024_10-Q.pdf — filed Nov 8, 2024
- Q3_2024_earnings_call_transcript.txt — call dated Nov 7, 2024

MISSING (not provided locally):
- Investor presentation
- Pre-earnings consensus estimates
- Prior-quarter materials for QoQ comparison
```

Sections of the report that depend on missing inputs will be marked "N/A — [document type] not provided".

**Step 1e: Handle naming variations**

Companies use different terminology — interpret the period from the document's own header:

- "Q1 2024", "Q1 FY24", "First Quarter 2024", "1Q24"
- "Third Quarter Fiscal 2024", "Q3 FY2024", "3Q FY24"
- Company name may differ from common name (e.g., "Meta Platforms, Inc." vs "Facebook")

**Step 1f: Verification checklist**

- [ ] Listed every file in the working directory
- [ ] Classified each file by document type
- [ ] Recorded the quarter and release/filing/call dates from inside each document
- [ ] Built a present / missing inventory
- [ ] Did NOT web-search, fetch IR pages, or pull from EDGAR
- [ ] Did NOT supplement with training-data recollections of past results

### Step 2: Inventory the Required Materials

Compare your CWD inventory against the list below. For each item, note whether the local file is present; if absent, flag it as a gap.

**Primary Materials (highly desirable):**
- **Earnings press release** — the company's own press release for this quarter, as a local PDF/HTML/text file in CWD.
- **10-Q or 10-K filing** — the SEC filing for this quarter (10-Q for Q1–Q3, 10-K for Q4), as a local file in CWD. Note: in practice the 10-Q is often filed 1–5 days after the release, so the user may or may not have provided it.
- **Earnings call transcript** — the management call transcript for this quarter, as a local file in CWD. Confirm the transcript's stamped date matches the release date (±1 day); if it doesn't, note the mismatch in the inventory rather than discarding it.

**Supplemental Materials (use if present):**
- **Investor presentation / slides** — typically a PDF with the management deck.
- **Supplemental data file** — typically an Excel/CSV with detailed quarterly metrics.

**Reference Materials (use if present, otherwise note in report):**
- **Prior quarter results** — a prior-period release file for QoQ comparison.
- **Prior year same quarter** — a year-ago release file for YoY comparison.
- **Prior internal estimates** — a prior earnings update or initiation file containing the estimates being compared against actuals.
- **Consensus estimates** — a local file containing pre-earnings consensus (Bloomberg/FactSet/Refinitiv/etc. export). If absent, the beat/miss-vs-consensus section is marked N/A; beat/miss-vs-internal-estimate can still proceed if prior estimates were provided.

**Verification checklist before proceeding to Step 3:**

- [ ] Every cited document type above has been checked against the CWD inventory
- [ ] Items present are queued for reading and extraction
- [ ] Items absent are recorded in the "Not provided locally" list for the report's Sources section
- [ ] Sections of the report that depend on missing items are flagged for "N/A — [document type] not provided" treatment
- [ ] No web searches, no external fetches, no EDGAR lookups were performed

### Step 3: Extract Key Metrics

Create a structured summary:

```
REPORTED RESULTS vs. ESTIMATES:
─────────────────────────────────────────────────
                    Reported    Our Est    Consensus    Beat/(Miss)
Revenue             $X,XXX      $X,XXX     $X,XXX       $XX (X%)
Gross Margin        XX.X%       XX.X%      XX.X%        XXbps
EBITDA              $XXX        $XXX       $XXX         $XX (X%)
Operating Profit    $XXX        $XXX       $XXX         $XX (X%)
EPS (Adjusted)      $X.XX       $X.XX      $X.XX        $X.XX
EPS (GAAP)          $X.XX       $X.XX      $X.XX        $X.XX

KEY BUSINESS METRICS:
─────────────────────────────────────────────────
[Metric 1]          XXX         XXX        XXX          +X% YoY
[Metric 2]          XXX         XXX        XXX          +X% YoY
[Metric 3]          XXX         XXX        XXX          +X% YoY
```

### Step 4: Identify Key Themes from Call

Listen to or read earnings call transcript and note:
- Management's tone (confident, cautious, defensive?)
- Key topics emphasized (product launches, geographic trends, competition)
- Questions from analysts (what are investors concerned about?)
- Guidance provided (raised, lowered, maintained, introduced?)
- Any surprises or unexpected commentary

## Phase 2: Analysis (2-3 hours)

### Step 5: Beat/Miss Analysis

For EACH key metric that beat or missed, explain:

**If BEAT:**
- What drove the outperformance?
- Was it one-time or sustainable?
- Did management guide higher going forward?
- How does this impact our thesis?

**If MISS:**
- What went wrong?
- Was it company-specific or industry-wide?
- Is management taking corrective action?
- How does this impact our thesis?

**Example Format:**
```
■ **Revenue Beat by 3% Driven by Strong DTC Performance**

Revenue of $13.5B exceeded our estimate of $13.1B by $400M (3%) and consensus
of $13.2B by $300M (2%). The outperformance was driven primarily by Direct-to-
Consumer channels, which grew 18% YoY (vs. our 12% estimate), offsetting
weaker-than-expected wholesale (-5% vs. flat estimate). Management cited strong
digital demand and successful product launches (Pegasus 40 running shoe, new
Jordan colorways) as key drivers. DTC now represents 42% of total revenue vs.
38% a year ago, demonstrating successful channel shift strategy.
```

### Step 6: Segment/Geographic/Product Analysis

Analyze performance by:
- Business segment (if multi-segment company)
- Geography (North America, Europe, China, etc.)
- Product category
- Channel (retail, wholesale, e-commerce)

Identify:
- What outperformed expectations?
- What underperformed?
- Trends vs. prior quarters
- Management commentary on outlook for each area

### Step 7: Margin Analysis

Analyze profitability:
- Gross margin: up or down? why?
- Operating margin: up or down? why?
- Key drivers (pricing, mix, costs, leverage)
- Outlook going forward

### Step 8: Guidance Analysis

If the local earnings release / transcript / presentation contains guidance:
- Compare new guidance to prior guidance — **only if a prior-period file is present in CWD**. If no prior-period file is provided, write "prior guidance not available locally" rather than reconstructing it from memory.
- Compare to internal estimates and Street estimates **if those files are present in CWD**; otherwise mark those comparisons N/A.
- Assess credibility based on what the local materials show; do not introduce historical track-record claims unless they are supported by a local file.
- Identify key assumptions behind guidance as stated in the local materials.

If the local materials do NOT contain guidance:
- Note this explicitly
- Provide independent outlook based on the results and commentary in the local materials only

### Step 9: Update Financial Model

Update estimates for:
- Current year (remaining quarters)
- Next year
- Potentially year after

**Show clearly:**
```
UPDATED ESTIMATES:
─────────────────────────────────────────────────
                        Old Est     New Est     Change      Reason
FY2024E Revenue         $XX.XB      $XX.XB      +X.X%      [Brief reason]
FY2024E EBITDA          $X.XB       $X.XB       +X.X%      [Brief reason]
FY2024E EPS             $X.XX       $X.XX       +X.X%      [Brief reason]

FY2025E Revenue         $XX.XB      $XX.XB      +X.X%      [Brief reason]
FY2025E EBITDA          $X.XB       $X.XB       +X.X%      [Brief reason]
FY2025E EPS             $X.XX       $X.XX       +X.X%      [Brief reason]
```

### Step 10: Update Valuation & Price Target

Based on updated estimates:
- Recalculate DCF (use updated cash flows)
- Update comparable company multiples (if peer group has reported)
- Determine new fair value
- Decide if price target changes

**Price Target Decision:**
- If estimates changed significantly (>5%) → Usually change price target
- If estimates changed marginally (<5%) → May maintain price target
- If thesis strengthened/weakened → May change even without estimate change

### Step 11: Assess Rating Impact

Decide whether to change rating:
- If results significantly better than expected + guidance raised → Consider upgrade
- If results significantly worse + guidance cut → Consider downgrade
- If inline or mixed → Usually maintain rating

**Consider:**
- Stock reaction (up/down/flat?)
- Valuation (expensive/cheap relative to new estimates?)
- Risk/reward (asymmetry shifted?)

## Phase 3: Chart Generation (1-2 hours)

### Step 12: Generate 8-12 Charts

Create charts focusing on QUARTERLY TRENDS and WHAT'S NEW.

**REQUIRED CHARTS (8-12 total):**

1. **Quarterly Revenue Progression** (Bar chart)
   - Last 8-12 quarters
   - Show beat/miss vs. estimates each quarter
   - Highlight current quarter

2. **Quarterly EPS Progression** (Bar chart)
   - Last 8-12 quarters
   - Show beat/miss vs. estimates
   - Adjusted and GAAP

3. **Quarterly Margin Trend** (Line chart)
   - Gross margin, EBIT margin, net margin
   - Last 8-12 quarters
   - Show trajectory

4. **Revenue by Segment/Geography** (Stacked bar OR table)
   - Current quarter vs. YoY
   - Growth rates by segment

5. **Key Operating Metrics** (Multi-line chart)
   - Customer count, ARPU, units sold, etc. (whatever is relevant)
   - Last 8-12 quarters

6. **Beat/Miss Summary** (Waterfall or table)
   - Show components of beat/miss
   - What drove variance from estimates

7. **Estimate Revision Chart** (Before/after comparison)
   - Old FY estimates vs. new FY estimates
   - Bar chart showing change

8. **Valuation Chart** (P/E or EV/EBITDA multiple)
   - Historical multiple range
   - Current multiple
   - Fair value multiple

**OPTIONAL CHARTS (if space allows):**
- Peer comparison (if peers have reported)
- Guidance vs. Street comparison
- Cash flow metrics
- Balance sheet highlights (if notable)

**Chart Style Guidelines:**
- Focus on TRENDS (quarterly progression)
- Highlight CHANGES (beat/miss, estimate revisions)
- Keep simple and clear (this is a fast-turnaround report)

## Phase 4: Report Creation (2-3 hours)

### Step 13: Create DOCX Report

Use DOCX skill to create 8-12 page report.

See [report-structure.md](report-structure.md) for complete page-by-page templates and formatting requirements.

**Key Steps:**
1. Create Page 1 with earnings summary and quick takeaways
2. Add detailed results analysis (Pages 2-3)
3. Include key metrics and guidance (Pages 4-5)
4. Update investment thesis (Pages 6-7)
5. Provide valuation and estimates (Pages 8-10)
6. Add appendix if needed (Pages 11-12)
7. Embed all 8-12 charts throughout
8. Add 1-3 summary tables
9. Include sources section listing every local file used (and any missing materials flagged)

### Step 14: Optional - Update XLS Model

If a full financial model exists for this company (from initiation), update it with:
- Actual Q[X] results
- Revised estimates for future quarters
- Updated valuation

**Note**: For earnings updates, a full XLS file is OPTIONAL (not required like in initiation reports). The DOCX report is the primary deliverable.

If creating XLS, include:
- Quarterly model tab
- Updated annual projections
- Revised DCF
- Updated comps analysis

## Phase 5: Quality Check & Delivery (30 minutes)

### Step 15: Quality Checklist

Before publishing, verify:

**Content:**
- [ ] Beat/miss clearly stated and quantified
- [ ] Key drivers explained (not just "strong performance")
- [ ] Updated estimates provided (old vs. new shown)
- [ ] Price target updated or explicitly maintained
- [ ] Rating confirmed or changed with rationale
- [ ] Guidance analyzed (if provided)
- [ ] Thesis impact assessed

**Formatting:**
- [ ] Page 1 has summary box and key bullets
- [ ] All tables have source lines
- [ ] All figures numbered and captioned
- [ ] Estimates table shows old vs. new
- [ ] 8-12 charts embedded throughout
- [ ] Report is 8-12 pages (not too long, not too short)

**Accuracy:**
- [ ] Numbers match company's reported results exactly
- [ ] Math checks out (estimates, valuation)
- [ ] No typos in ticker, company name, numbers
- [ ] Charts match text descriptions
- [ ] Date is current

**Citations:** ⭐ MANDATORY
- [ ] Every figure names a local source file in CWD with the document date
- [ ] Every table names a local source file in CWD
- [ ] Beat/miss analysis cites a local consensus file, or is marked N/A if none provided
- [ ] Guidance changes cite the current and prior local files (or note prior is unavailable)
- [ ] Key statistics have footnotes naming the local source file (and page/slide if knowable)
- [ ] Sources section lists every local file used, plus a "Not provided locally" list for gaps
- [ ] No URLs, EDGAR links, or external hyperlinks anywhere in the document
- [ ] Every cited filename exactly matches a file present in CWD
- [ ] Earnings call quotes cite the local transcript filename, the speaker, and approximate location in the transcript

**Sourcing discipline:**
- [ ] All data sourced from local files in the working directory
- [ ] No web searches, no WebFetch calls, no IR/EDGAR/Seeking Alpha access
- [ ] Consensus estimates (if present) are pre-earnings; if no consensus file is provided, beat/miss-vs-consensus is marked N/A
- [ ] Missing-material gaps flagged in the report's Sources section

### Step 16: Deliver Report

Provide user with:

1. **DOCX file**: `[Company]_Q[X]_[Year]_Earnings_Update.docx`
2. **Chart files**: All PNG/JPG charts (for reference)
3. **Optional XLS**: Updated financial model if maintained

**Brief summary for user:**
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

Deliverable: 8-12 page earnings update report with updated estimates and valuation.
```
