**Use Claude For Finance Better Than 99% of People**

*Luke Finance --- 9-Stage Boardroom-Ready Methodology*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=qLDwThdc3WQ

*Prepared: May 2026*

**Premise**

Move from unstructured prompts and fragile outputs to controlled, auditable, boardroom-ready financial workflows that hold up in real FP&A. Nine stages, each building on the previous one.

**Stage 1 --- Source Collection (Data Ingestion)**

Why critical: if inputs aren\'t verified, nothing later is reliable. Biggest modeling errors come from inputs never properly examined --- mislabeled period column, half-filled product tables, covenant buried in narrative text never translated to numbers, revenue total that doesn\'t match product detail.

**Procedure**

1.  Save untouched baseline of workbook before ingestion.

2.  Open Claude add-in in Excel. Select Opus 4.5 (structural reasoning task).

3.  Run ingestion prompt forcing Claude to inventory every sheet, every field, every structural dependency BEFORE analysis.

**What to Expect**

-   Structured table including every sheet.

-   All missing fields called out.

-   Each sheet has a confidence score.

-   Three clear next actions to complete ingestion.

**Verify Before Trusting**

-   All sheets appear.

-   Required modeling fields accounted for: period, revenue, COGS, SG&A, capex, debt, cash, product units, price.

-   If any required input missing → choose: generate synthetic inputs, manually add data, or accept placeholders for prototyping. Then rerun ingestion.

**Stage 2 --- Persona Configuration and Calibration**

Why critical: if Claude isn\'t locked into a professional finance role, everything downstream becomes unreliable. Casual language, hidden calculation steps, numbers without structure.

**Goal**

Transform Claude from generic chatbot into repeatable, auditable CFO and FP&A analyst persona operating within Excel. Every response must use finance terminology, cite exact sheets/columns, show step-by-step calculation logic, flag data quality issues before analysis, frame recommendations with trade-offs and risks.

**Procedure**

4.  Open Claude add-in. Set model to Opus 4.5.

5.  Paste exact persona prompt.

6.  Require Claude to explicitly confirm rule acceptance.

7.  Must include 3 demonstration examples: a step-by-step financial calculation, a model audit comment, a concise executive summary with risk implications.

8.  Review responses carefully. Calibration only at this stage --- no edits to sheets yet.

**Stage 3 --- Plan-First Prompting**

Why critical: if Claude makes fixes before you approve a plan, hidden assumptions become formulas. Audit trails weaken, credibility drops.

**Goal**

Generate prioritized auditable plan, 6-12 steps, converting workbook into driver-based three-statement model + DCF. Each step must define: objective, sheets involved, required inputs (precise columns or cells), outputs produced, explicit acceptance checks, and a \'do not proceed if\' gate.

**Critical Discipline**

-   No formulas at planning stage.

-   No fixes.

-   No execution.

-   Just the plan.

**After Approval**

Copy finalized plan into a new sheet titled \'stage_checklist.\' Becomes formal governance artifact.

**Stage 4 --- Scope Control and Data Filtering**

Why critical: financial workbooks have dozens of sheets --- legacy tabs, helper tables. If Claude sees everything, it can draw from wrong context, hallucinate joins, mix unrelated data.

**Goal**

Create input_history table and transparent mapping log. All mismatches documented (NOT auto-fixed). Trace from source to output without ambiguity.

**Procedure**

9.  Opus 4.5 in normal chat mode (NOT auto-build buttons).

10. Paste stage 4 prompt.

11. Claude creates input_history using only historical financials, revenue_by_products, drivers.

12. Extracts specified columns, validates revenue sums, flags mismatches, quantifies differences, builds mapping log.

13. Does NOT fix issues or generate formulas at this stage.

**Stage 5 --- Three-Statement Model Foundation**

Why critical: every formula, every link, every audit check must be established before considering valuation or sensitivity. If model has hard-coded numbers, hidden logic, or missing links, everything downstream becomes non-auditable.

**Procedure**

14. Opus 4.6 + \'Build Financial Models\' button (specifically).

15. Paste prompts verbatim.

16. Claude creates new sheets: IS, BS, CF, audit using ONLY formulas.

17. Revenue separated into price × volume where product data exists.

18. Fixed and variable costs distinguished where reasonable.

19. Run \'Debug My Formulas.\' Review audit sheet. Examine returned formula list.

**Audit Pass Required**

-   Revenue calculated as price × volume.

-   Net income flows correctly to equity AND cash flow.

-   Balanced balance sheet.

-   Reconciling cash flow.

-   No circular references, no missed link cells, no hardcoded values in forecast areas.

**Stage 6 --- DCF Valuation**

Why critical: small mistakes mislead leadership. Wrong cash flow, forgotten terminal value discount, sensitivities not referencing DCF output --- all distort decision-making.

**DCF Sheet Must Have**

-   Free cash flow defined as CFO - capex from CF sheet.

-   Cash flows discounted using assumptions WACC.

-   Gordon growth terminal value calculated AND discounted correctly.

-   Enterprise value, equity value, value per share (assume 1M shares default).

-   Scenario toggle: base / upside / downside (adjust revenue growth, gross margin, WACC).

-   Sensitivity for revenue growth, WACC, gross margin (±10% / ±20%) directly linked to DCF output.

-   Top 5 value drivers ranked by NPV impact.

-   Historical sheets remain untouched.

**Stage 7 --- 13-Week Cash Forecast**

Why critical: executives don\'t just see risk. They see cash. Without simplified dynamic cash forecast, liquidity risk stays abstract, scenarios feel unrealistic, leadership engagement drops.

**What to Build**

-   New \'rolling_cash\' sheet.

-   Cash flows spread weekly using formulas.

-   Incorporate ONE driver cell.

-   Generate simple line chart.

-   Add basic liquidity alert if cash falls below covenant threshold.

**Four Verification Checks**

20. Driver updates cache.

21. Chart moves.

22. Alert triggers correctly.

23. No formula errors.

**Stage 8 --- CFO Memo (Presentation Discipline)**

Why critical: even the most rigorous model loses influence if poorly communicated. Weak tone, missing citations, unclear recommendations derail approvals.

**One-Page Memo Specs**

-   Under 400 words.

-   Four labeled sections: key_ask, options, drivers_and_sensitivity, recommendation.

-   Exact cell references like \'DCF!B28.\'

-   Saved to deliverables sheet.

-   Tone reads like executive communication, not explanation.

-   Recommendation begins with \'Recommend.\'

-   Approved only when numbers match exactly, tone is decisive, recommendation is explicit.

**Stage 9 --- Contract Risk Extraction**

Why critical: contracts hide payment clauses, termination triggers, covenant thresholds often never in forecasts. Missing a clause leads to liquidity shortfalls or covenant breaches.

**contracts_mapped Table Must Have**

-   One row per contract.

-   Contract ID, next payment timing, annual commitment, termination notice days, risk flag (low/medium/high), concise model note explaining forecast implications.

-   12-month risks clearly flagged.

-   Source sheets NOT modified.

**End State**

Top 1% financial model: structured, auditable, defensible. Setup takes effort. After: every cycle becomes a workflow execution rather than a from-scratch rebuild.

**Source**

How to use Claude For Finance Better Than 99% of People by Luke Finance --- <https://www.youtube.com/watch?v=qLDwThdc3WQ>
