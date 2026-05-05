**Claude Skills Full Course**

*Nick Saraev --- Automate Your Work With Skills (2026)*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=sduaTkhIm_w

*Prepared: May 2026*

**Premise**

> *Most demos of skills are flashy and centered around the personal assistant angle. People are leaving tons of money on the table by not applying them to specific business use cases that produce large returns on investment.*

Host runs \$4M/year business managed primarily through AI agents and skills. Teaches over 2,000 people. This course shows skills in actual revenue-producing business contexts --- not glorified personal assistants.

**Five Real Skills Demonstrated First**

**Skill 1 --- Follow-Up Nurture (Lead Pipeline)**

Most operators have a list of leads at different pipeline stages: meeting booked, proposal sent, negotiation, etc. Manually checking each daily is tedious.

**How the Skill Works**

1.  Trigger: {backslash}follow-up-nurture.

2.  Skill goes through pipeline.

3.  Captures all conversations ever had with each prospect (full email chains).

4.  Uses templates to personalize check-ins based on stage.

5.  Meeting booked but not held → casual check-in: \'Hey Jimmy, just wanted to check in re: our meeting in a couple days.\'

6.  Proposal sent → \'Hi Sarah, hope you\'ve had a lovely week. Just wanted to circle back on the proposal. Let me know if you have any questions.\'

**Why It Works**

-   Casual, informal language so prospects think it\'s the human.

-   Pulls into existing email chains using the same tone of voice.

-   Reply chains used to stay in same thread.

-   Continuously customized based on where person is.

-   Lists all follow-ups generated for review.

**Skill 2 --- Thumbnail Generator (One-Shot)**

Reproduces a thumbnail image style with the host\'s face superimposed. Demo: reproduce \'Don Draper / John Hamm Madmen vibes\' image.

-   Trigger: \'Reproduce the John Hamm thumbnail. Use similar lighting.\'

-   Skill grabs source image, gets host\'s face, superimposes realistically.

-   Generates multiple variants (different lighting, tones --- Matrix blue, sepia, dark moody).

-   Pick the best one.

**How Skills Actually Work --- Plain English**

> *Skills are the evolution of standard operating procedures, just for agents. SOPs and checklists are for humans. Skills are for AI agent intelligences.*

**Markdown Format Quirks**

Skills are markdown files (.md). Difference from .txt:

-   Hashtag (\#) refers to header --- like a chapter heading.

-   Backticks refer to file references.

-   Slight syntax for links.

You\'ll never make these manually --- give your agent some bullets, brief description, and it combines into optimal markdown skill format.

**Universal Adoption**

As of recording, every major LLM provider supports skills:

-   Anthropic: claude code docs / \'extend claude with skills.\'

-   OpenAI: own skills format (very close to Anthropic\'s).

-   Gemini CLI: \'add agent skills.\'

**The Author\'s Rule of Thumb**

> *If you have a standard operating procedure (SOP), you have a skill. Copy that SOP from your business, feed it into Claude/Gemini/Codex, ask it to make a skill.*

**The Self-Annealing Property**

After first run, you ask agent to test the skill end to end.

-   If agent needs additional info, asks you for it.

-   Otherwise builds asset itself (Excel file, etc.).

-   Every subsequent run: if agent finds mistake during execution, automatically figures out solution AND patches the skill for you.

> *Skills are self-annealing over time. They heal themselves. They get better and improve constantly. Much like an ambitious staff member who sees a checklist, notices a gap, fills it. Skills are the same with agents.*

**Building Your Own Skill --- Procedure**

**Step 1 --- Get the skillspec.md**

Download from author\'s Google Drive (free, no email required). Contains:

-   Condensed spec/definition of skills.

-   File structure.

-   All locations.

-   Formatting options.

Author created it by going to Anthropic\'s Cloud Code docs, copying the entire skills page, feeding it back: \'Compress this significantly. Increase information density. Don\'t make it 500 lines --- make it 150-200.\'

**Step 2 --- Make it Your CLAUDE.md**

CLAUDE.md is prompt injected at top of every new conversation. Setting skillspec.md as CLAUDE.md ensures every conversation in this project knows the skill format.

**Step 3 --- Give Agent Your SOP + Request**

Drag SOP file into working directory. Tell agent: \'Turn this task list into a skill following the spec.\' Or \'I want a skill that does X. Build it.\'

**Step 4 --- Test**

Ask agent to run the skill at least once. If it asks for missing info, provide. If it builds asset successfully, you have a working skill.

**File Structure (Confusing But Important)**

Skills live at .claude/skills/\[skill-name\]/skill.md. The dot prefix in .claude makes it hidden in Mac/Windows file explorer. Reveal hidden folders:

-   Mac: Shift+Cmd+. (period).

-   Windows: right-click folder → Show Hidden Files (or just Google your version).

**Optional Sub-Files**

Anthropic\'s pattern: inside skill folder, you can have:

-   Scripts subfolder (Python, etc.).

-   execution_summary.txt or similar.

-   Auth tokens (e.g., Gmail OAuth).

-   Reference materials.

-   Author prefers an \'execution\' subfolder for scripts (cleaner).

**Live Build Demo --- YouTube Repurposing Skill System**

Author shows live: skill that takes YouTube transcript and converts into:

-   Twitter thread.

-   LinkedIn posts.

-   Newsletter draft.

**Process**

7.  Show transcript text.

8.  Skill spawns sub-agents in parallel --- three formats simultaneously.

9.  Encounters edge case (subtotal/credit terms row breaks parsing).

10. Skill fixes its own filtering logic to skip subtotals.

11. Outputs: tweet thread breakdown, LinkedIn post, newsletter draft.

Each format adjustable with one-line modification of the SOP.

**Author\'s Highest Revenue SOPs**

Author insists most demos miss the mark --- agentic platforms can do anything but don\'t replace the discipline of focusing on revenue-driving levers first. Hierarchy:

12. First: revenue acquisition. Door-to-door, content, sales, marketing.

13. Then: marketing across channels.

14. Last: backend fulfillment automation.

> *These things are so damn good they can design whatever crazy back-end fulfillment pipeline you want. But that doesn\'t mean you should. We\'ve been able to design these pipelines for years and most people doing them don\'t make money.*

**Bottom Line**

Skills are SOPs for agents. Every business has SOPs. Therefore every business has skills waiting to be built. Self-anneal over time. Rule of thumb: if you have a standard operating procedure, you have a skill. Copy it, feed to agent, build.

**Source**

CLAUDE SKILLS FULL COURSE: Automate Your Work (2026) by Nick Saraev --- <https://www.youtube.com/watch?v=sduaTkhIm_w>
