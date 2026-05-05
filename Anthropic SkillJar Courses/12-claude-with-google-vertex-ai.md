# Claude with Google Cloud's Vertex AI — Research Notes
**Source:** https://anthropic.skilljar.com/claude-with-google-vertex  
**Date captured:** 2026-05-05  
**Status:** Registration required  
**Type:** Technical course — Claude API via Google Cloud infrastructure  

---

## Overview

The Google Cloud equivalent of "Building with the Claude API" and "Claude with Amazon Bedrock." Same comprehensive curriculum — basic API calls through agents — but implemented via Google Cloud's Vertex AI platform using the Anthropic SDK configured for Vertex. Also covers Vertex-specific features: extended thinking, citations, and prompt caching with GCP authentication.

**Target audience:** Google Cloud developers building Claude-powered applications on GCP  
**Prerequisites:** Python proficiency; JSON handling; Google Cloud account with Vertex AI access  
**Cost:** Registration required  

---

## Full Curriculum

### Learning Objectives (verbatim)
1. Set up and authenticate Claude through Vertex AI using the Anthropic SDK
2. Select appropriate Claude models based on intelligence, speed, and cost trade-offs
3. Write and systematically evaluate prompts using objective scoring metrics
4. Implement tool calling for web search, file operations, and custom functionality
5. Build RAG pipelines with text chunking, embeddings, and hybrid search
6. Use advanced features like extended thinking, citations, and prompt caching
7. Connect Claude to external services using MCP (Model Context Protocol)
8. Design workflows for known task sequences and agents for flexible problem-solving

### Prerequisites (verbatim)
- Proficiency in Python programming
- Basic knowledge of handling JSON data
- A Google Cloud account with Vertex AI access

---

## Course Sections

### Section 1 — Getting Started with Claude (on Vertex AI)
- **Authentication** — Google Cloud auth: Application Default Credentials (ADC), service accounts, `gcloud auth application-default login`
- **Anthropic SDK for Vertex** — Using the standard `anthropic` SDK with `AnthropicVertex` client (different from `Anthropic` client)
- **Model selection** — Claude model IDs on Vertex; Opus/Sonnet/Haiku trade-offs; understanding Vertex pricing vs. direct API
- **Basic requests** — First API call via Vertex; response structure; handling completions

### Section 2 — Prompt Engineering & Evaluation
*(Infrastructure-agnostic — same content as direct API course)*
- Systematic prompt construction and iteration
- Automated evaluation pipelines with objective scoring
- Prompt versioning and regression testing in CI/CD

### Section 3 — Tool Use with Claude
- Tool definitions (same JSON schema format as direct API)
- Tool calling via Vertex endpoint
- Practical tool examples: web search, file operations, custom business logic
- Multi-step tool execution flows

### Section 4 — Retrieval Augmented Generation
- Text chunking strategies
- Embeddings via Google's Vertex AI embeddings (text-embedding-004 or similar) or Voyage AI
- Vector search via Vertex AI Vector Search or Cloud Spanner with vector support
- Hybrid search (BM25 + semantic)
- Alternative: Vertex AI Search (managed, fully integrated RAG)

### Section 5 — Model Context Protocol (MCP)
- Same MCP architecture; different host infrastructure
- Running MCP servers on Google Cloud (Cloud Run, GKE)
- Connecting Vertex-hosted Claude to MCP servers

### Section 6 — Claude Code & Computer Use
- Claude Code configured to use Vertex AI as backend
- Parallelised development workflows on GCP
- Computer use for UI automation and testing

### Section 7 — Agents and Workflows
- **Workflows** — Deterministic pipelines with Claude at specific steps; known task sequences
- **Agents** — Flexible, self-directed agents that choose tools based on the task; the loop-until-done pattern
- Workflow vs. agent decision framework: known sequence → workflow; flexible problem-solving → agent

---

## Key Differences: Vertex AI vs. Direct API

