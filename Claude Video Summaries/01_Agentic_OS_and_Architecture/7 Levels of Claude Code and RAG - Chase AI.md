**The 7 Levels of Claude Code & RAG**

*Chase AI --- A Roadmap From Auto-Memory to Agentic RAG*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=kQu5pWKS8GA

*Prepared: May 2026*

**Premise**

This video is about deconstructing the problem of Claude Code and AI memory in general, and giving a roadmap that shows where you stand in this fight between AI systems and memory and what you can do to get to the next level. Each of 7 levels covered with: what to expect, skills to master, traps to avoid, what to do to move on.

**The Core Tension**

> *We have to keep context rot in the back of our mind. We\'re constantly trying to deal with this tension of: I want to ingest context so Claude Code can answer questions about a number of things, yet at the same time I don\'t want context to get too large because then it\'s worse.*

**Context Rot Explained**

The more an AI system is used within the same session/chat --- filling its context window --- the worse it gets. Demonstrated: Claude Code 1M context window. At 256K tokens (\~25% full), accuracy 92%. By the end (\~800K), 78%. Two effects:

-   Effectiveness drops as context fills.

-   Token usage spikes (1M context costs vastly more than 80K).

Why people do this anyway: ingrained fear from ChatGPT/Claude web app days where exiting meant losing memory entirely. People bring that \'never close the chat\' habit to Claude Code where it actively hurts them.

**Level 1 --- Auto Memory**

**Where You Are**

You\'ve never set anything up intentionally to help Claude Code remember context. Just relying on what it does automatically.

**What Auto Memory Is**

Claude Code automatically creates markdown files listing things it thinks are important about you and the project. Find them at: \~/.claude/projects/\[project\]/memory/. Inside: memory.md as an index plus several sub-files. Like Post-it notes Claude wrote about you.

**The Verdict**

> *It\'s cute, but ultimately not that useful. Kind of like when ChatGPT shoehorns in random stuff from previous conversations. It\'s like \'Okay, I get it, you remembered this, but I don\'t really care.\'*

**Skills to Master**

-   Understand auto-memory isn\'t enough.

-   Take an active role in this relationship.

-   Recognize you need to control what Claude Code considers when answering.

**Trap**

-   Relying on a bloated context window to remember things.

-   Never editing CLAUDE.md or any other artifact.

-   Outcome: no control. Claude decides what\'s important.

**How to Unlock Level 2**

Memory must become explicit. Figure out what files to edit and understand they exist.

**Level 2 --- CLAUDE.md**

**The Apparent Godsend**

CLAUDE.md feels like progress at first. Single place to give Claude Code rules and conventions. Auto-created by Claude Code; can be edited or rebuilt with /init.

**What It Looks Like**

Standard structure for a personal assistant project: about-me section, file system structure, command operations. Referenced on essentially every prompt --- Claude Code is really good at following it.

**The Hidden Problem**

A study evaluating agents.md (interchangeable with CLAUDE.md) found these files can actually REDUCE LLM effectiveness.

> *The thing that makes it so good --- injection into every prompt --- is what can also make it so bad. Are we actually injecting the correct context? Have we pushed through noise? Or just throwing in things we think are good?*

**Skills to Master**

-   High-signal project context --- only what\'s relevant to virtually every prompt.

-   Context rot awareness.

-   Less is more in CLAUDE.md.

**Trap --- Bloated Rulebook**

Most people fall into this. Stuffing everything into CLAUDE.md and hoping Claude Code remembers. Wrong approach --- context pollution is real.

**How to Unlock Level 3**

Stop relying on a single static rulebook. Use CLAUDE.md as an INDEX file pointing Claude Code to other files instead of doing all the heavy lifting itself.

**Level 3 --- State Files (Multi-File Architecture)**

**The Pattern**

Multiple markdown files for specific tasks. CLAUDE.md becomes an index pointing to them. Example from GSD (Get Shit Done) orchestration tool:

  ----------------- ------------------------------------------------------------------
  **File**          **Purpose**
  project.md        High-level overview --- North Star context
  requirements.md   What needs to be built --- Claude Code always has memory of spec
  roadmap.md        What\'s been done in past, what\'s coming next
  state.md          Current state of work
  ----------------- ------------------------------------------------------------------

**Why It Works**

Fights against context rot by NOT injecting everything into every prompt. Claude Code goes to CLAUDE.md → CLAUDE.md says \'these are 5 options\' → Claude picks the relevant one. This is a crude reimagining of vector similarity search but at small scale.

**Skills to Master**

-   Structuring documents into logical chunks.

-   State management --- keeping files current as work evolves.

-   Using orchestration layers (GSD, Superpowers) that automate this multi-file architecture.

**Trap**

What you create in this project is just for that project. Clunky to shift markdown files between projects. Need a portable system.

**Level 4 --- Obsidian (The 99% Solution)**

**Why This Level Matters Most**

