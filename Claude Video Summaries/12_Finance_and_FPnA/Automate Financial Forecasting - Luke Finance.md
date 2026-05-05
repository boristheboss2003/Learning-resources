**Automate Financial Forecasting With Claude**

*Luke Finance --- Earnings PDFs to Self-Updating Forecast Model*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=N1No8NQ16Xc

*Prepared: May 2026*

**Premise**

Right now: every time new data comes in you repeat the process --- open PDF, find numbers, update model, fix what broke. The logic lives in your prompts, not in the system. Every run is slightly different.

This video: build a pipeline where raw financial data flows into a structured forecasting model that updates itself when new data arrives. Logic fixed. Structure consistent. System handles execution without restarting.

**Source Data**

Real Amazon quarterly earnings releases --- full income statements, cash flow, balance sheets, segment breakdowns (AWS, North America, International). Inconsistent table layouts, mixed labels across quarters, narrative sections between numbers, different terminology for same line items.

Workflow applies to ANY company --- Amazon is just realistic complexity demo.

**Project Structure**

  --------------- ------------------------------------------------------------------------
  **Component**   **Purpose**
  input/          Amazon PDFs land here
  processed/      Per-quarter Excel files after extraction
  model/          Final forecasting workbook
  logs/           Records each run --- files processed, periods detected, anything wrong
  workflow.md     Full pipeline logic --- Claude follows it strictly
  automation.md   Watch input/, trigger workflow.md on new arrivals (added later)
  --------------- ------------------------------------------------------------------------

**Build the Forecasting Model**

**Single Instruction**

> *Follow workflow.md strictly and execute the full pipeline end to end.*

**What Claude Does**

1.  Reads folder structure.

2.  Loads PDF reading and Excel building tools.

3.  Begins processing all 8 earnings releases.

4.  For each: extracts revenue, costs, operating income, net income from income statement.

5.  Pulls operating cash flow, capex, financing flows from cash flow statement.

6.  Captures balance sheet items and segment data (AWS, NA, International).

**Three Layers Per Excel File**

-   Raw extraction sheet --- every line exactly as in original document, preserving source labels and page numbers for traceability.

-   Structured data sheet --- financials cleaned and mapped into consistent categories. \'Net sales,\' \'revenue,\' \'total net sales\' all resolve to same standardized \'Revenue\' row.

-   Metadata sheet --- source file, extraction timestamp, processing details.

**Period Identification**

Period identified from CONTENT of each PDF, not file name. Whether document says \'Q1 2025\' or \'3 months ended March 31, 2025,\' system standardizes into same format. That consistency makes automation work later.

**The Forecasting Workbook**

**Sheets Created**

-   Historical model --- 8 quarters with calculated fields for gross profit, operating income, margins, FCF --- all formulas, not hardcoded.

-   Driver sheet --- key assumptions: revenue growth rates, cost percentages, capital intensity. Derived from historical patterns, not arbitrary inputs.

-   Forecast sheet --- projects future periods using formulas linked to historical AND drivers.

-   Scenario sheets --- base, upside, downside cases.

-   Validation sheet.

-   Commentary and sources sheet (citing original documents).

**Verification**

System runs final pass at end. All formulas recalculate with zero errors. Every cell is formula driven. Model is internally consistent.

**Schedule Automatic Updates**

**Setup**

7.  Click Schedule Tasks. New task.

8.  Name: \'financial_data.\'

9.  Prompt (the automation logic): \'Scan input folder for new PDFs. Compare against what\'s already processed. Only act on new files. For each new file, extract data using same structure as existing processed files --- same sheet names, same column order, same normalized labels. Create per-quarter Excel file in processed folder. Append new period into existing model.\'

10. Strict rules: do not change sheet names. Do not change layout. Do not overwrite formulas. Do not replace formula cells with hardcoded values. Only append new data. Let existing formulas extend.

11. Frequency: hourly (demo) --- daily/weekly fine for production since earnings don\'t arrive hourly.

12. More options → Opus 4.6 model. Working directory: forecasting_automation folder. Save.

**Continuous Loop Mode (Even More Responsive)**

Use Claude Code from terminal. System reacts as soon as new data appears.

**Setup**

13. Claude Code installed and signed in.

14. Add second instruction file \'automation.md\' inside project folder with same update logic.

15. Open terminal in project folder. Type \'claude.\'

16. Run loop executing automation.md every second.

**First Pass Behavior**

Loop checks input folder. All existing PDFs already have matching processed files. Lists what\'s there, confirms nothing new, exits cleanly. Good automation knows when to do nothing.

**Drop New PDF --- What Happens**

Without reopening Claude or explaining anything:

-   Loop detects new PDF on next pass.

-   Identifies reporting period from inside document.

-   Creates new Excel file in processed folder.

-   Maps financial data into same standardized categories.

-   Opens existing forecast model.

-   Appends new period into historical sheet.

-   Driver logic extends with new data points.

-   Forecast recalculates through existing formulas.

-   Scenario sheets update because historical averages shifted.

**Verification**

-   Check process file against original PDF --- revenue/cost match, segment data captured correctly, labels align.

-   Verify model --- new period flows through drivers and forecast without breaking formulas.

-   Logs folder has new entry recording exactly what happened.

**System Recap**

> *Raw earnings PDFs to a structured forecasting model. Update process scheduled to run automatically. Continuous loop reacts as soon as new filings arrive. Model gets built once. After that, the system maintains it.*

Whether you add one new quarter or a full year\'s worth of filings, the workflow stays the same. Structure stays fixed. Outputs remain consistent.

**Source**

How I Use Claude to Automate Financial Forecasting by Luke Finance --- <https://www.youtube.com/watch?v=N1No8NQ16Xc>
