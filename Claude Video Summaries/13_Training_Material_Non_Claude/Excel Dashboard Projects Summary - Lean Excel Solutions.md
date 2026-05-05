**Excel Dashboard Projects --- Training Material**

*Lean Excel Solutions --- Dashboard Templates by Domain*

**Comprehensive Reference Document**

Source: youtube.com/playlist?list=PLYjYcSjCw_LVDPyjNfCrlryE7i6sklJ7T

*Prepared: May 2026*

**About This Document**

Domain-specific Excel dashboard templates from Lean Excel Solutions. NOT Claude-specific. Reference patterns for sales / customer / stock portfolio / HR dashboards.

**Playlist Coverage**

  ----------------------------- --------------------------------------------------------------------
  **Domain**                    **Videos**
  Sales Dashboards              Sales Dashboard, Sales Distribution Dashboard
  Customer Analytics            Setup & Overview, Advanced Visuals & Analysis
  Stock Portfolio               4-part series --- Overview, Layout Design, Database, Visualization
  HR (Learning & Development)   2-part --- VBA UserForm, Power Pivot
  ----------------------------- --------------------------------------------------------------------

**Sales Dashboard Reference Pattern**

**KPI Layer (Top)**

-   Total Sales (period).

-   Total Profit.

-   Profit Percentage.

-   Combined into monthly comparative format.

-   Hide/unhide toggle for individual vs comparative view.

**Visualization Layer**

-   Product-wise sales for selected period --- top 10 with scroll.

-   Day-wise sales (trend across week).

-   Sales percentage by selling type (online/offline).

-   Sales percentage by mode of payment.

-   Top-selling product/category.

-   Category-wise sales contribution.

**Filter/Slicer Layer**

-   Year selector.

-   Month selector.

-   Sales type.

-   Mode of payment.

**Data Architecture**

  ----------------------- --------------------------------------------------------------------------------------
  **Sheet**               **Purpose**
  Master Data (Catalog)   Product ID (unique), Product, Category, Unit of Measure, Buying Price, Selling Price
  Transaction Data        Date, Product ID, Quantity, Sale Type, Payment Mode
  Calculations            Hidden --- joins master + transactions + computes profit
  Dashboard               Visible to user --- pulls from calculations
  ----------------------- --------------------------------------------------------------------------------------

**Customer Analytics Pattern**

**Two-Part Build**

1.  Setup & Overview --- data structure, foundational metrics, slicer panel.

2.  Advanced Visuals --- RFM (Recency, Frequency, Monetary) analysis, cohort analysis, retention curves.

**Key Metrics**

-   Customer count.

-   New vs returning split.

-   Average order value.

-   Customer lifetime value.

-   Churn rate.

-   RFM segmentation (Champions, Loyal, At Risk, Hibernating).

**Stock Portfolio Pattern (4-Part Build)**

**Part 1 --- Overview**

Big picture metrics: total invested, current value, unrealized gain/loss, percentage return, dividend income, top winners/losers.

**Part 2 --- Design Layout**

Layout grid: KPI banner top, allocation pie chart upper right, performance line chart center, holdings table below, individual stock card on right.

**Part 3 --- Prepare Database**

  -------------- --------------------------------------------------------------------------------
  **Sheet**      **Contents**
  Holdings       Ticker, name, sector, shares owned, average cost, current price, current value
  Transactions   Date, ticker, type (buy/sell), shares, price, fees
  Dividends      Date, ticker, amount per share
  Prices         Daily/weekly closing prices per ticker
  Calculations   FIFO cost basis, returns, gain/loss
  -------------- --------------------------------------------------------------------------------

**Part 4 --- Visualize Dashboard**

Drop visuals onto layout from part 2. Slicers for sector, holding period, return type.

**Learning & Development (HR) Pattern**

**Part 1 --- VBA UserForm**

VBA-based form for capturing training data. Fields: employee, training name, date, status, assessor, rating. UserForm pops up; data writes to source sheet.

**Part 2 --- Power Pivot**

Aggregations: trainings per employee, completion rates, average ratings, time-to-completion. Power Pivot data model relates: employees ↔ trainings ↔ assessments.

**Universal Pattern Across All Dashboards**

  ----------------------- -------------------------------------------------
  **Layer**               **Sheets**
  Source data (raw)       1-3 normalized sheets --- never modify directly
  Calculations (hidden)   Pivot tables, formulas, computed metrics
  Dashboard (visible)     Visuals + slicers --- what the user sees
  ----------------------- -------------------------------------------------

**Why Three Layers**

-   Source clean = source of truth.

-   Calculations hidden = changes don\'t affect user.

-   Dashboard = pretty + filtered. Update source data → dashboard updates automatically.

**Why This Matters For Claude**

-   If Claude is asked to build a sales / customer / portfolio / HR dashboard, these reference patterns ARE the templates.

-   Three-layer architecture (source/calc/dashboard) becomes Claude\'s default when building Excel dashboards.

-   The \'separate slicers from visualizations from data\' pattern is universal good practice Claude should follow.

-   Domain-specific KPIs (RFM for customers, FIFO cost basis for portfolio) are knowledge Claude can apply when given similar requests.

**Sources**

Excel Dashboard Projects playlist by Lean Excel Solutions --- <https://www.youtube.com/playlist?list=PLYjYcSjCw_LVDPyjNfCrlryE7i6sklJ7T>
