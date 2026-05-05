# Claude Code in Action — Research Notes
**Source:** https://anthropic.skilljar.com/claude-code-in-action  
**Date captured:** 2026-05-05  
**Status:** Registration required  
**Type:** Practical video course — Claude Code workflows  

---

## Overview

A practical, workflow-focused course that goes beyond conceptual introduction (Claude Code 101) into real-world usage. Video-based ("practical walkthrough"). Covers Claude Code's tool system, context management, hotkeys, Plan Mode, Thinking Mode, custom commands, MCP integration, GitHub integration, and hooks. This is the "how do I actually use this day-to-day" companion to the more conceptual 101 course.

**Target audience:** Developers who've installed Claude Code but want to use it more effectively; those who've done Claude Code 101 and want applied practice  
**Prerequisites:** Basic CLI familiarity; Claude Code access and API key  
**Cost:** Registration required (likely free based on platform pattern)  
**Format:** Video-based (the scrape shows "video still being processed" notices — active content)  

---

## Full Curriculum

### Learning Objectives (verbatim from course)
1. Use Claude Code's core tools for file manipulation, command execution, and code analysis
2. Manage context effectively using `/init`, Claude.md files, and `@` mentions
3. Control conversation flow with a variety of hotkeys and commands
4. Enable Plan Mode and Thinking Mode for complex tasks requiring deeper analysis
5. Create custom commands for automating repetitive development workflows
6. Extend Claude Code with MCP servers to add browser automation and other capabilities
7. Set up GitHub integration for automated PR reviews and issue handling
8. Write hooks to add additional behavior into Claude Code

### Prerequisites (verbatim)
- Basic familiarity with command line interfaces
- Access to Claude Code and an API key

### Who This Course Is For
Developers learning to use Claude Code as a day-to-day development tool.

### Course Sections

#### Claude Code in Action (the main section)
This appears to be a single large section with video walkthroughs of real workflows. Based on learning objectives, it covers:

1. **Core tools walkthrough** — file manipulation (read, write, edit), command execution (bash), code analysis (search, grep, AST analysis). Understanding what tools are available and when each is used
2. **Context management deep dive**
   - `/init` — initialises a new CLAUDE.md for a project (auto-generates based on code analysis)
   - CLAUDE.md files — project-level persistent memory (already covered in 101, here shown in practice)
   - `@` mentions — explicitly scoping Claude's attention to specific files (`@src/auth.py @tests/test_auth.py`)
3. **Hotkeys and commands** — keyboard shortcuts and slash commands for controlling the session; likely covers `/compact`, `/clear`, `/model`, and others
4. **Plan Mode in practice** — real example of enabling Plan Mode for a complex task; reading and modifying the plan before approval
5. **Thinking Mode** — extended thinking for deep reasoning on hard problems; when to use it (complex architecture decisions, debugging tricky issues) vs. when it's overkill
6. **Custom commands** — creating slash commands that automate repetitive workflows (e.g., `/review` runs your code review checklist, `/deploy-check` verifies pre-deployment criteria)
7. **MCP server integration** — connecting an MCP server (likely the browser MCP or filesystem MCP) to add capabilities not built into Claude Code; real example shown
8. **GitHub integration** — setting up Claude Code to automatically review PRs, post comments, handle issues; useful for async code review workflows
9. **Hooks in practice** — writing a real hook (pre-commit test runner, post-edit linter); seeing how hooks interact with Claude's execution

---

## Key Concepts

| Concept | What it is | Why it matters |
|---|---|---|
| `/init` | Auto-generates CLAUDE.md from codebase analysis | Quickest way to set up project memory |
| `@` mentions | Scopes Claude's context to specific files | Precision over breadth; avoid context noise |
| Thinking Mode | Extended reasoning for complex problems | Better outcomes on hard tasks at token cost |
| Plan Mode | Explicit plan before execution | Safety + alignment for multi-step tasks |
| Custom commands | Slash commands for your recurring workflows | Codify expertise; stop re-explaining |
| MCP integration | External tool connection | Expand Claude Code's capabilities modularly |
| GitHub integration | Automated PR/issue handling | Async AI code review at scale |
| Hooks | Pre/post action scripts | Deterministic guardrails and automation |

---

## Connections to Other Courses

- **Claude Code 101** — Prerequisite; this course is the applied companion
- **Introduction to Agent Skills** — Skills are the user-facing equivalent of custom commands; conceptual overlap
- **Introduction to Subagents** — Subagents extend the pattern of "delegating to specialised helpers"
- **Introduction to MCP** — Full course on MCP; this course shows a practical MCP integration
- **Building with the Claude API** — If you want to go beyond CLI into programmatic API usage

---

## How to Operationalise in Our Workflow

### After completing this course: immediate implementations

#### 1. `/init` every project
Run `claude /init` in every project that doesn't have a CLAUDE.md. The auto-generated file won't be perfect, but it's 80% of the way there. Edit it to add:
- Architecture decisions that aren't obvious from code
- Non-obvious test patterns
- Deployment/environment specifics

#### 2. Build your custom command library
Create a `~/.claude/commands/` directory with personal commands. Start with:
```
/review → Run my code review checklist against the current file
/explain → Give me a plain-English explanation of what this function does and why
/test → Generate tests for the current file following our testing patterns
/docs → Update or create docstrings for the current function
/commit → Generate a conventional commit message for staged changes
```

Each command is a markdown file with instructions. Start with 3–5 and expand as you notice repetition.

#### 3. Set up the GitHub integration
Configure Claude Code to auto-review PRs in your main repositories. Suggested workflow:
- Claude posts an initial review comment within minutes of PR creation
- Flags obvious issues (style, missing tests, potential bugs)
- You do the final review, using Claude's as a first pass
This cuts review turnaround time significantly.

#### 4. Implement core hooks
Priority hooks to set up first:
```bash
# Post-edit: run linter
# Post-edit: run type checker
# Pre-commit: run tests (block if failing)
# Session-end: log summary to ~/claude-logs/YYYY-MM-DD.md
```

#### 5. Context management habits
- Use `@filename` whenever you know the relevant file upfront — don't make Claude search for it
- Use `/compact` at context ~50% full, not when it's already overflowed
- Name sessions meaningfully when running multiple parallel sessions

#### When to use Thinking Mode
| Use | Don't use |
|---|---|
| Architecture decisions with multiple trade-offs | Simple CRUD implementations |
| Debugging non-obvious failures | Writing boilerplate |
| Security-sensitive code review | Adding a field to a data model |
| Designing complex data models | Generating tests for trivial functions |
| Multi-system integration design | Formatting/style fixes |

### For our specific context
- The GitHub integration is highest-leverage for teams — set it up before anything else
- Custom commands are a direct path to team consistency: everyone can use the same `/review` or `/test` command
- Hooks are how you make Claude Code behaviour deterministic rather than hoping it remembers preferences
