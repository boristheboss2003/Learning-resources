**Master 80% of n8n in 36 Minutes**

*Futurepedia --- Three Builds From Simple Automation to AI Personal Assistant*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=e3OV3LnrS7o

*Prepared: May 2026*

**Premise**

n8n looks complicated but isn\'t. The video teaches the 80% you\'ll actually use by building three automations: simple weather email, sponsorship intake form-driven workflow, and a fully customizable AI personal assistant. By interacting with a personal assistant daily, n8n becomes second nature.

**What n8n Is**

Node-based automation platform. Two output types:

-   Automations --- fixed sequences (A → B → C). Even with branches, executes predefined steps.

-   Agents --- dynamic, can reason and choose actions based on context.

**Use Cases (Why n8n Matters)**

-   Personal productivity --- assistant for emails, calendar, documents.

-   Marketing/business --- social media, CRM, customer onboarding, sales processes.

-   E-commerce --- product sync, orders, customer support.

-   Data and reporting --- multi-source data ingestion, cleaning, automated reports.

-   Home and lifestyle --- smart home, time/location triggers, quality-of-life automations.

-   AI integrations --- language models, image tools, custom APIs.

**Build 1 --- Daily Weather Email (Simple)**

Goal: every day at 6 AM, check weather, email it. Demonstrates core mechanics.

**Steps**

1.  Create new workflow, name it \'Daily Weather\'.

2.  Add trigger node --- Schedule Trigger. Settings: days, every 1 day, hour 6, minutes 0.

3.  Add action node --- Open Weather. Type \'weather\' in node search.

4.  Connect credentials: openweather.org → API keys → copy → paste into access token field. Save.

5.  Settings: current weather, Imperial units, by zip code, enter zip code.

6.  Test step --- pulls data: temp, location, range, wind speed.

7.  Add Gmail node --- Send a Message.

8.  Connect Gmail credentials --- sign in with Google.

9.  To: your email. Subject: \'Daily Weather\'. Email type: Text.

10. Body: drag-and-drop variables from input panel. \'Today\'s weather is {{\$json.main.temp}} in {{\$json.name}} with range {{\$json.main.temp_min}} to {{\$json.main.temp_max}}.\'

11. Options → toggle off \'append n8n attribution\'.

12. Test workflow --- green nodes confirm success.

13. Activate at top-right to enable schedule.

**Canvas Tips**

-   Click broom icon to tidy up.

-   Zoom-to-fit button.

-   Editor tab vs Executions tab --- Executions shows all past runs.

-   \'Copy to editor\' from any execution to recreate it.

**Account Setup Options**

  ---------------------------------------- -------------------------- -------------------------------------------------------
  **Option**                               **Pricing**                **Notes**
  n8n Cloud                                \$20/mo after free trial   Easiest, fully managed
  Self-host with Docker                    Server costs only          Most technical, lots of config
  Self-host on VPS (Hostinger one-click)   VPS pricing                Sweet spot --- easier than Docker, cheaper than cloud
  ---------------------------------------- -------------------------- -------------------------------------------------------

**5 Core Node Categories**

  -------------- ----------------------------------------------------------------------------
  **Category**   **What It Does**
  Triggers       Initiate workflows (schedule, form, chat, webhook, when-executed-by-other)
  Actions        Pre-built integrations (Gmail, Calendar, Notion, hundreds available)
  HTTP Request   Universal adapter for any API not on the pre-built list
  Logic          Filter, branch (switch), merge, loop
  AI Agent       Connects LLM, memory, tools --- reasons and chooses actions
  -------------- ----------------------------------------------------------------------------

**Build 2 --- Sponsorship Form Routing (Form-Driven)**

When a sponsor submission comes in: route based on budget, autorespond by email, log to Google Sheet.

**Steps**

14. Create workflow, add Form Submission trigger.

15. Add fields: company name, contact name, email, website, budget (number), notes (text area).

16. Execute step → opens form → fill it (e.g., OpenAI / Sam Altman / \$500K).

