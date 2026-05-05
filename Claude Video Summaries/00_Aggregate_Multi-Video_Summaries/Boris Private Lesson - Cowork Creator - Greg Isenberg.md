**Greg Isenberg\'s Private Lesson on Claude Cowork & Code**

*With Boris --- The Creator of Claude Code Himself*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=DW4a1Cm8nG4

*Prepared: May 2026*

**Premise**

Greg Isenberg interviews Boris, the maker of Claude Code and co-creator of Claude Cowork. Live demo of Cowork best practices, plus Boris\'s own production-tested rules for Claude Code (his viral 99,000-bookmark Twitter post).

> *Cowork was not actually built to be a product at all. When we first started thinking about it as a product, we thought people would use it for coding. But we learned very quickly that people used it for all sorts of stuff.*

**What Cowork Actually Is (From the Creator)**

-   Available only on macOS at recording time. Windows coming.

-   Three tabs in Claude Desktop: Chat (default), Cowork (new), Code.

-   Cowork under the hood IS Claude Code. Same agent (Claude Agent), same SDK.

-   Cowork is just one layer across everything --- best agent + best agentic model.

**What \'Agentic\' Actually Means (Per Boris)**

> *This word agentic has lost all meaning --- it\'s used too much. A lot of products marketed as agentic are not actually agentic.*

The real definition: it can take action. Not just text. Not just web searching. It can use tools on your computer. Interact with the world.

Anthropic\'s deliberate path:

1.  Get models really great at coding.

2.  Then really great at tool use.

3.  Then really great at computer use.

**Live Demo 1 --- Receipts Folder**

Boris\'s demo: receipts folder on desktop. 4 receipts. \'Can you rename the files to match the dates on the receipts?\'

**What Happens**

-   Boris grants Cowork access to specific folder (NOT entire system).

-   By default, Cowork can\'t see anything --- opt-in per folder.

-   Cowork finds 4 receipts.

-   One missing date. Boris uses \'reverse elicitation\' --- model asks for clarification when unsure rather than guessing.

-   Boris says \'up to you\' for one and \'don\'t rename it\' for another.

-   Cowork renames the files.

**Boris\'s First Tip for Beginners**

> *When you\'re first getting started with Cowork: just mount a folder, give Cowork access, and play around with it. It\'s super useful for cleaning up files, organizing things.*

**Demo 2 --- Spreadsheet Then Google Sheet (Computer Use)**

\'Now put this in a spreadsheet.\' Cowork uses built-in PPTX/Excel skill to generate one.

\'Make it a Google Sheet instead.\' Cowork opens Chrome browser, navigates to Sheets, types data, formats it. Asked Boris for permission ONCE per site --- Boris selects \'always allow for site.\'

**Boris on Speed Concerns**

> *Of course you can do this faster yourself. The model gets better at doing it quickly over time. And because you can do multiple things in parallel, it\'s actually a big time saver.*

Boris\'s workflow: kick off 5-10 different tasks in parallel. Tend to them like a manager. Different from past \'go super deep on one task\' mode.

**Built-In Safety Layers (Per Boris)**

-   Safety starts at the model layer --- Anthropic was the AI safety lab from the beginning.

-   Alignment + mechanistic interpretability research underpins it.

-   Whole virtual machine running under the hood --- actions don\'t affect broader system.

-   Deletion protection (added recently) --- prompts before deleting.

-   Prompt injection protections.

> *It\'s not perfect. We released this pretty early. A big part of making models safe isn\'t just studying them in a lab --- it\'s studying them in the wild.*

**Demo 3 --- Send Spreadsheet via Gmail**

\'Open Gmail and send the sheet to Amy.\' Cowork opens Gmail, composes new email, types \'Amy\' --- pulls from contacts. Sends.

**Multiple Parallel Tasks**

Boris kicks off another task while first is running: \'Cool startup ideas --- open browser, search.\' Both run simultaneously across virtual machines.

**Skills Discussion**

Cowork already has prepackaged skills (e.g., for Excel). When Cowork generated the spreadsheet, it loaded the Excel skill automatically.

**Skills Are Repeatable Workflows**

If you have weird file format (AutoCAD, Salesforce, niche tools), make a skill --- Cowork can then operate them. Boris\'s hypothesis: vertical skills become the differentiator. Everyone hires \'digital teammates\' for specific roles.

