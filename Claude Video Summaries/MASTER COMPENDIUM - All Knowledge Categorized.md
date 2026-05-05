**MASTER COMPENDIUM**

*Claude, Code, Cowork, RAG, Finance, Agentic OS & AI Agents*

**Cross-Categorized Knowledge from 70+ Videos**

Setup • Skills • RAG • Workflows • Agents • Finance • Business • Auto-Research • Multi-Modal

*V3 Update --- May 2026 (Adds Agentic OS, Auto-Research, RAG Levels, Finance, Training Material)*

**V3 Update Summary**

This master compendium now reflects 55+ individual documents covering 70+ source videos. Major additions in V3:

-   RAG levels --- Chase AI\'s 7-level hierarchy from auto-memory to agentic RAG.

-   Karpathy auto-research as a new work primitive --- covered across 5 separate angles.

-   7-layer Agentic OS architecture (AI Daily Brief / Newfar Gaspar).

-   Karpathy LLM Wiki pattern (Nate Herk implementation).

-   Boris\'s private lesson on Cowork (creator\'s own best practices).

-   6-hour Vibe Coding course (Antigravity + Gemini 3.1).

-   13_Training_Material_Non_Claude/ folder for general analysis methodology (Excel masterclasses, Agent Factory podcast, Saraev playlist) used to train Claude.

**Folder Structure (Final)**

  ----------------------------------------------- --------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------
  **Folder**                                      **Doc Count**   **Focus**
  00_Aggregate_Multi-Video_Summaries              3               11-video, 7-video aggregates + Boris private lesson
  01_Agentic_OS_and_Architecture                  10              Simon Scrapes, Karpathy Auto-Research, Skill Systems, Custom OS, RAG levels, Karpathy Wiki, Karpathy on No Priors, Agent Loops, Greg Isenberg, Personal OS
  02_Skills_Plugins_Tools                         4               Top 10, 10 AI Skills, 15 Cowork, Skills Full Course
  03_Cowork_Setup_and_Workflows                   1               Workflow Automation Guide
  04_Business_and_Notion                          2               Code for Business, Claude+Notion System
  05_Knowledge_Tools_Obsidian_Notion              2               Obsidian+Claude (Greg/Vin), AI Tools for Obsidian
  06_Prompt_Engineering_and_Best_Practices        1               God-Mode (8 cheating techniques)
  07_n8n_Automation                               2               36-min, 6-hour course
  08_Full_Courses                                 4               AI Agents 2hr, Build & Sell 10hr, Code Advanced 3hr, Vibe Coding 6hr
  09_Design_and_Visual                            1               Designing With AI
  10_AI_Master_Playlist_Claude_Full_Course_2026   9               Beginner-to-advanced playlist
  11_Office_Excel_Productivity                    1               Cowork × Excel reference
  12_Finance_and_FPnA                             9               AI Finance Team, Auto-Dashboard, 9-Stage, Reusable Workflow, 5-Stage Analysis, Forecasting, Banker DCF, Auto Research
  13_Training_Material_Non_Claude (NEW)           4               Agent Factory Podcast, Excel Masterclass, Excel Dashboards, Saraev 36-video playlist
  TOP LEVEL                                       2               MASTER COMPENDIUM, OPERATIONALIZED 90-DAY PLAN
  ----------------------------------------------- --------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------

**Master Topic Index (V3)**

  --------------------------------------------------- -----------------------------------------------------------------------
  **Topic**                                           **Folder Section**
  Choosing the right Claude model                     Playlist (10), section 1 of compendium
  Cowork setup from zero                              03 + 11-video aggregate (00) + Section 2
  Agentic OS architecture (9 layers, Simon Scrapes)   01
  Personal Agentic OS (7 layers, AI Daily Brief)      01 NEW
  Custom Agentic OS (3 steps, Chase AI)               01
  7 Levels of Claude Code & RAG                       01 NEW (Chase AI)
  Karpathy LLM Wiki                                   01 NEW (Nate Herk + sboNwYmH3AY)
  Karpathy Auto-Research                              01 (4Cb_l2LJAW8 standalone + qb90PPbAWz4 + nt9j1k2IhUY + kwSVtQ7dziU)
  Skills (creating, using, sharing)                   02 (4 docs)
  Skill Systems (chaining)                            01 (Simon Scrapes Massive Upgrade)
  Sub-agents & Agent Teams                            00 + 08
  Prompt engineering                                  06 (God-Mode)
  Memory & context                                    01 (Simon, AI Daily Brief, Karpathy Wiki) + 05
  Multi-agent orchestration                           08
  Self-improving systems                              01 (Karpathy Auto-Research family)
  Notion integration                                  04
  Obsidian integration                                05
  Excel & spreadsheets                                11 + 13 training material
  Design workflows (Figma)                            09
  n8n automation                                      07
  Vibe coding                                         08 (6hr course)
  Business deployment                                 04
  Selling Claude services                             08 (Build & Sell)
  Finance & FP&A                                      12 (8 docs)
  Banker\'s DCF critique                              12 (rareliquid)
  Boris\'s own best practices                         00 (private lesson)
  Comparison: Claude vs others                        Playlist 07/08/09 + Boris lesson
  Training material (non-Claude)                      13 (Agent Factory, Excel, Saraev playlist)
  --------------------------------------------------- -----------------------------------------------------------------------

