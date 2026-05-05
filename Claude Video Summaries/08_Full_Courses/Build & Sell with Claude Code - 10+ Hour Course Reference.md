**Build & Sell with Claude Code**

*10+ Hour Course --- Comprehensive Reference Document*

**Setup • Build • Productize • Sell**

Source: youtube.com/watch?v=mpALXah_PBg

Companion Curriculum: claude-code-curriculum-deploy.vercel.app

*Prepared: May 2026*

**Table of Contents**

Course Overview 3

Why This Course Matters 5

Module 01 --- Foundation + Setup 7

Module 02 --- Build a Real Website 11

Module 03 --- Power Features 15

Module 04 --- Memory System 20

Module 05 --- ClaudeBot 23

Module 06 --- Apps 26

Module 07 --- Build Anything 30

Module 08 --- Design Systems 33

Module 09 --- Compliance & Maintenance 37

Module 10 --- Turn This Into \$\$\$ 41

Bonus Resources 45

Recommended Learning Path 47

Source URLs 49

**Course Overview**

\'Build & Sell with Claude Code\' is a 10+ hour comprehensive course by Nick Saraev that teaches Claude Code mastery from zero, then progressively builds toward productization --- packaging your Claude Code skills into client-facing services priced at \$30K-\$50K per engagement.

The course is the long-form companion to a shorter 4-hour version. Where the 4-hour course condenses, this 10+ hour version expands every concept with live builds, step-by-step demonstrations, additional pattern variations, and deeper coverage of the productization layer.

**Course Statistics**

  ---------------- ---------------------------------------------------------------------
  **Dimension**    **Value**
  Total Runtime    10+ hours
  Modules          10
  Lessons          64
  Difficulty       Beginner to Intermediate
  Prerequisites    Curiosity. No coding experience required.
  Format           Video plus companion curriculum site, plus production templates
  Target Outcome   Operator who can build Claude Code systems and sell them to clients
  ---------------- ---------------------------------------------------------------------

**Course Promise**

> *Turn lessons into real AI co-workers that save 10-20 hours every week --- and learn to convert that capability into client revenue.*

**Who This Course Is For**

-   Solopreneurs and freelancers who want a productized Claude offering.

-   Operations professionals who automate workflows for living.

-   Consultants who want a new high-margin service line.

-   Engineers exploring AI-native product development.

-   Anyone who has tried Claude Code casually and wants to operate at a professional level.

**Who This Course Is NOT For**

-   People looking for a one-hour quickstart --- buy a shorter course.

-   Those expecting Claude Code to write their entire business plan for them.

-   Hobbyists who don\'t intend to apply the skills commercially.

**Why This Course Matters**

In 2026, Claude Code stopped being a developer-only tool. The release of Cowork, Routines, Skills, Plugins, and Connectors made it a complete operating system for knowledge work. The market for AI implementation services exploded in parallel --- small businesses, agencies, and enterprises now routinely budget \$30K-\$100K to have someone build them a custom Claude system.

The course\'s framing: this gap is closing fast. Operators who develop the skills now will capture the early market premium. Operators who wait until 2027 will compete in a saturated market against people who built their portfolios in 2026.

**The Three Skills Stacked**

  ------------ ------------------------------------------------------------------------------------------------- ------------------------------------------------------------
  **Skill**    **What You Learn**                                                                                **Why It Matters Commercially**
  Build        Use Claude Code to construct real systems --- websites, apps, agent teams, business automation.   Without this, you can\'t deliver.
  Sell         Pricing, positioning, contracting, client acquisition, deal structures.                           Without this, you build for free.
  Productize   Turn one-off projects into repeatable templates that compound.                                    Without this, every deal feels like reinventing the wheel.
  ------------ ------------------------------------------------------------------------------------------------- ------------------------------------------------------------

**The Build & Sell Flywheel**

1.  Build a system for yourself.

2.  Document the patterns and templates.

3.  Find a client with the same need.

4.  Deliver a customized version using your templates.

5.  Refine the templates based on what you learned.

6.  Repeat with the next client at higher confidence and higher price.

**Module 01 --- Foundation + Setup**

