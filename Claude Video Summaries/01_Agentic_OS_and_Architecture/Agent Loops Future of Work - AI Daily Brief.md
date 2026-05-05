**Autoresearch, Agent Loops and the Future of Work**

*AI Daily Brief --- Why Agentic Loops Are a New Work Primitive*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=nt9j1k2IhUY

*Prepared: May 2026*

**Premise**

This episode argues Karpathy\'s auto-research is not just a weekend project --- it\'s the cleanest example of a new work primitive. Primitives are basic building blocks of work that show up everywhere across roles and industries. New ones don\'t come around often. Spreadsheets, slide decks, email --- those are primitives. Agentic loops may be the next.

**What Karpathy Released (Saturday)**

Self-contained repo. Three files matter:

  ------------ ------------------------------------------------------------------------------------------------------
  **File**     **Purpose**
  prepare.py   Fixed infrastructure. Downloads training data, trains tokenizer, handles evaluation. Doesn\'t change
  train.py     GPT model definition + optimizer + training loop. THIS is the file the AI agent edits
  program.md   Plain English instructions for the AI agent. THIS is the file the human edits
  ------------ ------------------------------------------------------------------------------------------------------

**How It Runs**

1.  Point AI agent (Claude/Codex) at the repo.

2.  Tell it to read program.md and start experimenting.

3.  Agent reads instructions. Looks at train.py.

4.  Decides on modification. Makes edit. Kicks off 5-minute training run.

5.  System evaluates on validation set → val_BPB number (lower = better).

6.  If lower than previous best: keep, commit to git branch, becomes new baseline.

7.  If same/higher: discard, revert.

8.  Loop forever.

Run 1 hour → 12 experiments. Run overnight → \~100 experiments. Karpathy\'s session: 83 experiments, 15 kept, val_BPB went 0.9979 → 0.9697.

**Connection to Ralph Wiggum Loop**

Earlier (mid-2025) idea by Geoffrey Huntley. Software development loop running iteratively. Named after lovable Simpsons character known for indomitable persistence.

**Ralph Loop Mechanics**

Each iteration: feed agent prompt with project specification → agent reads codebase → picks task → implements → runs tests → commits if passing → loop terminates agent → spins up brand new agent → repeat.

**Why Kill And Restart**

-   Context window fills up over time → quality degrades.

-   Solution: deliberately kill before degradation.

-   Memory lives in files (commit history + progress.txt + JSON-based PRD), NOT in conversation history.

-   Each new instance bootstraps from external artifacts.

**How It Generalizes**

The auto-research framework:

  -------------------------------- ----------------------------- -----------------------------------
  **Step**                         **Auto-Research Version**     **General Version**
  1\. Define winning               Lower val_BPB                 Any objective metric
  2\. Hand over the variables      Hyperparameters in train.py   Whatever you can change
  3\. Let agent find what drives   Agent edits train.py          Agent edits whatever inputs exist
  4\. Score and commit/discard     Compare val_BPB               Compare metric
  5\. Loop                         5-min cycle, indefinitely     Whatever cycle fits
  -------------------------------- ----------------------------- -----------------------------------

**Application Patterns From the Episode**

**Vugola CEO\'s Use Case**

Built version for whole company. Each agent in setup reads shared brain file (learnings.md) before doing any work. Writes back after. \'Before starting work, read learnings.md. After completing, append what you learned.\' Agents become a network that accumulates knowledge.

**Marketing Experiments**

Most teams run \~30 experiments per year. Auto-research-style approach: 36,500+ easily. Cold email example:

-   15 inboxes, \~300 emails per day.

-   Modify one variable per experiment.

-   Send 100 emails, wait 72 hours.

-   Score positive reply rate. Keep or discard. Repeat.

**Advertising**

-   Define success: purchases, app installs, etc.

-   Set budget.

-   Meta/Google/TikTok generate thousands of ad variations: copy, format, imagery.

-   Test real-time. Keep what works. Kill what doesn\'t.

-   Campaign moves from fixed asset to living organism.

**Agentic Loop Readiness Map**

X-axis: how automatable evaluation is (subjective → fully automated). Y-axis: iteration speed (months → seconds).

**Top Quadrant (Seconds + Fully Automated) --- Where Loops Win**

-   Code generation.

-   Game AI / NPC behavior.

-   Ad bid optimization.

-   Algorithmic trading.

-   LLM training research (Karpathy\'s case).

**Middle Quadrant (Slower + Partial Automation)**

-   Content moderation.

-   A/B testing copy.

-   Supply chain routing.

**Bottom Quadrant (Months + Subjective) --- Loops Don\'t Apply**

-   Political negotiation.

-   Therapy and counseling.

-   Long-term creative work.

**Future Roles in Practice**

  ------------------- -------------------------------------------------------------------------------------------
  **Role**            **Loop Application**
  Product Manager     Write PRD, kick off Ralph loop before dinner, review PR in morning
  Sales Rep           Define targeting + tone, point loop at 200 leads overnight, review top 30
  Financial Analyst   Define constraints, loop through portfolio allocation back-tests, review optimized output
  Recruiter           Write scoring rubric, loop through 500 résumés, review flagged edge cases
  QA Engineer         Write acceptance criteria, loop through test generation and execution
  Lawyer              Write risk-flag checklist, loop through stack of vendor contracts
  ------------------- -------------------------------------------------------------------------------------------

**Boris\'s /loop Command (March 7)**

Released same week. Powerful new way to schedule recurring tasks for up to 3 days. Examples:

> */loop babysit all my PRs, autofix build issues, and when comments come in, use a worktree agent to fix them.*
>
> */loop every morning using the Slack MCP, give me a summary of top posts I was tagged in.*

OpenClaw heartbeat = core loop. Default: every 30 minutes the heartbeat fires. Agent wakes, asks where things are, continues mission.

**Closing Insight**

> *If you start to figure out how to implement agentic loops in your work, you are going to literally run circles, looping circles, around everyone else.*

**Source**

Autoresearch, Agent Loops and the Future of Work by AI Daily Brief --- <https://www.youtube.com/watch?v=nt9j1k2IhUY>
