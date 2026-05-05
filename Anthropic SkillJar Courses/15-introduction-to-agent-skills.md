# Introduction to Agent Skills — Research Notes
**Source:** https://anthropic.skilljar.com/introduction-to-agent-skills  
**Date captured:** 2026-05-05  
**Status:** Free — register to access  
**Type:** Claude Code / Cowork feature course — Skills system  

---

## Overview

A dedicated course on the Skills system in Claude Code — one of the most powerful but underutilised customisation features. Skills are reusable markdown instruction files that Claude automatically applies when relevant, without the user needing to re-explain them each time. The course covers creating, configuring, and sharing Skills, plus how they fit into the broader Claude Code customisation landscape (vs. CLAUDE.md, hooks, subagents).

**Key framing:** "Stop repeating yourself and start teaching Claude once."

**Target audience:** Claude Code users who want to build reusable, consistent, team-shareable AI workflows  
**Prerequisites:** Claude Code installed and in active use  
**Cost:** Free  

---

## What Are Skills (Definition)

Skills are markdown files with a specific frontmatter format that Claude Code reads and applies to matching tasks:

```markdown
---
name: my-skill
description: Clear description that tells Claude when to apply this skill
---

# Instructions for Claude

When [matching context], do the following:
1. Step one
2. Step two
...
```

**Key mechanism:** The `description` field is the trigger — Claude reads it and decides whether to apply the skill based on matching the current task. This is called "trigger matching."

Skills live in `.claude/skills/` (project-level) or `~/.claude/skills/` (global).

---

## Full Curriculum

### Lesson 1 — What Are Skills?
- Skills vs. CLAUDE.md: CLAUDE.md is always-on project context; Skills are selectively applied based on task matching
- Skills vs. hooks: hooks are deterministic script triggers; Skills are intelligent instruction matching
- Skills vs. subagents: subagents are isolated context windows; Skills are instructions applied in the main context
- The trigger matching mechanism: Claude reads the description, matches to the current task, applies if relevant
- Skills directory structure: single files or multi-file skill packages

### Lesson 2 — Creating Your First Skill
- Writing the SKILL.md frontmatter: `name`, `description` (required); `allowed-tools` (optional restriction)
- Crafting effective descriptions: what makes a description reliably trigger? Clear task type, context signals, specific vs. generic language
- Progressive disclosure: keep the main SKILL.md lean; offload detailed reference material into sub-files linked from the main file
- Skill directory structure for complex skills:
  ```
  .claude/skills/
  ├── code-review.md          (main skill file — lean, clear instructions)
  ├── code-review/
  │   ├── checklist.md        (detailed checklist — linked from main)
  │   └── examples.md         (examples — linked when needed)
  ```

