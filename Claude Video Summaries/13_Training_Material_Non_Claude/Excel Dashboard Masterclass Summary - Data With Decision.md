**Excel Dashboard Masterclass --- Training Material**

*Data With Decision --- General Excel Dashboard Methodology*

**Comprehensive Reference Document**

Source: youtube.com/playlist?list=PLwIcJx1aSL1Qx739cQXD8R70bzVIBX6gZ

*Prepared: May 2026*

**About This Document**

This is general-purpose Excel dashboard methodology --- NOT Claude-specific. Intended as reference for what makes a good dashboard, so Claude can be trained to produce dashboards matching these standards.

**14 Videos in the Playlist**

  -------- ------------------------------------------------------------------- -----------
  **\#**   **Video**                                                           **Hours**
  01-04    MS Excel Dashboard Masterclass Parts 1-4                            \~6.7
  05-06    Advanced Excel Dashboards With ChartGPT (AI for Data Analytics)     \~5.3
  07-09    Interactive Insights: Excel Dashboard Techniques                    \~7.3
  10-12    Excel Sales Dashboard: Analyze and Visualize Like a Pro Parts 1-3   \~3.9
  13       Become a Data Analyst: Skills, Tools, Career Path                   \~0.1
  14       9 Must-Know Tips for Excel Success                                  \~0.2
  -------- ------------------------------------------------------------------- -----------

**Universal Dashboard Architecture (From Across All Videos)**

**The 7-Step Build Process**

1.  Overview of the dashboard goal --- what business question does it answer?

2.  Data sheet inventory --- what raw data exists, where does it live, how does it update?

3.  Database preparation --- clean, normalize, structure the source data.

4.  Data analysis and visual prep --- pivot tables, slicers, KPI calculations.

5.  Background design --- layout grid, color palette, typography.

6.  Assemble dashboard --- drop visuals onto background grid.

7.  Final formatting --- polish, conditional formatting, theme consistency.

**Key Excel Concepts Covered**

-   Power Query for data import (instead of native Excel).

-   Power Pivot for data modeling --- relationships between tables.

-   Get Data from external sources (Excel workbook, CSV, web).

-   Pivot tables vs Data Model approach.

-   DAX measures for advanced KPIs.

-   Slicers for interactive filtering.

-   Form controls (combo box, list box, option button) for dynamic UX.

-   INDEX/MATCH for advanced lookups.

-   Conditional formatting based on KPI thresholds.

-   Sparklines for in-cell trends.

**Visual Components Universally Recommended**

  ------------------------------ ------------------------------------------------------
  **Component**                  **Best Use**
  KPI Cards (top of dashboard)   Headline numbers --- total sales, profit, growth %
  Trend chart (line)             Time series --- performance over months/quarters
  Bar/column chart               Category comparison --- sales by region/product
  Pie/donut chart                Composition --- share of total (limit to 5-7 slices)
  Heat map                       2D categorical comparison
  Waterfall chart                Build-up to a total --- variance breakdown
  Combo chart (bar + line)       Two related metrics on different scales
  Sparklines (in-cell)           Compact trend in tabular layouts
  Sortable tables                Drilldowns from summary visuals
  ------------------------------ ------------------------------------------------------

**Design Principles From the Videos**

**Layout**

-   KPIs always at top.

-   Trend charts middle band.

-   Detail tables/slicers below or on the right.

-   Filter slicers visible without scrolling.

-   Whitespace between sections.

-   Consistent grid alignment.

**Color**

-   Pick 3-5 brand colors. Use sparingly.

-   Use conditional formatting for variance (red/green) and threshold (red/yellow/green).

-   Avoid rainbow palettes --- too noisy.

-   Dark mode versions for executive presentation.

**Typography**

-   KPI numbers large (24-36pt), bold.

-   Labels small (10-11pt), regular.

-   Use one font family.

-   Right-align numbers; left-align labels.

**Interactivity**

-   Slicers control multiple visuals simultaneously.

-   Drop-downs for date range, region, product.

-   Drill-through to source data on click.

-   Drill-down hierarchy: total → category → product.

**ChartGPT / AI Section (Videos 5-6)**

These videos integrate AI-assisted dashboard creation:

-   Use AI to generate suggested visualizations from raw data.

-   AI can write DAX measures from natural language.

-   AI assists with data cleanup heuristics.

-   AI suggests appropriate chart types based on data shape.

-   AI generates explanatory text for each KPI.

**Why This Matters For Claude**

-   These dashboard architecture principles directly inform how Claude (when using Excel skill or Cowork × Excel) should build outputs.

-   If Claude is asked for an executive dashboard, the 7-step process and visual components above ARE the methodology to follow.

-   Color/typography/layout principles can be encoded in the working-preferences.md file so Claude defaults to good design.

-   \'Dashboard.md\' skill could be created with this exact methodology.

**Sources**

Excel Dashboard Masterclass playlist by Data With Decision --- <https://www.youtube.com/playlist?list=PLwIcJx1aSL1Qx739cQXD8R70bzVIBX6gZ>
