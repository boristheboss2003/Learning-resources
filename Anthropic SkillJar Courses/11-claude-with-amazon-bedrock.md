# Claude with Amazon Bedrock — Research Notes
**Source:** https://anthropic.skilljar.com/claude-in-amazon-bedrock  
**Date captured:** 2026-05-05  
**Status:** Registration required  
**Type:** Technical course — Claude API via AWS infrastructure  

---

## Overview

A parallel version of "Building with the Claude API" — the same comprehensive technical curriculum but implemented via AWS Bedrock instead of the direct Anthropic API. Originally created as part of an accreditation programme for AWS employees, now available publicly. Covers everything from basic boto3 API calls to Claude Code, computer use, RAG, MCP, and advanced prompt caching.

Notably includes features that may be slightly different via Bedrock (boto3 syntax vs. Anthropic SDK, AWS IAM authentication, Bedrock-specific model identifiers).

**Target audience:** AWS developers and cloud engineers building Claude-powered applications on AWS infrastructure  
**Prerequisites:** Python proficiency; JSON handling; AWS account with Bedrock access  
**Cost:** Registration required  
**Origin:** Created as first-of-its-kind Anthropic-AWS accreditation training  

---

## Full Curriculum

### Learning Objectives (verbatim)
1. Make requests to Claude models via AWS Bedrock using boto3
2. Implement multi-turn conversations, streaming responses, and structured data extraction
3. Build and evaluate prompts using automated testing pipelines with objective scoring
4. Create custom tools and handle multi-step tool execution workflows
5. Design RAG systems with text chunking, embeddings, and hybrid search (semantic + BM25)
6. Connect Claude to external services using MCP (Model Context Protocol) servers
7. Use Claude Code for automated development workflows and parallelised task execution
8. Configure and optimize features like prompt caching, extended thinking, and image processing
9. Implement computer use for automated testing and UI interaction

### Prerequisites (verbatim)
- Proficiency in Python programming
- Basic knowledge of handling JSON data
- AWS account with Bedrock access

---

## Course Sections

### Section 1 — Getting Started with Amazon Bedrock
- **boto3 API calls** — The AWS SDK for Python; how it differs from the Anthropic SDK (authentication, model IDs, response format)
- **AWS authentication** — IAM roles, access keys, Bedrock permissions; the AWS auth flow vs. API key auth
- **Model access** — Enabling Claude models in Bedrock (requires explicit request for model access in AWS console)
- **Basic request/response** — `bedrock-runtime` client; `invoke_model` vs `converse` API; response parsing
- **Multi-turn conversations** — Managing conversation history in the Bedrock format
- **Streaming** — `invoke_model_with_response_stream`; handling streamed events

### Section 2 — Prompt Engineering & Evaluation
*(Same as direct API course — prompt engineering is model-level, not infrastructure-level)*
- Systematic prompt construction
- Automated evaluation pipelines with objective scoring
- Prompt versioning and regression testing

### Section 3 — Tool Use with Claude
- Tool definition format (same JSON schema, just called via Bedrock)
- `invoke_model` with tools configuration
- Multi-step tool execution loops
- AWS-specific tool examples: calling Lambda functions, querying DynamoDB, reading S3

### Section 4 — Retrieval Augmented Generation
- Text chunking strategies
- Embeddings via Amazon Bedrock embeddings (Titan Embeddings or Cohere via Bedrock)
- Vector search via Amazon OpenSearch or Bedrock Knowledge Bases
- Hybrid search (BM25 + semantic)
- Alternative: using Amazon Bedrock Knowledge Bases (fully managed RAG)

### Section 5 — Model Context Protocol (MCP)
- MCP with Claude on Bedrock: same protocol, different host
- Building and connecting MCP servers to Bedrock-hosted Claude
- Bedrock-specific considerations for MCP deployment

### Section 6 — Claude Code & Computer Use
- **Claude Code on Bedrock** — Using Claude Code with Bedrock as the backend (instead of Anthropic direct); parallelised workflows
- **Computer use** — Implementing Claude's computer use capability via Bedrock; automating UI interactions; automated testing

### Section 7 — Advanced Features
- **Prompt caching** — Caching system prompt prefixes to reduce cost and latency on repeated requests; Bedrock's caching implementation
- **Extended thinking** — Claude's extended reasoning mode; configuring it via Bedrock; cost/quality trade-off
- **Image processing** — Sending images in requests; multimodal analysis via Bedrock