**Section 25 --- RAG Levels (Chase AI\'s Hierarchy)**

From Level 1 (auto-memory) to Level 7 (agentic RAG with multimodal). Where you should be depends on volume and cost-benefit.

  ----------------------------- -------------------------------------------------------------------------------------- -------------------------------------------------------------------------
  **Level**                     **Approach**                                                                           **When to Use**
  1\. Auto-Memory               Native Claude Code memory.md files                                                     If you\'ve never edited CLAUDE.md --- start here, but move past quickly
  2\. CLAUDE.md                 Single instruction file injected on every prompt                                       Universal --- but resist bloating; less is more
  3\. State Files               Multiple markdown files for specific aspects (project, requirements, roadmap, state)   Single project with growing complexity
  4\. Obsidian (99% Solution)   Markdown vault with raw → wiki → output structure                                      Most people\'s endpoint. Start here for any non-trivial knowledge
  5\. Naive RAG                 Embedding model + vector DB + chunking                                                 Skip --- most \'RAG products\' are this; ineffective
  6\. Graph RAG (LightRAG)      Entities + relationships + hybrid vector/graph queries                                 When Obsidian breaks --- needs relationship queries
  7\. Agentic RAG               Multimodal + production pipelines + intelligent routing                                Production teams with multi-modal data and many users
  ----------------------------- -------------------------------------------------------------------------------------- -------------------------------------------------------------------------

**The Critical Insight**

> *Most of you are fine with Obsidian (Level 4). You don\'t need graph RAG. You don\'t need RAG in general. Try Obsidian first. Only escalate when you actually hit a wall.*

**Section 26 --- Auto-Research as a Work Primitive**

Karpathy\'s auto-research released March 7. Becomes a primitive --- not just an ML pattern but a general work pattern.

**The Universal Pattern**

1.  Set a clear objective metric (val_BPB, reply rate, conversion rate, click-through, NPV).

2.  Define what changes (the variable to vary --- code, copy, layout, pricing, etc.).

3.  Set fast iteration loop (5 min, 4 hour, daily --- depends on metric speed).

4.  Agent proposes change, makes it, runs experiment, reads result.

5.  If improved → keep, commit. If not → discard, revert.

6.  Loop. Knowledge accumulates in resources.md or learnings.md.

**The 5 Requirements For Auto-Research to Work**

-   Score --- objective metric. Subjective metrics need proxies.

-   Fast iteration --- bad attempts waste minutes, not weeks.

-   API or programmatic access to deploy changes.

-   Bounded action space.

-   Cheap retry cost.

**10 Business Use Cases (From Greg Isenberg\'s Episode)**

-   Niche agent in a box (Amazon listings, realtor email, SaaS pricing).

-   AB testing for marketing (landing pages, ads, copy).

-   Research as a service (competitor reports, due diligence).

-   Optimize button inside your own product.

-   Optimization agency (we run more tests than anyone).

-   Auto-quant for trading ideas.

-   Always-on lead qualification.

-   Finance ops autopilot (invoice matching, expense exceptions).

-   Internal productivity lab for org.

-   Done-for-you research / DD shop.

**Auto-Research Loop Readiness Map (AI Daily Brief)**

  --------------------- ----------------------------------------------- ------------------------------------------------------------------
  **Iteration Speed**   **Evaluation Subjective**                       **Evaluation Automated**
  Seconds               ---                                             Code generation, ad bid optimization, algo trading, LLM training
  Hours-Days            Content moderation, A/B copy                    Supply chain routing
  Months                Therapy, political negotiation, long creative   ---
  --------------------- ----------------------------------------------- ------------------------------------------------------------------

**Section 27 --- The Loopy Era and Boris\'s 13 Production Rules**

From Greg Isenberg\'s interview with Boris (Cowork creator). Confirms what Karpathy said on No Priors --- the era of dictating to agents is here.

**The 13 Production Rules**

  ------------- -------------------------------------------------------------------------------------
  **Rule \#**   **Rule**
  1             Run tasks in parallel --- many tabs, switch between them
  2             5-10 Claude Code sessions in parallel --- terminal + web + iOS + Android
  3             Use Opus 4.5 with Thinking for everything --- counter-intuitively cheaper
  4             Team-shared CLAUDE.md, checked into git, contributed to weekly
  5             Tag \@claude on PRs to update CLAUDE.md (Claude Code GitHub action)
  6             Most sessions start in Plan Mode --- most underused feature
  7+            More tips covered in detail throughout video
  13            Give Claude a way to verify its output. Top 3: Opus + good CLAUDE.md + verification
  ------------- -------------------------------------------------------------------------------------

**Boris\'s Top 3 for Better Performance**

7.  Use Opus 4.5 with thinking --- always.

8.  Have a good CLAUDE.md.

9.  Give Claude a way to verify its output.

**Section 28 --- The Karpathy LLM Wiki Pattern**

Different from RAG. Just markdown files in a vault with structure. Free. No embedding model. No vector DB.

**Architecture**

-   vault/raw/ --- staging area, source documents.

-   vault/wiki/ --- structured Wikipedia-style articles + master index.

-   vault/output/ --- final deliverables.

-   CLAUDE.md --- explains structure to Claude.

**Why It Works**

-   Claude reads index → finds the right wiki entry.

-   Each entry has internal links --- backlinks act as \'soft\' RAG.

-   Token usage drops 95% vs flat-folder retrieval (per X user).

-   One X user: 383 scattered files + 100 meeting transcripts → compact wiki.

**vs Semantic RAG**

  ------------------------------------- ------------------------------------------
  **Karpathy Wiki**                     **Semantic RAG**
  Reads indexes + follows backlinks     Vector similarity search
  Markdown only --- free                Embedding model + DB + chunking pipeline
  Run lint to maintain                  Re-embed when things change
  Hundreds of pages with good indexes   Millions of documents
  ------------------------------------- ------------------------------------------

**Section 29 --- Personal Agentic OS (7 Layers)**

AI Daily Brief / Newfar\'s framework. Tool-, model-, harness-neutral. Build once, runs everywhere.

  ------------------ --------------------------- ------------------------------------------------------------------------------------------------------
  **Layer**          **Question Answered**       **How to Build**
  1\. Identity       Who are you? What rules?    Have AI interview you (15 questions). Don\'t write from scratch
  2\. Context        What you know               3-5 single-page focused files. Update as situation changes
  3\. Skills         How you work                Reusable instruction sets. \'When \[trigger\], do \[process\] using \[sources\], output \[format\]\'
  4\. Memory         What persists               Tool\'s auto-memory + dedicated specialized files. Audit periodically
  5\. Connections    How agent reaches systems   MCPs/CLI/APIs. Read-only first. Right access only after weeks of trust
  6\. Verification   How to know it\'s right     3-5 quick checks per task type. Periodic OS audit
  7\. Automations    What runs unattended        Only well-tested workflows. Drafts before sending. Always log
  ------------------ --------------------------- ------------------------------------------------------------------------------------------------------

**The Compounding Return**

> *Your first agent took a weekend. Your second built on top of this system takes an afternoon because it inherits everything. By your fifth, hours.*

**Section 30 --- Boris\'s Production Best Practices Summary**

Combining the 13 rules + Cowork lesson. The creator\'s own playbook.

**Multi-Tab Discipline**

-   3-10 sessions in parallel (terminal/web/iOS/Android).

-   \'Once Claude is making a plan, switch to next tab.\'

-   \'Once plan is good, the code is good.\'

-   Auto-accept after plan review.

**CLAUDE.md Discipline**

-   Team-shared. Checked into git.

-   Updated weekly by everyone.

-   \'When Claude does something incorrectly: add it.\'

-   Just a text file. No special format.

**Compound Engineering Pattern**

\@claude on PR/issue → CLAUDE.md auto-updates. Boris\'s prior life at Meta: kept spreadsheet of code review issues, wrote lint rules when same issue appeared 5x. Now: tag Claude, never have to point it out again.

**Verification Pattern**

> *As models get more intelligent, first-shot improves. But really, you want to give it a way to verify. Without verification, it\'s like a painter wearing a blindfold.*

**Updated Cross-Cutting Themes (V3)**

**Theme 16 --- RAG Is For Some, Not All**

Most operators don\'t need RAG. Obsidian (Karpathy wiki) is the 99% solution. Skip RAG until you actually hit a wall.

**Theme 17 --- Auto-Research Is the New Work Primitive**

Like spreadsheets and email before it. The pattern: clear metric + iteration loop + AI agent. Apply to anything with objective measurement.

**Theme 18 --- Multi-Tab is the New Multitasking**

Boris\'s confirmed pattern: 5-10 parallel agents. Plan in tab 1, switch to tab 2, plan, switch to tab 3, etc. Tend to your agents like a manager. Different mental model from \'go deep on one task.\'

**Theme 19 --- Context Engineering Is the New Prompt Engineering**

Three core strategies (Agent Factory):

-   Isolating --- pass only required data to each sub-agent.

-   Persisting --- retrieve memories by relevance and recency.

-   Compressing --- summarize before re-injecting.

**Theme 20 --- Verification Beats Confidence**

Across Boris\'s rules + Luke Finance\'s audit gates + general agent patterns: confidence without verification kills work. Always have agents verify their own output.

**Quick Reference Index --- All 55+ Documents**

**Top Level**

-   MASTER COMPENDIUM (this file)

-   OPERATIONALIZED IMPLEMENTATION 90-Day Plan

**00_Aggregate_Multi-Video_Summaries**

-   Claude Cowork and AI Agents - 11 Video Summaries

-   Claude Cowork & Business Automation - 7 Video Summaries

-   Boris Private Lesson - Cowork Creator (NEW)

**01_Agentic_OS_and_Architecture (10 docs)**

-   Creating Your Own Agentic OS - Simon Scrapes

-   Karpathy Autoresearch - Self-Improving AI - Nick Saraev

-   Skill Systems Massive Upgrade - Simon Scrapes

-   Custom Claude Code Agentic OS - Chase AI

-   7 Levels of Claude Code and RAG - Chase AI (NEW)

-   Karpathy LLM Wiki - 10x Claude Code - Nate Herk (NEW)

-   Karpathy on No Priors - Code Agents Auto-Research (NEW)

-   Agent Loops Future of Work - AI Daily Brief (NEW)

-   Karpathy Autoresearch 10 Business Ideas - Greg Isenberg (NEW)

-   Personal Agentic OS - 7 Layers - AI Daily Brief (NEW)

**02_Skills_Plugins_Tools (4 docs)**

-   Top 10 Claude Code Skills Plugins CLIs - Chase AI

-   10 Claude AI Skills - Julia McCoy

-   15 Cowork Skills - Brock Mesarich

-   Claude Skills Full Course - Nick Saraev

**03_Cowork_Setup_and_Workflows (1)**

-   Cowork Full Workflow Automation Guide

**04_Business_and_Notion (2)**

-   Claude Code for Business - Daron Vener

-   The Claude + Notion System

**05_Knowledge_Tools_Obsidian_Notion (2)**

-   Obsidian + Claude Code - Greg Isenberg & Vin

-   Building AI Tools for Obsidian - Paul Dickson

**06_Prompt_Engineering (1)**

-   Claude God-Mode - 8 Cheating Techniques

**07_n8n_Automation (2)**

-   Master 80% of n8n in 36 Minutes

-   N8N Full Course 6 Hours - Nick Saraev

**08_Full_Courses (4 docs)**

-   Claude Code Advanced Full Course 3 Hours - Nick Saraev

-   AI Agents Full Course 2 Hours - Nick Saraev

-   Build & Sell with Claude Code - 10+ Hour Course Reference

-   Vibe Coding Full Course 6 Hours - Nick Saraev (NEW)

**09_Design_and_Visual (1)**

-   Designing With AI - Claude Codex Figma - UI Collective

**10_AI_Master_Playlist_Claude_Full_Course_2026 (9 docs)**

Beginner-to-advanced playlist (per-video docs 01-11, with 03/04 covered in earlier categories)

**11_Office_Excel_Productivity (1)**

-   Claude Cowork x Excel - Full Walkthrough Reference

**12_Finance_and_FPnA (9 docs)**

-   AI Finance Team With Claude - Luke Finance

-   Automate Financial Dashboards - Luke Finance

-   Reusable Finance Workflow in Claude 2 - Luke Finance

-   Use Claude For Finance Better Than 99% - 9 Stages

-   Cowork For Finance Better Than 99% - 5 Setups

-   Automate Financial Forecasting - Luke Finance

-   5-Stage Financial Analysis - Luke Finance

-   Ex-JPM Banker Tests Claude DCF - rareliquid

-   Auto Research with Claude - Jason Edward (NEW)

**13_Training_Material_Non_Claude (4 docs, NEW FOLDER)**

-   Agent Factory Podcast Summary - Google Cloud Tech (21 episodes)

-   Excel Dashboard Masterclass Summary - Data With Decision (14 videos)

-   Excel Dashboard Projects Summary - Lean Excel Solutions

-   Nick Saraev 36-Video Playlist Summary
