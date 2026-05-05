# Building with the Claude API — Research Notes
**Source:** https://anthropic.skilljar.com/claude-with-the-anthropic-api  
**Date captured:** 2026-05-05  
**Status:** Registration required  
**Type:** Technical developer course — API integration  

---

## Overview

The comprehensive technical course for developers building applications with the Anthropic Claude API directly. Covers the full stack: basic API calls, prompt engineering with automated evaluation, tool use, RAG pipelines, MCP, Claude Code integration, computer use, and agent architectures. This is the most technically complete course in the catalogue for builders.

**Target audience:** Software engineers, ML engineers, and technical builders integrating Claude into applications  
**Prerequisites:** Python proficiency; JSON handling; Anthropic API key  
**Cost:** Registration required  
**Format:** Video-based + likely code examples  

---

## Full Curriculum

### Learning Objectives (verbatim)
1. Make API requests to Claude models and handle responses
2. Implement multi-turn conversations, streaming, and structured output generation
3. Build and evaluate prompts systematically using automated testing pipelines
4. Create custom tools and integrate Claude with external services
5. Design and implement RAG systems with hybrid search and reranking
6. Use MCP (Model Context Protocol) to connect Claude to various data sources
7. Understand common workflows and agent architectures

### Prerequisites (verbatim)
- Proficiency in Python programming
- Basic knowledge of handling JSON data
- Access to an Anthropic API key

---

## Course Sections

### Section 1 — Getting Started with Claude
Core API mechanics:
- **API request structure** — Messages API format: system prompt, user/assistant turns, model selection
- **Response handling** — Parsing completions, stop reasons, usage tokens
- **Multi-turn conversations** — Managing conversation history; the messages array pattern
- **Streaming** — Server-sent events; streaming responses for better UX; handling partial responses
- **Structured output** — Using JSON mode or tool calls to get machine-readable structured data from Claude
- **Model selection** — Claude Opus vs. Sonnet vs. Haiku: intelligence/speed/cost trade-offs; when to use which

### Section 2 — Prompt Engineering & Evaluation
This section goes beyond "write good prompts" into systematic, measurable prompt development:
- **Prompt construction principles** — System prompts, few-shot examples, chain-of-thought elicitation, XML tags for structure
- **Automated evaluation pipelines** — Building test suites for prompts; scoring outputs programmatically; regression testing when prompts change
- **Objective scoring metrics** — How to measure prompt quality at scale without manual review on every case
- **Iterative refinement** — Using eval results to improve prompts systematically rather than by intuition

### Section 3 — Tool Use with Claude
- **Tool definition** — JSON schema for tool definitions; name, description, input_schema
- **Tool call handling** — Detecting tool_use stop reason; extracting tool name and inputs; executing tools; returning results
- **Multi-step tool execution** — Agentic loops where Claude calls multiple tools in sequence; handling tool errors gracefully
- **Real-world tool examples** — Web search, file operations, database queries, external API calls

### Section 4 — Retrieval Augmented Generation (RAG)
- **Text chunking** — Strategies for splitting documents (fixed-size, sentence-boundary, semantic); chunk size trade-offs
- **Embeddings** — Generating embeddings with Voyage AI or similar; embedding storage; cosine similarity search
- **Hybrid search** — Combining semantic search (embeddings) with keyword search (BM25); why hybrid outperforms either alone
- **Reranking** — Cross-encoder reranking to improve retrieval precision after initial retrieval
- **Prompt assembly** — Injecting retrieved context into prompts; citation handling; staying within context limits

### Section 5 — Model Context Protocol (MCP)
- **MCP architecture** — Client-server model; how Claude connects to MCP servers
- **Using existing MCP servers** — Connecting to community or Anthropic MCP servers (filesystem, web, databases)
- **Building MCP servers** — Creating custom servers that expose tools to Claude
- **Data source integration** — Using MCP to give Claude access to structured data without manual RAG

### Section 6 — Claude Code & Computer Use
- **Claude Code integration** — Using Claude Code for automated development workflows; parallelised task execution (multiple Claude Code instances)
- **Computer use** — Claude controlling a GUI via screenshots and actions; automated UI testing; form filling and web interaction
- **Parallelised workflows** — Running multiple Claude instances simultaneously for throughput-heavy tasks

