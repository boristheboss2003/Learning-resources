**Ex-JPM Banker Tests Claude With Building a DCF**

*rareliquid --- Real Banker\'s Honest Critique of Claude in Excel*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=omNOAmQDcqU

*Prepared: May 2026*

**Premise**

Host: ex-JPMorgan investment banker, runs the rareliquid YouTube channel. Has built hundreds of models manually in Excel. Tests Claude in Excel by building a Google DCF using same assumptions as a recent manual DCF (built \~2 months prior in January 2026), then compares outputs and discusses pros/cons of using Claude for banker work.

**Setup**

1.  Download Claude as Excel plugin (search \'Claude Excel for Microsoft\' or \'for Apple\').

2.  Install. Plugin appears as side panel similar to ChatGPT/Claude chat.

3.  Bring in historical financials and future estimates that powered prior manual Google DCF.

4.  Use same figures to build DCF with Claude. Compare both.

**Initial Prompt**

> *I\'ve included historical and estimated projections for Google in the tabs. Build me a 5-year DCF model using these figures and assumptions as needed. Pull in any extra information you need from your own sources to build out the rest of the DCF.*

**Claude\'s Plan**

Plan Claude returned before executing:

5.  Build a new DCF sheet.

6.  Create key assumptions section.

7.  WACC inputs section.

8.  WACC calculation.

9.  Unlevered free cash flow projections.

10. Terminal value (BOTH perpetuity growth and exit multiple methods).

11. Enterprise value to equity value bridge.

12. Sensitivity table.

**Honest First Take from Banker**

> *This plan is fairly specified for a financial model. If I were learning DCF before working in finance, I could actually learn how to build a DCF just from reading this plan.*

**Detailed Audit of Claude\'s DCF**

**Risk-Free Rate**

Claude used 4.3% (10-year Treasury yield, March 2026). Verified accurate at 4.283%.

**Equity Risk Premium**

Claude used 4.6%. Banker checked Damodaran (NYU professor publishing data publicly): actual ERP was 4.38%. Slightly off but not crazy.

**Levered Beta**

Claude used 1.05 from Google/Yahoo. Banker has FactSet access. Compared: identical at 1.05.

**Cost of Debt**

Claude used 3.5% (Alphabet weighted average coupon on outstanding notes). Banker had used 4.07% (quick and dirty method). Claude\'s 3.5% probably more accurate.

**Tax Rate**

Claude used 17% effective tax rate from 2024. Banker used 16.89%. Very close.

**Debt vs Total Capital**

> *This is hardcoded at 2%. Big mistake in a model. You should NOT hardcode this.*

Banker would calculate from total debt and equity values rather than hardcoding.

**Terminal Growth Rate**

Claude used 3% (always high). Banker prefers 2.5% as more conservative/accurate.

**Date Pull Issues**

> *Claude pulled from 2024 10-K even though 2025 10-K had been published. That\'s a much bigger mistake.*

Claude initially pulled 2025 figures from 10-Q (March 2026 quarterly), not 10-K. Should have used latest 10-K.

**Color Coding**

-   Should use green for cell references from another sheet.

-   Should use purple for cross-sheet references.

-   Claude inconsistent on color coding.

**Real Errors Found**

  -------------------------------------------------------------------- ----------------------------------------------------
  **Error**                                                            **Should Be**
  Hardcoded 2% debt/total capital                                      Calculate from total debt and equity
  3% terminal growth                                                   2.5% (more conservative)
  Pulled from 2024 10-K                                                Should use latest 10-Q or 10-K
  Inconsistent color coding                                            Green for cross-sheet, purple for from-other-sheet
  EBIT inconsistent with DCF (used 391 in one place, 352 in another)   Same EBIT across DCF and exit multiple
  Sensitivity built with formulas instead of Excel data tables         Use Excel\'s What-If Analysis
  -------------------------------------------------------------------- ----------------------------------------------------

**How Claude Handled the Correction Prompt**

Banker added an \'errors\' column with corrections, then prompted: \'I\'ve added errors I found in column K. Make revisions based on the errors.\'

Claude updated equity risk premium to 4.38% (correct), recalculated debt/total capital from actual figures (correct, 0.54% close to banker\'s), updated terminal growth to 2.5%.

Still pulled from Q3 2025 10-Q rather than 2025 10-K. Should have been more specific in correction prompt.

Sensitivity tables Claude said: \'These data tables require specific cell references and manual setup that I can\'t fully automate. So I\'ll leave it as formula-based.\'

**DCF Comparison**

  ------------------------------------- ---------------- ----------------
  **Method**                            **Claude DCF**   **Manual DCF**
  Implied share price (perpetuity)      175              202
  Implied share price (exit multiple)   400              ---
  ------------------------------------- ---------------- ----------------

Claude\'s DCF more conservative than manual. Cause: Claude pulled estimates straight from inputs. Manual DCF grew capex down over time as % of sales (Google\'s heavy AI capex now → assumes it normalizes).

**Pros and Cons (Banker\'s Honest Take)**

**Pros**

-   Built it FAST --- minutes vs hours.

-   Plan structure was reasonable.

-   WACC formula correct.

-   Terminal value calculation correct.

-   Free cash flow calculation correct.

-   Could be much more complicated with 50+ assumptions if specified.

**Cons**

-   Data sources unreliable --- pulled 2024 10-K when 2025 was available.

-   Color coding inconsistent across the model.

-   Hardcoded values where formulas should be (the 2% debt ratio).

-   Internal inconsistencies (different EBIT in different places).

-   Used up tokens fast --- barely prompted before hitting limit.

**Banker\'s Verdict on Industry Impact**

> *There will always be a need for analysts and associates. VPs and MDs are not going to want to even prompt Excel to build a DCF. Their role is to maintain client relationships and run deal processes --- not build models.*

Even with massive automation, junior bankers will work the same hours but with more volume. Just like sales/trading automation didn\'t eliminate the function --- but reduced headcount.

**Advice for Future Bankers**

-   Play around heavily with Excel AI capabilities.

-   Have it build models for you. Then double-check.

-   Learn how to build everything from scratch as well.

-   Use voice-to-text (Whisper) for fast prompting.

-   Companies are starting to provide templates that AI uses to build models in YOUR format --- instead of stock format.

**Source**

Ex-JPM Banker Tests Claude With Building a DCF in Excel by rareliquid --- <https://www.youtube.com/watch?v=omNOAmQDcqU>