11 lessons, approximately 30 minutes. The foundation everything else builds on. Skipping or skimming this module is the most common mistake new viewers make.

**Lesson 1 --- Installation**

-   macOS install via brew or direct download.

-   Windows install (x64 only).

-   Linux install via curl one-liner.

-   Verifying the install: claude \--version returns 2.x or higher.

**Lesson 2 --- The Interface Tour**

-   Terminal pane --- where you type commands.

-   Status indicators --- token usage, model, plan tier.

-   File explorer --- navigating project structure inside Claude Code.

-   Settings --- accessing configuration and preferences.

**Lesson 3 --- Claude Code Plans**

  ------------ ------------------- ----------------------------------------------------
  **Plan**     **Price**           **Best For**
  Pro          \$20/month          Individual hobbyists, exploration
  Max          \$100-\$200/month   Power users, freelancers, regular Claude Code work
  Team         \$30/user/month     Teams of 3-50 users, shared resources
  Enterprise   Custom              Large orgs needing SSO, audit logs, compliance
  ------------ ------------------- ----------------------------------------------------

**Lesson 4 --- Permission Modes**

-   Read-only mode --- Claude can see but not modify.

-   Approval-per-action --- every change requires explicit approval (safest, slowest).

-   Allow-list mode --- pre-approved categories (e.g., file edits in /src) auto-execute.

-   Full autonomy --- only for trusted, scoped projects. Never use casually.

**Lesson 5 --- The 5 Claude Surfaces**

This is the most important conceptual lesson in the entire course. Operators who don\'t internalize the differences will misuse the wrong surface for the wrong job.

  --------------------------- --------------------------------- -----------------------------
  **Surface**                 **Strength**                      **Weakness**
  Chat                        Speed for one-off questions       Forgetful, no file access
  Cowork                      Local file access; non-coder UI   Less depth than Code
  Claude Code                 Maximum power, agent teams        Terminal-only, steep curve
  Managed Agents (Routines)   Cloud-hosted; runs without you    Cannot use local files
  API                         Programmatic; embedded in apps    Requires development effort
  --------------------------- --------------------------------- -----------------------------

**Lesson 6 --- Connecting External Tools**

-   MCP server installation --- the universal connector standard.

-   Gmail MCP --- for inbox automation.

-   GitHub MCP --- for repository operations.

-   Notion, Slack, Stripe MCPs --- common business integrations.

**Lesson 7 --- Daily Slash Commands**

-   /help --- list available commands.

-   /init --- initialize a new project with CLAUDE.md.

-   /clear --- reset context to free up tokens.

-   /compact --- compress conversation history without losing key facts.

-   /cost --- view token spend on the current session.

-   /model --- switch between Sonnet and Opus.

**Lesson 8 --- Organizing Your Desktop**

How to structure your filesystem so agent-driven work doesn\'t end up scattered:

-   /Projects directory at the home level.

-   Per-project subfolders containing CLAUDE.md and source files.

-   Shared /Templates directory for reusable starting points.

-   /Skills directory for personal skill library.

**Lesson 9 --- The CLAUDE.md Planning Document**

CLAUDE.md is the single most important artifact in the course. It is the system prompt for every session in that project. The course\'s recommended structure:

-   Project Overview --- what this project is and what success looks like.

-   Architecture --- how the codebase is organized.

-   Conventions --- naming, formatting, testing standards.

-   External Tools --- MCPs and connectors used by this project.

-   Active Tasks --- what is currently being worked on.

-   Don\'t Do --- explicit anti-patterns to avoid.

**Lesson 10 --- Plan Mode**

Plan Mode forces Claude Code to write out a plan before executing. The course argues this is the most underused power feature: when you suspect Claude is about to make a wrong choice, switch to Plan Mode and ask for the plan first. Approve, modify, or reject before any code is written.

**Lesson 11 --- First Project Setup**

End the module with a clean project: a folder, a CLAUDE.md, an installed MCP, and a /init command run successfully. The viewer is now ready for Module 2.

**Module 02 --- Build a Real Website**

10 lessons. The first concrete deliverable --- a deployed website, built end-to-end, that uses competitor research as its design input.

**The 3-Step System**