### Section 7 — Agents and Workflows
- **Workflow patterns** — Deterministic pipelines with Claude at specific steps (e.g., extraction → classification → formatting)
- **Agent architectures** — Flexible agents that decide their own next steps based on tool results; the loop until done pattern
- **Common agent patterns** — ReAct (Reason + Act), plan-and-execute, multi-agent coordination
- **Reliability engineering** — Making agents robust: retries, fallbacks, output validation, stopping conditions

---

## Key Concepts

| Concept | What it is | Why it matters |
|---|---|---|
| Messages API | Conversation format for the API | Foundation of every Claude integration |
| Streaming | Incremental response delivery | Critical for good UX in real applications |
| Structured output | Machine-readable responses | Required for programmatic downstream use |
| Tool use | Claude calls functions you define | Gives Claude access to real-world actions |
| RAG | Retrieve then generate with context | Grounds Claude in your specific data |
| Hybrid search | Semantic + keyword retrieval | Better precision than either alone |
| MCP | Standardised tool/data connection | Modular, reusable integrations |
| Agentic loop | Claude tools until done | Enables autonomous multi-step tasks |
| Computer use | Claude controls GUI | Automation of UI-based workflows |

---

## Connections to Other Courses

- **Introduction to MCP** — Deep dive on the MCP section in this course
- **MCP: Advanced Topics** — Further depth on MCP implementation
- **Claude with Amazon Bedrock** — Same content via AWS SDK instead of direct API
- **Claude with Google Cloud Vertex AI** — Same content via Vertex AI instead of direct API
- **Claude Code in Action** — Claude Code section expands into its own course
- **Introduction to Subagents** — Agents section; subagent patterns in Claude Code context

---

## How to Operationalise in Our Workflow

### Immediate implementations by section

#### API basics (Section 1)
- Use **streaming by default** in any user-facing application. Non-streaming feels slow and broken.
- For any output you'll process programmatically: use structured output with a defined JSON schema — don't parse freeform text.
- Build a **model routing layer**: route to Haiku for classification/filtering tasks, Sonnet for standard work, Opus for tasks where quality is paramount. This cuts costs dramatically.

#### Prompt evaluation (Section 2)
- Build an eval suite before shipping any prompt to production. Minimum: 20 representative examples with ground truth.
- Automate evals in CI — any change to a system prompt should re-run the eval suite and block if accuracy drops below threshold.
- Track prompt versions in git alongside code. Treat prompts as code.

#### Tool use (Section 3)
- Design tools with **narrow scope**. A `search_web(query: str)` tool is better than a `do_research(topic: str)` tool — the latter gives Claude too much latitude.
- Always handle the case where Claude calls a tool with invalid inputs. Validate inputs before executing; return structured errors, not Python exceptions.
- Log every tool call with inputs, outputs, and latency. You'll need this for debugging.

#### RAG (Section 4)
- Don't skip chunking strategy — it has the biggest impact on retrieval quality. Experiment with at least 3 strategies before settling.
- Implement hybrid search from the start; pure semantic search is fragile for keyword-heavy queries (product codes, names, etc.)
- Add a citation layer — show users exactly which chunks the answer came from. This builds trust and enables error correction.

#### Agents (Section 7)
- Start with deterministic workflows (fixed sequence of Claude calls), not fully autonomous agents. Add autonomy incrementally.
- Every agent needs a **stopping condition** and a **maximum iteration count**. Agents that loop indefinitely are expensive and fragile.
- Add an observation layer: log every step of the agent loop (tool called, result, next action decision). Invisible agents are impossible to debug.

### Architecture patterns to implement

```
Pattern 1: Extraction pipeline
Raw document → Claude (extract entities) → structured JSON → downstream system

Pattern 2: Classification + routing
Inbound request → Claude (classify intent) → route to specialised handler

Pattern 3: RAG assistant
User query → semantic + BM25 retrieval → Claude (answer with citations) → user

Pattern 4: Agentic task runner
Task description → Claude agent loop (plan, tool calls, observe) → final output

Pattern 5: Parallelised processing
Batch of items → N parallel Claude instances → aggregate results
```

### For our specific context
- The automated eval pipeline (Section 2) is the highest-leverage investment for any production Claude integration
- Hybrid search (Section 4) is almost always worth the extra implementation effort
- Build a logging/observability layer from day 1 — retrofitting it later is painful
