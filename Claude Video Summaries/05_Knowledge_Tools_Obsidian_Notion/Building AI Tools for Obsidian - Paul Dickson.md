**Building AI Tools for Obsidian**

*Paul Dickson --- Claude Code Integration via the Agent Client Protocol*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=a0k8wh69PjM

*Prepared: May 2026*

**Premise**

This video is the developer-side companion: how the AI Tools for Obsidian community plugin works, how the new onboarding system simplifies setup, and how to use Claude Code (and Gemini CLI) directly inside Obsidian for note maintenance and content creation.

**New Onboarding Flow (One Feature, One Week of Work)**

On install, the plugin walks you through:

1.  Select an AI agent (Claude Code or Gemini CLI; Codex/OpenCode coming).

2.  Enter API key (chat.obsidiantools.com → Settings → Account).

3.  Verify Node.js and npm are installed (link provided to Node.js install).

4.  Click Install and Connect.

5.  On Windows, may need to restart for npm to be on system path.

6.  If MPM package detected, jumps directly to confirmation.

Confirmation screen confirms Claude Code is installed, API key configured, base URL set. Click \'Start Chatting\' and Claude Code loads in the right pane.

**Manual Installation Path**

If auto-install fails:

-   Download three files from GitHub (main, manifest, styles).

-   Place in Obsidian/AI-Tools/ folder inside plugins folder.

-   Run terminal command to install Claude Code ACP by Zed Industries.

-   Path on Windows: C:\\Program Files\\Node.js\\Node.exe.

-   Use auto-detect to find npm package.

**Plugin Provenance**

Lineage: agent client protocol (ACP) by Zed.dev → Obsidian plugin called Agent Client → Ultimate AI\'s AI Tools for Obsidian → host\'s fork. Open source under Apache 2.0 --- free to modify, redistribute, use commercially as long as attribution preserved.

**Live Feature Add: \'Other\' Button (Demonstration)**

Author shows how to add a feature live --- adds an \'Other\' button to permission dialogs.

**Process**

7.  Pull repo to local VS Code.

8.  Open Claude Code with prompt: \'Add option to select Other and tell Claude Code ACP what to do instead.\'

9.  Use Plan Mode (just to see what Opus comes back with).

10. Authorize using Claude Pro/Max subscription (not API).

11. Plan returns: lists critical files to change, implementation steps, CSS changes, important notes (no ACP changes, leverages existing rejection mechanism).

12. Approve → Claude implements with change log.

13. Run: npm run build.

14. Three new files: main.js, manifest.json, styles.css.

15. Replace files in Obsidian/AI-Tools/ folder via network share to virtual machine.

16. Close and reopen Obsidian.

17. New \'Other\' button appears.

**Daily Maintenance Use Cases**

**Cleaning Up Inherited Notes**

Note \'Rats and Hope\' has only two YAML properties up top, plus old legacy info under \'meta details.\'

Workflow:

18. Load note in Obsidian.

19. Use slash command in Claude Code: /fix-idea (host\'s custom skill).

20. Skill prompts to read template, current note, then apply template.

21. Click Allow.

22. Claude reads template, generates updated note: YAML with date created, alias, tags, status, category, topics, summary.

23. Quote preserved. Reflection preserved. External sources moved to bottom.

24. Continue with: \'Please add the missing source to YAML.\' Claude adds \'YouTube\'.

25. \'Reference the book the note was created from.\' Claude adds \'Black Hole Focus.\'

**Inside the Custom Skill File (.claude/commands/fix-idea.md)**

-   Description: fixes ideas for note formatting using ideas template.

-   Permissions: read and edit allowed.

-   References: my idea template path.

-   9 instructions: read template, understand structure, read note, preserve content, apply structure with example, add meta details, callout if missing, preserve tags, keep thumbnail/featured.

-   Upgrade rule: seedling → fern → tree based on word count.

-   Fallback: refer to claude.md for conventions.

**Research Workflow**

Prompt: \'Create a note about integrating OAMA local LLM with the Claude Code ACP plugin.\' Claude Code makes web search calls (visible thinking icon), researches model context protocol, OAMA integration, etc. Takes a few minutes.

Output: comprehensive note with YAML properties, key benefits, how it works, supported models, references. Save to allowed folder via /allow command.

**Canvas Skill**

Prompt: \'/JSON-canvas --- select this note → create canvas file.\'

Output: JSON Canvas file with nodes for OAMA local server, 64K context, ACP protocol, MCP server. Visual canvas based on the skill specification.

**Outside Obsidian: Terminal Mode**

If the in-Obsidian AI Tools UI feels overwhelming:

-   Run Claude Code in a terminal.

-   Terminal sees the Obsidian vault folder.

-   Reference notes via @-syntax: \'\@ratshope.md improve note structure.\'

-   Claude finds the right skill (e.g., obsidian-markdown skill), applies it.

-   Two-monitor setup: Obsidian in one, terminal in the other.

**Known Bug --- Plugin Forgets After Two Closes**

Open Obsidian, plugin remembers. Close Obsidian. Reopen --- plugin remembered. Close again. Reopen --- \'The plugin that created this tab has gone away.\' Plugin auto-disabled. Workaround: re-enable in Community Plugins. Fix planned for next update.

**Source**

Building AI Tools for Obsidian by Paul Dickson --- <https://www.youtube.com/watch?v=a0k8wh69PjM>
