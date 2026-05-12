---
name: earnings-analysis
description: Create professional equity research earnings update reports as PDFs (8-12 pages, 3,000-5,000 words) analyzing quarterly results from locally-provided earnings materials in the working directory. Fast-turnaround format focusing on beat/miss analysis, key metrics, updated estimates, and revised thesis. Includes 1-3 summary tables and 8-12 charts. Local-only: no web search; reads release, transcript, 10-Q, presentation files present in CWD. Use when user requests "earnings update", "quarterly update", "earnings analysis", "Q1/Q2/Q3/Q4 results", or post-earnings report.
---

# Equity Research Earnings Update

Create professional **EARNINGS UPDATE REPORTS** analyzing quarterly results for companies already under coverage, following institutional standards (JPMorgan, Goldman Sachs, Morgan Stanley format).

**Key Characteristics:**
- **Length**: 8-12 pages
- **Word Count**: 3,000-5,000 words
- **Tables**: 1-3 summary tables (NOT comprehensive)
- **Figures**: 8-12 charts
- **Turnaround**: 1-2 days (within 24-48 hours of earnings)
- **Audience**: Clients already familiar with the company
- **Focus**: What's NEW - beat/miss, updated estimates, thesis impact
- **Font**: Times New Roman throughout (unless user specifies otherwise)

## When to Use

Use when the user requests:
- "Create an earnings update for [Company] Q3 2024"
- "Analyze [Company]'s quarterly results"
- "Post-earnings report for [Company]"
- "Q1/Q2/Q3/Q4 update for [Company]"

**Do NOT use if:**
- User requests "initiation report" → Use different skill
- User requests "flash note" or "quick take" → Different format
- Company is not already covered → Need initiation first

## Critical Requirements

### 1. Speed & Timeliness
- Publish within 24-48 hours of earnings release
- Focus on NEW information only
- Don't rehash company background extensively

### 2. Beat/Miss Analysis
- Lead with whether company beat or missed estimates
- Quantify variances (e.g., "Revenue beat by $120M or 3%")
- Explain WHY results differed from expectations

### 3. Summary Format
- Keep tables to 1-3 (summary only, not comprehensive)
- No full P&L/Cash Flow/Balance Sheet (just key metrics)
- Assume reader has seen initiation report

### 4. Citations & Source Attribution ⭐⭐⭐ MANDATORY

**CRITICAL**: Properly cite all data using the **local filenames** that are present in the working directory. Do not invent URLs, EDGAR links, or external references. Every citation must name a file that actually exists in CWD.

**Include specific citations in every figure and table:**

```
Source: Q3_2024_10-Q.pdf (filed Nov 8, 2024); Q3_2024_earnings_release.pdf
```

Citations should name the local file exactly as it appears in the working directory, plus the document date (taken from inside the document itself) where useful.

**REQUIRED SOURCES (only include those actually present in CWD):**

- ✅ Earnings release file (e.g., `*release*.pdf`, `*earnings*.pdf`)
- ✅ 10-Q or 10-K filing (e.g., `*10-Q*.pdf`)
- ✅ Earnings call transcript (e.g., `*transcript*.txt`, `*call*.txt`)
- ✅ Investor presentation / supplemental materials (e.g., `*presentation*.pdf`)
- ✅ Consensus estimates file (e.g., `*consensus*.xlsx`, `*estimates*.csv`) — only if provided
- ✅ Prior-period file for prior guidance comparison — only if provided

If any of these are **missing from CWD**, flag them explicitly in the report's Sources section as "not provided" and mark dependent analysis sections as "N/A — [document type] not provided".

**REFERENCE SECTION (local files only):**

Include a "Sources" section at the end of the report listing each local file used:

```
SOURCES & REFERENCES

Earnings Materials (from working directory):
• Q3_2024_earnings_release.pdf — dated November 7, 2024
• Q3_2024_10-Q.pdf — filed November 8, 2024
• Q3_2024_earnings_call_transcript.txt — dated November 7, 2024
• Q3_2024_investor_presentation.pdf — dated November 7, 2024

Not provided locally:
• Pre-earnings consensus estimates — sections referencing consensus marked N/A
```

**VERIFICATION CHECKLIST:**
- [ ] Every figure has source naming a local file in CWD
- [ ] Every table has source naming a local file in CWD
- [ ] Beat/miss analysis cites a local consensus file, or is marked N/A if none provided
- [ ] Guidance changes cite current and prior local files, or note prior is unavailable
- [ ] Key statistics have footnotes naming the local source file
- [ ] Sources section lists every local file used, plus a "Not provided locally" list for gaps
- [ ] No URLs, no EDGAR links, no external hyperlinks anywhere in the document
- [ ] Every cited filename exactly matches a file present in CWD

### 5. Updated Estimates
- Update forward estimates based on results
- Show old vs. new estimates clearly
- Explain what changed and why

