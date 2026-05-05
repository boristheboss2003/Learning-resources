# THE ULTIMATE CLAUDE MASTER GUIDE
### From Zero to Absolute Beast — Everything Synthesised

**Sources:** 17 Anthropic SkillJar courses + 70+ videos (Nick Saraev, Simon Scrapes, Chase AI, Greg Isenberg / Boris (Cowork creator), Luke Finance, Karpathy frameworks, AI Daily Brief, and more)  
**Compiled:** 2026-05-05  
**Purpose:** One document. Everything you need to become the top 1% of Claude users.

---

> *"They're both using the same tools, the same models — but have completely different outcomes. And it's not because one is better at prompting. It's because one group built something underneath the tool and the other group didn't."* — Simon Scrapes

---

## Table of Contents

1. [The Mental Model: What Claude Actually Is](#1-the-mental-model)
2. [The 4D Framework: How to Think About Every AI Interaction](#2-the-4d-framework)
3. [Prompting Mastery: The God-Mode Stack](#3-prompting-mastery)
4. [The Three Modes: Chat, Cowork, Code](#4-the-three-modes)
5. [Memory Architecture: Your Agentic OS](#5-memory-architecture)
6. [Skills: Teaching Claude Once, Benefiting Forever](#6-skills)
7. [Subagents: Delegation at Scale](#7-subagents)
8. [Hooks: Deterministic Guardrails](#8-hooks)
9. [MCP: Connecting Claude to Everything](#9-mcp)
10. [The Agentic OS: The Full Architecture](#10-the-agentic-os)
11. [RAG Levels: The Right Memory for Your Scale](#11-rag-levels)
12. [Auto-Research: The New Work Primitive](#12-auto-research)
13. [Boris's Production Rules: From the Creator](#13-boris-production-rules)
14. [Parallel Execution: The New Multitasking](#14-parallel-execution)
15. [Model Selection: Which Claude for What](#15-model-selection)
16. [Finance & FP&A: Boardroom-Ready Workflows](#16-finance-workflows)
17. [Building & Selling: The Business Layer](#17-building-and-selling)
18. [The Diagnostic Framework: When Things Go Wrong](#18-diagnostic-framework)
19. [Master Implementation Roadmap](#19-master-implementation-roadmap)

---

## 1. The Mental Model

*Before you touch a prompt, understand what you're actually working with.*

Claude is a **next-token prediction engine** trained on vast human knowledge. This sounds reductive — it's not. It produces the implications of that mechanism you must internalise:

### The Four Properties (Anthropic's Framework)

**Property 1: Next Token Prediction**
Claude generates the statistically most plausible next word given everything before it. This means:
- Fluent, confident output does NOT mean correct output
- Claude has no internal "I'm not sure" flag it shows you unprompted
- It will produce a convincing wrong answer as readily as a correct one
- **Your rule:** Every factual claim is a hypothesis. Verify anything that matters.

**Property 2: Knowledge**
Claude absorbed enormous amounts of human knowledge in training — but:
- Training ended at a cutoff date. Post-cutoff events = hallucination risk
- Rare, niche, or regional topics are weakly represented
- Claude can be confidently, fluently wrong on specialist topics
- **Your rule:** Test Claude in your domain before trusting it. Provide facts it can't know. Always verify niche claims.

**Property 3: Working Memory (Context Window)**
The context window is Claude's RAM — everything it can "see" in a session:
- The 200K token window (~500 pages) is large but not infinite
- Attention isn't uniform: content buried in the middle of very long contexts gets attended to less reliably ("lost in the middle" problem)
- Without Projects or CLAUDE.md, Claude starts every session at zero
- **Your rule:** Put critical instructions at the top (system prompt). Restate key context in long sessions. Use Projects for persistence.

**Property 4: Steerability**
Claude is highly instruction-following — but:
- Vague instructions get filled with Claude's defaults, which may not match your intent
- Conflicting instructions get resolved probabilistically — you don't control which "wins"
- Long instruction sets have interactions you can't fully predict
- **Your rule:** Specify format, length, tone, audience explicitly. Resolve conflicts before Claude does. Shorter, clearer prompts > long complex ones.

### What This Means Operationally

| Unexpected output type | Which property | Targeted fix |
|---|---|---|
| Sounds right but is factually wrong | Next Token Prediction | Verify; provide correct facts explicitly |
| Missing recent information | Knowledge | Tell it the current situation |
| Seems to have forgotten earlier context | Working Memory | Restate; move key info to top |
| Ignored an instruction | Steerability | Clarify; check for conflicting instructions |

**Stop retrying generically. Diagnose which property. Apply the targeted fix.**

---

## 2. The 4D Framework

*The judgment layer that makes everything else reliable. Tool-agnostic — works regardless of which model or product you're using.*

Developed by Rick Dakan (Ringling College) and Joseph Feller (UCC) in partnership with Anthropic. The difference between AI access and AI fluency.

### The Four Ds

#### Delegation — "Should I be doing this with AI at all?"
The most skipped question. Every AI task starts here.

**High delegation confidence:**
- Well-documented, stable knowledge domains
- First drafts of anything (documents, code, analyses)
- Pattern-matching tasks (classification, extraction, summarisation)
- Repetitive work with defined output formats
- Research synthesis across many sources

**Low delegation confidence:**
- Decisions with high stakes and niche domain requirements
- Anything where you can't evaluate the output quality
- Communications that require authentic personal relationship
- Situations requiring lived experience or moral judgment

**The key test:** Can you evaluate what Claude produces? If you don't know enough to judge the output, you're not ready to delegate that task to AI.

#### Description — "Have I given Claude enough to do this well?"
Poor outputs usually reflect poor description, not AI failure. Claude is *exactly as good as your brief*.

The minimum viable brief:
- **Role:** Who is Claude in this task? ("You are a CFO reviewing a budget proposal")
- **Context:** What does Claude need to know? (Company size, industry, constraints)
- **Task:** What specifically are you asking? (One clear deliverable)
- **Format:** Exactly how should the output be structured? (Headings, length, sections)
- **Constraints:** What to avoid, what to include, tone, audience

The multiplier: **one perfect example beats any description.** Showing Claude one paragraph in your voice tells it more than three paragraphs of adjectives.

#### Discernment — "Is this output actually correct and appropriate?"
The most commonly skipped step. Automation bias — accepting AI output without scrutiny — is the #1 failure mode for competent users.

**Discernment checklist for any AI output:**
- Are factual claims verifiable? Have I checked the ones that matter?
- Does the logic hold? Are there internal contradictions?
- Does this reflect actual domain expertise, or plausible-sounding generic content?
- Is the voice/tone/framing authentic to me/my organisation?
- What would change this conclusion — have I checked those things?

**"If you don't know enough to judge it, you're not ready to use AI for it."**

#### Diligence — "Am I using AI in a way I'd be comfortable explaining?"
The ethical and safety layer.

**Diligence checklist:**
- Data privacy: Does this data contain anything that shouldn't go into Claude? (Client PII, confidential financials, passwords, API keys)
- Disclosure: If someone asked whether AI helped produce this, would I be comfortable answering honestly?
- Quality: Has a qualified human reviewed this before it went anywhere important?
- Security: Could this prompt contain data that leaks if stored or logged?

**Hard rules:**
- Never input client/beneficiary PII without a clear consent and data-handling framework
- Never paste credentials, API keys, or passwords into Claude contexts
- Disclose AI assistance for any professional output where your reputation is on the line
- Every AI output that leaves your hands should have been reviewed by domain expertise (yours or someone else's)

### The 4D Checklist (Use for High-Stakes Work)

```
Before starting:
□ Delegation: Is this task appropriate to delegate? Can I evaluate the output?
□ Description: Have I given Claude role, context, task, format, and constraints?

After receiving output:
□ Discernment: Have I checked facts, logic, and appropriateness with my expertise?
□ Diligence: Is this use ethical? Privacy concerns? Disclosure required?
```

---

## 3. Prompting Mastery

*The God-Mode stack from Anthropic's own documentation + 99% of users miss this.*

### The 5 Mistakes That Halve Your Results

**Mistake 1 — Treating Claude like Google**
You type a search query. Claude generates text from your specification. These are fundamentally different. A search query gets the best pre-existing answer. A brief gets a fresh output built to your exact specs.
- Bad: `"Write article about nootropics"`
- Good: Brief with role + audience + angle + format + constraints
- Impact: 3× better first drafts, 75% fewer revisions

**Mistake 2 — Wall-of-text prompts**
Paragraphs blur instructions, data, and constraints. Claude has to guess priorities. A constraint buried in line 12 of a 300-word paragraph will get missed.
- Bad: One long paragraph with everything mixed in
- Good: Separate blocks with clear structure (instructions / context / task / output format)
- Impact: 40% better instruction-following (Anthropic's own testing)

**Mistake 3 — No role assignment**
Without a role, Claude writes for no one — average text with no voice, no stance, no depth.
- Bad: `"You're a doctor"`
- Good: `"You're an interventional cardiologist writing for American Heart Journal"`
- The difference: Claude adopts vocabulary, tone, framing, depth. Skip the role and you get unmistakable AI flatness.

**Mistake 4 — One-shot expectation**
Anthropic's documentation explicitly states: iteration is the intended workflow, not a sign of failure.
- First attempt: ~70% satisfaction
- After one targeted revision: 92%
- After two: 98%
- Total time: 5 minutes vs 30 minutes from scratch
- Workflow: draft → critique → revise. Always.

**Mistake 5 — Sending fragments instead of full documents**
Claude holds 200K tokens (~500 pages). Give it the full document. A 2-page summary produces generic insights. A full 50-page report lets Claude find patterns across 5 departments, catch footnote risks, make connections you missed.
- Sending snippets = driving a Formula 1 in first gear.

---

### The God-Mode Stack

#### Foundation: The 4-Block Formula

Every prompt should have these four blocks:

```
<instructions>
What Claude should do and how. Role, constraints, tone, what to avoid.
</instructions>

<context>
Background information. Documents. Data. What Claude needs to know.
</context>

<task>
The specific ask. One clear deliverable.
</task>

<output_format>
Exact structure you want back. Headings, sections, length, format.
</output_format>
```

**Real example — bad vs good:**

Bad: `"Write a welcome email for new users of my fitness app."`  
Result: Generic onboarding email. 6/10. 75% requires revision.

Good:
```
<instructions>
You're a conversion copywriter for mobile fitness apps targeting busy professionals.
Keep language urgent but warm. No filler. Every sentence earns its place.
</instructions>

<context>
App targets professionals aged 30-45. 14-day free trial.
Key differentiator: 15-minute workout library. Pain point: no time.
</context>

<task>
Write the welcome email sent 1 hour after sign-up.
</task>

<output_format>
- Subject line (under 50 chars)
- Preview text (under 90 chars)
- Body (under 150 words)
- One CTA button text
</output_format>
```
Result: Time-crunch angle in subject, 15-min hook in lead, CTA tied to first workout. 9/10. Ships.

---

#### Technique 1: XML Tags (Anthropic-Documented, 33% Uplift)

Claude is trained on XML structure. Anthropic uses XML in their own internal prompts. Wrapping sections in tags increases instruction-following compliance from 61% to 94% in Anthropic's testing.

```xml
<role>Senior financial analyst at Goldman Sachs</role>
<task>Review this P&L and identify the top 3 risks</task>
<constraints>
- Cite specific line items, not general observations
- Rank by potential impact
- Flag any data quality issues before analysis
</constraints>
<output>
Numbered list. Each entry: risk name, evidence, magnitude estimate, mitigation.
</output>
```

Use any tag names. Just open and close them consistently. This is the easiest single upgrade you can make.

---

#### Technique 2: Show, Don't Describe (The Example Multiplier)

"Friendly but professional" is meaningless. Claude averages adjectives into bland mush.

**Drop one perfect example.** Claude mirrors voice, rhythm, paragraph length, punctuation better from one real example than from multi-paragraph style descriptions.

```
Write a product review for the Sony WH-1000XM6 headphones.

Match this style exactly:
[paste one paragraph of the voice you want]
```

Tested across 30 writing styles: one well-chosen example beats description every time.

---

#### Technique 3: Prompt Chaining (Complex Tasks)

Never give Claude one mega-prompt for complex outputs. Split it into sequential steps where each response feeds the next.

**Bad — single mega-prompt:**
`"Write a 5-email cold outreach sequence for my analytics platform targeting marketing directors"`
Result: 5 disconnected pitches. Email 4 contradicts email 2. None build on each other.

**Good — chained:**
1. `"What are the top 5 objections a marketing director at mid-size e-commerce would have against a new analytics platform?"`
2. `"Rank these by where they appear in the buyer journey"`
3. `"Write emails 1 and 2. Email 1 addresses only objection 1. Email 2 builds on email 1 and tackles objection 2"`
4. `"Write emails 3-5 following the same logic. Each advances the narrative"`

Result: A real conversation, not 5 first emails.

---

#### Technique 4: Prefilling (Force Exact Output Structure)

Start Claude's response yourself. Claude continues seamlessly from where you left off.

```
[Your prompt]...

Product 1: Ultra Comfort Ergonomic Chair, Price: $299, Features:
```

Claude continues in clean bullet structure for all 50 products without the "I'll help you create..." preamble. Use for: JSON, CSV, tables, lists, forcing tone from word one.

---

#### Technique 5: Motivated Instructions ("Because" Clauses)

Documented Claude 4.6 feature: Claude applies rules better when it understands the *purpose* behind them.

- Commanding: `"Don't use ellipses."` → followed inconsistently
- Motivated: `"Don't use ellipses because the answer will be read by TTS and the system can't pronounce them."` → followed everywhere including edge cases

Claude understands spirit, not just letter. Give it the reason.

---

#### Technique 6: Constraint Stacking (More = Better)

Counterintuitive truth: more constraints = better output. Constraints free Claude from guessing.

Vague: `"Write a LinkedIn post about AI in healthcare"` → "In today's rapidly evolving landscape..."

Constraint-stacked:
```
Write a LinkedIn post about AI in healthcare.
- Open with a specific statistic (cite it)
- Natural voice, not thought-leadership jargon  
- Honest about limitations, not hype
- Under 200 words
- No bullet points
- End with a question
```

Tested across 50 posts: constraint-stacked averaged 3× higher engagement. Specificity forces originality.

---

#### Technique 7: Iterative Refinement (Draft → Critique → Revise)

1. Get the first draft
2. Ask Claude to critically analyse its own response: `"Critique this response. Find weak spots, redundancies, contradictions, and gaps."`
3. Ask it to rewrite considering its own critique

You're using Claude as both author and editor. One model, two roles. The rewrite is dramatically better than the original — every time.

---

#### The Full God-Mode Stack (Combined)

For important outputs, layer everything:

```
1. 4-block formula sets the skeleton
2. XML tags separate each block
3. One example locks voice
4. Constraints: specific, stacked, with "because" clauses
5. Get draft
6. Iterative refinement: Claude critiques → rewrites
```

Result: 12 minutes from blank page to publishable draft. Without stack: 3-4 rounds + heavy editing.

---

## 4. The Three Modes

*The wrong mode for the task is the most common efficiency killer.*

### Chat — Conversation and Thinking Partner
**What it is:** Back-and-forth conversation. Claude replies in text. You're the one executing.  
**Best for:** Thinking through problems, getting feedback, research synthesis, drafting content you'll edit, learning, brainstorming  
**Key features:** Projects (persistent workspaces), Artifacts (standalone editable outputs), Research Mode (autonomous multi-source web research)  

**Research Mode** is criminally underused:
- Claude autonomously searches multiple sources, synthesises, cites
- Use for: literature reviews, competitive research, policy lookups, due diligence
- Rule: Any question that requires more than one source → switch to Research Mode

**Projects** are how you stop starting from zero:
- Create one Project per ongoing area of work (client, project, research domain)
- Pin your most-referenced documents in each Project
- Claude gets ambient context from those documents in every conversation

---

### Cowork — Agentic Files & Tasks
**What it is:** Claude operates directly on your local files, folders, and apps — reading, editing, creating real outputs on your machine. A working session, not a conversation.  
**Best for:** File operations at scale, document processing, research that produces deliverables, recurring task automation  

**The Cowork Task Loop (memorise this):**
```
Describe → Plan → Execute → Steer → Review
```
- **Describe:** Clear, bounded task with success criteria
- **Plan:** Claude proposes an approach — READ IT FULLY before approving
- **Execute:** Claude acts on your machine
- **Steer:** Stay present. Intervene immediately when it goes wrong
- **Review:** Check what was actually created, edited, or deleted

**From Boris (Cowork's creator):**
> "99% failure mode is treating Cowork as a chatbot. Delegation, not conversation."

**Cowork's key differentiators:**
- **Plugins:** Turn Cowork from generalist to specialist (Obsidian plugin, Excel skill, browser extension). Without the right plugins, Cowork is generic.
- **Scheduled tasks:** Set tasks to run automatically (daily briefings, weekly reports, recurring file operations). This is the shift from "using AI" to "having AI work for you."
- **Parallel sessions:** Don't run one task at a time. Boris runs 5-10 in parallel.

**High-value Cowork workflows:**
| Task | Workflow |
|---|---|
| Weekly report prep | Cowork reads project folders → synthesises → drafts report |
| Document reorganisation | Describe target structure → Cowork moves and renames |
| Research synthesis | Point at folder of PDFs → Cowork produces synthesis doc |
| Meeting prep | Cowork reads relevant files → produces briefing |
| Email management | Cowork reads inbox exports → produces prioritised action list |

---

### Claude Code — Agentic Developer Tool
**What it is:** Terminal-based AI coding agent. Read-plan-act-observe loop. Claude reads code, executes commands, edits files.  
**Best for:** All software development work — exploration, implementation, code review, testing, deployment  

**The Explore → Plan → Code → Commit Loop (the core rhythm):**
```
1. EXPLORE: Claude reads the codebase. Understands the context.
2. PLAN: Claude proposes an approach (use Plan Mode — review before approving)
3. CODE: Claude implements, running tests and linting as it goes
4. COMMIT: Claude stages, writes commit message, commits
```

**Never rush to Code without Explore.** The #1 mistake is asking Claude to implement before it has read the relevant code. Bad assumptions compound.

**The critical tools:**
- **CLAUDE.md:** Project memory file. Claude reads this on every session start. Contains: stack, conventions, build/test commands, architecture decisions. Most leverage per minute invested.
- **Plan Mode:** Claude drafts a plan before executing. Non-negotiable for any task touching > 2 files or with side effects.
- **Approval mode vs. auto-accept:** In approval mode, review every action. Switch to auto-accept only once you've reviewed the plan and trust the task.
- **`/compact`:** Summarise and compress context when it fills up (~50% full)
- **`/clear`:** Reset context between distinct tasks
- **`@filename`:** Explicitly scope Claude's context to specific files. Don't make it guess.
- **Thinking Mode:** Extended reasoning for complex architecture decisions, hard debugging, security-sensitive reviews. Not for boilerplate.

**`/init` command:** Run this in every new project. Auto-generates CLAUDE.md from codebase analysis. Edit the output — it's 80% there. Add the 20% that isn't obvious from the code.

---

## 5. Memory Architecture

*The thing that separates power users from everyone else. LLMs don't know who you are — you have to build that.*

### Why This Is Everything

Every LLM session starts at zero by default. No memory of last week. No knowledge of your business. No understanding of your conventions. Without a memory architecture, you're re-explaining yourself every single session — and getting generic outputs in return.

The users who get dramatically better results didn't learn better prompts. They built the architecture underneath.

### The RAG Levels (Chase AI's Hierarchy) — Pick Your Level

| Level | Approach | When to use |
|---|---|---|
| 1. Auto-Memory | Native CLAUDE.md auto-memory | Never edited CLAUDE.md → start here |
| 2. CLAUDE.md | Single instruction file, injected every prompt | Universal. Always. But keep it lean. |
| 3. State Files | Multiple markdown files per aspect (project.md, requirements.md, roadmap.md) | Single project with growing complexity |
| 4. Obsidian Wiki | Markdown vault: raw/ → wiki/ → output/ structure | **This is the 99% solution. Start here.** |
| 5. Naive RAG | Embedding model + vector DB + chunking | Skip. Most "RAG products" are this. Ineffective. |
| 6. Graph RAG (LightRAG) | Entities + relationships + hybrid queries | Only when Obsidian breaks |
| 7. Agentic RAG | Multimodal + production pipelines | Production teams with millions of documents |

**The critical insight: most people are fine at Level 4. Don't skip to graph RAG because it sounds sophisticated. Start with Obsidian. Only escalate when you actually hit a wall.**

### CLAUDE.md — The Minimum Viable Memory

Every project gets a CLAUDE.md. Run `/init` to auto-generate, then edit. Template:

```markdown
# Project: [Name]
[2-3 sentence description of what this is]

## Stack
- Language: 
- Framework: 
- Key dependencies: 
- Database: 

## Commands
- Build: `npm run build`
- Test: `npm test`
- Lint: `npm run lint`
- Dev server: `npm run dev`

## Architecture
[Key architectural decisions that aren't obvious from code]
[Non-obvious patterns to follow]
[Things Claude should NEVER do in this codebase]

## Conventions
- [Naming patterns]
- [File organisation]
- [Error handling approach]
- [Testing patterns]

## When you get something wrong, I'll tell you here:
[This section grows over time]
```

**Boris's CLAUDE.md rules:**
- Team-shared and checked into git
- Everyone contributes multiple times a week
- When Claude does something wrong: add it immediately
- "Just a text file — no special format required"

### The Karpathy LLM Wiki Pattern

**Different from RAG. Free. Dramatically more token-efficient.**

Architecture:
```
vault/
├── raw/        ← staging area: drop source documents, transcripts, notes
├── wiki/       ← structured Wikipedia-style articles + a master INDEX.md
├── output/     ← final deliverables
└── CLAUDE.md   ← explains the structure to Claude
```

How it works:
1. Claude reads INDEX.md → finds the relevant wiki entry
2. Each entry has internal links — backlinks act as "soft" RAG
3. Token usage drops 95% vs flat-folder retrieval (one user: 383 scattered files + 100 transcripts → compact wiki)

vs. Semantic RAG:
| Karpathy Wiki | Semantic RAG |
|---|---|
| Reads indexes + follows backlinks | Vector similarity search |
| Markdown only — free | Embedding model + DB + chunking pipeline |
| No infrastructure | Re-embed when things change |
| Works up to hundreds of pages | Needed for millions of documents |

**To implement:** Create the vault structure → drop your existing notes/transcripts into `raw/` → tell Claude Code: "Implement Karpathy's LLM wiki. Ingest raw/ files into wiki structure." You get a searchable knowledge graph in markdown. Free. Immediate.

### The 7-Layer Personal Agentic OS (AI Daily Brief / Newfar Framework)

Build this once and every agent you use inherits it:

| Layer | Question | How to build |
|---|---|---|
| 1. Identity | Who are you? What rules? | Have AI interview you: "Ask me 15 questions about how I work, what I want, how I want you to respond." Output to `user.md` + `personality.md` |
| 2. Context | What do you know? | 3-5 single-page focused files (my-team.md, my-product.md, my-customers.md). Update as situation changes |
| 3. Skills | How do you work? | Reusable instruction sets: "When [trigger], do [process] using [sources], output [format]" |
| 4. Memory | What persists? | Tool's auto-memory + dedicated specialised files. Audit periodically |
| 5. Connections | How does the agent reach systems? | MCPs/APIs. Read-only first. Grant write access only after weeks of trust |
| 6. Verification | How do you know it's right? | 3-5 quick checks per task type. Monthly OS audit |
| 7. Automations | What runs unattended? | Only well-tested workflows. Drafts before sending. Always log |

**The compounding return:** Your first agent took a weekend. Your second builds on this foundation and takes an afternoon. By your fifth, hours. The system compounds.

---

## 6. Skills

*Stop repeating yourself. Teach Claude once. Benefit forever.*

### What Skills Are

Skills are markdown files with frontmatter that Claude Code reads and applies to matching tasks. The description field is the trigger — Claude reads it and decides whether to apply the skill.

```markdown
---
name: code-review
description: When reviewing code, a PR, or a diff, apply this structured review process
---

# Code Review Process

When asked to review code or a PR:
1. Check for security vulnerabilities (SQL injection, XSS, auth issues)
2. Check for missing error handling
3. Check for test coverage gaps
4. Check style against our conventions
5. Check for performance issues

Output: numbered finding list with SEVERITY, FILE:LINE, ISSUE, RECOMMENDATION
```

**Where they live:**
- `~/.claude/skills/` → global (personal, all projects)
- `.claude/skills/` → project-level (team-shared, in git)

### Writing Effective Descriptions (The Most Important Thing)

The description determines whether the skill auto-applies. Bad descriptions = skills that never fire.

**Bad:** `"Helpful instructions for various tasks"`  
**Good:** `"When the user asks to review a pull request, code diff, or files for quality issues, apply this review checklist"`

Pattern for effective descriptions:
- Starts with "When..." or "Use when..."
- Specifies a concrete task type
- Avoids overlap with other skills
- Written from Claude's perspective (it's what Claude reads)

### Progressive Disclosure (Keep Context Efficient)

Main skill file = lean. Keep the instruction light. Link to sub-files for detailed reference material Claude only loads when needed.

```
.claude/skills/
├── code-review.md          ← lean: 20 lines of core instructions
├── code-review/
│   ├── security-checklist.md   ← only loaded when security review needed
│   ├── test-standards.md       ← only loaded when test review needed
│   └── style-guide.md          ← only loaded when style review needed
```

### Skills vs. Everything Else (Decision Table)

| Feature | When to use |
|---|---|
| **Skill** | Reusable task-specific instructions; consistent behaviour across sessions |
| **CLAUDE.md** | Always-on project context; conventions, stack, build commands |
| **Hook** | Deterministic pre/post actions; linting, testing, session logging |
| **Subagent** | Isolated context; parallel or long-running task delegation |
| **Custom command** | Explicit slash commands the user invokes intentionally |

### The Self-Annealing Property (Nick Saraev)

> "Skills are self-annealing over time. They heal themselves. They get better and improve constantly. Much like an ambitious staff member who sees a checklist, notices a gap, fills it."

After each run, Claude finds mistakes during execution, solves them, and patches the skill. The skill improves automatically.

**Implementation:** After building a skill, add this at the end:
```markdown
## Self-improvement
After each execution, if you find a gap or error in this skill, update it.
Log the update to `skill-changelog.md`.
```

### The Skill Systems Pattern (Simon Scrapes)

> "Start thinking about your skills not as single isolated skills, but as part of a full pipeline or process."

One skill in isolation saves a little time. Chained skill systems save entire workflows.

**Example — Content Production Pipeline:**
```
Scheduled task → research-skill
↓ output feeds into
script-writing-skill
↓ output feeds into
human review step (only gate requiring human)
↓ approved →
video-creation-skill + transcription-skill (parallel)
↓ transcription feeds
repurposing-skill → auto-posts to platforms
```

You appear once (the review gate). The rest runs autonomously.

### The SOP-to-Skill Conversion (Nick Saraev's Rule)

> "If you have a standard operating procedure, you have a skill. Copy that SOP from your business, feed it into Claude, ask it to make a skill."

Every documented process in your business or workflow is a candidate for a skill. Treat your SOPs as a skill backlog.

### Skills to Build First (Priority Order)

**For developers:**
1. `code-review` — reviews any PR or file for security, tests, style, performance
2. `write-tests` — generates tests following your testing framework and coverage standards
3. `generate-docs` — writes or updates docstrings/documentation
4. `commit-message` — writes conventional commit messages from diffs
5. `pre-deploy-checklist` — runs your deployment verification checklist

**For knowledge workers:**
1. `research-synthesis` — structures research output as: executive summary, key findings, sources, gaps
2. `meeting-prep` — reads project files, produces briefing doc with agenda and context
3. `weekly-report` — reads project folders, produces status summary
4. `email-draft` — drafts emails in your voice for specified recipient/purpose
5. `document-review` — reviews documents against your standards and criteria

**For business operators:**
1. `follow-up-nurture` — checks pipeline, personalises follow-up messages per stage
2. `proposal-draft` — creates proposals from brief + client context
3. `onboarding-checklist` — runs new client/employee onboarding workflow
4. `reporting-automation` — pulls data, produces formatted reports
5. `competitive-analysis` — researches competitors against defined criteria

### Sharing Skills Across Teams

- **Team:** Commit `.claude/skills/` to the repository. Every team member gets the same skills automatically.
- **Wider distribution:** Package as a plugin — skills + metadata + installation instructions.
- **Organisation-wide:** Enterprise managed settings — admin deploys skills to all employees without per-user setup.

**Skills are how you make team AI behaviour consistent.** Without shared skills, every person is running their own incompatible prompting approach. With shared skills, the team shares a common language and common standards.

---

## 7. Subagents

*The most practical way to get more out of longer sessions.*

### What Subagents Are

Subagents are isolated Claude instances that the main conversation can delegate tasks to. They:
1. Receive a task + relevant context from the main conversation
2. Work independently (can use all Claude Code tools)
3. Produce a structured summary
4. Return ONLY the summary to the main context — not all the intermediate steps

**Why this matters:** The main context stays clean. A 50-file audit doesn't fill your context with file contents — you just get the findings.

### The Core Pattern

```
Main context (orchestrator) → delegates bounded task → Subagent (worker)
Subagent works independently
↓
Subagent produces: Summary + Findings + Blockers
Returns to main context
Main context acts on summary only
```

### Designing Reliable Subagents

**1. Structured output format (non-negotiable)**
```markdown
## Summary
[2-3 sentence summary of what was done]

## Findings
- [Finding 1]
- [Finding 2]

## Blockers
- [Anything preventing completion — be explicit, never silent]

## Recommendations
1. [Action 1]
```

**2. Explicit success criteria**
```markdown
You are done when: all files in the specified directory have been reviewed 
and you have produced a finding for each one, OR you have reported why 
a file could not be reviewed.
```

**3. Restrict tool access**
```yaml
tools: [read, grep, glob]  # Read-only — no bash, no write
```
A documentation reviewer doesn't need bash access. Minimise blast radius.

**4. Obstacle reporting**
Never silently skip. Always surface blockers:
- "Could not access file X due to permissions"
- "Found ambiguity in requirement Y — need clarification before proceeding"

### When to Use Subagents

**Use them:**
- Task requires reading 50+ files (context explosion risk)
- Task is parallelisable — run multiple subagents on different parts simultaneously
- Task produces lots of intermediate output the main context doesn't need
- Task is well-defined with a clear end state
- You do this type of task repeatedly

**Don't use them:**
- Task requires continuous dialogue with you
- Task is short and simple (overhead exceeds benefit)
- Task needs the full conversation history
- Task is ambiguous — clarify first, delegate second

### Parallel Analysis Pattern (High-Leverage)

```
Main: "Review all 20 modules for security issues"
→ Subagent-1: modules 1-7 (read-only tools)
→ Subagent-2: modules 8-14 (read-only tools)
→ Subagent-3: modules 15-20 (read-only tools)
← Aggregate findings → final report
```

Three subagents run in parallel. Total time ≈ time for one. Full coverage.

### Subagents to Build

```
code-reviewer: Reviews files for quality, security, correctness. Read-only.
doc-generator: Generates/updates docs for a module. Read + write.
test-generator: Generates tests. Read + write + bash (to run tests).
researcher: Researches a topic, returns structured summary. Web search + read.
data-extractor: Extracts structured data from files/documents. Read-only.
```

---

## 8. Hooks

*Deterministic guardrails. Things that must always happen, regardless of what Claude decides.*

### What Hooks Are

Hooks are shell scripts that execute before or after Claude's actions. Where skills are intelligent instructions Claude may or may not apply, hooks are deterministic — they always run.

### Core Hooks to Implement

**Post-edit: Linter**
```bash
# Runs after every file edit
npm run lint --fix $CLAUDE_FILE_PATH
```

**Post-edit: Type checker**
```bash
tsc --noEmit 2>&1 | head -20
```

**Pre-commit: Test runner**
```bash
# Blocks commit if tests fail
npm test -- --passWithNoTests
if [ $? -ne 0 ]; then
  echo "Tests failing. Commit blocked."
  exit 1
fi
```

**Session-end: Activity log**
```bash
# Append session summary to daily log
echo "$(date): $CLAUDE_SESSION_SUMMARY" >> ~/claude-logs/$(date +%Y-%m-%d).md
```

**Pre-dangerous-command: Confirmation gate**
```bash
# Require confirmation before destructive operations
if echo "$CLAUDE_COMMAND" | grep -E "(rm -rf|DROP TABLE|DELETE FROM)"; then
  echo "Dangerous command detected. Confirm? (y/n)"
  read confirm
  if [ "$confirm" != "y" ]; then exit 1; fi
fi
```

### The Compound Engineering Pattern (Boris)

Boris's prior life at Meta: kept a spreadsheet of code review issues. When the same issue appeared 5-10 times, he wrote a lint rule. Now:
- Tag `@claude` on a PR → CLAUDE.md updates automatically → Claude never makes that mistake again
- Tag `@claude` on an issue → Claude fixes it and adds the lesson to CLAUDE.md

**Hooks + CLAUDE.md + GitHub Action = self-improving system that compounds over time.**

---

## 9. MCP — Model Context Protocol

*The integration layer. Connect Claude to anything.*

### What MCP Is

MCP is Anthropic's open protocol for connecting Claude to external services in a standardised, reusable way. Instead of writing bespoke tool schemas for every integration, you build an MCP server once and any MCP-compatible client (Claude, Claude Code, your own app) can use it.

### The Three Primitives

| Primitive | Who controls invocation | What it is |
|---|---|---|
| **Tools** | Model (Claude decides) | Functions Claude can call — APIs, database queries, actions |
| **Resources** | App (host exposes) | Data Claude can read — files, records, knowledge bases |
| **Prompts** | User (explicitly selected) | Pre-defined workflow templates |

### When to Build an MCP Server

Build one when:
- A data source/service needs to be accessible across multiple contexts (Chat, Code, your app)
- You want to reuse an integration across projects or teams
- The integration is complex enough to isolate
- You want Claude to call it autonomously (tools) or users to invoke it deliberately (prompts)

Don't build one when:
- One-off integration used in one place only
- You're just formatting data to pass to Claude — do it inline

### MCP Server Patterns

**Data access server:**
- Tools: query, search, get_record
- Resources: expose collection, expose single record
- Prompts: summarise, compare

**Action server:**
- Tools: create, update, delete, trigger_workflow
- Resources: expose status, expose logs
- Prompts: standard operation sequences

**Search server:**
- Tools: semantic_search, keyword_search, hybrid_search
- Resources: expose index metadata
- Prompts: research workflow, literature review

### Priority MCPs to Connect

1. **Filesystem** — read/write your key project directories
2. **Browser** — Claude can do web research and interact with web apps
3. **Your primary data tool** — Notion, Obsidian, Airtable, whatever holds your work
4. **GitHub** — automated PR review, issue handling
5. **Email/Calendar** — Gmail/Outlook integration for communications workflows

### Connecting to Claude Code

```bash
claude mcp add my-server -- python server.py
# Now all your server's tools are available in every Claude Code session
```

---

## 10. The Agentic OS

*The full architecture. This is what separates 1% users from everyone else.*

### Simon Scrapes' 9-Layer Architecture

> "They're both using the same tools, the same models — but have completely different outcomes. Not because one is better at prompting. It's because one built something underneath the tool and the other didn't."

| Layer | What it does | How to build |
|---|---|---|
| 1. User Identity | Tells Claude who you are | AI-interview yourself: "Ask me 15 questions about how I work and how I want you to respond." Output to `user.md` + `personality.md` |
| 2. Brand/Business Context | Tells Claude about your work context | Brand voice, ICP, market positioning, business assets → `brand-context/` folder |
| 3. Memory System | Persistence across sessions | Start at Level 2 (CLAUDE.md); progress to Level 4 (Obsidian wiki) as needed |
| 4. Skills | Specialist knowledge | SOPs → skills. Start with 3-5 core recurring tasks |
| 5. Skill Systems | Chained workflows | Link skills into pipelines. Add the human review gate. |
| 6. Multi-Level Planning | Right depth for task complexity | Quick (Plan Mode) / Project (PRD) / Complex (GSD framework) |
| 7. Multi-Client Management | Clean context separation | One project per client/context. No cross-contamination |
| 8. Output Structure | Organised deliverables | `[project]/output/[YYYY-MM-DD]/[deliverable-type]/` |
| 9. Remote Access | Work from anywhere | Web, iOS, Android sessions for ongoing tasks |

**Layer 3 — Memory System (6 Levels):**
| Level | Approach | Use when |
|---|---|---|
| 1 | CLAUDE.md / native rules | Static rules that never change |
| 2 | Session-start hooks | Force context loading every session deterministically |
| 3 | Semantic search (mem-search, claude-mem) | Search by meaning across markdown notes |
| 4 | Verbatim recall | When exact phrasing matters (client work) |
| 5 | Knowledge bases | Specific reference material at scale |
| 6 | Cross-tool shared memory | Working across different LLMs/devices |

80/20: Levels 1 + 2 + 3 combined cover most users. Levels 4-6 are bolt-ons.

**Layer 4 — Skill Design Principles (Simon Scrapes):**
- Keep skills under 200 lines (Claude reliably recalls this length)
- Use progressive disclosure — name and description always load; full skill only when triggered
- Always reference business context — copywriting skills pull brand voice; research skills pull ICP
- Build a self-learning rule into each skill: ask for feedback after each run, log to `learnings.md`, read learnings before next run

**Layer 6 — Multi-Level Planning:**
| Level | Used for | Framework |
|---|---|---|
| 1 | Quick tasks | Built-in Plan Mode (Shift+Tab+Tab) |
| 2 | Half-day to multi-day projects | PRD-style files with checkboxes |
| 3 | Complex multi-week | GSD framework: plan phase → execute phase → verify phase |
| 4 | Full product builds | Custom multi-phase architectures |

---

## 11. RAG Levels

*Already covered in Section 5 — quick summary for reference.*

Most people don't need RAG. The progression:

1. **Start at Level 2 (CLAUDE.md).** Always. For every project.
2. **Move to Level 4 (Obsidian wiki)** when you have a real knowledge base.
3. **Consider Level 6 (LightRAG)** only when Obsidian fails you — when you need relationship queries across thousands of documents.
4. **Level 7 (Agentic RAG)** is for production teams with multi-modal data and many users.

**Don't skip to sophistication because it sounds impressive. Run Obsidian first.**

---

## 12. Auto-Research

*Karpathy's pattern. The new work primitive.*

### The Core Pattern

Auto-research is not an ML technique. It's a **general work pattern** applicable to anything with an objective metric and a fast iteration loop.

```
1. Define a clear objective metric (reply rate, conversion %, forecast accuracy, test coverage)
2. Define what changes (the variable: copy, code, pricing, layout)
3. Set a fast iteration loop (minutes for code, hours for marketing, days for finance)
4. Agent proposes change → implements → runs experiment → reads result
5. If improved → keep, commit, log to learnings.md
6. If not → discard, revert, log to learnings.md
7. Loop. Knowledge accumulates.
```

### The 5 Requirements for Auto-Research to Work

1. **Score** — an objective metric. Subjective metrics need proxies.
2. **Fast iteration** — bad attempts waste minutes, not weeks
3. **API or programmatic access** to deploy changes
4. **Bounded action space** — Claude varies one thing at a time
5. **Cheap retry cost** — failure is cheap and reversible

### Business Use Cases (Greg Isenberg / AI Daily Brief)

| Domain | Metric | Variable |
|---|---|---|
| Cold email | Reply rate | Subject line, opening, CTA |
| Landing page | Conversion % | Headline, CTA, layout, copy |
| Finance forecasting | MAPE vs actuals | Model parameters, assumptions |
| Ad creative | CTR | Headlines, images, copy |
| Product features | Usage/retention | Feature placement, onboarding |
| Content | Open/click rate | Subject, format, timing |
| Sales | Discovery-to-proposal % | Discovery questions, follow-up timing |

### Auto-Research Readiness

| Iteration Speed | Subjective evaluation | Automated evaluation |
|---|---|---|
| Seconds | — | Code generation, ad bids, algo trading |
| Hours-Days | A/B copy, content moderation | Supply chain routing |
| Months | Long-form creative, therapy | — |

**Only implement auto-research on the fast + automated cells.** Manual evaluation kills the loop.

### Implementation (Karpathy's Repo)

```bash
# Clone Karpathy's auto-research repo
git clone https://github.com/karpathy/auto-research

# Adapt program.md to your use case
# DO NOT tweak the agent code — only tweak the instructions

# Set evaluation metric
# Get API key for the measurement system (Instantly, Mixpanel, etc.)

# Set GitHub Action cron
# Add Slack webhook for notifications on new variants

# Let it run for 4 weeks. Compare baseline vs winners.
```

**Cost reality:** 4-hour loop on cold email: ~$5-10/day. After 500-1000 runs, consolidate learnings to prevent unbounded growth.

**When NOT to use:** Slow feedback loops (weeks per measurement), subjective metrics without proxies, no API access.

---

## 13. Boris's Production Rules

*From the creator of Claude Code and Claude Cowork. His viral 99,000-bookmark Twitter post.*

### Rule 1 — Run Tasks in Parallel, Not Sequentially

The old mode: go deep on one task. The new mode: tend your agents like a manager.

Boris's actual workflow:
1. Start task in Tab 1 → once Claude is making a plan, switch to Tab 2
2. Start second task in Tab 2 → once Claude has a plan, switch to Tab 3
3. When you've run out of immediate tasks → go back to Tab 1
4. Review plan. Adjust if needed. Switch to auto-accept. Claude executes.
5. Cycle between tabs, reviewing and steering

### Rule 2 — 5-10 Claude Code Sessions in Parallel

Boris runs sessions across: terminal + web + iOS + Android. Starts 3 sessions from his phone every morning before the laptop is even open.

> "If you asked me a year ago, I would never have predicted that the way I code now is probably half on my phone. It just sort of works."

### Rule 3 — Use Opus 4 with Thinking for Everything

> "It's the best coding model I've ever used. Even though it's bigger and slower, since you have to steer it less and it's better at tool use, it's almost always faster than a smaller model in the end. And cheaper. Counter-intuitive, but the smarter model uses fewer tokens overall."

**Practical implication:** Don't default to Sonnet to save money. Opus with thinking often costs less total because it gets it right faster with fewer correction loops.

### Rule 4 — Team-Shared CLAUDE.md, Checked Into Git

- Whole team contributes multiple times a week
- When Claude does something wrong: add it to CLAUDE.md immediately
- Other teams maintain their own CLAUDE.md
- No special format required — it's just a text file

### Rule 5 — Tag @claude on PRs to Update CLAUDE.md

Use the Claude Code GitHub Action (`/install-github-action`). Then:
- Tag `@claude` on any PR or issue
- Claude fixes the issue and/or updates CLAUDE.md with the lesson
- The same mistake never needs to be pointed out twice

**This is compound engineering.** Your codebase literally teaches itself via Claude over time.

### Rule 6 — Almost All Sessions Start in Plan Mode

> "Planning is just the most underused feature in Claude Code. I would say it's still underused. I use it for almost all my sessions."

Workflow: Plan Mode → iterate on plan until it's good → switch to auto-accept → Claude one-shots it.

> "Once the plan is good, the code is good. This was definitely not the case with previous models. Opus 4.5 changed it."

### Rule 13 — Give Claude a Way to Verify Its Output

> "Imagine you're a painter who has to make photorealistic paintings — but you wear a blindfold. It's not going to be good. Same with Claude."

**Boris's top 3 for better Claude Code performance:**
1. Use Opus 4 with thinking — always
2. Have a good CLAUDE.md
3. Give Claude a way to verify its output

**What verification looks like:**
- Engineering: run tests, start a server, test in browser
- App development: Chrome extension → Claude tests its own work in the browser
- Writing: have Claude critique its own draft, then rewrite
- Finance: audit gates at each stage before proceeding

---

## 14. Parallel Execution

*Multi-tab is the new multitasking.*

### The Mental Model Shift

**Old mode:** Go deep on one task. Finish it. Start next.  
**New mode:** Start multiple tasks. Tend them like a manager. Harvest outputs.

This is the single biggest productivity multiplier available right now. Most people never switch to this mode.

### Practical Parallel Setup

**Claude Code:**
- Open 5-10 terminal sessions or browser tabs
- Each runs an independent Claude Code session with its own context
- Distribute tasks: Tab 1 handles feature A, Tab 2 handles feature B, Tab 3 handles test writing
- While one plans, you're reviewing another's output, while a third is executing

**Cowork:**
- Multiple parallel Cowork tasks running simultaneously
- "Once Cowork is making a plan, switch to the next tab"
- Return to review and steer each task as it needs attention

**Cross-device:**
- Morning: start long-running tasks from phone (iOS/Android Claude)
- Desktop: pick up, review, redirect
- Kick off background research or automation while you work on foreground tasks

### The Parallel Architecture Decision Tree

```
Is this task fully self-contained (clear start, end, output)?
├── Yes → Candidate for subagent or parallel session
└── No → Keep in main context

Does this task require you to steer mid-execution?
├── Yes → Keep close (main context or Cowork with monitoring)
└── No → Perfect for delegation

Is this parallelisable with another task?
├── Yes → Run both simultaneously
└── No → Sequential
```

### Tasks That Parallelise Well

- Code review of multiple modules simultaneously
- Research on multiple topics at once
- Generating multiple variants (5 subject lines, 3 landing page versions)
- Background data processing while you work on analysis
- Running test suites while writing new features
- Documentation generation while implementing

---

## 15. Model Selection

*The right model for the right task. Don't default.*

### The Hierarchy

| Model | Use for | Don't use for |
|---|---|---|
| **Opus 4** | Complex architecture, hard debugging, security review, long agentic sessions, anything where quality is paramount | Simple queries, high-volume processing |
| **Sonnet 4** | Standard development, analysis, writing, most coding tasks | The hardest architectural decisions |
| **Haiku 4** | Classification, filtering, extraction, high-volume cheap tasks, routing decisions | Anything requiring real reasoning |

### Boris's Counter-Intuitive Rule

> "Use Opus 4 with thinking for everything. Even though it's bigger and slower, since you have to steer it less, it's almost always faster and cheaper in the end."

The math: Opus gets it right in 2 attempts. Sonnet takes 6. The total token cost of 6 Sonnet calls + your review time > 2 Opus calls with thinking.

**Where this breaks down:** High-volume, clearly defined tasks where you're running thousands of calls. For a classification pipeline processing 100K items, Haiku wins. For a complex refactor you'll review once, Opus wins.

### Model Routing Pattern (for Applications)

```python
def route_to_model(task_type: str) -> str:
    routes = {
        'classify': 'claude-haiku-4-5',
        'extract': 'claude-haiku-4-5',
        'filter': 'claude-haiku-4-5',
        'standard': 'claude-sonnet-4-6',
        'draft': 'claude-sonnet-4-6',
        'analyse': 'claude-sonnet-4-6',
        'architect': 'claude-opus-4-7',
        'security_review': 'claude-opus-4-7',
        'complex_debug': 'claude-opus-4-7',
    }
    return routes.get(task_type, 'claude-sonnet-4-6')
```

### When to Use Thinking Mode

| Use | Skip |
|---|---|
| Architecture decisions with multiple trade-offs | Simple CRUD |
| Debugging non-obvious failures | Writing boilerplate |
| Security-sensitive review | Adding a field to a model |
| Designing complex data models | Format fixes |
| Multi-system integration | Generating straightforward tests |

---

## 16. Finance & FP&A Workflows

*Luke Finance's 9-stage boardroom-ready methodology.*

### The Core Principle

Generic prompts produce fragile, non-auditable outputs. A boardroom presentation requires: every formula traceable, every number defensible, every recommendation backed by data. That requires a structured workflow, not a single prompt.

### The 9-Stage Methodology

**Stage 1 — Source Collection (Data Ingestion)**
Before any analysis: verify inputs. The biggest modeling errors come from inputs never examined — mislabeled columns, half-filled tables, covenants buried in narrative text.

```
Run ingestion prompt → Claude inventories every sheet, every field, every 
structural dependency BEFORE analysis → confidence score per sheet → 
3 clear next actions to complete ingestion
```
*Rule: Save untouched baseline workbook before ingestion. Never work on the original.*

**Stage 2 — Persona Configuration**
Transform Claude from generic chatbot into CFO/FP&A analyst:
- Finance terminology only
- Cite exact sheets/columns in every response
- Show step-by-step calculation logic
- Flag data quality issues before proceeding
- Frame recommendations with trade-offs and risks

*Rule: Require Claude to explicitly confirm rule acceptance. Include 3 demo examples before proceeding.*

**Stage 3 — Plan-First Prompting**
Generate the plan before touching anything:
- 6-12 step prioritised plan
- Each step: objective, sheets involved, inputs, outputs, acceptance checks, "do not proceed if" gate
- No formulas. No fixes. No execution. Just the plan.

*Output: Copy finalized plan into a sheet titled `stage_checklist`. Formal governance artifact.*

**Stage 4 — Scope Control**
Financial workbooks have dozens of sheets. Claude seeing everything = wrong context, hallucinated joins, mixed data.
- Create `input_history` table with only the data you're using
- Transparent mapping log — all mismatches documented (not auto-fixed)
- Full trace from source to output

**Stage 5 — Three-Statement Model Foundation**
Every formula, every link, every audit check before touching valuation:
- Income statement → balance sheet → cash flow statement, all fully linked
- Driver-based (variable inputs drive outputs — not hard-coded numbers)
- Every formula auditable: no hidden logic

**Stage 6 — Valuation Layer**
DCF built on top of verified three-statement model:
- Explicit assumptions sheet
- Sensitivity tables (two-variable: growth rate × discount rate)
- Scenario analysis (bear/base/bull)
- All assumptions visible and challengeable

**Stage 7 — Audit & Review**
Before any output leaves:
- Formula audit: every cell traces back to an input or a formula, never a hard-coded number
- Cross-check: income statement totals match balance sheet changes
- Covenant check: are there debt covenants? Do the projections respect them?
- Sanity check: do the numbers make business sense?

**Stage 8 — Executive Summary**
One-page: key findings, assumptions, risks, recommendations with data references. Written for someone who won't read the model.

**Stage 9 — Presentation Layer**
Convert model insights into boardroom-ready format:
- One slide per key message
- Supporting data table for each chart
- Source citation on every number
- Risk section — what would change this conclusion?

### Finance-Specific Claude Rules

- Always select Opus 4.5 for structural reasoning (Stage 1 ingestion, Stage 3 planning)
- Use "Build Financial Models" button specifically (not generic chat mode) for formula generation
- Never let Claude auto-fix issues during ingestion or planning stages — document, then fix
- Every recommendation must cite specific cells/rows, not general observations
- Add audit gate prompts: "Before proceeding, confirm: [specific check]. Do not proceed if [condition]."

### The Rareliquid Test (From JPMorgan Banker)

A former JPM banker tested Claude on a full DCF valuation. Results:
- Mechanics: excellent (formula construction, structure, sensitivity tables)
- Reasoning: needs grounding (Claude will produce a DCF with whatever assumptions you give it — it needs the right inputs and will also assume things if not provided)
- Verdict: Use Claude as the analyst doing the mechanics; you provide the judgment on assumptions

**Practical rule:** Claude builds the model. You own the assumptions. The output is only as good as your inputs and your review.

---

## 17. Building & Selling

*From the Build & Sell with Claude Code course and Nick Saraev's $4M/year operation.*

### The Business Model Stack

**Tier 1 — Services (~$5K-15K)**
Use Claude to deliver client work faster. Research, analysis, content, code — at 5-10× the speed. Your margin is the difference between Claude's cost and your billable rate.

**Tier 2 — Productized Services (~$15K-30K)**
Recurring deliverables: monthly research reports, ongoing content production, automated analysis pipelines. Built once on Claude infrastructure, delivered repeatedly. Margin compounds.

**Tier 3 — Automation Products (~$30K-75K+)**
Software products built with Claude. Claude handles the intelligence layer; you provide the distribution, the interface, and the specialisation. Your Claude-powered product does things a generic Claude subscription can't.

**Auto-Research Services (Highest Margin)**
> "We run more tests than anyone else" is a genuinely strong pitch.

$5K starter / $30K standard / $75K+ premium for companies that need systematic optimisation with objective metrics. You supply the infrastructure; they supply the data and the objective.

### The Vertical Skill Opportunity (Greg Isenberg + Boris)

Every industry has software that Claude doesn't natively know how to operate. AutoCAD users. Salesforce power users. Bloomberg terminal users.

Build a skill that makes Claude a specialist in that vertical tool. You become the "AutoCAD AI expert" or the "Salesforce automation consultant." The skill is the product.

### Nick Saraev's $4M Operation

- 2,000+ students in courses
- Business managed primarily through AI agents and skills
- Every process has a skill. Every skill is in a skill system. Every system runs with minimal human time.
- Key lesson: skills applied to **specific revenue-producing business cases**, not glorified personal assistants. The ROI comes from business process automation, not personal productivity.

---

## 18. The Diagnostic Framework

*When something goes wrong, stop retrying randomly. Use this.*

### Level 1 — Prompt Diagnosis

Before anything else, re-read your prompt as if you're seeing it for the first time:
1. Is the role specific enough? (Not "expert" — what specific expertise?)
2. Is the task one clear deliverable? (Not "help me with X")
3. Is the format specified? (Not "write something good")
4. Are there implicit assumptions you haven't stated?
5. Are there conflicting instructions?

**Half of "AI problems" are prompt problems.**

### Level 2 — Property Diagnosis

| Symptom | Property | Fix |
|---|---|---|
| Confident but factually wrong | Next Token Prediction | Verify; provide correct facts explicitly |
| Missing recent events/data | Knowledge | Tell it the current situation |
| Forgot earlier context | Working Memory | Restate; move to top of prompt |
| Ignored an instruction | Steerability | Clarify; add "because" clause; check for conflicts |
| Output in wrong format | Steerability | Show a format example; use prefilling |
| Hallucinated citation/stat | Knowledge + NTP | "If you don't know, say so. Don't guess." |
| Generic output despite specific prompt | Description | Add one example; add more constraints |

### Level 3 — Constraint Fixes

Add these explicit permission and constraint phrases:
- `"If the information is insufficient, say so. Do not guess."` → cuts hallucinations
- `"Cite the exact [line/section/sheet] for every claim."` → forces groundedness
- `"Do not proceed to [next step] until you have confirmed [check]."` → audit gates
- `"Before responding, re-read the [instruction/constraint] above."` → context priming

### Level 4 — The iterative fix
```
1. Get draft
2. "Critique this response. What's weak, wrong, missing, or redundant?"
3. "Rewrite it addressing all the issues you found."
```
This almost always produces a dramatically better second output than any amount of prompt engineering on the first.

---

## 19. Master Implementation Roadmap

*From zero to fully operational. Sequenced by leverage, not complexity.*

### Phase 0: Decisions (1 hour)

Answer these before touching anything:

1. **Primary mode?** Chat-heavy, Cowork-heavy, or Code-heavy work?
2. **Knowledge base level?** Where are you: auto-memory → CLAUDE.md → state files → Obsidian?
3. **Infrastructure?** Direct API, AWS Bedrock, or Google Vertex?
4. **Team vs. solo?** Team → shared CLAUDE.md in git from day one
5. **Auto-research candidate?** One optimization with: clear metric + fast feedback + API access?

---

### Phase 1: Foundations (Week 1)

**Day 1:**
- [ ] Install Claude Code in all environments (terminal, VS Code, Claude Desktop)
- [ ] Run `/init` in every active project → edit generated CLAUDE.md
- [ ] Set up `~/.claude/skills/` for global skills
- [ ] Set Approval Mode as default

**Day 2-3:**
- [ ] Complete Claude 101 → set up Projects for all active work areas
- [ ] Complete AI Fluency: Framework & Foundations → adopt 4D checklist
- [ ] Set up one Project per active client/domain with key documents pinned

**Day 4-5:**
- [ ] Write your first 3 global skills (choose from your most-repeated tasks)
- [ ] Set up the Agentic OS Layer 1-2: user.md + personality.md via AI interview

**End of Week 1 deliverable:** Every project has CLAUDE.md. You have 3 skills. You have your identity files. The 4D Framework is a habit.

---

### Phase 2: Cowork & Core Workflows (Week 2)

- [ ] Complete Introduction to Claude Cowork → set up context files and first scheduled task
- [ ] Install Cowork plugins relevant to your tools (Obsidian, browser, Excel)
- [ ] Set up 3 scheduled Cowork tasks (daily brief, weekly report, research template)
- [ ] Build your first 3 project-level skills (code review, doc generator, research synthesis)
- [ ] Implement the Karpathy Wiki structure for your primary knowledge domain

**Master the task loop:**
- Describe → Plan → Review plan → Execute → Steer → Review output
- Never skip the plan review. Even once.

**End of Week 2 deliverable:** Cowork running scheduled tasks. Obsidian wiki started. 6 total skills operational.

---

### Phase 3: Code & Developer Workflow (Week 3)

- [ ] Complete Claude Code 101 → implement Explore→Plan→Code→Commit as default rhythm
- [ ] Complete Claude Code in Action → build custom command library
- [ ] Install 3 core hooks: post-edit linter, pre-commit test runner, session log
- [ ] Create 3 subagents: code-reviewer, doc-generator, researcher

**The parallel work shift:**
- Switch from sequential to parallel sessions
- Start 3 tasks simultaneously, tend them as manager

**End of Week 3 deliverable:** E→P→C→C is your default rhythm. 3 hooks active. 3 subagents created. Running 3+ parallel sessions.

---

### Phase 4: Memory Architecture (Week 4-5)

- [ ] Build the 7-Layer Agentic OS fully:
  - Layer 1-2: Identity files via AI interview
  - Layer 3: Context files (team, product, customers, etc.)
  - Layer 4: Skills structured and linked
  - Layer 5: MCPs connected (filesystem, browser, primary data tool)
  - Layer 6: Verification patterns per task type
  - Layer 7: Defer until layers 1-6 are stable

- [ ] Complete Introduction to Agent Skills → build team skill library in repo
- [ ] Complete Introduction to Subagents → implement parallel analysis pattern

**End of Week 4-5 deliverable:** Full 7-layer OS running. Team skills committed to git. Parallel subagent workflows tested.

---

### Phase 5: Automation (Week 6-7)

- [ ] Build first skill system (chain 3+ skills into a pipeline)
- [ ] Set up recurring Cowork automations:
  - Daily brief (calendar + tasks + recent files)
  - Weekly status report (project folders → summary)
  - Research automation (trigger → research → synthesis doc)
- [ ] Implement GitHub integration for automated PR review
- [ ] MCP: Build server for primary data source

**Boris's automation recipes:**
- `/loop babysit all my PRs, autofix build issues`
- `/loop every morning, Slack MCP summary of top posts I was tagged in`

**End of Week 6-7 deliverable:** 3+ automated workflows running without manual trigger. GitHub PR review automated.

---

### Phase 6: Auto-Research Pilot (Week 8-9)

Pick one optimization from Phase 0 decision 5. Run the Karpathy auto-research loop.

- [ ] Clone auto-research repo
- [ ] Adapt `program.md` to your use case
- [ ] Set objective metric + API access
- [ ] Set GitHub Action cron
- [ ] Add Slack webhook notifications
- [ ] Run 4 weeks → compare baseline vs winners

**End of Week 8-9 deliverable:** One auto-research loop running autonomously. First results incoming.

---

### Phase 7: Advanced Technical (Week 10+)

- [ ] Complete Building with the Claude API → automated prompt eval pipeline
- [ ] Complete Introduction to MCP → additional MCP servers
- [ ] Complete MCP Advanced Topics → production deployment
- [ ] If AWS: Claude with Amazon Bedrock
- [ ] If GCP: Claude with Google Vertex AI
- [ ] Implement prompt caching on any system prompt that stays constant
- [ ] Build model routing layer (Haiku for classification, Sonnet for standard, Opus for complex)

---

### Ongoing Practices (Every Week Forever)

- **CLAUDE.md:** When Claude does something wrong, add it immediately
- **Skills:** When you do the same thing 3 times, build a skill
- **Review:** Weekly 30-min review of skill outputs, tweak descriptions, remove unused skills
- **Learning:** When auto-research surfaces a winner, understand why before scaling
- **Compound engineering:** Every PR/issue → @claude → CLAUDE.md update → permanent lesson

---

## The Operating Principles (Master Summary)

These are the cross-cutting truths from all 70+ videos and 17 courses:

---

> **"Setup is everything. Five minutes of folder structure and MD files saves hours every week."**

> **"Use Projects for anything you do more than once. Memory is what separates serious users from everyone else."**

> **"Scheduled tasks are the real unlock — moving from using AI to having AI work for you."**

> **"Apply 80/20. Claude handles 80% of execution. Keep 20% under human judgment."**

> **"The 99% failure mode is treating Claude as a chatbot. Delegation, not conversation."**

> **"If you have an SOP, you have a skill. Copy it, feed it, build the skill."**

> **"Skills beat isolated prompts 10× over. Skill systems beat skills 10× over."**

> **"RAG is for some, not all. Start with Obsidian. Don't skip to graph RAG because it sounds sophisticated."**

> **"Auto-research is the new work primitive. Anywhere you have a metric, an API, and fast iteration — apply it."**

> **"Multi-tab is the new multitasking. Plan in tab 1. Switch to tab 2. Tend your agents like a manager."**

> **"Once the plan is good, the code is good. Always start in Plan Mode."**

> **"Verification beats confidence. Always have agents verify their own output. A painter wearing a blindfold won't make photorealistic paintings."**

> **"The smarter model is often cheaper. Opus gets it right in 2 attempts. Sonnet takes 6. Do the math."**

> **"The compounding return: your first agent took a weekend. Your fifth takes hours. Build the foundation."**

> **"There's no one right way to use this. It's like one of those find-your-own-path books. See what's useful, see what's not, find your own workflows."** — Boris, creator of Claude Code

---

*This guide synthesises: 17 Anthropic SkillJar courses + 70+ videos from Nick Saraev, Simon Scrapes, Chase AI, Greg Isenberg, Boris (Cowork creator), Luke Finance, Karpathy frameworks, AI Daily Brief, and more. Compiled May 2026.*
