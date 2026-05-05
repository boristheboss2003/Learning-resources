**Claude Cowork × Excel**

*Full Walkthrough --- Comprehensive Reference Document*

**10 Spreadsheet Workflows • Plain-English Formulas • Multi-Sheet Models • Charts • Dashboards**

Source Video: youtube.com/watch?v=rqte_LEu2Y8

*Prepared: May 2026*

**Table of Contents**

Video Overview & Why It Matters 3

The April 2026 Excel Update --- What Changed 5

Setup Prerequisites 7

The Built-In Spreadsheet Skill 8

10 Excel Automation Workflows 10

1\. Convert Any File Format Into Clean Excel 10

2\. Understand Inherited Spreadsheets in Minutes 12

3\. Audit and Fix Data Errors Automatically 14

4\. Clean Messy Data in Under Two Minutes 16

5\. Write Excel Formulas in Plain English 18

6\. Build and Manage Multi-Sheet Workbooks 21

7\. Analyze Data Without Pivot Tables 23

8\. Create Charts and Dashboards Directly in Excel 26

9\. Format Spreadsheets for Professional Presentation 28

10\. Export Excel Data to Reports and Other Formats 30

Three Advanced High-Value Use Cases 32

Native Excel Operations Supported 36

Limitations and What Cowork Cannot Do 38

Security and Prompt Injection Risks 40

Best Practices and Pro Tips 42

FAQ 44

Source URLs Appendix 46

**Video Overview & Why It Matters**

This video documents a major capability expansion for Claude Cowork: native Excel automation. The \'NOW\' in the title is significant --- Cowork\'s spreadsheet capabilities went from rudimentary (couldn\'t reliably handle formulas, broke on complex layouts) to production-grade. The host walks through ten distinct workflows that demonstrate Cowork\'s new ability to read, write, edit, format, and analyze .xlsx files with the fluency of a competent spreadsheet analyst.

**The Headline Promise**

> *Work that would take 15-20 minutes manually takes under two minutes when using Cowork to convert and format CSV files into clean Excel spreadsheets.*

This is not marketing exaggeration. The video shows live demonstrations where the timing claim holds --- file format conversions, data cleaning, formula generation, and multi-sheet workbook construction all complete in under two minutes when Cowork is properly configured.

**Why This Matters in 2026**

Three pieces of context make this video important:

-   Excel remains the single most-used business application in the world. Any AI tool that can\'t operate it competently has a ceiling on its value.

-   The April 2026 Cowork update finally made Excel automation reliable. Earlier versions struggled with merged cells, non-columnar data, and presentation-style layouts. The update closed those gaps.

-   Skills 2.0 --- Anthropic\'s reworking of skills to bundle instructions, scripts, templates, and reference materials into modular workflow packages --- made Excel-specific skills auto-load whenever a spreadsheet task is detected.

**Who This Video Is For**

-   Finance professionals running variance reports, reconciliations, and modeling work.

-   Operations teams maintaining tracking spreadsheets, dashboards, and KPI rollups.

-   Anyone who has inherited a spreadsheet from a colleague and needs to understand it before modifying it.

-   Analysts cleaning messy CSV exports from third-party tools.

-   Consultants building client-ready financial models.

-   Project managers turning ad-hoc spreadsheets into formal deliverables.

**What You Walk Away With**

-   Concrete prompts you can copy and paste.

-   Knowledge of which spreadsheet tasks are worth handing to Cowork (most of them) and which are not (anything VBA-related).

-   A mental model for treating Cowork as an Excel power-user collaborator rather than a chatbot.

-   Awareness of the security pitfalls (prompt injection via cell content) before they cost you.

**The April 2026 Excel Update --- What Changed**

To understand why this video opens with \'NOW,\' you need the April 2026 release context. Three updates landed within a week of each other and combined to make Excel automation production-grade for the first time.

**Update 1 --- Cowork General Availability (April 9, 2026)**

Cowork went from research preview to generally available on macOS and Windows. This shipment included three enterprise capabilities relevant to spreadsheet work:

-   Analytics --- usage tracking and reporting for IT teams.

-   OpenTelemetry support --- observability hooks for production monitoring.

-   Role-based access controls --- permissioning for who can run what skills on which folders.

**Update 2 --- Routines Research Preview (April 14, 2026)**

Routines launched as a cloud-hosted automation tier that runs without your computer being awake. For Excel work, this means:

-   Daily reconciliations can run at 6 AM without anyone present.

-   Weekly variance reports can be drafted Friday night and waiting in your inbox Monday.

-   Month-end close routines can execute over the weekend, automatically.

**Update 3 --- Excel and PowerPoint Add-ins With Skills (April 13, 2026)**

This is the biggest change for Excel users. The native Microsoft Office add-ins gained support for Skills --- meaning the same skills configured in Cowork now activate inside Excel itself, sharing context with Cowork conversations.

-   Excel and PowerPoint add-ins can share the full context of conversations across both apps.

-   Anthropic released native support for pivot table editing and conditional formatting from inside Excel.

-   The model was bumped to Opus 4.6, which dramatically improved formula generation quality.

-   Amazon Bedrock, Google Cloud\'s Vertex AI, and Microsoft Foundry users can connect via an LLM gateway --- meaning enterprise teams can route spreadsheet work through their existing model providers.

