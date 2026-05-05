**Andrej Karpathy Just 10x\'d Everyone\'s Claude Code**

*Nate Herk --- Build Your LLM Wiki in 5 Minutes*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=sboNwYmH3AY

*Prepared: May 2026*

**Premise**

> *Andrej Karpathy released a post about LLM knowledge bases. In a few days it got massive traction on X. The TLDR: you give raw data to Claude Code, it organizes it, and puts it into the right spots with relationships. Then you can query it about anything.*

This video shows how to build a Karpathy-style LLM wiki in 5 minutes. Demo: 36 most recent YouTube videos organized into a knowledge graph with auto-generated backlinks for tools, techniques, and concepts.

**Why This Beats Both Chat and Traditional RAG**

  -------------------------------------------------------- --------------------------------------------------------------------
  **Issue**                                                **How LLM Wiki Solves It**
  Normal AI chats are ephemeral --- knowledge disappears   Knowledge compounds like interest in a bank --- accumulates
  Setup of vector DBs/embeddings/chunking is complex       Just markdown files with structure
  Cost of running rag pipelines                            Free (no embedding API, no vector DB)
  Token bloat from re-explaining context                   One X user reduced token usage 95% across 383 files + 100 meetings
  -------------------------------------------------------- --------------------------------------------------------------------

**Architecture**

Just a folder with markdown files. That\'s it.

  ----------------------- --------------------------------------------------------------------
  **Folder/File**         **Purpose**
  my_wiki/ (vault root)   Top-level container
  raw/                    Where you put source documents (PDFs, articles, transcripts, etc.)
  wiki/                   Where Claude Code creates structured wiki pages
  wiki/index.md           Master index of everything in the knowledge base
  wiki/log.md             Operation history --- every ingestion logged
  CLAUDE.md               Explains the project, structure, and how to update
  ----------------------- --------------------------------------------------------------------

**Optional Subfolders Under wiki/**

Karpathy says sometimes flat (no subfolders) is best. Other times, subfolders by category make more sense.

Author\'s YouTube transcripts vault uses subfolders for: tools, techniques, agent teams, sub-agents, permission modes, MCP servers, RAG, vibe coding, sources, people, comparisons. Each populated dynamically as ingestion happens.

**5-Minute Setup Procedure**

**Step 1 --- Install Obsidian (Free, Optional)**

obsidian.md → download for your OS. Open. Manage Vaults → create new. Name it (e.g., \'demo_vault\'). Choose location (desktop).

**Step 2 --- Open Folder in IDE With Claude Code**

VS Code or any IDE. Open the demo_vault folder. Open Claude Code (terminal preferred for status line visibility).

**Step 3 --- Paste Karpathy\'s Prompt**

Find Karpathy\'s LLM wiki post on X (or his linked GitHub gist). Copy the entire prompt.

**Step 4 --- Add Your Adapter Prompt**

Before sending: add this. \'You are now my LLM wiki agent. Implement this exact idea file as my complete second brain. Guide me step by step. Create the CLAUDE.md schema. Tell me when you need clarification.\'

**Step 5 --- Send**

Claude Code reads Karpathy\'s prompt + adapter, creates raw/, wiki/, CLAUDE.md, index.md, log.md. By default creates 4 wiki subfolders: analysis, concepts, entities, sources.

**Step 6 --- Tell Claude What This Vault Is For**

> *This project is for my second brain --- personal things and business things. Or: this is just a research project where I\'ll dump articles and things I want to learn about.*

**Adding Source Documents**

**Method 1 --- Manual Drop**

Just drag files into raw/ folder.

**Method 2 --- Obsidian Web Clipper (Recommended)**

Chrome extension. On any article: click extension → set folder to \'raw\' → \'Add to Obsidian.\' Article appears as markdown in raw/.

**Settings Tip**

Open Obsidian Web Clipper options. Default save folder is \'clippings\' --- change to \'raw\' so future clips land correctly.

**Ingestion Process**

Demo: dropped AI 2027 article into raw/. Prompt: \'I just threw in an article called AI 2027 into raw. Can you ingest it?\'

**What Claude Does**

1.  Reads through the article.

2.  Asks clarifying questions: focus, granularity, what to emphasize.

3.  Creates \~25 wiki pages from one article (entities, concepts, organizations, people, AI systems, analysis).

4.  Sets relationships between pages --- backlinks.

5.  Updates index.md with new entries.

6.  Logs the ingestion in log.md.

AI 2027 ingestion took \~10 minutes. 36 YouTube transcripts batch took \~14 minutes. Patience required.

**How Querying Works**

Click any wiki page → see all related entities, concepts, organizations. Click related → drill into that. Same as following backlinks in any wiki. Or use Claude Code: \'Tell me about Eli\'s role in AI 2027\' → Claude searches via grep, links the actual markdown file, gives detailed answer.

**The Hot Cache (Optional Add-On)**

In personal/business vaults, add hot.md --- 500 character cache of most recent thing discussed. Saves Claude from crawling wiki pages for routine \'where did we leave off\' queries.

Author uses hot.md in personal HerkBrain vault but NOT in YouTube transcript vault --- depends on use case.

**Linting (Periodic Maintenance)**

Karpathy says: run LLM health checks over the wiki periodically to find:

-   Inconsistent data.

-   Missing data (impute via web searches).

-   Interesting connections for new article candidates.

Run lint daily, weekly, or whenever --- keeps the system scalable and structured.

**Wiki Graph vs Semantic RAG --- Comparison**

  -------------------------------- --------------------------------------------------- -------------------------------------------------
  **Dimension**                    **Karpathy Wiki**                                   **Semantic RAG**
  How it finds info                Reads indexes + follows backlinks                   Vector similarity search
  Understanding of relationships   Deep --- explicit links                             Inferred from chunk similarity
  Infrastructure needed            Markdown files only                                 Embedding model + vector DB + chunking pipeline
  Cost                             Free, only token cost                               Ongoing compute and storage
  Maintenance                      Run lint, add articles                              Re-embed when things change
  Scale ceiling                    Hundreds of pages with good indexes                 Millions of documents
  Best for                         Solo operator, personal knowledge, small business   Enterprise, regulatory, very large corpora
  -------------------------------- --------------------------------------------------- -------------------------------------------------

**Plug Into Other Projects**

The vault is portable. Author\'s executive assistant project (Herk2) has CLAUDE.md that says: \'When you need things about me and my business that you don\'t already have, go to \~/HerkBrain vault, read CLAUDE.md, read hot cache, read index, read domain sub-index, then search.\'

Don\'t read wiki unless actually needed (saves tokens). Author saw token reduction switching from in-project context files to vault references.

**Source**

Andrej Karpathy Just 10x\'d Everyone\'s Claude Code by Nate Herk --- <https://www.youtube.com/watch?v=sboNwYmH3AY>
