# Introduction to Claude Cowork — Research Notes
**Source:** https://anthropic.skilljar.com/introduction-to-claude-cowork  
**Date captured:** 2026-05-05  
**Status:** Free — register to access  
**Type:** Foundational Cowork course — agentic desktop/file tasks  

---

## Overview

Dedicated course for Claude Cowork — the mode where Claude operates directly on your local files, folders, and apps. Distinct from Chat (conversation) and Code (developer tooling), Cowork is for knowledge workers who want Claude to do real work on their machine: read and edit documents, run research tasks, manage files, work across tools. The course covers the core task loop, plugins, scheduled tasks, file workflows, research at scale, and responsible use.

**Target audience:** Knowledge workers, analysts, writers, operators — anyone who wants Claude to act on their local environment, not just converse  
**Prerequisites:** Familiarity with Claude chat recommended; complete Claude 101 first  
**Cost:** Free  
**Certificate:** Yes (Quiz on Claude Cowork)  

---

## Full Curriculum

### Section 1 — Meet Claude Cowork
- **What is Cowork?** — Defining Cowork vs. Chat vs. Code:
  - Chat = back-and-forth conversation; Claude replies in text
  - Cowork = Claude reads/edits/creates actual files on your machine; working session not a chat session
  - Key framing: "You describe the task, Claude plans and executes it, and you steer along the way"
- **Getting set up** — Installation, permissions, connecting to your file system; likely covers the permissions model (what Cowork can and can't access)
- **Running your first task** — End-to-end walkthrough of a complete Cowork task from description → plan → execution → review
- **The task loop** — The core mental model: Describe → Plan → Execute → Steer → Review. Not fire-and-forget; requires active steering

### Section 2 — Making Claude Cowork Yours
- **Giving Cowork context** — How to provide Claude with the right information about your work environment: relevant folders, file conventions, project background; analogous to CLAUDE.md in Code
- **Plugins: Cowork as a specialist** — Plugins are extensions that give Cowork specialised capabilities. Examples likely include: Obsidian plugin (for note-taking workflows), browser plugin, spreadsheet tools. Plugins turn Cowork into a specialist rather than a generalist
- **Scheduled tasks** — Setting tasks to run automatically on a schedule (daily digest, weekly reports, recurring file operations). This enables automation without being present

### Section 3 — Claude Cowork in Practice
- **File & document tasks** — Practical workflows: editing documents in bulk, reorganising folder structures, summarising large sets of files, extracting data from PDFs and documents
- **Research & analysis at scale** — Using Cowork to run research tasks that would be tedious manually: gathering sources, synthesising across documents, producing structured reports from raw data
- **Working responsibly** — Safety and oversight: understanding what Cowork can affect, reviewing plans before execution, the importance of not giving Cowork unnecessary permissions, checking outputs

### Section 4 — Operations & Troubleshooting
- **Permissions, usage, & choosing your model** — The permissions model for what Cowork can access; selecting the right Claude model for a task (speed vs. intelligence trade-off); understanding usage/billing implications
- **Troubleshooting & next steps** — Common failure modes and how to recover; when tasks go wrong, how to steer back on course

### Section 5 — Assessment
- **Quiz on Claude Cowork** — Understanding check; likely covers task loop, plugin concepts, responsible use principles

---

## Key Concepts

| Concept | What it is | Why it matters |
|---|---|---|
| Task loop | Describe → Plan → Execute → Steer → Review | Core operating rhythm for all Cowork sessions |
| Plugins | Specialist capability extensions | Transform Cowork from generic to domain-specific |
| Scheduled tasks | Automatic recurring Cowork tasks | Background automation without manual triggering |
| Context provision | Telling Cowork about your environment | Quality of output depends on quality of context |
| Permissions model | What Cowork can and can't touch | Critical for safety and trust |
| Steering | Active course-correction during execution | Cowork is not fire-and-forget; requires judgment |

---

## Connections to Other Courses

- **Claude 101** — Prerequisite; introduces Cowork at a high level
- **Introduction to Agent Skills** — Skills in Cowork context (plugins overlap with skills concept)
- **Introduction to Subagents** — Related architecture; subagents in Claude Code parallel Cowork's plugin model
- **AI Capabilities and Limitations** — Helpful for understanding why Cowork behaves unexpectedly

---

## How to Operationalise in Our Workflow

### First-session setup
1. **Connect your primary working directories** to Cowork during setup. Start with: Desktop, Documents, and your main project folder. Add more as you identify needs.
2. **Create a context file** (a plain text or markdown file) in each major folder describing what lives there and how it's organised. Cowork will use this as ambient context.
3. **Start with low-stakes tasks** to build a feel for the task loop before trusting Cowork with anything irreversible.

### Mastering the task loop
- **Always review the plan before approving execution.** The plan step is your safety check. Read it fully — if anything looks wrong, say so before Claude acts.
- **Stay present during execution.** Unlike a batch script, Cowork benefits from real-time steering. When Claude hits an ambiguity or takes a wrong turn, intervene immediately.
- **After each task, do a brief review.** Check what was actually created, edited, or deleted. Build this into your habit.

### High-value use cases to implement immediately
| Task type | Cowork workflow |
|---|---|
| Weekly report prep | Cowork gathers data from folders, synthesises, produces draft |
| Email/calendar summary | Cowork reads inbox exports, produces prioritised summary |
| Document reorganisation | Describe the target structure; Cowork moves and renames files |
| Research synthesis | Point at a folder of PDFs/notes; Cowork produces a synthesis doc |
| Meeting prep | Cowork reads relevant project files; produces a briefing doc |

### Plugins to set up first
- **Obsidian plugin** (if you use Obsidian): Cowork can read and write vault notes directly
- **Browser plugin**: enables web research as part of Cowork tasks
- Look for any plugins related to your primary tools (Notion, Google Drive, etc.)

### Scheduled tasks to create
1. **Daily: morning brief** — Summarise today's calendar, open tasks, and recent files modified
2. **Weekly: project status** — Read all active project folders; produce a status summary
3. **As needed: research brief** — Trigger on demand with a standard prompt structure

### Safety guardrails
- Never give Cowork write access to irreversible locations (cloud sync roots, system folders) until you've verified it behaves as expected
- For the first month, always use the "plan review" step — don't skip it even when you trust the task
- Keep a separate folder called `_Cowork-output` where Claude drops new files; review before promoting to your actual workspace

### For our specific context
- Cowork is most powerful for recurring knowledge work tasks that are too complex for a simple script but too tedious to do manually every time
- The scheduled tasks feature is transformative for weekly reporting and research workflows
- Plugins are the key differentiator — without the right plugins, Cowork is generic; with them, it's a specialist