**Update 4 --- Claude for Word Add-In (April 13, 2026)**

With Word added, Claude now has native add-ins for the full Microsoft Office trio --- Word, Excel, PowerPoint. The implication for Cowork users: a single conversation can now touch a Word doc, an Excel sheet, and a PowerPoint deck simultaneously, with shared context across all three.

+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| **The Net Effect**                                                                                                                                                                                                                                                                                                                                                                           |
|                                                                                                                                                                                                                                                                                                                                                                                              |
| Before April 2026, getting Cowork to reliably handle complex Excel work required workarounds, careful prompt design, and acceptance of regular failures. After April 2026, Excel automation is a first-class Cowork capability that handles formulas, multi-sheet workbooks, charts, conditional formatting, and pivot tables with the same fluency as file management or document creation. |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

**Setup Prerequisites**

Before running any of the workflows in this video, your environment needs to be set up correctly. Skipping this section is the most common reason workflows misbehave.

**Required Tooling**

-   Claude Desktop app (downloaded from claude.com/download --- not the web version).

-   Active paid Claude plan: Pro (\$20/mo), Max (\$100-\$200/mo), Team (\$30/user/mo), or Enterprise.

-   macOS or Windows (x64). Excel must also be installed if you plan to verify outputs in Excel directly.

-   Active internet connection during sessions.

**Recommended Configuration**

-   Model: Opus 4.6 with Extended Thinking enabled. The host explicitly states this is the right configuration for Excel work --- Sonnet handles simpler tasks but Opus consistently produces correct multi-step formulas, while Extended Thinking trades latency for accuracy on cross-sheet logic.

-   A dedicated Cowork folder containing the Excel files you want to work with. Avoid pointing Cowork at your full Documents folder.

-   The built-in spreadsheet skill enabled (it is on by default after the April update).

**First-Time Setup Steps**

1.  Open Claude Desktop. Switch to the Cowork tab.

2.  Settings \> Models --- set Opus 4.6 as default. Enable Extended Thinking.

3.  Settings \> Capabilities --- verify the Spreadsheet skill is enabled (it should be by default).

4.  Create a folder called \'Cowork Excel\' in your Documents directory.

5.  Click the Cowork folder selector in the bottom-left of the app and choose this new folder.

6.  Drop a test Excel or CSV file into the folder.

7.  In the chat, run a simple test: \'Read the file in this folder and tell me what\'s in it.\' Verify it works.

**The Built-In Spreadsheet Skill**

Cowork ships with a built-in spreadsheet skill that loads automatically whenever you ask for spreadsheet work. Understanding what this skill knows determines what you can ask of it without writing custom skills.

**What the Skill Knows**

-   Excel structure --- sheets, ranges, named ranges, tables.

-   Formula syntax across hundreds of Excel functions, including SUMIFS, INDEX/MATCH, XLOOKUP, dynamic arrays, LET, LAMBDA.

-   Data type handling --- text, numbers, dates, currencies, percentages, booleans.

-   Common formatting patterns --- title rows, frozen panes, banded rows, currency formats, date formats.

-   Chart types --- bar, line, column, pie, scatter, combination.

-   Conditional formatting rules --- color scales, data bars, icon sets, cell-level rules.

-   Pivot table mechanics --- rows, columns, values, filters.

**How the Skill Activates**

You don\'t need to invoke the skill explicitly. When Cowork detects spreadsheet-related work --- by the file types in the folder or by the language of your prompt --- the skill loads automatically. You can also invoke it explicitly by typing \'/\' in the chat and selecting it.

**Why This Matters**

> *You describe what you want, and Cowork handles the technical execution.*

Before the spreadsheet skill, you had to either write VBA yourself or know enough Excel to construct the formulas in your prompt. After the skill, you describe the outcome in plain English and Cowork translates.

**Skills 2.0 Architecture**

The April 2026 Skills 2.0 update transformed skills into full workflow packages. The spreadsheet skill is not just a markdown instruction file --- it bundles:

-   Instructions --- what kinds of spreadsheet tasks the skill handles.

-   Scripts --- reusable code for common operations like formula validation.

-   Templates --- boilerplate spreadsheet structures (financial model, P&L, dashboard) the skill can populate.

-   Reference materials --- Excel function documentation, common patterns, Microsoft\'s style guides.

**10 Excel Automation Workflows**

The core of this video. Ten distinct ways to use Cowork on Excel work, with concrete prompts the host demonstrates live.

**Workflow 1 --- Convert Any File Format Into Clean Excel**

The most universally useful workflow. Cowork takes a file in any format --- PDF, CSV, text, Word, Markdown --- and produces a structured .xlsx with proper headers, consistent data types, totals rows, and clean formatting.

**Example Prompt --- CSV Conversion**

> *Take the invoice sample CSV and turn it into a clean formatted Excel spreadsheet with proper headers and formatting.*

**What Cowork Produces**

-   Cleaned column headers (capitalized, descriptive, no underscores or weird characters).

-   Consistent formatting per column (currency formatted, dates aligned, numbers right-aligned).

-   Totals row at the bottom where applicable, with SUM formulas (not hardcoded values).

-   Proper data types --- dates parsed as dates, currency as currency, percentages as percentages.

**Example Prompt --- Text File Conversion**