7.  Competitor Intel --- instruct Claude Code to research 3-5 competitors and surface positioning gaps.

8.  Design --- produce a design brief and corresponding HTML/CSS that addresses the gaps identified.

9.  Host --- deploy to Vercel directly from Claude Code; verify the live site behaves correctly.

**Lesson Walkthrough**

**Lessons 1-3 --- Competitor Intel**

-   Use the WebFetch or browser MCP to scrape competitor sites.

-   Extract positioning, hero copy, value propositions, pricing, calls-to-action.

-   Generate a \'positioning gap analysis\' identifying themes competitors emphasize and what they overlook.

**Lessons 4-6 --- Design**

-   Convert the gap analysis into a design brief.

-   Generate hero section variants (3-5 to choose from).

-   Build the full page in HTML/CSS, mobile-first.

-   Add interactive elements with vanilla JS --- no heavy frameworks needed.

**Lessons 7-9 --- Host**

-   Connect Vercel via CLI.

-   Deploy from Claude Code with a single command.

-   Configure custom domain.

-   Add basic analytics (Plausible or Vercel Analytics).

**Lesson 10 --- Verification Workflow**

Run a final check: load the deployed site in three browsers, test mobile responsiveness, verify CTAs work, confirm forms submit. Claude Code can drive this verification loop semi-autonomously.

**Why This Module First**

A deployed website is the most concrete possible early win. It is shareable, evidence of capability, and small enough to complete in an afternoon. For operators selling Claude services to clients, a website rebuild is the most common first engagement.

**Module 03 --- Power Features**

12 lessons. The techniques that separate competent Claude Code users from professional operators.

**Lessons 1-3 --- Skills Creation**

How to convert a workflow you do repeatedly into a skill. The course\'s specific creation pattern:

10. Run the workflow manually inside Claude Code.

11. Iterate on outputs until they meet your standard.

12. Ask Claude Code: \'Convert this workflow into a skill saved as a markdown file.\'

13. Test the skill on a fresh similar task.

14. Refine the skill markdown based on what didn\'t quite work.

**Lessons 4-5 --- Token Management**

-   /cost to monitor current session spend.

-   /compact to compress conversation history at strategic points.

-   Use Sonnet for simpler tasks, Opus for complex reasoning --- switching mid-session via /model.

-   Avoid loading entire repos into context; use targeted file reads.

**Lessons 6-7 --- Custom MCPs**

When official MCPs don\'t fit, build your own. The course walks through:

-   MCP server scaffolding --- minimal Node.js or Python boilerplate.

-   Defining tools, resources, and prompts that the MCP exposes.

-   Local installation and connection to Claude Code.

-   Publishing to the MCP registry for reuse.

**Lessons 8-10 --- Subagents**

How to spawn isolated subagents for parallel work that doesn\'t require communication between them. The classic use cases:

-   Multi-file refactoring where each subagent owns a directory.

-   Parallel research where each subagent investigates one source.

-   Audit-style work where each subagent reviews one aspect (security, performance, testing).

**Lessons 11-12 --- Autonomous Critic Loops**

The most advanced pattern in the module. An autonomous critic loop has Claude Code generate output, then critique its own output against explicit criteria, then revise based on the critique --- repeating until criteria are met or a max iteration count is reached. This produces dramatically higher-quality work than single-pass generation, at the cost of more tokens.

**Module 04 --- Memory System**

5 lessons. The course teaches a three-tier memory architecture rather than relying solely on Claude Code\'s built-in memory. This is overkill for casual use but essential for productized client work where you need durable knowledge across long projects.

**The Three Tiers**

  ---------- ------------ ---------------------------------------------- ---------------------
  **Tier**   **Tool**     **Purpose**                                    **Latency**
  Hot        Pinecone     Vector search across project knowledge         Milliseconds
  Warm       NotebookLM   Source-cited reference material                Seconds
  Cold       Granola      Meeting transcripts and conversation history   On-demand retrieval
  ---------- ------------ ---------------------------------------------- ---------------------

**Lesson Walkthrough**

**Lesson 1 --- Why a Memory System**