| Feature | Direct Anthropic API | Google Cloud Vertex AI |
|---|---|---|
| Authentication | API key | Google ADC / service account |
| SDK | `anthropic.Anthropic()` | `anthropic.AnthropicVertex()` |
| Region | Anthropic global | GCP regions (us-central1, europe-west1, etc.) |
| Pricing | Anthropic billing | Google Cloud billing |
| Compliance | Anthropic data handling | Google Cloud (SOC2, HIPAA, ISO 27001) |
| Embeddings | Voyage AI (separate) | Vertex AI embeddings (native GCP) |
| RAG | Manual build | Vertex AI Search (managed) |
| Enterprise | Anthropic Enterprise | Google Cloud Enterprise Support |

---

## Key Concepts

| Concept | What it is | Vertex-specific note |
|---|---|---|
| AnthropicVertex | Vertex AI client | Same SDK; different initialisation |
| ADC | Application Default Credentials | GCP-native auth; no API keys |
| Citations | Source attribution in responses | Claude feature enabled via Vertex |
| Extended thinking | Deep reasoning mode | Available on Vertex; same capability |
| Prompt caching | Cache repeated context | Reduces cost on Vertex; same mechanism |
| Vertex AI Search | Managed RAG | Replaces manual embedding pipeline |

---

## Advanced Feature: Citations

Citations allow Claude to attribute specific claims to source documents. Particularly useful for:
- RAG applications where you want to show which document a claim came from
- Legal/compliance applications where attribution is required
- Research assistants where users need to verify sources

```python
# Enable citations in request
response = client.messages.create(
    model="claude-3-5-sonnet-20241022",
    messages=[{"role": "user", "content": [...documents..., query]}],
    # Citations are returned in the response with source document references
)
```

---

## Workflow vs. Agent Decision Framework

The agents section of this course provides a useful framework:

**Use a Workflow when:**
- Task sequence is known and fixed
- Steps are predictable; no branching based on intermediate results
- Latency and cost predictability matters
- Debugging needs to be straightforward

```
Input → Claude step 1 → Claude step 2 → Claude step 3 → Output
```

**Use an Agent when:**
- Task is open-ended; don't know which tools will be needed
- Intermediate results determine next steps
- Flexibility > predictability
- Willing to accept some non-determinism

```
Input → Claude decides → [tool A / tool B / done] → Claude decides → ... → Output
```

---

## Connections to Other Courses

- **Building with the Claude API** — Direct API equivalent; same curriculum
- **Claude with Amazon Bedrock** — AWS equivalent; same curriculum  
- **Introduction to MCP** — Full MCP course; this covers MCP briefly
- **Claude Code in Action** — Full Claude Code course; this covers it briefly

---

## When to Choose Vertex AI vs. Other Options

**Choose Vertex AI if:**
- Organisation is Google Cloud-native
- Need GCP-specific compliance (HIPAA on GCP, etc.)
- Want native GCP embeddings and vector search (Vertex AI Search)
- Budget managed through Google Cloud billing commitments
- Need Gemini and Claude in the same infrastructure

**Don't choose Vertex AI if:**
- Fastest model access needed (Vertex has some delay vs. direct API)
- Non-GCP infrastructure is primary
- Simpler API key authentication preferred

---

## How to Operationalise in Our Workflow

### Setup steps
```bash
# 1. Install dependencies
pip install anthropic[vertex] google-cloud-aiplatform

# 2. Authenticate
gcloud auth application-default login

# 3. Test connection
python -c "
import anthropic
client = anthropic.AnthropicVertex(region='us-central1', project_id='YOUR_PROJECT')
response = client.messages.create(model='claude-3-5-sonnet-20241022', max_tokens=100, messages=[{'role':'user','content':'Hello'}])
print(response.content[0].text)
"
```

### Prompt caching on Vertex
```python
response = client.messages.create(
    system=[{"type": "text", "text": "...long system prompt...", "cache_control": {"type": "ephemeral"}}],
    # ... rest of request
)
# Check cache performance
print(response.usage.cache_creation_input_tokens)
print(response.usage.cache_read_input_tokens)
```

### For our specific context
- If GCP-native: use Vertex for consolidated billing and GCP compliance
- Citations feature is particularly valuable for any research or document-reference workflow
- Vertex AI Search is worth evaluating before building custom RAG for document corpora