> *Obsidian is the level most people should strive for. This is enough for most people in most use cases. Levels 5-7 are overkill for most people. Obsidian is the 80% solution that in reality is a 99% solution for the solo operator.*

**Why It\'s the Right Stop For Most**

-   Free.

-   Basically no overhead.

-   Solves the problem: Claude Code connected to many markdown files, accurate timely retrieval.

-   As a HUMAN, you can see what\'s in each document and how they relate.

-   Author\'s argument: insight you get from Obsidian\'s link graph trumps the insight you get from RAG embeddings.

**Karpathy\'s LLM Knowledge Base Pattern (3-Subfolder Architecture)**

  --------------- ----------------------------------------------------------------------------------------------------------
  **Subfolder**   **Purpose**
  raw/            Staging area --- everything ingested goes here first (e.g., 50 competitor sites, 2,500 raw entries)
  wiki/           Structured Wikipedia-style articles. Master index file lists what exists. Each article in its own folder
  output/         Final deliverables (slide decks, reports)
  --------------- ----------------------------------------------------------------------------------------------------------

**How Claude Code Navigates**

1.  Goes to vault.

2.  From vault → wiki/.

3.  Wiki has master index markdown --- what exists in this knowledge base.

4.  Index points to specific articles.

5.  Sub-articles also have indexes (recursive structure).

Clear hierarchy. Claude doesn\'t have to grep an entire chaotic folder of 10M files.

**How Many Documents Can This Scale To**

If structure is clean: hundreds, possibly thousands of documents. Most people fail not because Claude can\'t handle volume, but because they have a billion docs in one folder. \'It\'s the equivalent of having 10 million files strewn across the factory floor and saying Claude code, find it.\'

**Skills to Master**

-   Setting up Obsidian vault with clear hierarchy.

-   Karpathy raw → wiki → output flow.

-   CLAUDE.md as the file that explains the structure to Claude Code.

-   Discipline: always have Claude turn raw research into structured wiki entries before consuming.

**Trap --- When Does Obsidian Hit a Wall?**

Not as simple as \'wrong answers.\' Token cost and speed also matter. Older 2025 study showed naive RAG was 1,200x faster AND 1,200x cheaper than textual LLM for the same retrieval task. Even though that gap has narrowed, it\'s still significant at scale.

> *Where exactly is the line where Obsidian becomes too slow or expensive? You won\'t know until you experiment.*

**Level 5 --- Naive RAG**

**What RAG Actually Is (3 Stages)**

  --------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  **Stage**       **What Happens**
  1\. Embedding   Each document gets chunked. Each chunk → embedding model → vector in vector database
  2\. Storage     Vector database with hundreds/thousands of dimensions. Each vector represented by series of numbers. Semantically similar items cluster (bananas/apples/pears in fruit area; ships/boats elsewhere)
  3\. Retrieval   User question → embedding model → question vector. System finds vectors most similar to question vector. Pulls top N (5/10/20). Augments LLM\'s training data with retrieved context
  --------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**Why Naive RAG Fails**

-   Chunking is arbitrary --- random tokens or fixed sizes ignore semantic boundaries.

-   Chunk 3 may reference Chunk 1; if retrieval doesn\'t pull both, answer is wrong.

-   Whole document often needed to answer questions about it.

-   Silos --- vectors don\'t know how concepts relate to each other.