### Lesson 3 — Configuration and Multi-File Skills
- `allowed-tools` — Restrict which Claude Code tools a skill can use (e.g., a documentation skill that shouldn't be able to run bash commands)
- Scripts that execute without consuming context — Shell scripts or scripts that Claude can reference without reading their full content; keeps context window efficient
- Multi-file skill packages: when a skill is complex enough to need supporting reference material
- Skill loading mechanics: how Claude reads and prioritises skills

### Lesson 4 — Skills vs. Other Claude Code Features
Comprehensive comparison and decision framework:

| Feature | When to use |
|---|---|
| **Skills** | Reusable task-specific instructions; consistent behaviour across sessions |
| **CLAUDE.md** | Always-on project context; conventions, stack info, build commands |
| **Hooks** | Deterministic pre/post actions; linting, testing, logging |
| **Subagents** | Task delegation to isolated context; parallel or long-running work |
| **Custom commands** | Explicit slash commands the user invokes |

### Lesson 5 — Sharing Skills
- **Team sharing via repository** — Committing skills to your project repo (`.claude/skills/`) makes them available to all team members
- **Plugins** — Distributing skills more broadly through the plugin system; packaging for external distribution
- **Enterprise managed settings** — Organisation-wide skill deployment via admin configuration; ensures all employees have the same skills without manual setup
- Versioning and updating shared skills

### Lesson 6 — Troubleshooting Skills
- **Skills that won't trigger** — Description not specific enough; Claude not recognising the task match; skill not in the right directory
- **Priority conflicts** — Multiple skills matching the same task; how Claude resolves conflicts
- **Runtime errors** — Invalid frontmatter; missing linked files; tool restrictions blocking needed tools
- Debugging workflow: check skill loading, test description matching, verify file structure

---

## Key Concepts

| Concept | What it is | Why it matters |
|---|---|---|
| Trigger matching | Claude matches description to current task | The mechanism for automatic skill application |
| Progressive disclosure | Lean main file + detailed sub-files | Keeps context window efficient |
| `allowed-tools` | Tool restriction per skill | Safety and scope control |
| Plugin distribution | Packaging skills for sharing | Organisation-wide consistency |
| Enterprise managed settings | Admin-level skill deployment | Centralised consistency without per-user setup |
| Priority conflicts | Multiple matching skills | Must understand resolution order |

---

## Skill Design Principles

### Effective description writing (the most important thing)
The description is everything — it determines if/when Claude applies the skill.

**Bad description:** "Helpful instructions for various tasks"  
**Good description:** "When the user asks to review a pull request or code change, apply this code review checklist"

**Good description pattern:**
- Starts with "When..." or "Use when..."
- Specifies a concrete task type (not a vague domain)
- Avoids overlap with other skills (specificity prevents conflict)
- Is written from Claude's perspective (Claude reads it to decide)

### Progressive disclosure structure
```
code-review.md:
---
name: code-review
description: When reviewing code or a PR, apply this structured review process
---
## Process
1. Check for security issues → see [security checklist](code-review/security.md)
2. Check for test coverage → see [test standards](code-review/tests.md)
3. Check style → see [style guide](code-review/style.md)
```

This way, Claude loads the main file (small context cost), then loads sub-files only when they're referenced in the task.

---

## Skills to Build for Our Workflow

### Immediate high-value skills to create

**1. Code review skill**
```markdown
---
name: code-review
description: When reviewing code, a PR, or a diff, apply this review checklist
---
Review the code for: security vulnerabilities, missing tests, style violations, performance issues, documentation gaps.
```

**2. Documentation skill**
```markdown
---
name: write-docs
description: When asked to write or update documentation, follow these documentation standards
---
[Our documentation standards and templates]
```

**3. Commit message skill**
```markdown
---
name: commit-message
description: When writing a commit message, follow conventional commits format
---
Format: type(scope): description
Types: feat, fix, docs, refactor, test, chore
```

**4. Test generation skill**
```markdown
---
name: write-tests
description: When writing tests, follow these testing patterns and coverage requirements
---
[Our testing standards, framework conventions, coverage requirements]
```

**5. Research synthesis skill**
```markdown
---
name: research-synthesis
description: When conducting research or summarising multiple sources, structure output as follows
---
[Our research output format: executive summary, key findings, sources, gaps]
```

---

## Connections to Other Courses

- **Claude Code 101** — Introduces skills conceptually; this course is the deep dive
- **Claude Code in Action** — Shows custom commands in action; skills are the broader system
- **Introduction to Subagents** — Companion course; subagents and skills are complementary customisation tools
- **Introduction to Claude Cowork** — Cowork plugins are closely related to the skills concept

---

## How to Operationalise in Our Workflow

### Setup sequence
1. Create `~/.claude/skills/` directory for global (personal) skills
2. Create `.claude/skills/` in each project for project-specific skills
3. Start with 3 skills only — resist the urge to build everything at once
4. Test each skill by explicitly telling Claude to use it first; then rely on automatic trigger matching

### Skill governance for teams
- All team skills live in `.claude/skills/` in the main repository
- Skills are reviewed like code — PRs, review, merge
- Naming convention: `[verb]-[object].md` (e.g., `review-code.md`, `write-tests.md`, `generate-docs.md`)
- A `SKILLS-INDEX.md` in `.claude/skills/` documents all skills and their triggers

### Measuring skill effectiveness
- After implementing a skill, check: is Claude applying it without being asked?
- If not: rewrite the description to be more specific
- If applying incorrectly: add specificity or exclusion language ("but not when...")

### For our specific context
- Skills are how we encode team knowledge into Claude's behaviour — they're essentially "teach Claude once, benefit forever"
- The enterprise managed settings option is key for team-wide deployment without individual setup
- Building a shared skill library should be treated as an ongoing team practice, not a one-time setup
