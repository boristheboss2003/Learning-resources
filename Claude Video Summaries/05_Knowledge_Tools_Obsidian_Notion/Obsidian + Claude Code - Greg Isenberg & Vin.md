**Obsidian + Claude Code**

*Greg Isenberg & Vin --- Run Your Life as a Connected Markdown Vault*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=6MBq1paspVU

*Prepared: May 2026*

**The Premise**

This podcast episode features Greg Isenberg and his guest Vin (Internet Vin) showing how pairing Obsidian with Claude Code creates a self-improving second brain. The argument: people using these tools well live happier, healthier, wealthier lives because they get better ideas at the right time.

> *If you are serious about using LLMs to take your ideas and put and get the most out of them, if you\'re serious about building a personal OS, and you are not using a centralized note-taking tool that uses markdown as the foundation, then you are not using LLMs properly.*

**What Claude Code Is --- Plain English**

Claude Code is an agent that runs in a command-line interface and controls your computer through natural language.

**Simple Demo**

\'Make a file on my desktop that says hello Greg.\' Claude Code creates the text file on the desktop. Tasks scale: the more context Claude has, the more complex things it can do.

**The Context Problem**

If you write a long project description or have a one-hour conversation, you don\'t want to re-explain it every session. Memory tools (ChatGPT, Claude web) have memory but you don\'t know what\'s stored. The fix: pass context in as files --- text files referenced explicitly. Context becomes deterministic and reusable.

**What Obsidian Is**

