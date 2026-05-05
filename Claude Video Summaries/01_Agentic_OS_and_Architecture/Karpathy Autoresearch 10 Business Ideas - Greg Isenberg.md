**Karpathy\'s Autoresearch Broke the Internet**

*Greg Isenberg --- 10 Business Use Cases for Auto-Research*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=qb90PPbAWz4

*Prepared: May 2026*

**Premise**

> *Auto-research is like having a super nerd robot intern that runs science experiments on AI models for you all night without you doing the boring stuff.*

Greg Isenberg\'s solo episode breaking down what auto-research is in plain English, plus 10 specific business ideas to build with it. Includes setup guide for non-technical users.

**How Auto-Research Works (Plain English)**

1.  Give it a goal --- \'make this small AI model smarter.\'

2.  AI agent plans what to try --- different settings, code changes.

3.  Edits the Python code automatically.

4.  Runs short training experiment on GPU (\~5 min).

5.  Reads results.

6.  Decides what to change next.

7.  Loop repeats.

You wake up, grab the best version, ship it. Or sell it.

**Toby Lutke\'s Take (Shopify CEO)**

> *Auto-research works even better for optimizing any piece of software. Make an auto folder. Add a program.md, that\'s just a markdown file. Add a bench script. Make a branch and let it rip.*

**Mental Model --- Research Boss You Can Boss Around**

8.  Write clear task. For code: \'improve this model test score.\' For business: \'find top 5 competitors and write a report.\'

9.  Give bot access --- code, GPU for ML, internet, documents.

10. Bot runs loop: plans → acts → reads results → updates plan.

11. You come back later. See logged charts and metrics.

12. Get a written summary in plain language.

**10 Business Ideas for Auto-Research**

**1. Niche Agent in a Box**

Package tiny auto-research loops tuned for one painful niche. Examples:

-   Amazon listing experimenter.

-   Email sequence tuner for realtors.

-   Pricing optimizer for SaaS.

Charge monthly fee. Value prop: \'this thing runs experiments for you 24/7 and shows you the winner to click accept.\'

**2. AB Testing for Marketing (Print Money)**

Auto-research for landing page conversion optimization. Agent writes variants of headlines, layouts, offers, pushes them to traffic, measures which converts better, iterates.

Sell as \'always-on experiment engine\' to clients as retainer service for \$5K/mo.

**3. Research as a Service**

Auto-research\'s recipe IS a loop for research. Apply to:

-   Constantly updated reports on competitor pricing/features/gaps.

-   Investor and M&A decks.

-   Compliance and regulation tracking (crypto, healthcare, finance).

Charge per report or monthly subscription for fresh dashboards.

**4. Power Tool Inside Your Own Product**

If you have a SaaS, embed an auto-research-style \'optimize button.\' Press it → mini research loop runs.

-   Tune prompts.

-   Pick best pricing.

-   Rank suppliers.

Charge higher tiers for this feature. Use as wedge to upsell Pro and Enterprise.

**5. Optimization Agency**

Pitch: \'we run more tests than anyone else.\' Auto-research lets you run hundreds of experiments instead of a few.

-   Niches: Shopify store conversion lab, B2B SaaS pricing experiment service, email subject line optimizer.

-   Pricing: monthly retainer + bonus for hitting KPI lifts (revshare performance fee).

**6. Auto-Quant for Trading Ideas**

Run small fast back-tests of many simple trading rules:

-   LLM-based factor screens.

-   Sentiment filters.

-   On a single GPU, overnight.

Keep promising strategies. Trade your own account or sell signals as digital products.

**7. Always-On Lead Qualification & Follow-Up**

Point auto-research at CRM. Test rules and messages to see which leads most likely to buy. Auto-grades leads, suggests next actions, drafts follow-ups.

**8. Finance Ops Autopilot**

Loop through invoice matching, expense report generation, exception detection. Continuous small improvements to rules and prompts.

Sell as: \'we cut your AP expense time in half.\' Either as software or ops service with small team + agent. Likely acquired by big fintech.

**9. Internal Productivity Lab for Your Org**

Treat your company like Karpathy\'s GPU lab. Define KPIs (response time, close rate, ticket resolution). Let agents iterate on workflows, templates, routing rules.

Result: fewer meetings, less manual grunt work, you only touch high-impact decisions.

**10. Done-For-You Research / Due Diligence Shop**

Loop chews through docs, filings, product pages, reviews. Keeps an evolving \'living memo\' for clients (investors, acquirers, execs).

Sell fast, well-structured briefs + monthly update packs. Clients pay for fresh info.

**Toby Linton\'s Tweet (Quoted)**

> *I woke up this morning and all I can think about is auto-research. So many ideas swirling. Not sure 99% of the world realized the incredible breakthroughs Karpathy is making and just sharing casually on X. Where my mind is going is medicine. It feels like in many ways clinical trial design is itself kind of like a hyperparameter search.*

Trials cost tens of millions of dollars minimum. An agent swarm could optimize treatment protocols on small proxy experiments, promote the most promising to humans for review.

**AgentHub --- Karpathy\'s Next Project**

Karpathy launched alongside auto-research. Description: \'GitHub is for humans. AgentHub is for agents.\' Agent-first collaboration platform. Bare git repo + message board for swarm of agents working on same codebase. No main branch, no PRs, no merges. Sprawling DAG of commits in every direction.

**How to Get Started (Non-Technical)**

Need: Nvidia GPU OR cloud GPU rental.

**Cloud GPU Options**

-   Lambda Labs.

-   Vast.ai.

-   RunPod.

-   Google Colab (Greg\'s recommendation --- has free tier; trusts Google most).

**Setup**

13. Tell Claude Code: \'I need help installing auto-research by Karpathy.\'

14. Claude reads the GitHub repo (currently 25,000+ stars).

15. Walks you through: clone repo, install dependencies (UV package manager), prepare data, run training experiment.

16. If no Nvidia GPU: rent on Colab or similar.

17. Open colab.google.com → new notebook → change runtime to T4 GPU → run commands Claude provides.

**Source**

Karpathy\'s autoresearch broke the internet by Greg Isenberg --- <https://www.youtube.com/watch?v=qb90PPbAWz4>