> *The team contact text file has a list of contacts. Convert it into an Excel spreadsheet with columns for name, email, phone, and department.*

**Edge Cases the Skill Handles**

-   Multiple delimiter types in the same file (commas, tabs, pipes, semicolons).

-   Out-of-order columns --- Cowork detects column meaning by content, not position.

-   Missing values --- flagged for review rather than silently dropped.

-   Embedded headers in the middle of files --- Cowork reorganizes around them.

**The Time Claim**

The host explicitly times this workflow: 15-20 minutes of manual cleanup compressed to under 2 minutes of Cowork execution. That includes reading the file, structuring the output, applying formatting, and saving the .xlsx --- all from a single plain-English prompt.

**Workflow 2 --- Understand Inherited Spreadsheets in Minutes**

This workflow addresses one of the most common time sinks in spreadsheet work: receiving a file from someone who\'s left, and having to figure out how it works before you can modify it.

**Example Prompt --- Plain English Explanation**

> *I just inherited this spreadsheet from a coworker. Can you explain what it does in plain English?*

**What Cowork Produces**

-   Breakdown of the main data sheet\'s purpose.

-   Column-by-column definitions --- what each column tracks and where it gets data from.

-   Formula logic --- what each calculation is computing.

-   Calculation drivers --- which inputs feed which outputs (essentially a dependency map).

-   Notable assumptions baked into the model.

**Example Prompt --- Formula Walkthrough**

> *Walk me through the formulas in this file. What is each one calculating and why?*

**What Cowork Produces**

