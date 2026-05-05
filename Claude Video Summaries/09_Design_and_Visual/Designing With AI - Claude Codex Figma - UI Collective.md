**Designing With AI: Claude, Codex, Figma**

*UI Collective --- The Full AI Design Workflow*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=j_ZPV10bu54

*Prepared: May 2026*

**Premise**

> *AI is not a tool. AI is a workflow. It\'s about knowing how to use multiple tools, how to collaborate between those tools, and how to adjust your approach depending on what you\'re working on.*

This 87-minute video is the most comprehensive AI design workflow guide. Covers Claude Code, Codex, Claude Design, Figma\'s role, Google Stitch, training AI on design systems, generating original screens, and building a workflow that\'s actually usable for real product design.

**The Designer\'s AI Stack**

  ---------------- -------------------------------------------------------------- ---------------------------------------
  **Tool**         **Best Use**                                                   **Limitations**
  Claude Code      Production-quality designs, Figma push accuracy                Token-expensive, slower
  Codex (OpenAI)   Iteration on existing designs, 3-4x fewer tokens than Claude   Lower out-of-box design quality
  Claude Design    Polished hi-fi wireframes for stakeholder review               Heavy usage limits, slow
  Google Stitch    Fast mid-fi wireframing, exploring concepts                    Web designs poor; mobile good
  Figma + MCP      Design system source of truth, manual adjustments              AI design system import is incomplete
  ---------------- -------------------------------------------------------------- ---------------------------------------

**Setup --- Figma MCP and Skills**

**Figma MCP vs Figma Skills**

-   Figma MCP --- gives AI access to actual design files (read structure).

-   Figma skills --- teach AI HOW to use Figma (auto-layout, components, variables).

-   Both required for production-quality work.

**Installation in Claude**

1.  Download Figma MCP server zip from community skills site.

2.  Customize → Plugins → upload zip.

3.  Connectors → install Figma → connect → authorize in browser.

4.  Optional: download apply-design-system.skill.md and audit-design-system.skill.md from GitHub.

**Installation in Codex**

5.  Skills tab → search \'Figma\' → install all related skills (Figma MCP, Figma code-connect, Figma create-design-system-rules).

6.  Note: some Figma plugins available only on workspace tier.

**Tool 1 --- Google Stitch (Fast Mid-Fi)**

Free tool for fast iteration. Mobile output is much better than desktop.

**Workflow**

7.  stitch.google.com → choose mode (3.1 Pro Thinking for quality).

8.  Prompt: \'Build a financial management app for financial advisors.\'

9.  Output in \~30 seconds.

10. Click \'Generate\' → \'Variations\' to spin up alternatives.

11. Specify variation type (layouts, content, full reimagining).

12. Use to gather feedback from stakeholders before burning Claude tokens.

**When to Use**

-   Earliest stage exploration.

-   Internal stakeholder concept reviews.

-   Aligning on data points to display, widget formats.

-   Generating multiple layout variants quickly without burning tokens.

**Tool 2 --- Claude Design (Hi-Fi Wireframes)**

Claude\'s dedicated design product. Higher quality output, but limited usage and slower.

**Workflow**

13. Claude Design → New Project → choose hi-fi or wireframe.

14. Prompt with same financial app brief.

15. Claude asks clarifying questions: primary user, key workflows, hero screen, aesthetic direction, info density.

16. Each can be \'decide for me\' or specified.

17. Output in \~6+ minutes --- much slower than Stitch but production-grade.

**Cost Reality**

Single dashboard build = 8% of weekly Claude Design usage. Easy to run out mid-sprint. Use carefully.

**Limitations**

-   Doesn\'t feel like a design tool --- items are static, can\'t drag/resize.

-   Edits via chat or comments only.

-   Hand-off to Claude Code button to take design further.

**Tool 3 --- Claude Code vs Codex Comparison**

**Live Test Setup**

Same prompt, both tools: \'Build a financial management app for financial advisors.\' Push to Figma. Then make 4 changes: light mode, search bar on top households, full-width households, swap AUM and households positions.

