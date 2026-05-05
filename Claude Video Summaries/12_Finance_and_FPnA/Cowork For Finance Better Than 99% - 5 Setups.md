**Use Claude Cowork For Finance Better Than 99% of People**

*Luke Finance --- 5 Setups That Build On Each Other*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=nT9FboXdfrM

*Prepared: May 2026*

**Premise**

Cowork takes you from prompting for outputs to building automated systems that run end-to-end without manual intervention. Five concrete setups, each building on the previous one --- moving from isolated tasks to a fully integrated finance system.

**Tip 1 --- Turn Gmail Into a Finance Intelligence Feed**

Your inbox already contains signals about cash flow, risk, operational pressure --- buried in unstructured messages. Vendor payment reminders, client delay notices, unusual invoice amounts.

**Setup**

1.  Open Cowork. Click connectors \'+\' icon near input area.

2.  Select Gmail. Authorize the account.

3.  Once connected, start new Cowork task with Gmail in context.

4.  Run prompt: \'Analyze last 7 days. Group vendor and client communications separately. Flag overdue payments, unusual amounts, urgent internal requests. Filter out everything irrelevant.\'

**What You Get**

-   Executive summary quantifying total accounts payable exposure, confirmed incoming cash, financial context.

-   Vendor table: invoice numbers, amounts, due dates, risk levels (Vendor B flagged high-risk, 10 days overdue).

-   Receivables: confirmed payments, partial payments, delayed payments separated.

-   Prioritized action plan: pay vendor B immediately, validate vendor C invoice, follow up with client B.

-   Filtered out: newsletters, non-financial emails (visible filtering logic).

**Tip 2 --- Combine Gmail + Calendar = CFO Briefing With Remote Execution**

Daily CFO briefing combining email and calendar. Cross-reference. Most preparation happens in your head --- that\'s where things fall apart.

**Setup**

5.  Click \'+\' near input. Connect both Gmail AND Google Calendar.

6.  Start new Cowork task with both available in context.

7.  Prompt: \'Create daily finance briefing by cross-referencing emails and calendar events. Identify urgent issues and financial risks. Surface upcoming meetings and what needs to be prepared for each. Link relevant emails directly to the meetings they relate to.\'

**Output Connects Everything**

-   Daily snapshot: meeting count, finance email count, urgent items.

-   Cash flow snapshot: confirmed inflows (\$20K), upcoming outflows (\$42K), client B delay flagged as risk.

-   CFO email asking for cash flow check tied directly to 2:30 PM cash flow review meeting.

-   Each meeting has specific preparation steps backed by exact financial context.

**Dispatch --- Trigger From Phone**

Cowork has dispatch mode --- trigger tasks from phone while execution happens on main system.

Demo: open Cowork on phone. \'Find March_CashFlow file in downloads, analyze position, give me a short summary I can send to CFO.\'

Don\'t re-explain context --- Claude has full briefing context. On phone: acknowledges immediately. On desktop: locates file, recognizes Excel, runs analysis. Output appears in BOTH places. Phone shows concise message version. Desktop shows full sectioned summary.

**Tip 3 --- Skills Inside Structured Finance Project**

Up until now, every task required re-writing prompts and re-explaining structure. Skills change that. Built once → bring new data → Claude executes.

**Setup**

8.  Sidebar → Projects → Start From Scratch.

9.  Name: \'monthly_finance_analysis.\'

10. Choose project location → finance workspace folder.

11. Find Instructions section. Paste analysis framework: \'Act as a financial analyst. Always identify key financial risks. Highlight anomalies and unusual changes. Focus on key drivers behind performance. Explain results in concise, structured format. Prioritize business impact over raw numbers.\'

12. Save.

13. Drop Q1 budget vs actual file into project folder.

14. New task → type {backslash}finance:variance-analysis.

**Three Configuration Questions Pop Up**

-   What type of output do you want?

-   What should actuals be compared against?

-   Which variance drivers matter most?

Same way a real analyst would clarify the brief before doing the work.

**What Cowork Builds**

-   Q1 2026 P&L variance summary with budget vs actual, variance amounts, percentages, favorable/unfavorable flags.

-   Variance decomposition.

-   Waterfall bridge from budget to actual.

-   Narrative explanations per line item.

-   Threshold-based materiality flags.

-   All 134 formulas validated, zero errors.

**Tip 4 --- Automate Recurring Analysis With Scheduled Tasks**

Finance workflows are inherently recurring --- weekly cash flow reviews, monthly variance analysis, regular reporting cycles. Structure stays. Only data changes.

**Setup**

15. Inside monthly_finance_analysis project, find Schedule Tasks. Click \'New Task.\'

16. Name: \'weekly-variance-analysis.\'

17. Description: \'Run weekly variance analysis on financial data and highlight key performance drivers.\'

18. Prompt: \'Analyze latest financial data in this folder. Compare actuals vs budget and prior period if available. Identify key variance drivers, anomalies, financial risks. Provide concise structured summary suitable for management review.\'

19. Frequency: weekly. Day: Monday. Time: 9:00 AM.

20. More options → Folder to work in → finance workspace folder.

21. Save.

**What Happens Every Monday at 9 AM**

-   Claude enters workspace.

-   Finds latest budget vs actuals file.

-   Runs full variance analysis using same structured logic.

-   Generates management-ready output.

Same pattern for monthly reporting, cash flow monitoring, budget vs forecast tracking, KPI dashboards --- anything recurring.

**Tip 5 --- End-to-End Pipeline (Data to Presentation)**

Going from raw financial data to finished PowerPoint in one continuous run. Removes the manual slide-building step entirely.

**Setup**

22. Open monthly_finance_analysis project. Start new task.

23. If data needs restructuring: \'Recreate clean financial consolidation file based on available data with proper structure, correct formulas, clear labeling, updated periods.\'

24. Once built, give presentation prompt: \'Prepare financial review presentation comparing current performance with previous period. Include company-level summary, key financial metrics, variance analysis, one slide per segment. Keep clear, structured, presentation-ready.\'

**What Cowork Does**

25. Reads Excel data.

26. Asks clarifying questions about entity structure and sheets.

27. Builds financial model layer (IS, BS, CF).

28. Validates 268 formulas with zero errors.

29. ONLY THEN moves into presentation generation.

30. Generates PPTX file.

31. Converts slides to images for visual QA.

32. Detects layout issues (spacing, alignment).

33. Fixes them automatically.

34. Regenerates the deck.

**Final Slide Structure**

-   Executive layer: revenue, gross profit, net income, margin.

-   Bridge view: budget to actual.

-   Drill into drivers: revenue, COGS, OpEx.

-   Closes with prioritized recommendations.

-   Numbers flow consistently from Excel through model into slides --- anchored to same data source. No manual copying. No reformatting.

**System Flow**

> *The inbox becomes an intelligence feed. The calendar adds context and timing. Project environment adds consistency. The scheduler removes manual triggering. The pipeline delivers finished outputs.*
>
> *Your role shifts from running the process to reviewing results and making decisions. The systems do execution. Your judgment makes the output useful.*

**Source**

How to use Claude Cowork For Finance Better than 99% of People by Luke Finance --- <https://www.youtube.com/watch?v=nT9FboXdfrM>
