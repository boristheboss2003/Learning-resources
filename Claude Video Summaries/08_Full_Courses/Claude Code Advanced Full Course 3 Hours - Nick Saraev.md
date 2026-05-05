**Claude Code Advanced Full Course (3 Hours)**

*Nick Saraev --- The Definitive Cloud Code Course for Advanced Users*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=UPtmKh1vMN8

*Prepared: May 2026*

**Course Premise**

The definitive Claude Code course for advanced users. The host runs a \$4M/year business using Claude Code and AI agents. Teaches \~2,000 people how to use these tools personally and in business. Assumes foundation of Claude Code experience --- for total beginners, recommends his 4-hour beginner course first.

**Course Outline**

-   CLAUDE.md and system prompts --- optimization for quality.

-   Agent harnesses --- building larger projects.

-   Agent teams --- extreme task parallelization.

-   Skills, sub-agents, organization.

-   Karpathy\'s auto-research approach for progressive improvement.

-   Browser automation --- computer-use, browser-use, when to use which.

-   Performance fluctuations and alternatives.

-   Workspace organization --- personal, business, client projects.

-   Security for larger projects (auto-mode, OAuth).

-   Future of work and Claude Code.

**Module 1 --- CLAUDE.md (Advanced System Prompts)**

CLAUDE.md is four things:

  -------------------------- ---------------------------------------------------------
  **Function**               **What It Does**
  Knowledge Compression      Summarizes workspace so Claude doesn\'t read every file
  Personal Preferences       Conventions Anthropic hasn\'t baked in yet
  Capabilities Declaration   Lists what Claude can do in this workspace
  Architecture Doc           How files are organized and what depends on what
  -------------------------- ---------------------------------------------------------

**Knowledge Compression Use**

Without CLAUDE.md: Claude reads every file in your codebase before reasoning. Slow, expensive. With CLAUDE.md: Claude reads the summary, knows where to drill down. 90% of file-by-file reads eliminated.

**Capabilities Declaration**

Without it, Claude says \'I don\'t have a built-in way to do this.\' Wastes time. With it, you itemize what Claude has access to: this skill, this MCP, this folder, this autonomous build flow. Claude knows what\'s possible.

**Module 2 --- Agent Harnesses**

Agent harness = orchestration layer for larger projects with multiple sub-agents. The host uses harnesses to build complex SaaS applications, multi-feature systems, and orchestrated workflows.

**Components**

-   Lead orchestrator agent.

-   Specialist sub-agents (frontend, backend, testing).

-   Shared task list.

-   CLAUDE.md per scope.

-   Worktrees per agent for isolation.

**Module 3 --- Agent Teams (Extreme Parallelization)**

Anthropic\'s experimental Agent Teams feature. Multiple Claude sessions communicating directly. Set CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1.

**Use Cases**

-   Research from competing angles.

-   Code review with multiple perspectives (security, performance, tests).

-   Debugging with competing hypotheses.

-   Frontend/backend/database in parallel.

**Stochastic Multi-Agent Consensus (Skill Demonstrated)**

Skill spawns N agents with same/slightly different prompts to independently analyze a problem. Aggregate by consensus. Use for: decision-making, ranking, strategic analysis, hallucination filtering, surfacing high-variance ideas.

**Demo: Tomatillo Sauce Brainstorm**

Host invokes skill with: \'Brainstorm all the different ways you can make a nice tasting sauce using tomatillos.\'

10 agents spawned with slightly different framings:

-   Conservative tradition-minded chef.

-   Adventurous boundary-pushing chef.

-   Challenge conventional wisdom.

-   Reasoning from first principles.

Result: 119 raw ideas, 52 unique. Salsa verde, tomatillo-avocado crema, Aji verde, Indian-influenced, Persian-influenced, Caribbean-Latin fusion, Total Blanc (French butter sauce using tomatillo pectin as natural emulsifier --- outlier).

