**Claude Code + Karpathy Autoresearch**

*Self-Improving AI Pipelines for Business --- Nick Saraev*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=4Cb_l2LJAW8

*Prepared: May 2026*

**Video Premise**

Andrej Karpathy released an open-source autoresearch repo while training his own LLM. The idea: instead of manually running ML experiments, give an AI agent a small training setup and let it experiment overnight. It modifies code, trains for 5 minutes, checks improvement, keeps or discards, repeats. You wake up to a log of experiments and a better model.

> *The idea is to give an AI agent a small but real LLM training setup and just let it experiment autonomously overnight. It\'ll modify the code, train for 5 minutes, check if the results improved, keep or discard, and then just repeat.*

The host\'s insight: this same loop applies to any business optimization task with a clear metric and an API. Combined with Claude Code, autoresearch becomes a self-improving system for sales, marketing, ads, copywriting, pricing, and more.

**The Auto-Research Loop**

Three components are required:

1.  Hypothesis --- a slight variation you want to test.

2.  Metric --- an objective measure of success (reply rate, conversion, validation loss).

3.  API --- a way for the agent to make changes and read results.

With these three, the loop runs autonomously: experiment → measure → keep winner → modify → repeat. Iteration speed determines how fast progress accumulates. Karpathy\'s loop is 5 minutes per cycle. The host runs his own cold-email loop every 4 hours.

**Live Example: Cold Email Optimizer**

The host\'s actual production setup. Goal: improve reply rate on cold email campaigns autonomously.

**Setup**

-   Folder called email-optimizer.

-   orchestrator.py contains the agent prompt.

-   Instantly API provides reply-rate data per campaign.

-   baseline.md contains the original well-performing copy.

-   resources.md is a growing document of learnings about what improves reply rates.

-   GitHub Actions runs the loop every 4 hours via cron.

**Loop Execution**

4.  Harvest --- read results from the previous campaign.

5.  Generate --- produce a challenger variant based on learnings.

6.  Deploy --- push the new campaign to Instantly with a fresh lead pool.

7.  Repeat --- every 4 hours, with reply rates accumulating to choose winners.

**Evolved Output Example**

Baseline copy was lengthy and burying the offer. Challenger hypothesis from the agent:

> *The baseline is too long. It buries the offer and lacks a specific CTA time.*

Challenger output (under 75 words) led with relevance, frontloaded risk reversal, and ended with a concrete time ask. The campaign was deployed alongside baseline; reply rate measured; winner harvested.

**Where to Apply Auto-Research**

Any task with three properties: clear objective metric, fast feedback loop, API for changes. Examples the host walks through:

  ----------------------------------- -------------------------- ---------------------------
  **Use Case**                        **Metric**                 **API / Method**
  Cold Email Copy                     Reply rate                 Instantly API
  Landing Page CRO                    Conversion rate            Wix/Webflow/WordPress API
  Ad Creatives                        CVR / CTR                  Facebook/Google Ads API
  Customer Service Scripts            CSAT score                 CRM API
  Product Descriptions (Amazon FBA)   Sales / day                Chrome DevTools MCP
  YouTube Titles                      CTR                        YouTube Data API v3
  Newsletter Subject Lines            Open rate                  ESP API
  Pricing Pages                       Trial-to-paid conversion   Custom API
  SEO Pages                           Keyword rankings           Search Console API
  ----------------------------------- -------------------------- ---------------------------

**Where Auto-Research Doesn\'t Work**

-   Slow feedback loops --- if measurement takes weeks, iteration is too slow to compound.

-   Subjective metrics --- \'warmth\' or \'happiness\' need proxies; otherwise the agent can\'t measure.

-   No API access --- without a way to deploy changes, the agent can only generate suggestions.

**Step-By-Step Setup**

**Step 1 --- Clone the Repo**

Andrej Karpathy\'s autoresearch repo on GitHub contains:

-   Python training scripts.

-   Project description.

-   program.md --- the orchestrator prompt that manages the research loop.

**Step 2 --- Open in IDE with Claude Code**

-   Use Anti-Gravity, VS Code, Cursor, or any IDE with Claude Code support.

-   Create a new folder for your variant of autoresearch.

-   Clone Karpathy\'s repo into the folder so Claude Code has full context.

**Step 3 --- Adapt with Voice Prompt**

Use voice dictation (e.g., Whisper Flow) to describe what you want adapted. Example prompt the host used:

> *Use the context in the autoresearch folder to help me build a similar system, except instead of validation loss and ML model iteration, I want to optimize cold email reply rate. Platform is Instantly. The thing to vary is cold email copy. Put it on GitHub Actions to run every hour autonomously.*

**Step 4 --- Provide API Credentials**

-   Get Instantly API key from Settings → Integrations → API Keys.

-   Get Anthropic (or other LLM) API key.

-   Add Slack webhook for notifications when new variants are tested.

-   Store all keys in a .env file (never commit to GitHub).

**Step 5 --- Schedule with GitHub Actions**

-   Use a cron schedule in .github/workflows/ to trigger every hour or 4 hours.

-   Each run executes orchestrator.py.

-   Output logs and notifications keep you informed without manual intervention.

**Architectural Components**

**The Orchestrator Agent**

Top-level agent that manages the loop. Responsible for:

-   Reading previous experiment results.

-   Generating new hypothesis based on learnings.

-   Calling sub-agents to write copy / code / variants.

-   Deploying via API.

-   Logging outputs to JSON or database.

**Resources.md --- The Compounding Learning File**

After each run, the agent appends learnings to resources.md. Examples accumulate over time:

-   Subject lines under 6 words outperform longer ones.

-   First sentence with company-specific detail beats generic openers.

-   Risk reversal in the first paragraph improves reply rate.

-   Concrete time asks beat \'let me know when you\'re free\'.

The agent reads this file before generating new copy, getting smarter over time.

**Cost & Iteration Reality**

-   Each loop runs on API credits --- budget accordingly.

-   4-hour loop on a moderate cold email campaign costs \~\$5-10/day in API.

-   Faster loops (5 min) compound faster but cost more --- only do this if you have volume.

-   After \~500-1,000 runs, consolidate learnings to prevent the resources file from growing unboundedly.

**The Long-Term Vision**

> *Imagine this running for a year. Instead of optimizing once every 4 hours, optimizing every 5 minutes. That\'s what major AI labs do behind the scenes --- many experiments overnight to make models better.*

Auto-research democratizes the experimental loop that used to require dedicated ML engineering. Any operator with a metric and an API can now run their own continuous improvement engine --- for cold email, ads, landing pages, or any optimizable workflow.

**Source**

Claude Code + Karpathy Autoresearch by Nick Saraev --- <https://www.youtube.com/watch?v=4Cb_l2LJAW8>
