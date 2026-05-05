**I Built an Entire AI Finance Team With Claude**

*Luke Finance --- Five Specialist Roles + Coordinator + Presentation Builder*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=BhKdOfKPSaY

*Prepared: May 2026*

**Premise**

> *Using different prompts and chats for different financial outputs while trying to keep the context of your project aligned will break down fast. The outputs don\'t tie together, the logic will drift, and the moment you need to reuse it, you\'re rebuilding everything from scratch.*

This video shows how to build a complete AI finance team that works both independently and together while maintaining full context across the entire workflow. The system doesn\'t replace your role --- it automates execution so you stay focused on decision-making.

**The Five Roles**

  ------------------------------ ---------------------------------------------------------------------------
  **Role**                       **Responsibility**
  Revenue Operations Manager     Owns the revenue picture --- MRR, ARR, churn, customer growth, plan mix
  Financial Control Manager      Validates financial activity, classifies transactions, builds monthly P&L
  FP&A Manager                   Forecasts using outputs from RevOps and Financial Control
  Reporting & Strategy Manager   Synthesizes everything into executive reports
  Workflow Coordinator           Orchestrates all four roles in strict sequence
  ------------------------------ ---------------------------------------------------------------------------

**Folder Structure**

One main folder called Finance Team. Inside it, six subfolders:

-   revenue_ops/ --- instruction file (revenue_ops.md), inputs/, outputs/.

-   financial_control/ --- fc_manager.md + inputs/outputs.

-   fpna/ --- fpna_manager.md + inputs/outputs.

-   reporting/ --- reporting_manager.md + inputs/outputs.

-   shared/ --- three files every role reads.

-   PPT_builder.md sits at top level alongside coordinator.

**Three Shared Files**

  -------------------- ---------------------------------------------------------------------------------------------------------------
  **File**             **Contents**
  company_context.md   Business description (SaaS company Flow Sync), pricing model, customer segments, growth stage
  assumptions.md       Growth rates, churn targets, hiring plans, cost behaviors. Change once → next forecast picks up automatically
  calendar.csv         Single source of truth for months/quarters. When one role says Q1, matches every other role
  -------------------- ---------------------------------------------------------------------------------------------------------------

**Role 1: Revenue Operations Manager**

Build first because everything downstream depends on it.

**revenue_ops.md Specifies**

-   What the role is responsible for.

-   Three input files: customer_data.csv, subscription_data.csv, pricing_plans.csv.

-   Calculations to run: MRR, ARR, churn rate, customer growth, plan mix breakdown.

-   Output: mrr_summary.csv saved to BOTH its own outputs/ AND fpna/inputs/.

**Run Prompt**

> *Act as the revenue operations manager and follow the instructions inside revenue_ops.md.*

Short prompt because all logic is in the .md file. Claude reads role definition → scans input folder → confirms files → loads data → builds analysis. No clarifying questions needed.

**Role 2: Financial Control Manager**

Validates financial activity. While RevOps focuses on what customers paid, Financial Control focuses on what was actually recorded.

**Functions**

-   Classifies every transaction as revenue, expense, or refund.

-   Validates revenue against invoices.

-   Aggregates everything into monthly P&L view.

**Outputs**

financial_summary.csv and expense_summary.csv saved to own outputs/ AND fpna/inputs/ AND reporting/inputs/.

**Role 3: FP&A Manager (The Handoff Pattern Pays Off)**

Unlike first two roles, FP&A doesn\'t work with raw business data. Inputs are outputs from previous roles:

-   MRR summary from RevOps.

-   Expense summary from Financial Control.

-   Assumptions file from shared folder.

Projects the next 12 months. Saves to FP&A outputs/ and reporting/inputs/.

**Role 4: Reporting & Strategy Manager**

Loads financial summary + forecast summary + company context. Generates executive_report.md structured into five sections. Saves to reporting outputs/ AND shared/ so the whole system has access.

**Role 5: Workflow Coordinator**

full_finance_workflow.md tells Claude to operate as coordinator instead of single role. Manages entire sequence.

**Coordinator Strict Rules**

-   Cannot skip a role.

-   Cannot proceed before previous output is saved.

-   Cannot reinvent the logic.

Without strictness, Claude improvises and shortcuts validation --- defeating the point of defined roles.

**Live Demo Flow**

1.  Update assumptions.md to a more aggressive growth scenario (higher growth, lower churn, expanded hiring).

2.  Refresh subscription_data with stronger recent performance.

3.  Open FRESH Claude Cowork session in finance team folder (no leftover context).

4.  Prompt: \'Act as finance workflow coordinator and follow full_finance_workflow.md.\'

5.  Coordinator reads file → scans folder → loads every role\'s instructions → checks data sets.

6.  Maps full workflow BEFORE executing.

7.  RevOps → Financial Control → FP&A → Reporting in sequence.

8.  Final verification confirms every output exists in required location.

> *From a single high-level instruction, the entire team has executed. That\'s the difference between using Claude as a tool and using it as a coordinated finance system.*

**PPT Builder --- From Files to Presentation**

PPT_builder.md sits at top of finance team folder alongside coordinator.

**How It Works**

-   Loads the presentation file.

-   PPTX skill pulls every output from the team.

-   Builds deck in one pass.

-   Converts slides to images, runs visual check for layout/spacing/contrast/alignment.

-   Fixes issues before saving.

-   Saves PPTX to reporting/outputs/ + markdown version alongside for easy editing.

**System Architecture Summary**

-   5 role files (4 specialists + coordinator).

-   Shared folder with company_context.md + assumptions.md + calendar.csv.

-   Coordinator (full_finance_workflow.md) runs end to end.

-   PPT builder turns output into a deck.

-   Single prompt triggers everything.

**Key Insight --- Your Role Shifts**

> *You\'re no longer the one extracting data, building the model, or formatting slides. You become the person looking at the executive report and deciding whether the recommendations are right for the business. The team handles execution. Your judgment makes the output worth presenting.*

**Source**

I Built an Entire AI Finance Team With Claude by Luke Finance --- <https://www.youtube.com/watch?v=BhKdOfKPSaY>
