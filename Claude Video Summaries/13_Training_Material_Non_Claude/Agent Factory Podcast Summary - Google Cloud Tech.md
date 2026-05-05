**Agent Factory Podcast --- Training Material**

*Google Cloud Tech --- General Agentic AI Patterns (Not Claude-Specific)*

**Comprehensive Reference Document**

Source: youtube.com/playlist?list=PLIivdWyY5sqLXR1eSkiM5bE6pFlXC-OSs

*Prepared: May 2026*

**About This Document**

This document summarizes 21 episodes of Google Cloud Tech\'s Agent Factory podcast. Material is general-purpose AI agent development knowledge --- patterns, architectures, frameworks, principles. NOT Claude-specific. Intended as reference / training material to feed into Claude when designing agent systems.

**Why This Folder Is Separate**

These videos teach analysis methodology, agentic system design, and adjacent technical concepts that will inform how Claude operates --- without being Claude-specific. They make Claude smarter at the meta-task.

**21 Episode Topics**

  -------- ---------------------------------------------------------------- -------------------------------------------------------------
  **\#**   **Episode**                                                      **Core Concept**
  01       Google\'s Agents CLI                                             Build, eval, deploy AI agents in minutes
  02       Gemma 4 Sandbox / Self-Teaches Physics                           Sandbox environments for autonomous agent learning
  03       He built business with Google AI                                 End-to-end business automation case study
  04       RL & Fine-Tuning on TPUs                                         Custom model training fundamentals
  05       Antigravity + Nano Banana Pro                                    IDE-integrated agent development
  06       Agent Sandbox + Pod Snapshots on GKE                             Production-grade agent infrastructure on Kubernetes
  07       Building With Gemini 3 + AI Studio + Antigravity + Nano Banana   Multi-tool agent development workflow
  08       Build ANYTHING With Gemini 3                                     Generalist agent capabilities
  09       Cracking Open an Open Model                                      Open source LLM internals
  10       Vibe Coding With Google AI Studio                                Natural language → working app
  11       AI Agents for Data Engineering & Science                         Agentic data pipelines
  12       Agent Security                                                   Securing agent systems against prompt injection, data leaks
  13       Agent Evaluation With ADK & Vertex AI                            Measuring agent performance objectively
  14       Agent Payments --- Can You Do My Shopping?                       Agentic commerce workflows
  15       Gemini CLI With Taylor Mullen                                    CLI patterns for AI
  16       Impossible Computing With Keith Ballinger                        Future of compute and agents
  17       Hardest Questions in Agent Development                           Practical engineering challenges
  18       Memory in Agents                                                 Memory systems for long-lived agents
  19       Building Custom Tools for Agents                                 Tool calling patterns
  20       Multi-Agent Systems Concepts & Patterns                          Orchestration: lead/specialist, swarm, etc.
  21       Agents and Their Frameworks                                      When to use which framework (ADK, LangGraph, etc.)
  -------- ---------------------------------------------------------------- -------------------------------------------------------------

**Key Concepts Across All Episodes**

**1. The Software 3.0 Transition**

Andrej Karpathy\'s framing referenced multiple times:

  -------------- -------------------------------------------------------------------------
  **Era**        **What You Did**
  Software 1.0   Traditional encoding --- explicit instructions
  Software 2.0   Train neural networks --- learn from data
  Software 3.0   Program with natural language prompts. LLMs become the operating system
  -------------- -------------------------------------------------------------------------

**2. Context Engineering**

Replaces prompt engineering as the dominant skill. Acknowledges prompt engineering is one piece. Real bottleneck is the limited context window. LLMs ≈ CPU; context window ≈ RAM. Three core strategies:

-   Isolating --- pass only required data + schema to each sub-agent. Cuts noise.

-   Persisting --- retrieve memories based on relevance and recency.

-   Compressing --- summarize before re-injecting.

**3. Multi-Agent System Patterns**

  --------------------- -----------------------------------------------------------------
  **Pattern**           **How It Works**
  Sequential            Step 1 → Step 2 → Step 3 --- each builds on previous
  Parallel              Multiple sub-agents run simultaneously, results merged
  Orchestrator-Worker   Lead agent decomposes, delegates to specialists
  Hierarchical          Manager agents oversee specialist groups
  Swarm                 Decentralized --- agents cooperate without central coordinator
  Dynamic With Swarm    Hybrid: dynamic decisions on which agents to spawn within swarm
  --------------------- -----------------------------------------------------------------

**4. Memory Systems for Agents**

-   Working memory --- current conversation context.

-   Short-term episodic --- recent interactions.

-   Long-term semantic --- facts and concepts.

-   Procedural --- how to do things (skills).

-   Vector retrieval as the universal lookup mechanism.

**5. Agent Tools and Function Calling**

Tools = APIs the agent can call. Function calling spec lets the model select which tool, with which arguments. Key principles:

-   Tool name should describe what it does, not how it\'s implemented.

-   Each tool needs clear input/output schema.

-   Errors should be informative --- agent learns to recover.

-   Idempotency matters --- safe to retry.

**6. Agent Evaluation**

-   Latency.

-   Accuracy.

-   Cost per task.

-   Tool call success rate.

-   End-to-end task completion.

-   Human-rated quality.

**7. Agent Security Threats**

-   Prompt injection (in retrieved data, in tool outputs, in user input).

-   Data exfiltration via crafted requests.

-   Token abuse / cost amplification.

-   Action without confirmation (financial transactions, deletions).

-   Cross-tenant leakage.

**Why This Matters For Claude Operators**

Even though Claude isn\'t mentioned in these podcasts, the patterns are universal. Specifically:

-   Multi-agent patterns (sequential / parallel / orchestrator-worker) directly apply to Claude Code Agent Teams + sub-agents.

-   Context engineering principles guide CLAUDE.md design and skills creation.

-   Tool calling patterns inform MCP server design.

-   Evaluation frameworks tell you when to scale up vs back off.

-   Security threats apply identically --- Claude\'s systems need same protections.

**Specific Recommendations for Claude Stack**

  --------------------------------------------------------- -----------------------------------------------------------------------------------------------
  **From Agent Factory**                                    **Apply to Claude Code**
  Context engineering\'s 3 strategies                       Build CLAUDE.md as compression. Isolation = scoped folders. Persistence = memory.md
  Orchestrator-worker pattern                               Claude Code Agent Teams (lead + teammates)
  Memory hierarchy (working/episodic/semantic/procedural)   Hot cache (working), conversation logs (episodic), wiki vault (semantic), skills (procedural)
  Tool design with idempotency                              MCP server design --- read operations should be idempotent
  Security: prompt injection in retrieved data              Don\'t blindly trust scraped content. Sanitize
  Eval: end-to-end task completion                          Always have Claude verify its work. Boris\'s rule 13
  --------------------------------------------------------- -----------------------------------------------------------------------------------------------

**Sources**

Full playlist (21 videos):

Agent Factory Podcast playlist by Google Cloud Tech --- <https://www.youtube.com/playlist?list=PLIivdWyY5sqLXR1eSkiM5bE6pFlXC-OSs>