Claude Code\'s built-in context is bounded. For projects that span weeks or months, you need a way to persist knowledge in queryable form so Claude Code can pull what\'s relevant for the current session without overflowing context.

**Lesson 2 --- Pinecone Setup**

-   Create Pinecone index.

-   Build embedding pipeline that vectorizes new project notes as they\'re created.

-   Connect via MCP so Claude Code can query the index in-session.

**Lesson 3 --- NotebookLM Integration**

-   Upload reference documents (specs, contracts, briefs) to NotebookLM.

-   Use NotebookLM\'s source-cited responses to ground Claude Code outputs.

-   Critical for client work where citations matter.

**Lesson 4 --- Granola for Meeting Memory**

-   Granola records and transcribes meetings automatically.

-   Tag transcripts by project.

-   Connect via MCP so Claude Code can pull conversation history when relevant.

**Lesson 5 --- Tier Routing**

How to teach Claude Code which tier to query for which kinds of questions. Hot tier for \'what did we discuss about X\', warm tier for \'what does the contract say\', cold tier for \'what was decided in the kickoff meeting.\' This routing logic lives in the project\'s CLAUDE.md.

**Module 05 --- ClaudeBot**

2 lessons. Building a custom AI operator (the course calls it \'OpenClaw\' or \'ClaudeBot\') that wraps Claude Code\'s capabilities into a more focused agent. This module is short but pivotal --- it\'s the bridge between using Claude Code yourself and building products on top of it for clients.

**Lesson 1 --- Building OpenClaw**

-   Use the Claude Agent SDK to build a custom agent.

-   Define a narrow scope --- what the agent does and doesn\'t do.

-   Connect to your three-tier memory system.

-   Expose a simple interface (CLI, web UI, or Slack bot).

**Lesson 2 --- Memory Integration**

Wire the custom agent into the same Pinecone/NotebookLM/Granola stack from Module 4. The result: a focused operator with all the memory advantages of the full system, but with a UX simple enough to hand to a non-technical client.

**Module 06 --- Apps**

5 lessons. Building real applications with three core capabilities baked in: authentication, payments, and CRM. Once these three components are in your pattern library, the marginal cost of building a paid SaaS goes from weeks to days.

**Lesson 1 --- App Architecture**

-   Recommended stack: Next.js, Vercel, Supabase, Stripe.

-   File structure conventions for AI-friendly codebases.

-   How to write CLAUDE.md for an app project.

**Lesson 2 --- Authentication**

-   Sign-up, login, password reset, magic links.

-   Session management.

-   Social login via Google/GitHub OAuth.

-   Role-based access (admin, user, guest).

**Lesson 3 --- Stripe Payments**

-   One-time charges and subscription billing.

-   Webhook handling for asynchronous events.

-   Customer portal integration.

-   Test mode vs production cutover.

**Lesson 4 --- CRM with Smart Follow-Ups**

-   Lead capture from forms.

-   Pipeline stages.

-   Automated follow-up sequences triggered by stage changes.

-   Claude Code-generated personalization based on lead data.

**Lesson 5 --- Putting It Together**

A complete demo app combining all four components: a paid SaaS with login, subscriptions, lead pipeline, and AI-driven personalization. Built end-to-end in the lesson --- the kind of app that takes weeks the first time and hours the tenth time.

**Module 07 --- Build Anything**

3 lessons. Systems-thinking applied to projects you have not seen before. The lessons teach how to decompose any client request into a buildable plan.

**Lesson 1 --- Systems Design Principles**

-   Start with the deliverable, work backward to inputs.

-   Identify the data flow before designing the components.

-   Sketch the architecture as a CLAUDE.md before writing any code.

-   Always define what \'done\' looks like upfront.

**Lesson 2 --- Lead Generation Pipelines**

A common client ask. The course\'s reference architecture:

-   Source --- scraping, list rentals, paid ads, content.

-   Enrichment --- Claude Code-driven research and qualification.

-   Routing --- assigning leads to humans or automated outreach.

-   Outreach --- Claude Code-drafted messages, sent via Gmail/HubSpot/etc.

-   Tracking --- pipeline status, response rates, conversion.

**Lesson 3 --- Marketing Agency Stacks**

A complete agency-in-a-box that the course argues is the highest-value productized service in 2026:

-   Content production --- blog posts, social, newsletters.

-   Paid media --- ad concepting, copy variants, campaign setup.

-   SEO --- keyword research, on-page optimization, link building research.

-   Reporting --- automated weekly client reports.

-   Each piece is a Claude Code skill or routine; the agency layer is the orchestration.

**Module 08 --- Design Systems**

7 lessons. The visual creation tools that turn Claude Code from a code generator into a multimedia production studio.

**Lesson 1 --- HTML Presentations**

Generate slide decks as HTML/CSS rather than PowerPoint. Benefits: web-native, version-controllable, embedable, and dramatically more design-flexible than PPTX.

**Lesson 2 --- 3D Integration**

-   Three.js scenes for product visualizations.

-   React Three Fiber for interactive 3D in web apps.

-   Use cases: e-commerce product viewers, architectural visualizations.

**Lesson 3 --- Video Generation**

-   Coordinating Claude Code with video generation APIs (Runway, Pika, Sora).

-   Generating prompt sequences for consistent multi-shot output.

-   Editing pipelines that combine generated clips with stock footage.

**Lesson 4 --- Image Generation**

-   Coordinating with Midjourney, DALL-E, Flux, Stable Diffusion via API.

-   Style consistency across image sets.

-   Brand-locked image generation for client deliverables.

**Lesson 5 --- Logo Extraction**

-   Pulling logos from competitor sites.

-   Generating brand-aligned logo variations.

-   Vectorizing raster logos using Claude-driven SVG generation.

**Lessons 6-7 --- Putting It Together**

The final two lessons stitch all five capabilities into a single design-system-in-a-box that an agency can use to produce branded deliverables across formats --- slides, videos, images, logos, 3D --- from a single brand brief.

**Module 09 --- Compliance & Maintenance**

5 lessons. The least sexy module and the one that actually closes enterprise deals. Most operators lose enterprise contracts not because they can\'t build, but because they can\'t answer compliance questions.

**Lesson 1 --- HIPAA Protocols**

-   Business Associate Agreements (BAAs) with cloud providers.

-   PHI handling --- what Claude Code can and cannot see.

-   Audit logging requirements.

-   De-identification techniques.

**Lesson 2 --- GDPR Compliance**

-   Data residency requirements for EU customers.

-   Right to deletion and how to implement it.

-   Data Processing Agreements (DPAs).

-   Cookie and consent management.

**Lesson 3 --- Security Audits**

-   What to run before a client review (SAST, dependency scans, secret scans).

-   Static analysis tools that integrate with Claude Code.

-   Penetration testing readiness.

-   How to write a one-page security posture document.

**Lesson 4 --- Monitoring**

-   How to know when your deployed agents misbehave.

-   Logging, alerting, and incident response basics.

-   OpenTelemetry integration with Claude Code.

-   Dashboards for client-facing reliability evidence.

**Lesson 5 --- SDK Certification**

-   Anthropic\'s certification paths for vendors.

-   Why certification matters for procurement teams.

-   How to position certification in proposals.

**Module 10 --- Turn This Into \$\$\$**

4 lessons. The money module --- the entire reason the course exists. The previous 60 lessons have been infrastructure. These four lessons are the conversion.

**Lesson 1 --- Pricing Strategies**

> *Hourly billing kills the model. You are not selling time; you are selling outcomes.*

-   Value-based pricing --- anchor on the value delivered, not the hours worked.

-   Tiered packages --- Starter, Standard, Premium with clear scope differences.

-   Retainer structures for ongoing work.

-   Why \$30K is the floor for serious engagements.

**Lesson 2 --- Deal Structures**

  ---------- ----------------- ------------------------------------------------- --------------
  **Tier**   **Price Range**   **Scope**                                         **Timeline**
  Starter    \$5K-\$15K        Single workflow automation, 2-3 skills            1-2 weeks
  Standard   \$30K-\$50K       Multi-workflow system, 5-10 skills, training      3-6 weeks
  Premium    \$75K-\$150K+     Custom agents, app development, ongoing support   2-4 months
  ---------- ----------------- ------------------------------------------------- --------------

**Lesson 3 --- The Build & Sell System Framework**

The flywheel made operational:

15. Build for yourself first --- solve a real problem with Claude Code.

16. Document the patterns in templates and skills.

17. Identify the customer with the same pain --- usually one degree removed from your own work.

18. Sell a customized version of what you\'ve already built.

19. Deliver in weeks, not months, by leveraging your existing patterns.

20. Refine the templates.

21. Repeat with successively higher prices and successively bigger clients.

**Lesson 4 --- Bonuses and Templates**

The course concludes with the bonus pack: 11 production-ready files including pricing frameworks, proposal scripts, and skill configurations. The argument is that operators who would otherwise spend weeks crafting their first proposal can copy and adapt the included templates and ship their first deal within days of finishing the course.

**Bonus Resources**

11 supplementary files included with the course. These are not video lessons but template artifacts --- the kind of things that, used directly, can save weeks per client engagement.

**The 11 Bonuses**

22. Pricing framework spreadsheet --- calculator for tiered pricing across project types.

23. Proposal scripts --- templated proposals for Starter, Standard, and Premium engagements.

24. Production templates for websites --- the Module 2 architecture, parameterized.

25. Production templates for apps --- the Module 6 architecture, parameterized.

26. Skill configurations --- pre-built skills you can drop into any project.

27. Token optimization cheatsheet --- how to do more work without burning Pro plan limits.

28. Decision trees for surface selection --- when to use Chat vs Cowork vs Claude Code.

29. Compliance checklist --- HIPAA, GDPR, security.

30. Client onboarding kit --- questionnaires, kickoff agendas, status report templates.

31. Marketing materials --- case study templates, portfolio page templates.

32. CLAUDE.md library --- sample CLAUDE.md files for common project types.

**Recommended Learning Path**

10+ hours of video is a substantial commitment. The course rewards being watched in order, but specific modules can be jumped to once you are operating commercially.

**Path 1 --- First Pass (Build For Yourself)**

-   Modules 1-3 --- install, build a website, learn power features. (\~3 hours)

-   Module 6 --- build a real app for yourself with auth + payments + CRM. (\~2 hours)

-   Module 8 --- design systems for visual polish. (\~1.5 hours)

Outcome: You have a portfolio of personal projects that demonstrate capability.

**Path 2 --- Second Pass (Productize)**

-   Module 4 --- install the three-tier memory system. (\~1 hour)

-   Module 5 --- build OpenClaw. (\~30 min)

-   Module 7 --- build-anything thinking. (\~1 hour)

Outcome: You can now deliver client-grade systems, not just personal projects.

**Path 3 --- Third Pass (Sell)**

-   Module 9 --- compliance and maintenance. (\~1 hour)

-   Module 10 --- pricing, deals, the Build & Sell framework. (\~1 hour)

-   Bonus Resources --- adapt templates to your offer. (\~Indefinite)

Outcome: You are running a productized Claude Code services business.

**Suggested Cadence**

-   Watch 2-3 lessons per day.

-   After each module, build something real before continuing.

-   Don\'t speed-watch --- the value compounds in the building, not the watching.

**Source URLs**

**The Course**

Build & Sell with Claude Code (10+ Hour Course) --- <https://www.youtube.com/watch?v=mpALXah_PBg>

**Companion Resources**

• Official Curriculum Site (claude-code-curriculum-deploy.vercel.app) --- <https://claude-code-curriculum-deploy.vercel.app/>

• AI Automation Society (Skool community) --- <https://www.skool.com/ai-automation-society/>

• Nick Saraev YouTube Channel --- <https://www.youtube.com/@nicksaraev>

• The 4-Hour Companion Version (CLAUDE CODE FULL COURSE) --- <https://www.youtube.com/watch?v=QoQBzR1NIqI>

• CC for Everyone (Free non-coder Claude Code tutorial) --- <https://ccforeveryone.com/>

• Anthropic Skilljar --- Claude Code in Action --- <https://anthropic.skilljar.com/claude-code-in-action>

• Coursera --- Claude Code: Software Engineering with Generative AI Agents --- <https://www.coursera.org/learn/claude-code>