-   Detailed explanation of each formula, including sample math (e.g., \'\$60K revenue × 10% rate = \$6,000\').

-   Flags for hardcoded errors --- magic numbers in formulas that should reference cells instead.

-   Identification of inconsistent patterns --- same calculation done differently in different places.

-   Suggested cleanup steps.

**Why This Workflow Is High-Leverage**

Onboarding a new team member to a complex spreadsheet typically takes hours. With this workflow, that gets compressed to a 5-minute Cowork session that produces a written explanation the new team member can keep as reference.

**Workflow 3 --- Audit and Fix Data Errors Automatically**

Cowork can systematically scan a spreadsheet for anomalies, errors, and red flags. This is one of the workflows that justifies Cowork\'s existence on its own --- it catches things human eyes miss in a 5-figure-row dataset.

**Example Prompt --- Detection**

> *Review the spreadsheet and flag anything that looks like an error, anomaly, or red flag.*

**Example Issues Cowork Found in a 20-Row Demo Sheet**

-   Duplicate order IDs --- same ID assigned to two different orders.

-   Future-dated entries --- a transaction dated 18 months in the future.

-   Corrupted dates --- dates rendered in 1900 format due to Excel\'s leap-year bug.

-   Negative quantities --- physically impossible for the inventory system.

-   Invalid customer names --- entries like \'asdf\' and \'TEST\'.

-   Formula mismatches --- adjacent cells that should compute identically but don\'t.

**Example Prompt --- Auto-Fix**

> *Fix all of these and save a second version called clean\_\[filename\].*

**How the Auto-Fix Workflow Works**

-   Cowork creates a new file rather than overwriting the original --- preserves auditability.

-   Changes are logged in a separate sheet or comment trail explaining what was modified and why.

-   Duplicates renamed (e.g., \'ORD-1234\' becomes \'ORD-1234-A\' and \'ORD-1234-B\') rather than deleted.

-   Dates corrected when unambiguous; flagged for human review when ambiguous.

-   Blank values flagged for review rather than auto-filled.

**Audit-Trail Bonus**

If you need formal change tracking, add this to your prompt:

> *Apply all the changes and add a comment to each modified cell explaining what you changed and why.*

Cowork attaches Excel comments to each modified cell, giving you a permanent audit trail visible inside the spreadsheet.

**Workflow 4 --- Clean Messy Data in Under Two Minutes**

Standardizing inconsistent data is one of the most common Excel tasks. Cowork handles it from a single prompt.

**Example Prompt**

> *Clean up this spreadsheet. Standardize all the formatting, fix capitalization, and make it consistent throughout.*

**Cowork\'s Clarifying Questions**

Cowork doesn\'t blindly apply defaults --- it asks before making decisions that depend on your preferences:

-   How should blank values be handled --- left empty, filled with \'N/A\', or flagged?

-   Phone format preference --- (XXX) XXX-XXXX, XXX-XXX-XXXX, or XXX.XXX.XXXX?

-   State abbreviations --- two-character codes or full names?

-   Date format --- MM/DD/YYYY, DD/MM/YYYY, or YYYY-MM-DD?

**Example Results --- 30-Row Contact List**

  ------------ ----------------------------------------- -----------------------------
  **Field**    **Before**                                **After**
  Names        MIXED case, lowercase, ALLCAPS            Title Case across the board
  Emails       Mixed cases, trailing whitespace          All lowercase, trimmed
  Phones       Various formats including no formatting   \(XXX\) XXX-XXXX consistent
  States       Mix of full names and abbreviations       Two-character abbreviations
  Dates        Mix of MM/DD, MM/DD/YY, MM/DD/YYYY        MM/DD/YYYY consistent
  Duplicates   Several entries with minor variations     Deduplicated based on email
  ------------ ----------------------------------------- -----------------------------

**Header Formatting**

After data cleanup, Cowork applies professional header formatting --- bold, colored backgrounds, frozen panes --- without being asked. This is the spreadsheet skill\'s default behavior, designed to produce client-ready output.

**Workflow 5 --- Write Excel Formulas in Plain English**

Arguably the most demonstrated workflow in the video. Five real prompts and the corresponding formulas Cowork produces.

**Prompt 1 --- Profit Margin**

> *Add a profit margin column that calculates the margin as a percentage of revenue.*

Resulting formula:

> =(F2-G2)/F2

Wrapped with IFERROR to handle divide-by-zero cases. Formatted as a percentage with two decimals.

**Prompt 2 --- Running Total**

> *Create a running total column that shows the cumulative revenue as you go down the rows.*

Resulting formula:

> =SUM(\$F\$2:F2)

Note the absolute reference at the top of the range and relative reference at the bottom --- this is the canonical pattern, and Cowork applies it correctly without prompting.

**Prompt 3 --- Conditional Flag**

> *Add a column that flags any sale where the discount is greater than 20% with the word review.*

Resulting formula:

> =IF(I2\>0.2,\"review\",\"\")

Outputs the word \'review\' for flagged rows and blank otherwise --- clean and filterable.

**Prompt 4 --- Date Calculation**

> *Write a formula that calculates how many days ago each sale was made.*

Resulting formula:

> =TODAY()-DATEVALUE(B2)

Uses DATEVALUE to handle text-formatted dates safely. Output is an integer count of days.

**Prompt 5 --- Tiered Commission**

> *Add a commission column: 8% for sales under 5K, 10% for 5K to 10K, and 12% for anything else.*

Resulting formula:

> =IFS(F2\<5000,F2\*0.08,F2\<=10000,F2\*0.10,TRUE,F2\*0.12)

Uses IFS rather than nested IF --- cleaner and easier to maintain. The fall-through TRUE clause handles all values above 10K.

**What Makes This Work**

The spreadsheet skill knows the difference between \'IF\' and \'IFS,\' knows when to use absolute vs relative references, knows to wrap division in IFERROR, and knows to use DATEVALUE to handle ambiguous text dates. These conventions appear automatically in Cowork\'s output even when not explicitly requested.

**Workflow 6 --- Build and Manage Multi-Sheet Workbooks**

Cowork handles cross-sheet logic --- workbooks where one sheet pulls data from others. This is where pre-April-2026 Cowork frequently broke; the new release handles it cleanly.

**Example Prompt --- Cross-Sheet Summary**

> *I have data on separate sheets for each region. Create a new summary sheet that pulls the total revenue from each region into one table.*

**What Cowork Produces**

-   New summary sheet positioned at the front of the workbook.

-   Region column listing each of the regional sheets.

-   Monthly revenue breakdown pulling SUM ranges from each regional sheet.

-   Grand total row aggregating across all regions.

-   Conditional formatting highlighting the highest- and lowest-performing regions.

**Example Prompt --- Dynamic Formula Updates**

> *If I add a new row to any regional sheet, will the summary update automatically? If not, fix it.*

**What Cowork Improves**

Cowork audits the formulas in the summary sheet and replaces any hardcoded ranges with dynamic formulas:

-   Hardcoded: =SUM(North!B2:B20)

-   Dynamic: =SUM(North!B:B) or =SUM(North!B2:INDEX(North!B:B,COUNTA(North!B:B)))

This is the difference between a spreadsheet that breaks every time someone adds a row and one that grows with the data.

**Why This Matters Commercially**

Multi-sheet workbooks are where most professional financial work lives --- three-statement models, KPI rollups, departmental P&Ls. Cowork\'s ability to construct and maintain these reliably is what makes it viable for finance work, not just simple spreadsheets.

**Workflow 7 --- Analyze Data Without Pivot Tables**

Pivot tables are powerful but cumbersome. Cowork can answer pivot-table-style questions directly in chat, then output formatted summaries --- often in less time than building the pivot table would take.

**Setup Used in the Video**

50 e-commerce orders across 6 months, with columns: order date, customer name, customer tier, product category, product name, quantity, price, total revenue, day of week.

**Prompt 1 --- Trend Analysis**

> *Summarize the key trends in this data set. What stands out to you?*

**What Cowork Reports**

-   Electronics drove 60% of revenue.

-   June showed a significant revenue spike.

-   Gold-tier customers showed distinctive purchase patterns.

-   Keyboards were the top product.

-   High variance noted across customer types --- flag for further investigation.

**Prompt 2 --- Top Customers**

> *Who are the top five customers by total spend?*

Output: a ranked table with total spend, order count, average order value, and tier --- plus a flag noting that several top spenders are bronze tier rather than gold, suggesting the tier classification may not align with actual behavior.

**Prompt 3 --- Day-of-Week Patterns**

> *Is there a pattern in which days of the week have the highest sales?*

**What Cowork Reports**

-   Friday and Saturday peaked, accounting for 58% of total sales.

-   Wednesday was the lowest sales day.

-   Sunday had high order count but low revenue per order.

**Prompt 4 --- Executive Summary**

> *Write me a three-sentence executive summary on this data I could paste into a Slack message to my manager.*

**Cowork\'s Output**

> *Across 50 orders from January through June, electronics and gold-tier customers drove the majority of revenue, with Friday and Saturday alone accounting for 58% of total sales. The top customer contributed \$3,650 individually. Three of the five highest spenders are bronze tier, suggesting the current tier classification may not be aligned with actual spend behavior.*

This is publishable analyst-quality writing produced from a 50-row dataset in under a minute.

**Workflow 8 --- Create Charts and Dashboards Directly in Excel**

Cowork doesn\'t just describe charts --- it embeds actual chart objects in the .xlsx file. Same for conditional formatting and dashboard layouts.

**Chart Prompt 1 --- Single-Series Bar Chart**

> *Create a bar chart showing total revenue by month.*

Output: an embedded bar chart on the active sheet, sized appropriately, with axis labels and a title.

**Chart Prompt 2 --- Dual-Series Line Chart**

> *Add a line chart that shows both revenue and expenses on the same chart so I can see the trend.*

Output: a line chart with two series, with the area between them shaded to visualize the profit gap.

**Conditional Formatting Prompt**

> *Apply conditional formatting to the profit column and add a color scale to the conversion rate column.*

Output: rule-based formatting applied to both columns simultaneously. The profit column uses red/yellow/green based on threshold values; the conversion rate column uses a continuous color scale from low (red) to high (green).

**Dashboard Prompt**

> *Create a simple dashboard view on a new sheet that shows key metrics at a glance.*

**What Cowork Produces**

-   New sheet inserted, named \'Dashboard\'.

-   Header banner with title and date range.

-   KPI summary row across the top --- total revenue, total orders, average order value, top customer.

-   Color-coded data table with embedded charts.

-   Frozen panes so KPIs stay visible while scrolling.

**HTML Dashboard Alternative**

> *Create an HTML dashboard from this data.*

If you want a dashboard you can embed in reports or share over email, ask for HTML output instead. Cowork generates a standalone .html file that opens in any browser, with the same structure as the Excel dashboard but no Excel dependency.

**Workflow 9 --- Format Spreadsheets for Professional Presentation**

Internal spreadsheets and client deliverables look the same to the data but very different visually. Cowork closes that gap with a single prompt.

**Example Prompt**

> *Make this spreadsheet look professional. Clean up the formatting, add proper headers, and make it presentable.*

**Example --- Project Budget Sheet Transformation**

-   Colored header rows with clean typography (Calibri, bold, white-on-blue).

-   Consistent column widths set to fit content.

-   Currency formatting on all numeric monetary columns.

-   Renamed columns from machine-style to human-style (\'Allocated\' instead of \'budget_alloc\', \'Spent To Date\' instead of \'spend_ytd\').

-   Visual status indicators in the status column --- green/yellow/red dots.

-   Frozen header row so labels stay visible while scrolling.

-   Banded row coloring for readability.

-   Date formatting normalized.

**Iterative Refinement**

Once the initial pass is complete, the host iterates with follow-up prompts:

-   \'Change the header color to dark green to match our brand.\'

-   \'Add a project name title at the top of the sheet.\'

-   \'Make the column widths a bit narrower so everything fits on one screen.\'

Each follow-up prompt adjusts the spreadsheet without re-doing the previous formatting work. This iterative refinement is what makes Cowork feel like a competent spreadsheet collaborator rather than a one-shot generator.

**Workflow 10 --- Export Excel Data to Reports and Other Formats**

Once a spreadsheet is finalized, you usually need it in another format --- a PDF report for executives, a printable handout for a meeting, a snippet for Slack. Cowork handles the export.

**Example Prompt --- PDF Report**

> *Turn the spreadsheet into a formatted PDF report with a title, executive summary, and the data table.*

**Example --- Department Headcount Report**

-   Title banner with date and fiscal year.

-   KPI summary row across the top.

-   Formatted data table --- alternating row colors, currency formatted, dates aligned.

-   Confidentiality footer.

-   Production-ready PDF that doesn\'t need additional formatting work.

**Layout Adjustments**

> *I want the full data table on the second page. Don\'t split it across pages.*

Cowork adjusts page break logic so the table renders on a single page. Other layout tweaks Cowork handles via plain English:

-   Color and font changes.

-   Section reordering (\'move the chart above the table\').

-   Adding/removing summary boxes.

-   Logo placement (if a logo file is in the folder).

**Other Export Formats**

-   CSV --- for handoff to other systems.

-   Markdown --- for documentation pipelines.

-   HTML --- for email or web embed.

-   PowerPoint --- Cowork can generate slides directly from spreadsheet data.

-   Word --- when the report is more narrative than tabular.

**Three Advanced High-Value Use Cases**

Beyond the 10 core workflows, the video calls out three use cases that operators with Excel-heavy roles will recognize as transformative.

**Use Case A --- Budget vs Actuals Variance Analysis**

Variance analysis is the bread and butter of financial reporting. Done manually it takes hours per cycle. Cowork\'s version takes minutes.

**Example Prompt**

> *I have a budget sheet and an actuals sheet for Q1. Build a variance table that shows each department\'s allocated budget, actual spend, the dollar variance, and the percentage variance. Highlight anything over 10% in red.*

**What Cowork Produces**

-   Cross-sheet variance table on a new sheet.

-   Department column pulled from the budget sheet.

-   Allocated, Actual, Dollar Variance, and Percentage Variance columns.

-   Conditional formatting highlighting variances \> 10% in red, \< -10% in green.

-   Summary row with total budget, total actual, and total variance.

-   Output formatted for direct inclusion in board decks.

**Why This Is High-Leverage**

Manual variance reports are error-prone and slow. The same report regenerated next quarter takes the same hours. With Cowork, you save the workflow as a skill and run it monthly with a single command --- the 10x leverage compounds across reporting cycles.

**Use Case B --- Month-End Close & Bank Reconciliation**

Reconciliation is a recurring task that combines tedium with high stakes. Errors lead to audit findings; correctness requires patient, line-by-line attention.

**Example Prompt**

> *Reconcile the bank statement against the internal transaction log. Flag any discrepancies, categorize expenses by vendor, and produce a formatted reconciliation report with a summary of unmatched items.*

**What Cowork Produces**

-   Side-by-side comparison of bank statement entries and internal transaction log entries.

-   Matched transactions auto-categorized by vendor name (using fuzzy matching to handle merchant name variations).

-   Unmatched items flagged with a category --- possible duplicate, possible missing entry, possible different date, possible fee.

-   Summary of unmatched items with suggested resolution paths.

-   Final reconciliation report formatted for accounting team review.

**Compounding Improvement**

The host explicitly notes that this workflow improves with repetition. By month 2 or 3, the exception list shrinks dramatically because Cowork has learned which patterns are routine for your specific business. Reconciliation time drops from a half-day to under an hour.

**Use Case C --- Scenario Analysis & Sensitivity Tables**

Scenario modeling is where strategic thinking meets spreadsheet mechanics. Building it manually requires expert spreadsheet skills; Cowork builds it from a description.

**Example Prompt --- Scenario Analysis**

> *Build a scenario analysis with base, bull, and bear cases using the revenue assumptions in column C. Base is current values. Bull is 20% higher. Bear is 15% lower. Show the impact on net profit for each scenario in a summary table.*

**What Cowork Produces**

-   Three-scenario model with linked formulas.

-   Assumption cells in distinct visual style (e.g., yellow highlight) so users know what to change.

-   All scenarios update simultaneously when assumptions change.

-   Summary table at the top showing key metrics across all three cases.

-   Conditional formatting visualizing scenario delta vs base.

**Example Prompt --- Sensitivity Table**

> *Build a sensitivity table showing net margin across five price points and five volume levels.*

Output: a 5×5 sensitivity grid with price tiers as rows, volume levels as columns, and net margin as the cell value. Color-coded heatmap visualization. Includes the base case value highlighted with a thick border for visual reference.

**Why This Matters**

Scenario and sensitivity analysis is what separates a flat financial projection from a usable strategic tool. Manually building these takes the spreadsheet equivalent of expert-level skill. Cowork makes the construction accessible to anyone who can describe what they want.

**Native Excel Operations Supported**

Beyond Cowork\'s spreadsheet skill, the Claude for Excel add-in supports native Excel operations directly. The video calls these out specifically because they distinguish surface-level Excel automation from deep integration.

**Operations Supported Natively**

-   Sorting and filtering data.

-   Editing pivot tables (creating, modifying, refreshing).

-   Editing charts (data sources, chart types, formatting).

-   Applying conditional formatting rules.

-   Setting data validation (drop-downs, range checks, custom rules).

-   Preparing workbooks for printing --- page setup, print areas, headers/footers.

-   Finance-specific formatting tools --- currency, accounting, percentages, basis points.

-   Sorting by multiple criteria simultaneously.

-   Filtering with complex multi-condition logic.

**Why Native Operations Matter**

Before April 2026, even when Cowork could write Excel files, it couldn\'t trigger Excel\'s native operations. You\'d get a static .xlsx that lacked pivot tables, sortable filters, or proper page setup. After the update, those operations are first-class --- Cowork instructs Excel to build a real pivot table, not just a flat data summary.

**How To Trigger Them**

You don\'t usually need to. The spreadsheet skill knows when to apply native operations --- when you ask for a pivot summary, it builds an actual pivot table; when you ask for color coding, it builds conditional formatting rules; when you ask for sortable data, it builds an Excel table with native filter handles.

**Cross-App Context Sharing**

With the April 2026 update, Excel and PowerPoint add-ins can share full conversation context. Practical implication: you can have a conversation in Excel about your budget model, then switch to PowerPoint and ask Cowork to generate slides --- and the slide generator already knows what was just modeled.

**Limitations and What Cowork Cannot Do**

The video is honest about Cowork\'s Excel limitations. Knowing them up front prevents frustration.

**Hard Limitations**

-   Cannot execute or modify VBA macros. Cowork can open .xlsm files and analyze the spreadsheet\'s structure and formulas, but the VBA code remains untouchable.

-   Cannot modify Power Query --- Cowork doesn\'t manipulate the M language behind Power Query transformations.

-   Cannot create or modify live data connections --- anything pulled via ODBC, Power Pivot, or external query tables stays as-is.

-   Cannot trigger sheet-level events --- workbook protection settings, data tables, and similar features are not supported.

**Soft Limitations**

-   Pivot tables are powerful but for most analysis questions, you don\'t need them. Cowork can read a dataset and answer specific business questions directly. So for many tasks, building a pivot table is overkill --- but Cowork can build one if asked.

-   Very large workbooks (1M+ rows) may exceed context limits. The skill works best on workbooks where the relevant data fits in a reasonable token budget.

-   Highly stylized layouts (merged cells, multi-row headers, presentation-style formatting) still cause occasional misreads. The April update closed many of these gaps but not all.

-   Real-time collaborative editing --- Cowork operates on the file on disk, not on a live shared document.

**Versions Not Supported by Claude for Excel Add-In**

-   Excel 2016 and 2019 (perpetual/volume license versions).

-   Excel on Android.

-   Older Microsoft 365 builds below the SharedRuntime threshold.

**What Not To Use Cowork For**

-   Final client deliverables without human review --- always verify Cowork\'s output.

-   Audit-critical calculations without verification --- Cowork is fast and usually correct, but the cost of a wrong financial calculation justifies a manual second pass.

-   Replacing professional financial judgment --- Cowork accelerates analysis, it doesn\'t replace the analyst.

-   Highly sensitive or regulated data without proper controls --- verify your enterprise plan and BAA/DPA coverage first.

**Security and Prompt Injection Risks**

This is the section the video spends real time on, and rightly so. A spreadsheet with a malicious cell can hijack Cowork\'s behavior. Operators need to know how this works.

**The Threat Model**

> *Only use Claude for Excel with trusted spreadsheets and not spreadsheets from external untrusted sources, as malicious instructions can be embedded in cells, formulas, or comments.*

A prompt injection attack on a spreadsheet works like this: an attacker embeds text into a cell or comment that contains instructions phrased as if they came from you. When Cowork reads the spreadsheet to do legitimate work, it also reads the injected instructions and may follow them --- exfiltrating data, modifying formulas, sending emails, etc.

**Where Injections Hide**

-   Cell values --- especially in columns that look like notes, descriptions, or comments.

-   Cell comments --- Excel\'s comment feature embeds text invisibly in normal views.

-   Formula text --- particularly in long custom formulas or LAMBDA definitions.

-   Defined names --- named ranges with descriptive names that contain instructions.

-   Sheet names --- multi-word sheet names can carry payloads.

-   Hidden sheets, rows, and columns --- easy to forget exist.

-   Header/footer text on print layouts.

**Functions Requiring Approval**

Cowork requires explicit user approval before triggering any of these dangerous Excel functions:

  ------------------------ -----------------------------------
  **Category**             **Functions**
  External Data Fetching   WEBSERVICE, STOCKHISTORY
  Imports                  IMPORTDATA, IMPORTXML
  Dynamic References       INDIRECT
  Command Execution        DDE
  Code Execution           CALL, EVALUATE
  File System Access       IMAGE, FILES
  System Information       Various INFO and SYSTEM functions
  ------------------------ -----------------------------------

**Operator Discipline**

-   Treat external spreadsheets as untrusted by default --- read the cells before letting Cowork loose.

-   Disable or restrict Cowork\'s connector access when working on suspicious files.

-   Run analysis sessions in a dedicated folder isolated from other work.

-   Always review Cowork\'s plan before approving execution.

-   If a prompt produces unexpected behavior, stop immediately and check whether the spreadsheet contains injected instructions.

**Data Storage Reality**

Inputs and outputs are automatically deleted from Anthropic\'s backend within 30 days of receipt or generation, except under specific circumstances outlined in retention policies. For sensitive data, verify your plan tier covers the data residency and retention requirements your organization needs.

**Best Practices and Pro Tips**

Distilled from the video and surrounding documentation, these are the practices that separate operators who get marginal value from Cowork\'s Excel capabilities from those who get transformational value.

**Tip 1 --- Use Outcome-Oriented Prompts**

\'Make this professional\' beats \'change column A to bold and column B to italic.\' Cowork\'s spreadsheet skill knows what \'professional\' looks like; spelling out every micro-decision is slower and worse.

**Tip 2 --- Build Skills From Repeated Workflows**

If you do the same Excel task more than twice, save the workflow as a skill. The variance analysis, monthly reconciliation, and weekly reporting workflows are textbook candidates.

**Tip 3 --- Configure Persistent Formatting Rules**

Set your house-style preferences in Cowork\'s settings (preferred fonts, header colors, currency format, date format). These apply automatically across all files you work on, eliminating the need to re-specify them every session.

**Tip 4 --- Use Opus 4.6 with Extended Thinking for Complex Models**

On simple data cleanup, Sonnet is fine. On multi-sheet financial models, scenario analysis, and reconciliation work, the upgrade pays for itself.

**Tip 5 --- Save Versions Instead of Overwriting**

Always ask Cowork to save a new version (e.g., \'save as clean\_\<filename\>\') instead of overwriting the original. Audit trails preserved this way are invaluable when something goes wrong or when you want to compare before/after.

**Tip 6 --- Add Comment-Based Audit Trails**

For any spreadsheet that will be reviewed by another human (auditor, manager, client), append: \'Apply all the changes and add a comment to each modified cell explaining what you changed and why.\' Cowork attaches Excel comments documenting every edit.

**Tip 7 --- Use Cell Citations When Asking Questions**

Cowork returns answers referencing exact source cells, not generic explanations. So when you ask a question like \'why is the gross margin different in March?\', Cowork\'s answer cites the specific cells that drive the difference. Treat this like academic citation --- it makes the answer verifiable.

**Tip 8 --- Treat Cowork as a Collaborator, Not a Replacement**

The 10x leverage on Excel work comes from the human doing the strategy and validation while Cowork handles the mechanical execution. Reverse that division of labor and quality drops.

**Tip 9 --- For Recurring Work, Use Routines Not Schedules**

Anything that needs to run weekly, monthly, or on an external trigger should be a Routine (cloud-hosted) rather than a Scheduled Task (desktop-bound). The reliability difference is dramatic when reports need to land at 6 AM regardless of whether your laptop is awake.

**Tip 10 --- Backup Your Skills**

Skills don\'t transfer between computers automatically. Back them up to Google Drive or a Git repository so you don\'t lose months of refinement when you switch machines.

**FAQ**

**Can Cowork edit existing Excel files in place?**

Yes. Cowork can either overwrite the original file or save a new version, depending on your prompt. The host\'s recommended default is to save new versions for auditability.

**Does it work with multi-sheet workbooks?**

Yes --- full cross-sheet formula support, summary sheet construction, and dependency tracking. This was unreliable before the April 2026 update; it is reliable now.

**How accurate are the formulas?**

In the host\'s testing, formula accuracy is high. Cowork wraps risk-prone formulas (division, lookups) in IFERROR to catch edge cases. The April 2026 model upgrade to Opus 4.6 was the inflection point that made this consistent.

**What file formats convert to Excel?**

CSV, plain text, Word (.docx), PDF, Markdown. Anything tabular-ish converts cleanly; anything narrative requires structuring guidance in the prompt.

**Does it work with Google Sheets?**

Cowork produces .xlsx files. Google Sheets can import .xlsx directly, so the workflow works --- you just import the output file. Native Google Sheets editing is not yet supported by Cowork\'s spreadsheet skill.

**Can it modify VBA macros?**

No. Cowork can open .xlsm files and analyze the spreadsheet\'s structure and formulas, but cannot read, write, or execute VBA code.

**What about pivot tables?**

Yes --- the April update added native pivot table editing. Cowork can build, modify, and refresh pivot tables. For most analysis questions, however, asking Cowork directly is faster than building a pivot table.

**Does Cowork preserve existing formulas when modifying a sheet?**

Yes. The Claude for Excel add-in maintains formulas, dependencies, cell relationships, and existing formatting unless you explicitly ask for them to be changed.

**Can I use this on the web version of Excel?**

Yes --- Claude for Excel works on Excel for the web, Windows, Mac, and iPad. The Cowork desktop app and the Excel add-in share context, so you can move between them.

**Which Claude plans support Excel work?**

Pro, Max, Team, and Enterprise. Free tier does not include Cowork or the Excel add-in.

**How do I switch models?**

In Excel, use the model selector in the Claude pane to switch between Opus 4.7, Opus 4.6, and Sonnet 4.6. Opus 4.6 is the recommended default for Excel work as of this video.

**Source URLs Appendix**

**Primary Source**

Claude Cowork Can NOW Automate Your Excel! (Full Walkthrough) --- <https://www.youtube.com/watch?v=rqte_LEu2Y8>

**Companion Sources Consulted**

• Anthropic --- Use Claude for Excel (Help Center) --- <https://support.claude.com/en/articles/12650343-use-claude-for-excel>

• Anthropic --- Claude for Excel product page --- <https://claude.com/claude-for-excel>

• Ryan & Matt Data Science --- Cowork Excel: 10 Ways to Automate Spreadsheets --- <https://ryanandmattdatascience.com/claude-cowork-excel/>

• DataCamp --- Claude in Excel Tutorial --- <https://www.datacamp.com/tutorial/claude-in-excel>

• Claude Cookbook --- Skills Introduction --- <https://platform.claude.com/cookbook/skills-notebooks-01-skills-introduction>

• Anthropic Cookbook --- Skills README --- <https://github.com/anthropics/claude-cookbooks/blob/main/skills/README.md>

• GitHub --- claude-office-skills (PPTX/DOCX/XLSX/PDF) --- <https://github.com/tfriedel/claude-office-skills>

• GitHub --- excel-analyst-pro (Financial Modeling Toolkit) --- <https://github.com/jeremylongshore/excel-analyst-pro>

• Pasquale Pillitteri --- Claude for Excel and PowerPoint Guide --- <https://pasqualepillitteri.it/en/news/265/claude-excel-powerpoint-ai-add-ins-guide>

• Microsoft Marketplace --- Claude by Anthropic for Excel --- <https://marketplace.microsoft.com/en-us/product/saas/wa200009404?tab=overview>

• Anthropic --- Advancing Claude for Financial Services --- <https://www.anthropic.com/news/advancing-claude-for-financial-services>

• Anthropic --- Release Notes (April 2026) --- <https://releasebot.io/updates/anthropic/claude>

• ChatFin --- AI Finance Assistant in Spreadsheets Guide --- <https://chatfin.ai/blog/ai-finance-assistant-in-spreadsheets-claude-integration-guide-2026/>

• Orbilon Tech --- Claude in Excel: AI Spreadsheet Automation Guide --- <https://orbilontech.com/claude-in-excel-ai-spreadsheet-automation-2026/>
