**Reusable Finance Workflow in Claude 2.0**

*Luke Finance --- Define Once, Run Every Cycle*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=dTPndJ5VG_I

*Prepared: May 2026*

**Premise**

Most finance professionals using AI prompt their way through every step. Data cleaning is one prompt. Structuring tables another. Building the model another. Each step is faster than manual but you\'re still constantly repeating the process. Claude\'s latest update supports structured multi-step workflows you define once and execute repeatedly. For finance, this is a significant shift --- monthly closes, quarterly reporting, budget vs actuals, forecast updates, investor decks all follow the same analytical sequence every cycle.

**What Changed**

Claude now supports defining the full workflow logic --- sequence of steps, rules for handling data, model structure, validation checks, output format --- in one workflow file. Claude follows it from beginning to end in a single run.

Plus: Claude operates inside structured project environments. The workflow file = process documentation. Scripts folder = reusable logic. Reports folder = every output ever generated. All inside normal file structure that integrates with version control, shared drives, project management.

**Project Structure**

  --------------------- ---------------------------------------------
  **Component**         **Purpose**
  data/                 Where incoming spreadsheets go
  scripts/              Where reusable automation code gets saved
  reports/              Where all generated outputs land
  finance_workflow.md   Brain of the system --- at the project root
  --------------------- ---------------------------------------------

**Workflow File Specifies**

-   Input expectations --- required columns: month, revenue, COGS, OpEx, marketing, R&D.

-   Numeric columns must be numeric --- no currency symbols, no text formatting.

-   Six stages the workflow executes.

**The Six Stages**

**Stage 1 --- Data Structuring**

-   Reads spreadsheet from data folder.

-   Standardizes column names and data types.

-   Strips formatting artifacts that break calculations.

-   Generates derived financial fields: gross profit (revenue - COGS), gross margin (GP/revenue), operating income (GP - OpEx).

-   Cleaned data saved as standalone CSV or written into data sheet of output workbook.

**Stage 2 --- Model Construction**

-   Generates reusable Python script saved to scripts folder.

-   Builds Excel workbook with structured sheets: data, model, audit, analysis, dashboard, report.

-   Critical: model sheet uses formulas referencing data sheet directly. Revenue links via cell references. Gross profit calculated through formulas. Nothing hardcoded.

-   Script persists in project --- workflow checks if it exists before generating new one. Reused across runs without regeneration.

-   Standard Python file you can open, read, modify if reporting requirements change.

**Stage 3 --- Model Review and Audit (Most Skipped Step)**

This is the step most people skip when using AI for finance. Critical.

-   Audit sheet runs diagnostic checks.

-   Verifies gross profit equals revenue minus COGS.

-   Confirms margin calculations are consistent.

-   Checks for negative revenue values.

-   Confirms COGS doesn\'t exceed revenue.

-   Flags broken formula references.

-   Each check gets pass/fail status with description.

**Hard Stop Rule**

> *If any critical check fails, the workflow stops. It does not proceed to analysis or generate a dashboard on top of broken numbers.*

**Stage 4 --- Financial Analysis**

-   Calculates month-over-month revenue growth.

-   Tracks gross margin and operating margin trends.

-   Breaks down cost drivers as percentages of revenue.

-   Generates plain-language interpretation lines feeding executive summary.

-   If revenue growth accelerated, called out. If COGS trending up as share of revenue, flagged with context.

**Stage 5 --- Dashboard and Reporting**

-   Visual layer: dashboard sheet with charts (revenue trends, gross margin trends, operating margin movement, cost breakdown for most recent period, revenue growth bar chart).

-   Report sheet with bullet-point insights summarizing findings.

-   Insights pull from interpretation lines in stage 4 --- clear analytical thread from raw numbers through metrics to executive summary.

**Stage 6 --- Save and Log**

-   Output saved to reports folder.

-   Run logged with timestamp, dataset name, output filename, warnings.

-   If output file is locked (someone has it open in Excel), workflow saves timestamped version automatically --- nothing lost.

**Reusing the Workflow**

Real value: this is now reusable forever.

**Next Cycle Pattern**

1.  Drop new spreadsheet into data folder.

2.  Tell Claude: \'Execute the workflow using the dataset in the data folder.\'

3.  Single instruction triggers full pipeline:

-   Data cleaned with same standardized logic.

-   Model rebuilt using script already in scripts folder.

-   Audit checks run against new numbers.

-   Analysis calculates updated metrics.

-   Dashboard regenerates with latest trends.

**Verification (30 Seconds)**

-   Confirm data sheet loaded the new dataset correctly.

-   Check audit sheet --- no critical failures.

-   Scan analysis --- margin and growth calculations look reasonable.

-   Confirm dashboard charts reflect latest data, not previous run artifacts.

**Where This Heads**

> *The value is no longer in getting AI to answer individual questions or perform isolated tasks. The value is in building structured systems that reflect the way finance teams actually operate --- repeatable processes applied to changing data with built-in validation and consistent output formats.*

Same approach applies to budgeting, forecasting, operational reporting, performance diagnostics --- anything where analytical steps stay the same and data refreshes.

**Source**

How to Build a Reusable Finance Workflow in Claude 2.0 by Luke Finance --- <https://www.youtube.com/watch?v=dTPndJ5VG_I>
