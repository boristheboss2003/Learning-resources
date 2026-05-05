**Top 10 Claude Code Skills, Plugins & CLIs**

*April 2026 --- The Toolkit Every Operator Should Install*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=KjEFy5wjFQg by Chase AI

*Prepared: May 2026*

**Premise**

This video lists the 10 specific skills, plugins, and CLI tools the host would install on day one if starting Claude Code in 2026. Each entry includes what it does, why it matters, installation instructions, and the specific use case where it shines.

**Tool 1 --- Codex Plugin (Claude × OpenAI Codex)**

**What It Is**

A plugin that lets Claude Code call OpenAI Codex for code review, including \'adversarial review\' that hardcore-checks Claude\'s own code.

**Why It Matters**

LLMs look favorably on their own code. They won\'t tell you their architecture is wrong. An outside agent (Codex) doing adversarial review catches issues Claude won\'t flag itself. This is critical when you don\'t have technical background to verify Claude\'s choices.

**Installation**

-   Search \'Codex plugin Claude Code\' on GitHub.

-   Copy the install command from the README, paste into Claude Code.

-   Run /reload-plugins.

-   Run /codex-setup.

-   Requires an OpenAI account (Go plan at \$7/mo is sufficient).

**Commands**

-   /codex:adversarial-review --- hardcore review of Claude\'s code.

-   /codex:review --- standard code review.

-   /codex:rescue --- switch entirely to Codex for a feature when Claude is stuck.

**Tool 2 --- Obsidian + Obsidian Skills**

**What It Is**

Obsidian is a free markdown note-taking tool. The Obsidian skills (created by Obsidian\'s CEO) teach Claude Code how to use it as a personal knowledge base.

**Why It Matters**

Obsidian becomes a miniature RAG system without overhead. Knowledge graphs auto-build. Claude Code creates and reads markdown files; the vault organizes them with backlinks. Karpathy-style wiki workflows where Claude researches and writes wiki articles into folders.

**Installation**

-   Download Obsidian from obsidian.md (free).

-   Designate a folder as \'the vault\' (host calls his \'the vault\').

-   Open Claude Code inside the vault folder.

-   Install Obsidian skills from CEO\'s GitHub repo.

**Best Use Case**

Personal assistant projects with thousands of growing markdown files.

**Tool 3 --- Auto-Research**

**What It Is**

Karpathy\'s machine learning experimentation algorithm in a box. Use it inside Claude Code to optimize any program with a measurable metric.

**Why It Matters**

Self-improving optimization. Claude tries variations, discards losers, keeps winners, accumulates learnings. Runs autonomously.

**Installation**

-   Clone the autoresearch repo with a few lines of code.

-   Open Claude Code in the folder.

-   Tell Claude what program/skill you want to improve.

**Tool 4 --- awesome-design.md (Front-End Design)**

**What It Is**

A repo of design.md files extracted from popular websites --- Claude, Eleven Labs, Cohere, Vercel, etc. --- each one a detailed style guide that informs Claude\'s frontend output.

**Why It Matters**

> *Claude Code sucks at front-end design. Even with the baked-in front-end-design skill, it\'s just not very good. This is a huge step forward.*

Inspired by Google Stitch\'s design.md format. Each markdown file contains comprehensive design guidance for buttons, colors, fonts, spacing, layouts. When designing a website, you feed Claude the relevant template and get production-grade design.

**Installation**

-   Copy the install command from the GitHub repo.

-   Paste into Claude Code.

-   Repo went viral --- 38,000+ stars within a week of release.

**Tool 5 --- Firecrawl CLI + Skill**

**What It Is**

A web scraping CLI that handles anti-bot protections and returns structured data optimized for LLM consumption.

**Why It Matters**

Claude\'s standard web search hits walls on protected sites. Firecrawl gets through. Returns clean structured output (markdown/JSON) instead of raw HTML.

**Installation**

-   Single install command.

-   Firecrawl API requires payment for the proprietary engine.

-   Open-source version is free but lacks advanced bot bypass.

**Tool 6 --- Playwright CLI**

**What It Is**

Browser automation for Claude Code. Better than Playwright MCP and cheaper.

**Why It Matters**

Lets Claude Code create real Chrome instances and test websites. Works on accessibility-tree code (faster, cheaper) instead of screenshots like Claude-in-Chrome.

> *If anyone tells you to use the MCP, don\'t listen to them. The CLI is more effective and cheaper.*

**Use Cases**

-   Test forms, login flows, click sequences.

-   Spawn multiple Chrome tabs simultaneously.

-   Scrape complex multi-page workflows.

**Tool 7 --- NotebookLM CLI + Skills**

**What It Is**

Hooks Claude Code up to Google\'s NotebookLM web app (which has no public API).

**Why It Matters**

Google does the heavy analysis on their servers; Claude Code just orchestrates. Massive token savings. Plus features the NotebookLM web app doesn\'t expose: batch downloads, slide revision, full-text access, programmatic sharing, deliverable generation (videos, slide decks, reports).

> *If you\'re someone who\'s struggling with Claude Code usage, combining it with NotebookLM is a godsend because you\'re using way less tokens.*

**Tool 8 --- Skill Creator Skill (Most Important)**

**What It Is**

Official Claude Code plugin that creates new skills AND benchmarks them with A/B tests.

**Why It Matters**

Skills are the most powerful native feature. Creating one without measuring whether it actually improves output was guesswork. Skill Creator runs benchmarks, A/B tests, gives quantifiable data on whether a new skill helps. Also benchmarks edits to existing skills.

**Installation**

-   Type /plugin in Claude Code.

-   Browse marketplace.

-   Search \'skill creator skill\'.

-   Install.

**Tool 9 --- LightRAG**

**What It Is**

Open-source graph RAG system for when Obsidian breaks down at scale.

**Why It Matters**

Lightweight, free alternative to enterprise graph RAG (Microsoft\'s GraphRAG). Use for client projects with thousands of documents where Obsidian\'s knowledge graph becomes unwieldy.

**Tool 10 --- GWS (Google Workspace Suite)**

**What It Is**

CLI that connects Claude Code to your full Google Suite --- Gmail, Calendar, Docs, Drive.

**Why It Matters**

Built by Google developers (not officially blessed but as close as you can get). Replaces the hacky workarounds people have used. Includes pre-built skills for common workflows: rescheduling meetings, organizing Drive, scheduling recurring events.

**Setup Caveats**

-   Setup is laborious --- requires Google Cloud configuration.

-   Many skills available --- don\'t load all at once.

-   Best practice: point Claude at the GWS repo and ask which skills are relevant for your daily work.

**The Operator\'s Default Stack**

If you only install three tools on day one: Codex Plugin (review), Skill Creator Skill (skill development), Obsidian + Skills (knowledge management). Add the rest as use cases emerge.

**Source**

Top 10 Claude Code Skills, Plugins & CLIs (April 2026) by Chase AI --- <https://www.youtube.com/watch?v=KjEFy5wjFQg>
