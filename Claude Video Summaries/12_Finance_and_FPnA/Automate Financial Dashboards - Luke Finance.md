**Automate Financial Dashboards With Claude**

*Luke Finance --- ERP Cleaner + Self-Updating Dashboard*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=otB1byZUvAA

*Prepared: May 2026*

**Premise**

Building a dashboard isn\'t the problem. The problem is what happens the month after --- new ERP export lands, columns don\'t match, dates inconsistent, labels messy. You fix it manually. Same thing next month. The dashboard looks automated but the process behind it is completely manual.

This video doesn\'t automate the dashboard itself (built once). It automates everything behind it --- raw ERP files drop into a folder, get cleaned the same way every time, flow into one structured dataset that the dashboard reads from.

**Project Folder Structure**

Folder name: automate_financial_reporting/. Three subfolders + one instruction file.

  --------------- ------------------------------------------------------------------------------------------
  **Component**   **Purpose**
  input/          Where raw ERP Excel reports land each month
  data/           Where the clean CSV is stored after first run
  logs/           Records what happened during each run --- file processed, rows cleaned, anything skipped
  cleaner.md      Instruction file --- how to process ERP export end to end
  --------------- ------------------------------------------------------------------------------------------

**cleaner.md Specifies**

-   Which sheet to read from Excel file (transactions, not summary or metadata).

-   How to standardize inconsistent column names into fixed structure.

-   How to normalize date formats (4 different formats → 1).

-   Which rows to remove (missing revenue, missing dates).

-   How to append only new rows into existing CSV without duplicating.

**Step 1 --- Connect Project to Cowork**

1.  Open Claude Cowork.

2.  Click \'work in a project.\'

3.  \'Choose a different folder\' → automate_financial_reporting/.

4.  Click \'Always allow\' on permission popup.

**Step 2 --- Clean ERP Data**

Demo data: ABC Manufacturing Limited --- three monthly exports for January, February, March 2024. Each has three sheets: transactions, summary, metadata. Transaction sheet matters.

Realistic messiness: column names differ across exports, dates in 4 different formats, department labels in every case imaginable.

**Run Prompt**

> *Follow the instructions in cleaner.md.*

**What Happens**

-   Reads January file → selects transactions sheet.

-   Maps inconsistent column names to fixed 6-column structure.

-   Normalizes every date to one format.

-   Standardizes department/product labels.

-   Removes rows with missing revenue or dates.

-   Checks if CSV exists in data/. First run: no → creates dashboard_data.csv from scratch.

**Why This Matters**

Every future run will append into this same file instead of replacing it. History builds month by month. Dashboard shows real trends, not single-month snapshots.

**Step 3 --- Build the Dashboard (Once)**

Same Cowork session. Dashboard prompt defines structure in three layers:

  ------------------- --------------------------------------------------------------------------------------------------------
  **Layer**           **Defines**
  Data contract       File location to read from, the 6 columns the data will contain
  Visual layout       KPI cards top, trend charts, breakdown by region/product/department, sortable transaction table bottom
  Interaction layer   Filter bar (date range, region, product, department) + manual CSV upload fallback
  ------------------- --------------------------------------------------------------------------------------------------------

Output: single self-contained HTML file using chart.js. Runs in any browser. No backend.

**Why Lock the Structure**

Dashboard has to stay the same every month while underlying dataset grows. Leave layout undefined → every rebuild produces slightly different output → breaks month-over-month comparisons.

**Honest Caveat**

Dashboard didn\'t auto-pull CSV on first load. Had to click upload button and point at clean file. After that it worked as expected.

**Step 4 --- Build the Automation Layer**

Add automation.md to project folder alongside cleaner.md. New file contains NO cleaning logic --- only watches input/, detects new files, triggers cleaner.md.

Tracks which files already processed using logs/ to ensure same file never gets cleaned twice.

**Why Two Files**

Cleaning logic lives in ONE place. That\'s what makes the system consistent across every run.

**Step 5 --- Run as Continuous Loop**

Use Claude Code from terminal so system reacts as soon as new data lands, not on timer.

**Setup**

5.  Claude Code installed and signed in.

6.  Open terminal inside project folder.

7.  Type \'claude\' to confirm environment.

8.  Run a simple loop executing automation instruction every 10 seconds (demo). In practice use longer interval based on how often files arrive.

**First Pass Behavior**

Loop checks input/, compares against logs. January file already processed. Exits cleanly without doing anything. Good automation knows when to do nothing.

**The Monthly Loop in Action**

Drop February ERP file into input/. Don\'t touch terminal. Don\'t re-explain anything.

**What Happens Within Seconds**

-   Loop detects new file.

-   Hands off to cleaner.md.

-   Same cleaning logic applied.

-   Cleaned data appended to existing CSV.

-   January data stays where it was. February rows land underneath. Dataset now 74 rows. File grows instead of being rebuilt.

**Why Strict Rules Matter**

cleaner.md explicitly tells the system:

-   Do not override the full dataset.

-   Do not change column structure.

-   Do not add extra columns.

-   Only append new rows.

Manual update workflows break exactly here --- someone pastes new data in wrong place, overwrites a clean row, inserts a column shifting layout, replaces whole file losing history. Automation prevents all that.

**Drop March File**

Same process. Dataset now 112 total rows across Q1 --- all in same file with consistent structure.

**Open Dashboard With Updated CSV**

-   Revenue and profit trend charts now show real shape --- full quarter of movement.

-   Date filter for middle slice of quarter --- dashboard updates without touching file.

-   Same clean CSV supports full quarter view AND narrower slice from same load.

**System Recap**

-   Raw ERP exports → input folder.

-   Cleaner standardizes and appends to single growing CSV.

-   Automation layer triggers cleaner on new arrivals.

-   Dashboard reads from same file every time, never rebuilt.

-   Dashboard built once. Cleaning logic defined once. New months flow through on their own.

**Source**

How I Use Claude to Automate Financial Dashboards by Luke Finance --- <https://www.youtube.com/watch?v=otB1byZUvAA>
