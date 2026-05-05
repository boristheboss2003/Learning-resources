**The Claude + Notion System That Runs My Business**

*Systems Made Better --- When To Use Each Tool*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=k06CtnONgWE

*Prepared: May 2026*

**Central Question**

> *Are you still using Notion? And if so, how do you use them together?*

Short answer: yes, both, every day. The video lays out exactly when to reach for each tool. Notion is where teamwork and complex context get managed. Cowork is where thinking, building, and strategy happen. Both setups use the same architecture --- specialist agents, knowledge bases, skills libraries running in both.

**Three-Layer Notion Setup**

**Layer 1 --- Business OS**

The visible workspace where the team interacts:

-   Content manager (videos).

-   Areas dashboard.

-   Projects dashboard with task tracking.

-   Team resources, goal setting.

-   Meeting notes system using AI transcription + summarization.

-   Consolidated databases for cross-references.

**Layer 2 --- Personal Agent (Specialist Coaches)**

One Notion personal agent with multiple specialist modes --- picks the right mode based on what you ask. Saves credits versus separate custom agents.

**Specialist Modes the Host Built**

-   Productivity coach.

-   Decision coach.

-   Content strategist.

-   Business strategist.

-   Online business marketing strategist (with linked knowledge base).

**Architecture**

-   Single global instructions page sets agent-wide behavior.

-   Mode protocol selects specialist agent based on query.

-   Each mode has sub-agent playbook.

-   Skills database backs up all agents.

-   Anti-AI writing style guide for all knowledge work.

-   Voice profile, beliefs, non-negotiables, personality structures.

**Agent Brains (Knowledge Bases)**

Example: online business marketing knowledge base seeded with key strategies. Online business strategist mode answers ONLY based on what\'s in this knowledge base --- strict context constraint.

**Layer 3 --- Custom Notion Agents (Background Workers)**

Page-instruction agents with triggers and schedules. Credit-based. Use sparingly for high-leverage repetitive structured-data jobs only.

**Two Qualifying Questions Before Setting One Up**

1.  Would you do this every week if the agent didn\'t?

2.  Does it have a clear, measurable ROI?

Both yes → set up in Notion (worth credits). Otherwise → use Cowork\'s scheduled tasks (cheaper).

**Demonstrated Custom Agents**

-   Customer support playbook curator --- scans support inbox, drafts SOPs and templates that actually work.

-   Walt the weekly briefer --- schedule trigger, runs every Monday, sends email summary.

-   Andrea the customer service analyzer --- reads emails on schedule, builds reports with trends and quotations.

**Database Agents (New Notion Feature)**

AI Autofill within databases. Custom agent option lets you control intelligence vs cost (Sonnet for low cost; Opus for high intelligence). Set recurrences, on-page-update, on-page-create triggers. Can fill entire databases automatically.

**Pricing**

1,000 credits \~ \$10. Weekly customer service analyzer \~\$2.50/run. Significant cost over time. Compare to Cowork scheduled tasks where computer must be on but no per-run charge.

**Cowork --- Where Thinking, Building, Strategy Happens**

If Notion is for teamwork, Cowork is for thinking. Mirrors the Notion architecture but for local work.

**Cowork OS Folder Structure (PARA Method)**

  ------------ ------------------------------------------------------------
  **Folder**   **Purpose**
  About-Me/    Voice profile, who I am, context map for Notion
  Areas/       Broad ongoing parts of life/work (admin/PA, finance, etc.)
  Projects/    Specific jobs with multiple tasks, scoped per area
  Resources/   Templates, SOPs, reference material
  Archives/    Past material, kept in case needed later
  Outputs/     Per-project finished deliverables (separate from inputs)
  ------------ ------------------------------------------------------------

**Project Files**

Each project folder contains:

-   memory.md --- running notes from sessions on this project.

-   project-brief.md --- current state of work, decisions, what good looks like.

-   outputs/ --- finished deliverables only.

To resume work: \'Go to project X and read its brief and memory files.\' Cowork picks up where it left off.

**Plugins (Cowork) = Specialist Agents (Notion)**

Plugins in Cowork map to specialist sub-agents in Notion. Personal Assistant plugin example:

-   Has its own instructions and personality.

-   Includes specific skills (e.g., /log).

-   Skills can be shared across multiple plugins.

**Sub-Agent Builder (Custom)**

Host built a specialist sub-agent builder skill --- when invoked, prompts you through:

3.  Define the specialist.

4.  Seed knowledge into a knowledge base.

5.  Link the plugin to the knowledge base.

6.  Package as a usable plugin.

**Critical: About-Me System**

System needs to know who you are without being re-briefed.

**Three Files**

  ------------------ ------------------------------------------------------------------------
  **File**           **Contents**
  voice-profile.md   Core identity, beliefs, key questions answered, how you speak
  about-me.md        Who you are, what makes you tick, background, brand voice, how to work
  context-map.md     Where information lives in Notion (key databases, relationships)
  ------------------ ------------------------------------------------------------------------

Plus an anti-AI writing style guide derived from Wikipedia\'s article on AI-generated writing --- Cloud told to never do any of those things.

**Avoiding Token Burn**

Common objection: reading about-me files burns credits. Host\'s response: stronger first output beats reprompting and re-explaining. Worth it. But:

-   Always read who-am-I page.

-   Hold voice-profile and anti-AI guides until output is being created.

-   Keep memory file pruned (host noted his was getting long).

-   Distinguish global memory vs project memory.

**Notion Connector vs Context Map**

Cowork\'s Notion connector is expensive in tokens. Host\'s solution: maintain context-map.md in Cowork that lists Notion\'s key databases. Reduces token use; Cowork only opens the Notion connector for specific lookups, not exploration.

**Live Artifacts (New Cowork Feature)**

Quick dashboards that refresh on demand.

**Demonstrated**

Host asks for YouTube content pipeline live artifact. Cowork:

7.  Asks clarifying questions.

8.  Builds an n8n flow that gathers YouTube data.

9.  Creates the artifact with channels view, net subs, views by video.

10. Refreshes on demand.

Note: Cowork can directly build n8n workflows since they\'re AI-native --- no manual node configuration.

**Scheduled Tasks Beat Custom Notion Agents for Most Work**

**Why Scheduled Tasks (Cowork)**

-   Cheaper --- no per-run credits.

-   Computer must be on (only constraint).

-   Can use Dispatch from phone.

-   Examples: weekly inbox triage, daily morning briefing.

**Weekly Inbox Triage Demo**

Scheduled task reads inbox, filters by Gmail tag, surfaces important items. Briefing file saved to folder. Example artifact: schedule view with overdue tasks, unread emails, Slack info to address.

**Workspace Setup Verdict**

-   Notion: shared team workspace, structured databases, dashboards.

-   Cowork: local files, design exports, transcripts, multi-format outputs (PDF/PPTX), things not cleanly fitting databases.

-   Use both. Sync about-me and brand context across both --- write once, point to it from Cowork via Notion connector then have Cowork copy locally.

**Source**

The Claude + Notion System That Runs My Business by Systems Made Better --- <https://www.youtube.com/watch?v=k06CtnONgWE>