---

## Key Differences: Bedrock vs. Direct API

| Feature | Direct Anthropic API | AWS Bedrock |
|---|---|---|
| Authentication | API key in header | AWS IAM (roles/access keys) |
| SDK | `anthropic` Python package | `boto3` |
| Model IDs | `claude-3-5-sonnet-20241022` | `anthropic.claude-3-5-sonnet-20241022-v2:0` |
| Pricing | Anthropic billing | AWS billing (consolidated with other AWS costs) |
| Compliance | Anthropic's data handling | AWS data handling (SOC2, HIPAA, etc.) |
| Latency | Direct | Via AWS infrastructure |
| Enterprise features | Anthropic Enterprise | AWS Enterprise Support + Bedrock features |
| Knowledge Bases | Manual RAG required | Amazon Bedrock Knowledge Bases (managed) |

---

## Key Concepts

| Concept | What it is | Bedrock-specific note |
|---|---|---|
| boto3 | AWS Python SDK | Different from anthropic SDK; more verbose |
| Bedrock Knowledge Bases | Managed RAG service | Replaces manual embedding/retrieval pipeline |
| IAM permissions | AWS access control | Requires explicit Bedrock model access grants |
| Prompt caching | Reuse cached context | Reduces latency and cost on repeated requests |
| Extended thinking | Deep reasoning mode | Higher token cost; better on hard problems |
| Computer use | GUI automation | Claude controls browser/desktop via screenshots |

---

## Connections to Other Courses

- **Building with the Claude API** — The direct API equivalent; same curriculum, different infrastructure
- **Claude with Google Cloud Vertex AI** — The third option for enterprise Claude access
- **Introduction to MCP** — The MCP sections in this course connect to the dedicated MCP course
- **Claude Code in Action** — Claude Code section here connects to dedicated Claude Code courses

---

## When to Choose Bedrock vs. Direct API

**Choose Bedrock if:**
- Your organisation is already AWS-native (existing IAM, billing consolidation, compliance)
- You need AWS-specific compliance certifications (HIPAA, FedRAMP)
- You want managed RAG via Bedrock Knowledge Bases
- Your budget is managed through AWS billing and commitments (reserved capacity)

**Choose Direct Anthropic API if:**
- You want the latest models and features immediately (Bedrock has some delay)
- Simpler authentication (API key vs. IAM)
- Direct Anthropic support and SLAs
- Building outside the AWS ecosystem

**Choose Vertex AI if:**
- Your organisation is Google Cloud-native
- You need GCP-specific compliance or services

---

## How to Operationalise in Our Workflow

### AWS Bedrock setup steps
1. Enable Claude model access in AWS Console → Amazon Bedrock → Model access
2. Create IAM role/user with `bedrock:InvokeModel` permission
3. Install boto3: `pip install boto3`
4. Set up AWS credentials (environment variables or IAM instance profile)
5. Test with a basic invocation before building anything complex

### Bedrock-specific implementations
```python
import boto3
import json

client = boto3.client('bedrock-runtime', region_name='us-east-1')

# Converse API (recommended, model-agnostic)
response = client.converse(
    modelId='anthropic.claude-3-5-sonnet-20241022-v2:0',
    messages=[{'role': 'user', 'content': [{'text': 'Hello'}]}],
    system=[{'text': 'You are a helpful assistant.'}]
)
```

### Prompt caching on Bedrock
If making repeated calls with the same system prompt or context:
```python
# Mark context for caching
system = [{'text': '...long system prompt...', 'cachePoint': {'type': 'default'}}]
```
This can reduce costs by 90% and latency significantly on cached prefixes.

### Bedrock Knowledge Bases (managed RAG)
If you need RAG without building it yourself:
- Set up a Knowledge Base in AWS Console pointing to your S3 data
- Use `bedrock-agent-runtime` client to query it
- Eliminates chunking, embedding, and vector store management

### For our specific context
- If we're AWS-native: use Bedrock for consolidated billing, IAM, and compliance
- Prompt caching is a mandatory optimisation for any system prompt that stays constant across requests
- Bedrock Knowledge Bases is worth evaluating before building custom RAG — managed is faster to ship
