**AI Agents Full Course 2026 (2 Hours)**

*Nick Saraev --- Master Agentic AI*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=EsTrWCV0Ph4

*Prepared: May 2026*

**Course Premise**

Definitive course on AI agents. The host teaches over 2,000 people personally and runs a \$4M/year business with AI agents. No programming required --- host has no formal computer science degree. Platform-agnostic --- works for Codex, Anti-Gravity, Claude Code.

**Opening Demo**

Host shows 5 AI agents controlling 5 separate Chrome browsers performing economically valuable activities --- going to lead websites, filling out contact forms with personalized outreach. The kind of work that would have been absurd just months ago.

**Course Topics**

-   Core agent loop (platform-independent).

-   3 major platforms --- Codex, Anti-Gravity, Claude Code (sign-up demos).

-   What each platform is best/worst at.

-   Self-modifying agent instructions --- agent rewrites own rules to minimize errors.

-   Multi-agent MCP orchestration --- Codex/Gemini/Claude as MCP servers in one thread.

-   Video-to-action pipelines --- agents learn from YouTube videos.

-   Stochastic multi-agent consensus.

-   Agent chat rooms.

-   Sub-agent verification loops.

-   Prompt contracts.

-   Reverse prompting.

-   Context management.

-   Token pricing and optimization.

**Core Agent Loop**

Every agent platform has the same loop:

1.  Receive task.

2.  Make plan.

3.  Execute step (potentially with tool calls).

4.  Verify result.

5.  Iterate or finish.

Strength of agents = parallelization. Multiple instances simultaneously. Less smart per individual than humans, but vastly faster at scaling.

**Skills (Standardized SOPs)**

Skills convert flexibility (variance) into deterministic paths. Spec format:

-   Three hyphens at top and bottom of metadata header.

-   Name (e.g., \'pdf-processing\').

-   Description (e.g., \'extract text and tables from PDFs\').

-   License/metadata optional.

-   Body: detailed instructions, optional scripts, optional reference docs.

**Demonstrated: Algorithmic Art Skill**

Host copies anthropic/skills/algorithmic-art/skill.md --- a long skill that creates algorithmic art with a particular library. Pastes into Claude Code: \'create things according to this skill spec.\' Claude builds the skill directory, templates, and produces algorithmic art generator. Works in browser as embedded canvas.

**Multi-Agent MCP Orchestration**

Pattern for combining the best of each model. Stack:

-   Manager (Claude) --- receives task.

-   Splits into sub-tasks.

-   Routes UI to Gemini (better at multimodal).

-   Routes API/backend to Codex (better at code).

-   Routes testing to Codex.

-   Final validation by Claude.

Requires registering each as MCP server. Router decides routing based on task type.

**Stochastic Multi-Agent Consensus**

Spawn N agents with same/varied prompts. Aggregate by consensus. Used for: decision-making, ranking, strategic analysis, hallucination filtering. Each agent samples different parts of search space simultaneously.

**Agent Chat Rooms**

Centralized place for agents to debate ideas. Push toward higher quality. Reduces single-agent confidence biases.

**Sub-Agent Verification Loops**

Agents review each other\'s work in real time. Catches errors one agent misses. Like pull request review for AI.

**Video-to-Action Pipelines**

Teach agents from YouTube transcripts. Workflow: download transcript → clean → parse instructions → agent executes the lesson. Useful for automation tutorials, sales training, technical procedures.

**Self-Modifying Agent Instructions**

Agent rewrites own rules to minimize errors. Pattern: after each task, agent reflects, identifies what went wrong, updates instruction file. Compounds intelligence over time.

**Prompt Contracts**

Formal input/output specifications. Define what an agent must produce in each role. Versioned. Tested. Like API contracts but for agents.

**Reverse Prompting**

Have the agent generate prompts for itself. Especially useful when you don\'t know exactly what you want --- describe outcome, agent crafts the prompt to achieve it, you tweak.

**Context Management**

-   Global CLAUDE.md --- wide-ranging user preferences.

-   Local CLAUDE.md --- project-specific.

-   Skills --- collapsed reusable workflows.

-   Inline prompt --- fresh task instructions.

-   Goal: collapse maximum functionality into minimum tokens --- model quality and cost both improve with shorter, focused contexts.

**Token Pricing & Optimization**

-   Use Sonnet for routine, Opus for complex reasoning, Haiku for cheap bulk.

-   Switch mid-session via /model.

-   Compress context with /compact.

-   Track via /cost.

-   Cache long-running prompts where applicable.

**Source**

AI Agents Full Course 2026: Master Agentic AI by Nick Saraev --- <https://www.youtube.com/watch?v=EsTrWCV0Ph4>