## High-Level Workflow

The earnings update process follows 5 phases:

### Phase 1: Data Collection (15-30 minutes)

**🚨 LOCAL-ONLY: USE ONLY FILES IN THE WORKING DIRECTORY 🚨**

This skill operates entirely on locally-provided documents. Do **not** web-search, do **not** call WebFetch, do **not** reach for IR sites or EDGAR. Use only files in the current working directory.

**BEFORE STARTING - COMPLETE THESE 3 STEPS IN ORDER:**
1. **LIST** every file in the working directory (and any subdirectory the user points to).
2. **CLASSIFY** each file by document type (earnings release, 10-Q/10-K, transcript, investor presentation, supplemental data, consensus estimates, prior-period materials) using filename patterns and a quick content peek.
3. **INVENTORY** what is present and what is missing. The report will cite only files that are present and will mark sections that depend on missing files as "N/A — [document type] not provided".

**Do NOT:**
- Search the web for "latest earnings"
- Assume a quarter based on today's date
- Fetch from EDGAR, IR sites, Seeking Alpha, or any external source
- Fall back to training-data recollection of past results

**Trust the user's local materials.** Whatever quarter and dates are stamped inside those documents is the period being analyzed.

**See [references/workflow.md](references/workflow.md)** for the file-discovery procedure and classification patterns.

### Phase 2: Analysis (2-3 hours)
- Beat/miss analysis for each key metric
- Segment/geographic/product breakdown
- Margin and guidance analysis
- Update financial model and estimates

**See [references/workflow.md](references/workflow.md)** for detailed analysis framework.

### Phase 3: Chart Generation (1-2 hours)
Create 8-12 charts focusing on quarterly trends and what's new:
- Quarterly revenue progression
- Quarterly EPS progression
- Quarterly margin trends
- Revenue by segment/geography
- Key operating metrics
- Beat/miss summary
- Estimate revisions
- Valuation charts

**See [references/workflow.md](references/workflow.md)** for chart specifications.

### Phase 4: Report Creation (2-3 hours)
Create 8-12 page PDF report with specific structure.

**See [references/report-structure.md](references/report-structure.md)** for complete page-by-page templates and formatting requirements.

**High-level structure:**
- Page 1: Earnings summary with rating and price target
- Pages 2-3: Detailed results analysis
- Pages 4-5: Key metrics & guidance
- Pages 6-7: Updated investment thesis
- Pages 8-10: Valuation & estimates
- Pages 11-12: Appendix (optional)

### Phase 5: Quality Check & Delivery (30 minutes)
Verify content, formatting, accuracy, and timeliness before delivery.

**See [references/best-practices.md](references/best-practices.md)** for quality checklist and common mistakes to avoid.

## Output Specification

**Primary Deliverable**: PDF report (8-12 pages)
**File Name**: `[Company]_Q[Quarter]_[Year]_Earnings_Update.pdf`
**Example**: `Nike_Q2_FY24_Earnings_Update.pdf`

**Contents:**
- Page 1: Summary with rating, price target, key takeaways
- Pages 2-3: Detailed results analysis
- Pages 4-5: Key metrics and guidance
- Pages 6-7: Updated thesis assessment
- Pages 8-10: Valuation and estimates
- Pages 11-12: Appendix (optional)
- 8-12 embedded charts
- 1-3 summary tables
- Complete sources section listing every local file used (and any missing materials flagged)

**Optional Deliverable**: XLS model update (optional for earnings updates)

## Key Differences from Initiation Report

| Aspect | Earnings Update | Initiation Report |
|--------|----------------|-------------------|
| **Length** | 8-12 pages | 30-50 pages |
| **Words** | 3,000-5,000 | 10,000-15,000 |
| **Tables** | 1-3 summary | 12-20 comprehensive |
| **Figures** | 8-12 | 25-35 |
| **Turnaround** | 1-2 days | 3-6 weeks |
| **Scope** | Quarterly results | Complete company |
| **Focus** | What's NEW | Everything |
| **Company Background** | Brief mention | 6-10 pages |
| **XLS Model** | Optional | Required |

## Resources

### references/workflow.md
Detailed Phase 1-5 instructions with step-by-step procedures for data collection, analysis, chart generation, and report creation.

### references/report-structure.md
Complete page-by-page templates, table formats, and formatting requirements for the PDF report.

### references/best-practices.md
Examples of good/bad headlines, tips for success, common mistakes to avoid, and comprehensive quality checklist.

## Dependencies

**Required:**
- Python (matplotlib, pandas, seaborn) for chart generation
- `document-skills:pdf` skill for PDF report creation (uses `reportlab` Platypus for multi-page layout with text, tables, and embedded chart images)

**Optional:**
- XLS skill for model updates (not required for earnings updates)
