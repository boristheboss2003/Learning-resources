**OPERATIONALIZED IMPLEMENTATION (V3)**

*From Knowledge to Working System --- A 90-Day Plan*

**Adds Auto-Research Loops + RAG Levels + Personal Agentic OS**

*V3 --- May 2026*

**V3 What\'s New**

This version adds three things to the V2 plan:

1.  Phase 6 now includes Auto-Research as a deployable pattern --- for any optimization with a clear metric and an API.

2.  Phase 3 (architecture) now references the 7-Layer Personal Agentic OS framework as the canonical reference.

3.  Phase 1 setup now mentions the RAG levels (start at Level 4 Obsidian, not Level 1).

**V3 Phase 0 --- Decisions (Day 0, 60 min)**

Same as V2 but with two new decisions:

**New Decision 6 --- Knowledge Base RAG Level**

  ---------------------------------------------------- -------------------------------------------------------
  **You\'re at\...**                                   **Recommended Level**
  Brand new --- no notes/docs yet                      Level 1-2 (auto-memory + CLAUDE.md). Don\'t overthink
  You take notes occasionally                          Level 3 (state files) or Level 4 (Obsidian)
  You have a personal second brain                     Level 4 (Obsidian) --- start here
  You manage thousands of documents for clients/team   Level 6 (LightRAG) --- but only after Obsidian fails
  Production team needs multi-modal                    Level 7 (Agentic RAG) --- likely overkill
  ---------------------------------------------------- -------------------------------------------------------

**New Decision 7 --- Auto-Research Pilot**

Pick ONE optimization target with: clear metric + fast feedback + API access. This becomes Phase 6 deliverable.

-   If marketing --- cold email reply rate, landing page conversion, ad CTR.

-   If finance --- forecast accuracy month-over-month.

-   If sales --- discovery-to-proposal conversion.

-   If content --- newsletter open rate, video CTR.

-   Revisit at Phase 6. Skip if no clear use case.

**V3 Phase 3 --- Memory & Architecture (Weeks 4-5)**

Now grounded in the 7-Layer Personal Agentic OS framework. For both tracks:

  ------------------ --------------------------------------------------------------------------
  **Layer**          **What to Build in Week 4-5**
  1\. Identity       Have AI interview you (15 questions). Build identity.md / claude.md
  2\. Context        3-5 single-page focused files (my-team, my-product, my-customers, etc.)
  3\. Skills         5-7 from your Phase 2 skills, now structured
  4\. Memory         Tool\'s auto-memory + dedicated specialized files
  5\. Connections    Read-only first. Gmail/Calendar/Drive baseline. Add Notion if applicable
  6\. Verification   3-5 quick checks per task type. Schedule monthly OS audit
  7\. Automations    Defer until Phase 5 --- only after layers 1-6 are stable
  ------------------ --------------------------------------------------------------------------

**Karpathy LLM Wiki Track (Optional)**

If you have lots of accumulated notes/research/transcripts, run the Karpathy Wiki setup as a parallel exercise:

4.  Create vault folder. Set up raw/ + wiki/ + output/ subfolders.

5.  Drop existing notes/transcripts into raw/.

6.  Tell Claude Code: \'Implement Karpathy\'s LLM wiki idea. Ingest raw/ files into wiki structure.\'

7.  Result: searchable knowledge graph in markdown. Free. Token-efficient.

**V3 Phase 5 --- Automation (Weeks 8-9)**

Now references Boris\'s /loop command for OpenClaw and recurring tasks.

**Boris\'s Production Recipes**

-   \'/loop babysit all my PRs, autofix build issues\' --- every time comments come in.

-   \'/loop every morning using Slack MCP, give me summary of top posts I was tagged in.\'

-   OpenClaw heartbeat = core loop firing every 30 minutes by default.

**V3 Phase 6 --- Auto-Research Pilot (Weeks 10-11)**

New phase: deploy ONE auto-research workflow on the optimization target chosen in Phase 0.

**Auto-Research Setup**

8.  Clone Karpathy\'s auto-research repo (auto-research on GitHub).

9.  Adapt the program.md to your use case (don\'t tweak the agent code; tweak the instructions).

10. Set evaluation metric (reply rate, conversion, NPV, accuracy, etc.).

11. Get API key for whatever system has the metric (Instantly for cold email, Mixpanel for analytics, etc.).

12. Set GitHub Action cron to run loop every N hours.

13. Slack webhook for notifications when new variants tested.

14. Let it run for 4 weeks. Compare baseline vs winners.

**Cost Reality**

-   4-hour loop on moderate cold email: \~\$5-10/day in API.

-   5-min loop (Karpathy speed): only if you have volume to support it.

-   After 500-1,000 runs, consolidate learnings to prevent unbounded growth.

**When NOT to Use Auto-Research**

-   Slow feedback loops (weeks per measurement).

-   Subjective metrics without good proxies.

-   No API access.

**V3 Phase 7 --- Productize (Weeks 12-13, Optional)**

Same V2 framework. New emphasis: auto-research pilots are some of the highest-margin services to sell. \'We run more tests than anyone else\' is a strong pitch. Tier as \$5K starter / \$30K standard / \$75K+ premium.

**V3 Reference Docs to Re-Read**

  ---------------------------------------------- ---------------------------------------------------------------------------
  **When You Need\...**                          **Read**
  RAG decision framework                         7 Levels of Claude Code and RAG - Chase AI
  Karpathy LLM wiki setup                        Karpathy LLM Wiki - 10x Claude Code - Nate Herk
  Auto-research deployment                       Karpathy Autoresearch (Saraev) + Greg Isenberg + AI Daily Brief versions
  7-layer Agentic OS framework                   Personal Agentic OS - 7 Layers - AI Daily Brief
  Boris\'s production rules                      Boris Private Lesson - Cowork Creator (in 00 folder)
  Vibe coding from scratch                       Vibe Coding Full Course 6 Hours - Nick Saraev
  When agents are overused                       Karpathy on No Priors podcast
  Skill systems vs isolated skills               Skill Systems Massive Upgrade - Simon Scrapes
  Train Claude on general analysis methodology   13_Training_Material_Non_Claude folder (Excel masterclass, Agent Factory)
  ---------------------------------------------- ---------------------------------------------------------------------------

**V3 Operating Principles**

> *Setup is everything. Five minutes of folder structure and MD files saves hours every week.*
>
> *Use projects for anything you do more than once. Memory is what separates Cowork from every other AI tool.*
>
> *Scheduled tasks are the real unlock --- moving from using AI to having AI work for you.*
>
> *Folder structure determines output quality. Bad structure = AI slop.*
>
> *Apply 80/20 --- Cowork handles 80% of execution; keep 20% under human judgment.*
>
> *99% failure mode is treating Cowork as a chatbot. Delegation, not conversation.*
>
> *FINANCE: every formula traceable. Every recovery has a basis. Every recommendation defensible.*
>
> *Build skills designed for reuse from day one. Skill systems beat isolated skills 10× over.*
>
> *If you have a standard operating procedure, you have a skill. Copy it, feed to agent, build.*
>
> *RAG is for some, not all. Start with Obsidian. Don\'t skip to graph RAG because it sounds sophisticated.*
>
> *Auto-research is the new work primitive. Anywhere you have a metric, an API, and fast iteration --- apply it.*
>
> *Multi-tab is the new multitasking. Plan in tab 1. Switch to tab 2. Tend your agents like a manager.*
>
> *Verification beats confidence. Always have agents verify their own output.*