-   Hard to query relationships (\'how do bananas relate to boats\').

-   Re-rankers help (re-score retrieved vectors with LLM) but don\'t fix architecture.

**Skills to Master**

-   Understanding chunking, embeddings, vectors.

-   Knowing how documents become numbers and how numbers find each other.

-   Understanding why basic RAG falls short.

**Trap --- The Glorified Search Engine**

> *With naive RAG you\'ve kind of just created a crappy search engine. How is that different from an overcomplicated Ctrl+F system?*

Effectiveness often \~25% --- basically guessing. Many \'rag systems\' on the market are this. If they don\'t mention graph RAG or sophisticated re-rankers, they\'re naive RAG. Don\'t get scammed.

**Level 6 --- Graph RAG (The First Real RAG)**

**Author\'s Take**

> *If you\'re going to use RAG, this is the lowest level of infrastructure you need to create.*

**The Big Idea**

Everything is connected. Not vectors in silos --- a graph of relationships. Click on document → see relationships, entity types, connected files.

**Performance vs Naive RAG**

LightRAG benchmarks (open source, 6-8 months old): naive RAG vs LightRAG, often 100%+ jumps. 31.6% → 68.4%, 24% → 76%, 24% → 75% across multiple benchmarks. (Take with grain of salt --- these are LightRAG\'s own numbers).

**Tools**

  -------------------- ------------------------------------------------------------------------------
  **Tool**             **Notes**
  LightRAG             Lightest weight graph RAG. Open source. Author\'s recommended starting point
  Microsoft GraphRAG   Robust, well-known, but not cheap
  Other commercial     Various --- vet carefully
  -------------------- ------------------------------------------------------------------------------

**Obsidian vs LightRAG --- Crucial Distinction**

Obsidian\'s link graph LOOKS like LightRAG\'s but is fundamentally different:

  ------------------------------------------------------------------- --------------------------------------------------------
  **Obsidian**                                                        **LightRAG**
  Connections set MANUALLY (or by Claude when it generated the doc)   Connections derived from actual content via embeddings
  You could connect random unrelated docs                             Connections only set where content actually relates
  No entity extraction                                                Defines entities and relationships automatically
  Pure visual + text reference graph                                  Hybrid vector + graph query system
  ------------------------------------------------------------------- --------------------------------------------------------

> *We are not the same, brother. Two totally different systems.*

**Skills to Master**

-   Understanding entity extraction.

-   Understanding relationship-based retrieval.

-   Hybrid vector + graph query design.

-   Setting up LightRAG (author has dedicated tutorial).

**Traps**

-   Multimodal --- what about scannable PDFs, videos, images? LightRAG is text-only.

-   No agentic intelligence --- system reactively retrieves, doesn\'t decide WHEN/WHETHER to retrieve.

**Level 7 --- Agentic RAG (Bleeding Edge, April 2026)**

**What Defines This Level**

-   Multimodal ingestion (text, scannable PDFs, images, videos).

-   Architecture and pipelines for production team use.

-   Agent intelligently decides which DB to query, when to retrieve.

**Multimodal Tools**

  ---------------------------------- ------------------------------------------------------------------------------
  **Tool**                           **Adds**
  RAGAnything                        Imports images, scannable PDFs, non-text into LightRAG-style knowledge graph
  Gemini Embedding (March 2026)      Embed videos themselves into vector database
  Combined: RAGAnything + LightRAG   Author\'s recommended setup for sophisticated solo operator
  ---------------------------------- ------------------------------------------------------------------------------

**Why Multimodal Is the Frontier**

> *How much information is trapped on YouTube as video? A transcript doesn\'t do enough. The multimodal problem is real.*

**Production-Level Architecture (n8n-Style Pipeline)**

Author\'s example: 90%+ of agentic RAG infrastructure is data ingestion and syncing. Only a small slice is the actual RAG retrieval.

**Critical Production Questions**

-   How does data get there in a team setting?

-   How do you handle version 2 of an existing document?

-   Who can edit/upload?

-   How do duplicates get cleaned up?

-   How does information stay current?

**Agentic Routing**

Real teams don\'t have just one knowledge base. They have:

-   Documents in graph RAG (qualitative knowledge).

-   Standard Postgres with structured business data.

-   Maybe a SQL data warehouse.

-   Maybe specific tool APIs.

Agentic RAG = top-of-funnel agent that decides: \'Is this a graph RAG question or a Postgres SQL query?\' Routes appropriately.

**Skills to Master**

-   Multimodal embedding (images/videos/PDFs).

-   Data ingestion pipelines (Drive → ingestion → graph + log).

-   Agentic routing logic (which DB for which question).

-   Update mechanisms --- versioning, dedup, freshness.

-   Team access patterns.

**Trap**

> *The trap, honestly, is trying to force yourself into this level when it\'s just not needed. Most of you are fine with Obsidian. You don\'t need graph RAG. You really don\'t need RAG in general.*

**Decision Framework --- Which Level Are You?**

  --------------------------------------------------------- -----------------------------------------------
  **Symptom**                                               **Right Level**
  Never edited CLAUDE.md                                    Level 1 --- start by editing it
  Have CLAUDE.md but stuffing everything in it              Level 2 --- start trimming
  Single project with growing complexity                    Level 3 --- multi-file state architecture
  Many notes, want personal second brain, free + simple     Level 4 --- Obsidian (probably your endpoint)
  Need to query thousands of documents with relationships   Level 6 --- graph RAG
  Multimodal + production team + intelligent routing        Level 7 --- agentic RAG
  --------------------------------------------------------- -----------------------------------------------

**The Author\'s Strong Recommendation**

-   Always start at Level 4 (Obsidian) if you have any non-trivial knowledge.

-   Don\'t skip to Level 6/7 because it sounds sophisticated.

-   Experiment in ascending order --- Obsidian → LightRAG → RAGAnything+LightRAG → custom agentic system.

-   Always ask: \'Is the marginal cost of upgrading worth the marginal benefit?\'

-   Solo operator answer is almost always: \'No, Obsidian is enough.\'

**The Hidden Discipline (All Levels)**

> *Manage your context window aggressively. Clear and reset more often than you think. Since 1 million context got introduced, people have no clue how to manage their context window. They aren\'t nearly as aggressive with clearing as they should be.*

**Source**

The 7 Levels of Claude Code & RAG by Chase AI --- <https://www.youtube.com/watch?v=kQu5pWKS8GA>