**Model-Chat Skill (Debate Mode)**

Spawns 5 Claude instances in shared conversation room. They debate, disagree, converge. Round-robin turns with parallel execution. Triggers on \'chat,\' \'debate.\' 10-agent debate on tomatillo sauces produced more nuanced output than consensus alone --- agents challenged each other on tradeoffs.

**Module 4 --- Skills, Sub-Agents, Organization**

Already covered in foundation course. Advanced points:

-   Skills as standardized SOPs --- reduce variance.

-   Description fields critical for auto-invoking.

-   Skill spec format: title section with three hyphens above and below; name, description, optional license/metadata.

**Module 5 --- Karpathy Auto-Research**

Same approach covered in the dedicated auto-research video --- apply to any business optimization with metric and API.

**Module 6 --- Browser Automation**

  --------------------------- -----------------------------------------------------------------------------
  **Tool**                    **When to Use**
  Playwright CLI              Production-grade automation, faster than MCP, accessibility-tree-based
  Computer Use (Anthropic)    Visual interaction when Playwright doesn\'t work --- slower, more expensive
  Chrome DevTools MCP         Direct DOM manipulation
  Browser Use (open source)   Free alternative to Computer Use
  --------------------------- -----------------------------------------------------------------------------

**Module 7 --- Performance Fluctuations & Alternatives**

-   Claude has bad days --- known issue with API performance variation.

-   Mitigation: model selection (Opus for complex, Sonnet for routine, Haiku for cheap).

-   Multi-agent MCP orchestration --- let an orchestrator route to GPT-5.4, Gemini, Claude based on task fit.

-   Alternatives: Codex (OpenAI), OpenClaw (open source variant), Anti-Gravity (Google).

**Module 8 --- Workspace Organization**

**Three-Tier Pattern**

  ---------- --------------------------- -----------------------------------------------
  **Tier**   **Path**                    **Purpose**
  Personal   \~/work/personal/           Your own projects, hobbies, learning
  Business   \~/work/business/           Company operations, products, internal
  Client     \~/work/clients/\[name\]/   Per-client folders with CLAUDE.md inheritance
  ---------- --------------------------- -----------------------------------------------

CLAUDE.md inheritance: parent \~/work/CLAUDE.md → \~/work/clients/CLAUDE.md → \~/work/clients/clientA/CLAUDE.md. Override at deeper levels.

**Module 9 --- Security**

**Critical Security Pattern**

Claude Code logs every conversation in \~/.claude/. JSONL files line-by-line.

**Demo: Search for API Keys in Logs**

Run prompt: \'Search through Claude in the tilde folder for any conversation mentioning quetzalcoatl.\' Claude pulls long-running conversation log word-for-word. If you\'ve ever pasted an API key in chat, it\'s in your conversation log.

**80/20 Security**

Everything is hackable. Goal: dispel 90% of attackers with low-friction protections.

**Key Practices**

-   Never paste API keys in chat --- use .env files.

-   Never commit .env to git.

-   Add .env to .gitignore from project start.

-   Tell Claude in CLAUDE.md: \'Never read or display contents of .env files.\'

-   Reference secrets by name, not value: \'use the API key in ANTHROPIC_API_KEY.\'

-   Rotate keys regularly.

-   Use separate keys for dev/prod.

-   Audit log access --- review \~/.claude/ periodically and clear old conversations.

**Module 10 --- Future of Work**

Course closes with the host\'s view on where Claude Code goes:

-   Cloud Code becomes increasingly the predominant generator of productivity.

-   Operators who get fluent with these tools now compound advantages.

-   Build & sell economy emerging --- selling implementation services.

-   Memory systems and context engineering become core skills.

-   Agent teams and multi-model orchestration are next frontier.

**Source**

CLAUDE CODE ADVANCED FULL COURSE (3 HOURS) by Nick Saraev --- <https://www.youtube.com/watch?v=UPtmKh1vMN8>