17. Pin data button preserves test data so you don\'t refill on every iteration.

18. Add Switch logic node. Rule 1: budget \< 1,000,000. Rule 2: budget ≥ 1,000,000.

19. Test step --- data routes through correct branch.

20. Add Gmail node to top branch (low budget). Drag email field into \'To\'. Subject: \'Hello {{company}}\'. Body: \'Sam Altman, how dare you waste my time\...\' (joke).

21. Documentation link in node connects to step-by-step credential setup if Google credentials issue.

22. Toggle off n8n attribution.

23. Duplicate node, drag to lower branch (high budget). Change wording: \'Anything you can do to sweeten the deal.\'

24. Add Google Sheet node --- Append Row. Document URL, sheet name. Drag fields to columns.

25. Add \'action\' column at end --- write \'decline\' for top branch, \'follow up sent\' for bottom.

26. Duplicate Sheet node to lower branch.

27. Test full workflow --- submit form with high budget → email arrives → sheet updates.

**Recommended Extensions**

-   Lead enrichment --- add AI agent node researching company website.

-   Merge nodes --- combine streams (host\'s AI subreddits scraper merges 6 sources into one summary).

-   Set node --- clean/reshape data (strip \$ from budget if user typed \'\$5M\').

**JSON 101 (Just Enough)**

Format data moves through. Every field reference looks like {{ \$json.fieldname }}. The dollar-sign-JSON means \'from previous node.\' For data from earlier nodes, reference by node name: {{ \$(\'On Form Submission\').item.json.company }}.

In practice: drag-and-drop, don\'t type JSON. ChatGPT explains/generates expressions. Common helpers:

-   Math.round() for clean numbers.

-   Replace, parseInt, etc. for data cleaning.

**Build 3 --- AI Personal Assistant (Agent)**

Final build: agent with calendar, email, documents, and custom integrations all controllable from one chat interface.

**Components**

-   Trigger --- chat trigger inside n8n (later swap for Slack/Telegram/Discord).

-   AI Agent node --- connect brain, memory, tools.

-   Brain --- OpenAI/Anthropic/Gemini. Add credentials via API key from platform.openai.com.

-   Memory --- simple memory option. Set to 10 (last 10 messages remembered).

-   Tools --- Gmail (read/write), Calendar (read/write), Google Sheet, custom workflows.

**System Prompt Components**

-   Role --- \'a personal assistant.\'

-   Instructions --- what to do.

-   Tools --- list each tool and when to use it.

-   Context --- relevant facts about you/business.

-   Restrictions --- what to avoid.

Easiest way: ask ChatGPT to draft a system prompt for an agent with the tools you\'ve connected. Add via Add Options → System Message.

**Live Test Prompts**

-   \'Summarize my recent emails\' → uses Gmail tool.

-   \'Do I have any good sponsorship requests?\' → uses sheet, returns ranked list.

-   \'What openings do I have on my calendar tomorrow?\' → uses Calendar.

-   \'Draft an email response with the two free options\' → uses Gmail.

**Sub-Workflows for Action Permissions**

To allow agent to make changes (send emails, schedule events) cleanly: build separate sub-workflows. Calendar sub-workflow has trigger \'When Executed by Another Workflow.\' Same for Gmail. Main agent calls these via Call n8n Workflow tool. Cleaner than putting all action nodes in one agent.

**Custom Tool Examples (Host\'s Setup)**

-   Reddit Curator --- scrapes 6 AI subreddits, ChatGPT picks top 10.

-   YouTube Summarizer --- analyzes comments on a video, returns sentiment/critique/insights.

-   HTTP Request to YouTube Shorts Creator --- generates AISMR video, posts to YouTube, sends email when done.

**Final Tips**

-   Errors are part of process --- test, iterate, adjust.

-   ChatGPT (custom GPT trained on n8n docs) is your best partner.

-   RAG with Pinecone is the natural next step beyond memory.

**Source**

Master 80% of n8n in 36 Minutes by Futurepedia --- <https://www.youtube.com/watch?v=e3OV3LnrS7o>