Obsidian is an interface that sits on top of a folder of markdown files (called a \'vault\'). What separates it from a regular folder: bidirectional links between files.

**Backlinks Demo**

File \'Daily Notes\' contains: \'Today I am on a podcast with Greg Eisenberg.\' Now this file is linked to the Greg Eisenberg file. Later when you write about Greg in another file, all the connections accumulate into a graph.

**The Graph View**

Visualization of every file as a circle, connected to other files via backlinks. Clicking on a node (e.g., \'Greg Eisenberg\') shows all the times you\'ve written about that topic. Brain-like associative connections instead of folder hierarchy.

**Obsidian + Claude Code = The Unlock**

Obsidian recently released a CLI. Combined with Claude Code:

-   Claude reads all files in the vault.

-   Claude reads the bidirectional link relationships.

-   Claude surfaces patterns about what you\'re thinking that you can\'t see yourself.

-   A latent idea you\'ve been writing about for a year --- Claude names it for you.

**Vin\'s Custom Commands (Live Demos)**

Vin built slash commands that load context from his vault. Each takes seconds to invoke and minutes to execute (because they read many files).

**/context**

Loads full context about life, work, current state. Reads context files, daily notes, follows backlinks. Removes need to re-explain at session start.

**/today (Morning Review)**

Pulls calendar, tasks, iMessages, past week of daily notes. Outputs a prioritized plan for the day. Connected via Obsidian to actual interests, not just calendar mechanics.

**/close-day (End of Day)**

Extracts action items, surfaces vault connections, checks confidence markers (hypotheses with confidence ratings).

**/ghost (Voice Mimicry)**

Answers a question the way Vin would. Builds a voice profile from the vault, writes in that voice, evaluates fidelity. \'What do I think of AI?\' returns Vin\'s actual perspective synthesized from his writing.

**/challenge**

Pressure-tests current beliefs using vault history. Finds contradictions, counter-evidence, shifts in thinking. Used to ensure POV isn\'t overly biased or limited.

**/emerge**

Surfaces ideas the vault implies but never states. Conclusions from scattered premises, unnamed patterns, unarticulated directions.

**/drift**

Compares stated intentions against actual behavior over 30-60 days. Surfaces what you\'re avoiding.

**/ideas (Demo)**

Deep 30-day vault scan with cross-domain pattern detection and graph analysis. Generates ideas across all domains --- tools to build, films to watch, products to buy. Influenced by what\'s in your vault.

**/trace \[Topic\]**

Tracks how an idea has evolved over time across the vault. Demo for /trace \'How I use Obsidian\':

-   Pre-vault December 2024: Vin used a different system.

-   Discovery and skepticism January-May 2025.

-   \'Backlinking to general terms is wasteful --- link to patterns and projects.\'

-   January 2026: explosive building, unlock = automated agent execution.

This is autobiographical archaeology of one specific concept. Crazy useful for self-understanding.

**/connect \[Domain1\] \[Domain2\]**

Takes two domains and connects them using vault link graph. Demo: \'connect filmmaking and worldbuilding.\' Output: bridges between concepts based on what Vin has actually written.

**/schedule \[Question\]**

Demo: \'Can I take a meeting with Greg Eisenberg today at 2 PM?\'

Reads calendar AND daily notes. Considers what Vin actually cares about. Response: \'Day is stacked. Already on Greg\'s podcast this morning. Recording, lunch outing, meeting with Peter and Vince. Greg episode top of mind in Feb 17 note. Recommendation: no, not a 2 PM. You might not need a separate meeting at all.\'

**Building Custom Commands**

Vin\'s process: \'I just asked Claude Code to create the command.\' Easy. Two patterns:

-   Bottom-up --- you think of the command, ask Claude to build it.

-   Top-down (better) --- ask Claude based on vault contents to suggest commands. Works at higher level of abstraction.

**Top-Down Prompt**

> *Based on my Obsidian vault and what you know about me, form an understanding of what you think my level of understanding is and the projects I\'m working on. Based on that, suggest the kinds of commands I should use that would take me from the level I\'m at to a higher level.*

Demo: Claude proposed /graduate (daily note idea extractor --- surfaces ideas in daily notes that never became standalone notes).

**Working with Other Documents**

**Meeting Transcripts (Granola)**

-   Create folder Meetings/ProjectName/Year/.

-   Drop Granola transcripts into folders.

-   Tag transcripts with project/podcast tag.

-   Now linked into vault graph; agents can pull from them.

**AI-Generated Files**

Vin doesn\'t let Claude write into the vault --- wants strict separation between his thoughts and AI\'s. Claude writes to scratch areas; Vin curates what becomes part of the vault.

Reasoning: \'When pattern-finding happens, is it finding patterns about things I wrote or things AI wrote?\' Strict boundary preserves authenticity of pattern detection.

**OpenClaw --- The Future**

OpenClaw is an autonomous agent that can act independently. With access to the Obsidian vault:

-   Reads vault on its own schedule.

-   Finds patterns and makes decisions on behalf of you.

-   Better decisions because deeper personal context.

New management pattern: instead of managing the agent, manage the vault. Vault becomes the source. Agents pull from it.

**Privacy Trade-Off**

> *Giving OpenClaw access to your second brain is scary. You have to really think about how much information you\'re sharing with these agents and whether that\'s the right decision.*

Vin gives broad access deliberately to understand the technology. Privacy will evolve as society fights for or against various norms.

**Why Markdown Files Matter**

> *People think tokens are the oxygen. But they\'re not. The markdown files are the memories.*

Files are perfect memories --- they don\'t decay or transform like human memory. Whatever you wrote at the time is exactly what\'s stored. Combined with bidirectional links, they form a queryable representation of your thoughts.

**The Operator\'s Takeaway**

-   Download Obsidian (free, open source).

-   Set up your vault.

-   Start writing --- daily notes, project notes, hypotheses with confidence ratings.

-   Install Obsidian CLI.

-   Build slash commands for the patterns you care about.

-   Let Claude propose commands based on your vault.

-   Maintain strict separation: you write, AI surfaces patterns.

-   Write daily --- even small notes --- for compounding context.

**Source**

How I Use Obsidian + Claude Code to Run My Life by Greg Isenberg & Vin --- <https://www.youtube.com/watch?v=6MBq1paspVU>
