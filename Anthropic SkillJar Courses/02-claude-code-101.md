# Claude Code 101 — Research Notes
**Source:** https://anthropic.skilljar.com/claude-code-101  
**Date captured:** 2026-05-05  
**Status:** Registration required (likely free)  
**Type:** Developer onboarding course — agentic coding  

---

## Overview

The foundational developer course for Claude Code — Anthropic's terminal-based AI coding agent. Addresses the conceptual shift from "AI autocomplete" to "AI agent": understanding agentic loops, context windows, tools, permissions, and the Explore → Plan → Code → Commit workflow. Also covers installation across all environments and how to customise Claude Code to your setup.

**Target audience:** Developers new to AI coding agents, or developers using GitHub Copilot/Cursor who haven't worked with agentic tools  
**Prerequisites:** Basic development experience; command line familiarity  
**Cost:** Likely free (registration required)  
**Certificate:** Not explicitly mentioned  

---

## Full Curriculum

### Section 1 — What is Claude Code?
Conceptual foundation before touching a single command:
- **The agentic loop** — How Claude Code actually works: reads code → forms a plan → executes tools (bash, file read/write, search) → observes results → iterates. This is a read-plan-act-observe cycle, not a chat.
- **Context window mechanics** — What Claude can "see" at any time; why large codebases require deliberate context management; what falls off the edge when context fills
- **Tools and permissions** — The tool system: Bash, file read/write, search; how permissions govern what Claude is allowed to do; why you should care about tool scope

### Section 2 — Your First Prompt
- **Installation across environments** — Terminal, VS Code, JetBrains, Claude Desktop, web. Key insight: Claude Code runs everywhere, not just the terminal
- **Approval mode vs. auto-accept** — In approval mode, you review every action before it runs. Auto-accept lets Claude run freely. The course teaches when to use which
- **Plan Mode** — Claude drafts a plan before executing. Critical for complex or risky tasks — review the plan before anything touches files

### Section 3 — Daily Workflows
- **Explore → Plan → Code → Commit** — The repeatable task rhythm:
  1. **Explore**: Claude reads the codebase, understands the context
  2. **Plan**: Claude proposes an approach (reviewable in Plan Mode)
  3. **Code**: Claude implements, running tests and linting as it goes
  4. **Commit**: Claude stages, writes a commit message, commits
- **Code review with Claude Code** — Using Claude to review PRs, summarise diffs, and flag issues
- **Context management** — `/compact` (summarise and compress context), `/clear` (reset context), `/context` (view what Claude can see); essential for keeping long sessions productive

### Section 4 — Customising Claude Code
- **CLAUDE.md files** — Project-level instruction files that persist across sessions. Claude reads this at startup. Contains conventions, style guides, build commands, test patterns. This is how you stop repeating yourself.
- **Custom subagents** — Building specialised sub-agents for tasks you run often (e.g., a dedicated "documentation writer" or "test generator")
- **Skills** — Reusable markdown instruction files that Claude applies automatically; distinct from CLAUDE.md in that they're invokable on-demand or triggered by task type
- **MCP servers** — Connecting external systems (databases, APIs, web) directly into Claude Code's tool space
- **Hooks** — Shell scripts that run before/after Claude actions; used to add deterministic guardrails (e.g., run linter after every code change, prevent certain commands)

---

## Key Concepts

| Concept | What it is | Why it matters |
|---|---|---|
| Agentic loop | Read → Plan → Act → Observe cycle | Mental model for understanding Claude Code behaviour |
| Context window | What Claude can see at any moment | Governs accuracy; must be managed on long sessions |
| Tools | Bash, file read/write, search, etc. | Claude's hands; permissions determine safety |
| CLAUDE.md | Project memory file | Persist conventions without repeating them |
| Plan Mode | Draft plan before execution | Safety check for complex/risky tasks |
| Approval mode | Review every action before it runs | Essential when learning or in production code |
| Explore → Plan → Code → Commit | Task rhythm | Repeatable, consistent workflow |
| Hooks | Pre/post action scripts | Deterministic guardrails around Claude's autonomy |
| /compact, /clear, /context | Context management commands | Keep long sessions accurate and efficient |

---

## Connections to Other Courses

- **Claude Code in Action** — Practical companion; walks through real workflows with Claude Code in action
- **Introduction to Agent Skills** — Deep dive on the Skills system referenced in Section 4
- **Introduction to Subagents** — Deep dive on custom subagents referenced in Section 4
- **Building with the Claude API** — If you want to go beyond Claude Code into programmatic API use
- **Introduction to MCP** — Full course on the MCP integration mentioned in Section 4

---

## How to Operationalise in Our Workflow

### Setup checklist (do this once)
1. **Install Claude Code in all environments you use:** terminal, VS Code or JetBrains, Claude Desktop
2. **Start every new project with a CLAUDE.md file.** Minimum content:
   - Project purpose in 2–3 sentences
   - Stack and key dependencies
   - Build, test, and lint commands
   - Coding conventions and naming patterns
   - Anything you'd tell a new developer on day 1
3. **Set approval mode as your default.** Switch to auto-accept only for well-understood, low-risk tasks (e.g., generating boilerplate, writing tests for existing code you've already reviewed)

### Daily workflow integration
- **Never start a Claude Code session without a plan.** Use Plan Mode for any task touching more than 2 files or that has side effects (DB writes, API calls, deployments)
- **Use Explore before Code.** Type a task → let Claude explore first → review its understanding → then say "proceed". Rushing to Code without Explore leads to wrong assumptions.
- **Commit frequently.** Let Claude commit after each atomic unit of work. This creates a rollback point and a clear audit trail.

### Context hygiene
- Run `/compact` when a session exceeds ~30 exchanges or when switching to a different part of the codebase
- Run `/clear` when starting a genuinely new task in the same terminal session
- Pin essential files explicitly with `@filename` rather than letting Claude discover them

### Guardrails to implement via hooks
- Post-edit hook: run linter/formatter automatically after every file edit
- Pre-commit hook: run tests; block commit if tests fail
- Log hook: write a session log of all actions taken (useful for audit)

### For our specific context
- CLAUDE.md is the most high-leverage thing to set up immediately — it's your persistent memory across sessions
- The Explore → Plan → Code → Commit loop should become the standard rhythm for any coding task
- Hooks are how you enforce team standards without relying on Claude remembering preferences