**Results**

  ------------------------ -------------------------------------------------- ------------------------------------------
  **Metric**               **Claude**                                         **Codex**
  Initial design quality   Excellent --- production-grade                     Poor --- basic and plain
  Push to Figma fidelity   Good --- uses auto-layout, fill/hug                Adequate
  Time for 4 changes       12 minutes                                         4 minutes
  Tokens for 4 changes     38,000                                             17,000
  Conclusion               Better for initial design, especially Figma push   Better for iteration, 3-4x token savings
  ------------------------ -------------------------------------------------- ------------------------------------------

**Practical Workflow**

18. Start in Claude (or Claude Design) for initial design quality.

19. Push to Figma.

20. Bring into Codex for cheaper iteration when many changes needed.

21. Push back to Figma when ready.

22. Bring into Claude Code only for substantial design quality work.

**Training AI on Your Design System**

**The Reality Check**

Importing your design system into Claude Design via \'create design system\' import is incomplete. Misses variants, component types, type styles. Don\'t trust it for production work.

**The Better Approach: Custom Skills**

Build skills specific to YOUR design system that Claude references on demand.

**Skill 1 --- Variables**

In Figma: prepare a frame with table of variables (token name, value light, value dark, when used). Copy frame link. In Claude:

> *Please study all of the Figma variables inside of this table. After coming to an elite understanding of the variables, their values, their naming, and when they are used, build a Claude skill that will help train Claude on when to use different variables for future designs. Do not include type styles. Only focus on surface, border, text, and icon variables.*

Output: a skill folder with: skill.md, plus individual MD files for border, icon, surface, text variables. Each lists variables with usage rules and common pairings.

**Skill 2 --- Type Styles**

Same approach with text styles frame. Reference: \'Please study all the text styles available inside our design system. Take note of variables applied and their values on desktop/mobile. Build a Claude skill which will inform Claude on which styles are available when building new designs.\'

**Skill 3 --- Components (Methodical)**

In Figma: organize components by groupings --- form elements (input, dropdown, text area, checkbox, radio), navigation, data display (tables, tags, avatars). Reference Figma file. Prompt:

> *Please study the following component groupings: form elements, navigation, data display. Do not move to navigation unless you have a mastery of form elements. Same with data display. After coming to an elite understanding of all components, build a skill around which components are available and when to use them.*

Critical detail: should also reference \'components, properties, variants, and anything else associated with it.\' Author admits he forgot this in the prompt and missed some variants.

**Generating Designs Right**

**AI Always Works Better From Visuals**

Tell builders \'I want a dark kitchen\' --- they imagine one thing. Show them a photo --- they build what you actually want. Same with AI.

**Mobbin (Sponsor)**

Best place to find specific examples. Massive repository of app/web screens. Find an app you like (Tonal example), take screenshot, drop into Claude with: \'Using the screenshot attached and our variable + type-style + component skills, build a page like this using our design system. Do not push to Figma yet. Simply generate locally.\'

**Always Multiple Examples**

Provide 2+ examples. Claude finds synergies between them. Single example risks one-to-one copying (someone else\'s design).

**Common Pitfall: Over-Iteration in Claude**

If only 1-2 small things to fix, do them in Claude. If many changes, push to Figma → bring into Codex → iterate cheaply → push back to Figma → bring back to Claude. Decision point: token cost of pushing/pulling vs cost of changes in Claude.

**ChatGPT 5.5 for Design Variations**

Lesser-known capability: GPT-5.5 generates very good design variations from prompts/screenshots. Drop screenshot into ChatGPT, prompt \'generate alternate options of a screen like this.\' Faster than Claude. Some highlight buttons let you specify what to change. Great for quick variation exploration.

**AI for Variable Library Generation**

Author warns: AI can generate complete variable libraries, but you\'ll spend more time figuring out what AI gave you than building it yourself. Recommendation: build variables yourself (3 hours), then use AI for components/layouts/dialogues --- the higher-leverage parts.

**Workflow Summary**

-   Stitch --- fast variations for stakeholder alignment (cheap).

-   Claude/Claude Design --- initial polished design (expensive but quality).

-   Push to Figma --- manual cleanup, design system application.

-   Codex --- iteration on existing design (cheap).

-   Back to Figma → back to Claude --- only when major design changes need quality boost.

-   Custom skills for variables/types/components --- train AI on your specific design system.

**Source**

Designing With AI: Claude, Codex, Figma \| Full Guide by UI Collective --- <https://www.youtube.com/watch?v=j_ZPV10bu54>