**Customization Philosophy**

  ------------------------------- -------------------------------------------------------------------------------------------------------------------------
  **Audience**                    **Customization Style**
  Engineers (Claude Code users)   Love hacking. Most customizable coding agent --- skills, custom agents, hooks, config, settings, permissions
  Non-engineers (Cowork users)    Started in opposite direction --- keep it really simple. Don\'t customize too much. Cowork + Chrome extension is enough
  ------------------------------- -------------------------------------------------------------------------------------------------------------------------

**Boris\'s Production Rules (His Viral 99K-Bookmark Post)**

**Rule 1 --- Run Tasks in Parallel**

Don\'t go super deep on one task. Do many in parallel. Boris\'s actual workflow:

4.  Start task in tab 1. Once Cowork is making a plan, switch to tab 2.

5.  Tab 2: ask for plan on second task.

6.  Tab 3: third task.

7.  When you\'ve run out of immediate tasks, go back to tab 1.

8.  Review plan. Adjust if needed.

9.  Once plan is good → auto-accept edits → model executes pretty much perfectly.

> *This was definitely not the case with previous models. Opus 4.5 changed it. Once the plan is good, the code is good.*

**Rule 2 --- 5-10 Claude Code Sessions in Parallel**

Boris runs 5-10 in parallel --- terminal + web + iOS + Android. Hands off local terminal sessions to web. Manually kicks off Chrome sessions. Teleports back and forth. Starts 3 sessions from his phone every morning.

> *If you ask me a year ago, I would never have predicted that the way I code now is probably half on my phone. It just sort of works.*

**Rule 3 --- Use Opus 4.5 With Thinking for Everything**

> *It\'s the best coding model I\'ve ever used. Even though it\'s bigger and slower than Sonnet, since you have to steer it less, and it\'s better at tool use, it\'s almost always faster than using a smaller model in the end. And cheaper. Counter-intuitive, but the smarter model uses fewer tokens overall.*

**Rule 4 --- Team-Shared CLAUDE.md, Checked Into Git**

Whole team contributes multiple times a week. When Claude does something incorrectly: add it to CLAUDE.md. Other teams maintain their own. CLAUDE.md is just a text file --- no special format required.

**Rule 5 --- Tag \@claude on PRs to Update CLAUDE.md**

Use Claude Code GitHub action: /install-github-action installs it. Then \@claude on issues or PRs updates CLAUDE.md or makes fixes.

Inspired by Dan Chipper\'s compound engineering. Boris\'s prior version at Meta: kept spreadsheet of code review issues. When same issue appeared 5-10x, he wrote a lint rule. Now: tag Claude → updates CLAUDE.md → never have to point it out again.

**Rule 6 --- Most Sessions Start in Plan Mode**

> *Planning is just the most underused feature in Claude Code. I would say it\'s still underused. I use it for almost all my sessions.*

Use plan mode → go back and forth until plan is good → switch to auto-accept → Claude usually one-shots it.

**Rule 13 --- Give Claude a Way to Verify Its Output**

Boris\'s three top tips for getting better Claude Code performance:

10. Use Opus 4.5 with thinking --- always.

11. Have a good CLAUDE.md.

12. Give Claude a way to verify its output.

> *Imagine you\'re a painter who has to make photorealistic paintings --- but you wear a blindfold. It\'s not going to be good. Same with Claude. As models get more intelligent, first-shot improves. But really, you want to give it a way to verify the output.*

Concretely:

-   If engineering: run tests, start a server, test in browser.

-   If app development: use Chrome extension to have Claude test its own work.

-   If writing: have Claude critique its own draft, then rewrite.

**Boris\'s Predictions**

**On Coding**

> *In the last two months, Claude Code has written 100% of my code. I haven\'t written a single line by hand. A year ago, this seemed impossible --- but trace the exponential.*

**On Cowork**

Boris plans on a 1-week timeline. The model is changing too fast. But: anything tedious --- connecting App A to B, shuffling data, etc. --- Cowork will increasingly just do for you.

**Greg\'s Bet**

Cowork is the gateway drug to Claude Code. People will develop vertical use cases (one for AutoCAD users, one for Salesforce users, etc.). Verticals + skills + \'digital teammate\' hiring.

**Boris\'s Closing Tip**

> *There\'s no one right way to use this stuff. It\'s like one of those find-your-own-path books. Just see what\'s useful, see what\'s not, find your own workflows.*

**Source**

I got a private lesson on Claude Cowork & Claude Code by Greg Isenberg --- <https://www.youtube.com/watch?v=DW4a1Cm8nG4>
