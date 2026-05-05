# Introduction to Subagents — Research Notes
**Source:** https://anthropic.skilljar.com/introduction-to-subagents  
**Date captured:** 2026-05-05  
**Status:** Free — register to access  
**Type:** Claude Code feature course — subagent delegation  

---

## Overview

A course on Claude Code's subagent system — one of the most powerful tools for managing complex, context-heavy work. Subagents are isolated Claude instances that the main conversation can delegate tasks to; they run independently, produce a summary of their work, and return that summary to the main context — without polluting the main conversation with all the intermediate detail. Covers the full subagent lifecycle: when to use them, how to create them, how to design them for reliability, and common anti-patterns.

**Key value proposition:** "Sub-agents are one of the most practical ways to get more out of longer Claude Code sessions."

**Target audience:** Claude Code users managing complex, long-running, or parallel tasks  
**Prerequisites:** Claude Code actively in use; ideally Claude Code 101  
**Cost:** Free  

---

## How Subagents Work — The Core Mechanism

When you delegate to a subagent:
1. Claude Code spins up a separate context window (a new Claude instance)
2. The main context passes the subagent: a task description, any needed files/context, and a summary of what it needs to return
3. The subagent works independently — it can use all Claude Code tools: file reading, bash commands, web search, etc.
4. When the subagent finishes, it produces a structured summary
5. That summary returns to the main context — not the full working history

**Why this matters:** The main context only "sees" the final summary, not all the intermediate steps. This keeps the main conversation focused and prevents context window saturation on complex tasks.

---

## Full Curriculum

### Course overview content (verbatim from course page)
- How sub-agents work — what happens when Claude Code spins up a separate context window, how inputs flow in, and how summaries come back
- Creating custom sub-agents — using the `/agents` command to build sub-agents tailored to your workflow, from code reviewers to documentation generators
- Designing effective sub-agents — patterns that make sub-agents reliable, including structured output formats, obstacle reporting, and limiting tool access
- When to use them (and when not to) — practical guidance on where sub-agents help the most and the common anti-patterns to avoid

### Lesson 1 — What Are Subagents?
- The context window problem: long sessions accumulate context that degrades Claude's performance
- Subagents as the solution: delegate a task out; get back only what you need
- The architectural pattern: orchestrator (main context) + worker (subagent)
- Built-in vs. custom subagents:
  - **Built-in**: Claude Code ships with some built-in subagents (e.g., the Agent tool used by Claude Code internally)
  - **Custom**: You define specialised subagents for your specific recurring tasks

### Lesson 2 — Creating a Subagent
- The `/agents` command — interface for creating and managing custom subagents
- Subagent definition file — markdown file defining the agent's purpose, tools, and instructions
- Minimal subagent structure:
  ```markdown
  ---
  name: code-reviewer
  description: Reviews code for quality, security, and style issues
  tools: [read, grep, glob]
  ---
  
  You are a code reviewer. When given a file or diff:
  1. Check for security vulnerabilities
  2. Check for test coverage gaps
  3. Check for style violations
  Report findings in structured format: [SEVERITY] [FILE:LINE] [ISSUE] [RECOMMENDATION]
  ```
- Testing a subagent: invoke explicitly, check its output, refine

### Lesson 3 — Designing Effective Subagents
The practical patterns that make subagents reliable:

**1. Structured output formats**
Subagents should return information in a predictable format the main context can parse:
```markdown
## Summary
[2-3 sentence summary of what was done]

## Findings
- [Finding 1]
- [Finding 2]

## Recommendations
1. [Action 1]
2. [Action 2]

## Blockers
- [Anything that prevented task completion]
```

**2. Obstacle reporting**
A reliable subagent explicitly reports when it couldn't complete something:
- "Could not access file X due to permissions"
- "Found ambiguity in requirement Y — need clarification"
- "Test coverage analysis incomplete due to missing test framework"

Never silently skip — always surface blockers.

**3. Limiting tool access**
Restrict subagents to only the tools they need:
```markdown
tools: [read, grep, glob]  # Read-only — no bash, no write
```
A documentation generator shouldn't be able to run bash commands. Minimise blast radius.

**4. Explicit success criteria**
Tell the subagent what "done" looks like so it knows when to stop:
```markdown
You are finished when: all files in the specified directory have been reviewed 
and you have produced a finding for each one, OR you have reported why a file 
could not be reviewed.
```

### Lesson 4 — Using Subagents Effectively
When to use subagents (and when not to):

