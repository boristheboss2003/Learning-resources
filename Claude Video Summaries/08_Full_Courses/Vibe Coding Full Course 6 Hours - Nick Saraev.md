**Vibe Coding Full Course (6 Hours)**

*Nick Saraev --- Gemini 3.1 + Antigravity + Claude Code*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=gcuR\_-rzlDw

*Prepared: May 2026*

**Premise**

The definitive course on vibe coding for beginners. The host runs a \$4M/year business using Antigravity, Gemini 3.1 Pro, and Claude Code. Teaches \~2,000 people. Six hours. Build-along format --- author recommends building each project as you watch.

**Course Outline**

  ------------------------------- --------------------------------------------------------------------------------------------------------
  **Module**                      **Output**
  1\. Toolkit Setup               Antigravity + Gemini 3.1 + Claude Code in dev environment (\~15 min)
  2\. First Vibecoded Product     Personal site designed with Antigravity + Gemini, deployed live (\~15 min)
  3\. Auth & Security 8/20        Critical 80/20 of security for fully-fledged apps with auth, DB, backend
  4\. Client-Facing Dashboard     Auth + database + clean UI
  5\. Foundational Concepts       Hosting, databases, software design patterns, versioning, frameworks, agents for vibe coding
  6\. Design Deep Dive            Rough idea → polished professional design in Antigravity
  7\. Lead Gen SaaS App           Production-grade lead generation: scrape + enrich + cue automatic emails (Boris\'s actual prod system)
  8\. AI-Based SaaS App           Thumbnail generator (the same tech that made the video\'s own thumbnail --- \'pretty meta\')
  9\. Debugging & Iteration       Framework to steer Gemini and Claude back when veering off-spec
  10\. Content Automation SaaS    Repurpose single content piece across multiple platforms
  11\. Economics of Vibe Coding   Pricing, packaging, and selling what you build
  ------------------------------- --------------------------------------------------------------------------------------------------------

**Module 1 --- Toolkit Setup**

**Antigravity**

-   Visit antigravity.google.

-   Click \'Download\' button. Choose for your OS.

-   If unsure (Mac): About This Mac → see if Apple silicon (M-series) or Intel.

-   Windows: check x64 in download options.

-   Run installer. Mac: drag to Applications. Windows: standard wizard.

**Gemini 3.1 Pro Inside Antigravity**

-   Antigravity ships with Gemini access.

-   Sign in with Google account.

**Claude Code Extension**

-   In Antigravity: extensions → search \'Claude Code\' → install.

-   Authenticate with Claude paid plan (NOT API).

**Module 2 --- First Vibecoded Product (Personal Site)**

Live build of a personal portfolio site:

1.  Open Antigravity, new project.

2.  Prompt Gemini 3.1 Pro for design --- gives multiple variants.

3.  Iterate on design with natural language.

4.  Deploy to Vercel directly from Antigravity.

5.  Live URL ready in \~15 minutes.

**Module 3 --- Auth & Security (Critical 80/20)**

Topic the host considers most underrated for vibe coders. As soon as you have a real app with backend/database/auth, security matters.

**Key Concepts Covered**

-   Authentication: sign-up, login, password reset, magic links, OAuth (Google/GitHub).

-   Sessions and JWT tokens.

-   Role-based access (admin, user, guest).

-   Why API keys never go in code or chat --- always .env.

-   Why .env never goes in git.

-   CORS, rate limiting, input validation as default.

-   HTTPS everywhere.

-   Secret rotation.

**Module 4 --- Client-Facing Dashboard**

First real app build:

-   Auth (Supabase Auth or Clerk).

-   Database (Supabase Postgres).

-   Clean dashboard UI with Tailwind.

-   Multi-page navigation.

-   CRUD operations.

-   Profile / settings flows.

**Module 5 --- Foundational Software Concepts**

80/20 high-level overview. Author admits this isn\'t a CS degree --- software engineers may laugh, but you don\'t need internals to build.

**Hosting**

-   Hosting = running web app on a server.

-   \'Works on my machine\' is the scariest thing a dev can say.

-   Develop entirely locally → push live → 1,000 problems is a common pattern.

-   Push EARLY and often instead --- short feedback loop.

-   Client = your browser. Server = the machine running your app (Vercel, Netlify, Hostinger, AWS, etc.).

**Databases**

-   SQL (Postgres, MySQL) --- relational, structured.

-   NoSQL (MongoDB, Firebase) --- flexible, schema-less.

-   Pick SQL for most use cases unless you have a specific need.

-   ORMs (Prisma, Drizzle) abstract away SQL writing.

**Software Design Patterns**

-   MVC (Model-View-Controller).

-   Component-based UI.

-   REST vs GraphQL APIs.

-   Server-side rendering vs client-side.

**Versioning + GitHub**

-   Always git from day one.

-   Branch per feature.

-   PR-based review.

**Major Frameworks**

-   Next.js for fullstack React.

-   FastAPI/Express for pure backend.

-   Tailwind for CSS.

-   Shadcn/ui for components.

**Module 6 --- Design Deep Dive**

Going from rough idea to polished design in Antigravity:

6.  Find inspiration on Mobbin (sponsor) --- drop screenshots into Gemini.

7.  Generate design.md file describing the visual system.

8.  Have Gemini build initial design.

9.  Iterate with natural language: \'darker theme,\' \'more whitespace,\' \'remove this section.\'

10. Push to Figma if collaborator review needed.

11. Pull back to Antigravity for development.

**Module 7 --- Lead Gen SaaS App (Production System)**

Real production system the host uses. Build:

-   Scraping component (collect leads from sources).

-   Enrichment (LinkedIn data, contact info, company info).

-   Email queue (drip campaigns).

-   Personalization layer (per-lead messaging).

-   Tracking (replies, clicks, conversions).

-   Compliance (CAN-SPAM, GDPR).

**Module 8 --- AI-Based SaaS (Thumbnail Generator)**

Same tech that made the course\'s own thumbnail. Build:

-   User uploads source image + face photo.

-   Prompt template for Gemini image generation.

-   Multiple variants per generation.

-   User picks favorite, downloads.

-   Stripe integration for paid tier.

**Module 9 --- Debugging & Iteration Framework**

How to steer back when Gemini/Claude veers off-spec. Common failure modes:

-   Adding features you didn\'t ask for.

-   Removing features you wanted.

-   Hardcoding values that should be config.

-   Breaking existing functionality.

**The Steering Pattern**

12. Stop. Don\'t keep building on broken state.

13. Reset to last good commit (git checkout).

14. Re-read original prompt. Did model understand correctly?

15. Re-prompt with explicit constraints: \'Do NOT change X. Do NOT touch Y. Only modify Z.\'

16. Verify with browser/tests before committing.

**Module 10 --- Content Automation SaaS**

Repurposes single content piece across platforms. Real production system:

-   Input: long-form video, blog post, or podcast transcript.

-   Output: LinkedIn posts, Twitter threads, YouTube Shorts scripts, newsletter draft.

-   Subscription billing (Stripe).

-   API key for power users.

-   Mobile-optimized.

-   Security audit at the end.

**Module 11 --- Economics of Vibe Coding**

**Pricing**

-   Hourly billing kills the model. Sell outcomes, not hours.

-   Tiered packages: Starter (\$5K-\$15K), Standard (\$30K-\$50K), Premium (\$75K+).

-   Retainer for ongoing maintenance.

**Packaging**

-   Productize repeatable systems (lead gen, content automation).

-   Sell the SAME system to multiple clients.

-   Templates compound --- each delivery refines the next.

**Selling**

-   Discovery call: identify highest-leverage repetitive task.

-   Quantify time/money saved.

-   Demo from your portfolio.

-   Propose scoped engagement with clear deliverables.

**Source**

VIBE CODING FULL COURSE: Gemini 3.1 + Antigravity (6 Hrs) by Nick Saraev --- <https://www.youtube.com/watch?v=gcuR_-rzlDw>