**Use subagents when:**
- Task requires reading many files (50+) — avoids filling main context with file contents
- Task is parallelisable — multiple subagents can run on different parts of a codebase simultaneously
- Task produces a lot of intermediate output that the main context doesn't need to see
- Task is well-defined and bounded (clear start, clear end, clear output format)
- You're doing the same type of task repeatedly (code review, test generation, documentation)

**Don't use subagents when:**
- Task requires continuous back-and-forth with you — subagents work in isolation; they can't ask you questions mid-task
- Task is short and simple — overhead of spinning up a subagent exceeds the benefit
- Task requires the full history of the main conversation — subagents get a summary, not the full context
- The task is ambiguous and likely to fail — clarify first, delegate second

---

## Key Concepts

| Concept | What it is | Why it matters |
|---|---|---|
| Isolated context window | Subagent has no access to main conversation | Keeps main context clean; subagent can't be distracted |
| Structured output | Consistent format for subagent return | Main context can reliably parse and use the results |
| Obstacle reporting | Explicit failure/blocker signalling | Prevents silent failures that corrupt downstream work |
| Tool restriction | `tools` frontmatter limits access | Safety and scope control |
| Success criteria | Explicit done condition | Prevents agents that loop indefinitely |
| `/agents` command | Interface for creating/managing subagents | The management UI |

---

## Subagents as an Architecture

Subagents enable patterns that aren't possible with a single context:

### Pattern 1: Parallel analysis
```
Main context: "Review all 20 modules for security issues"
→ Subagent-1: modules 1-7
→ Subagent-2: modules 8-14  
→ Subagent-3: modules 15-20
← Aggregate all findings into final report
```

### Pattern 2: Specialist pipeline
```
Main context: "Prepare the release"
→ Subagent-1 (test runner): run full test suite, report failures
← Summary: 3 tests failing in auth module
→ Subagent-2 (fix agent): fix the 3 failing tests
← Summary: tests fixed, here's the diff
→ Subagent-3 (changelog): write changelog from git log
← Summary: changelog ready
Main context: Everything assembled; ready to tag release
```

### Pattern 3: Research + synthesis
```
Main context: "Research how competitors implement X"
→ Subagent-1: web research (limited to research tools)
← Summary: found 5 implementations, here are the approaches
Main context: synthesise findings into recommendation
```

---

## Connections to Other Courses

- **Claude Code 101** — Introduces subagents conceptually; this is the full course
- **Introduction to Agent Skills** — Skills and subagents are complementary; skills are instructions applied in-context; subagents are out-of-context workers
- **Claude Code in Action** — Section on custom commands and workflows connects to subagent patterns
- **Building with the Claude API** — The multi-agent architecture section covers similar patterns at the API level

---

## How to Operationalise in Our Workflow

### Subagents to build immediately

**1. Code reviewer subagent**
```markdown
---
name: code-reviewer
description: Reviews code files for quality, security, and correctness
tools: [read, grep, glob]
---
Review for: security vulnerabilities, missing error handling, test coverage gaps, performance issues.
Output: structured findings list with severity and file/line references.
Report blockers explicitly if any file cannot be reviewed.
```

**2. Documentation generator subagent**
```markdown
---
name: doc-generator
description: Generates or updates documentation for a module or function
tools: [read, grep, glob, write]
---
Read the target code. Generate/update documentation. 
Output: what was created/updated and where.
Report if documentation cannot be generated due to unclear code.
```

**3. Test generator subagent**
```markdown
---
name: test-generator
description: Generates comprehensive tests for a file or function
tools: [read, grep, glob, write, bash]
---
Analyse the code. Generate tests. Run tests. Report coverage achieved.
Output: files created, tests passing, coverage percentage.
Report any test failures or edge cases that need human review.
```

**4. Research subagent**
```markdown
---
name: researcher
description: Researches a technical topic and returns a structured summary
tools: [web_search, read]
---
Research the given topic. Return: executive summary (3-5 sentences), key findings (bullet points), relevant sources, open questions.
Do not include raw search results — synthesise only.
```

### Operating guidelines
- Before delegating: write a clear, bounded task description. Ambiguous tasks produce ambiguous outputs.
- After a subagent returns: read the summary critically. Check for obstacles it reported. Verify key claims before acting on them.
- Build a library of tested subagent definitions in `.claude/agents/` and commit them to the repo.
- Don't run more than 5 parallel subagents at once unless you've tested the pattern — parallelism adds debugging complexity.

### For our specific context
- The parallel analysis pattern is immediately applicable to any codebase audit or large document analysis
- Custom subagents for our most common task types (review, doc, test, research) should be standard tooling
- Treating subagent output as a first draft to be reviewed (not accepted uncritically) is the right mental model
