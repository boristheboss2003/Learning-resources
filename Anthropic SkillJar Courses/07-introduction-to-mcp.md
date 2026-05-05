# Introduction to Model Context Protocol — Research Notes
**Source:** https://anthropic.skilljar.com/introduction-to-model-context-protocol  
**Date captured:** 2026-05-05  
**Status:** Registration required  
**Type:** Technical course — MCP server and client development  

---

## Overview

Hands-on course teaching developers how to build both MCP (Model Context Protocol) servers and clients from scratch using Python. MCP is Anthropic's open protocol for connecting Claude to external tools and data sources in a standardised, reusable way — rather than writing bespoke tool schemas for every integration. The course culminates in a hands-on project: building a document management system using MCP.

**Target audience:** Python developers building applications that need Claude to interact with external services or data  
**Prerequisites:** Basic Python; async/await patterns; familiarity with API concepts  
**Cost:** Registration required  
**Format:** Video + hands-on project  

---

## What is MCP?

MCP (Model Context Protocol) is a standardised protocol that allows Claude (and other LLMs) to connect to external services through a consistent client-server architecture. Instead of writing custom tool schemas for every integration, you build an MCP server once and any MCP-compatible client (Claude, Claude Code, etc.) can use it.

**Before MCP:** Every Claude integration required custom tool schemas, bespoke data parsing, and maintaining the integration code separately.  
**After MCP:** Build a server once. Any MCP client connects to it and gets access to all its tools, resources, and prompts automatically.

### MCP's three core primitives

| Primitive | What it is | Control pattern |
|---|---|---|
| **Tools** | Functions Claude can call (like API endpoints) | Model-controlled: Claude decides when to call |
| **Resources** | Data Claude can read (like files or database records) | App-controlled: host decides what to expose |
| **Prompts** | Pre-defined instruction templates | User-controlled: user selects when to apply |

---

## Full Curriculum

### Learning Objectives (verbatim)
1. Understand MCP architecture and the client-server communication model
2. Build MCP servers that expose tools using the Python SDK
3. Implement MCP clients to connect your applications to MCP servers
4. Create resources for exposing data and prompts for pre-defined workflows
5. Test and debug MCP servers using the MCP Inspector
6. Choose between tools, resources, and prompts based on control patterns
7. Handle resource cleanup and async communication in MCP implementations
8. Basic Python programming experience
9. Understanding of async/await patterns
10. Familiarity with API concepts

### Prerequisites (verbatim)
- Basic Python programming experience
- Understanding of async/await patterns
- Familiarity with API concepts

### Who This Course Is For
Developers who want to build modular AI applications that connect Claude to external tools and data sources.

---

## Course Sections

### Section 1 — MCP Fundamentals & Server Development
- **MCP architecture** — Client-server model; the host (Claude or your app) runs the client; you build the server; JSON-RPC 2.0 as the communication protocol
- **Python MCP SDK** — `mcp` package; `@server.tool()` decorator pattern; how tools are registered and called
- **Building your first tool** — Simple tool implementation; testing with the MCP Inspector (a debugging tool that simulates a client)
- **Resources implementation** — Exposing data sources (files, database records) as MCP resources; the difference between static and dynamic resources
- **Prompts implementation** — Creating reusable prompt templates that users can select from; parameterised prompts
- **Async patterns** — MCP is async-first; proper handling of async tool functions, resource streams, and error propagation

### Section 2 — MCP Client Implementation & Advanced Features
- **Building an MCP client** — Connecting your own application to an MCP server; reading the server's tool/resource/prompt list; sending tool calls and handling results
- **Multi-server clients** — Connecting a single client to multiple MCP servers simultaneously
- **Resource cleanup** — Context managers and lifecycle management; avoiding connection leaks
- **The hands-on project: Document Management System**
  - An MCP server that exposes document operations as tools (create, read, update, delete documents)
  - Resources for browsing the document collection
  - Prompts for common document workflows
  - A client that connects Claude to this server
- **MCP Inspector for debugging** — Using the official debugging tool to inspect message flows, test tools, and diagnose issues

---

## Key Concepts

| Concept | What it is | Why it matters |
|---|---|---|
| Tools | Model-controlled callable functions | Claude decides when and how to call them |
| Resources | App-controlled data exposure | Exposes data without giving Claude arbitrary read access |
| Prompts | User-controlled instruction templates | Reusable workflows the user explicitly activates |
| JSON-RPC 2.0 | Wire protocol for MCP | How server and client communicate |
| MCP Inspector | Debugging tool for MCP servers | Essential for development; simulates a client |
| Async lifecycle | Resource cleanup and connection management | Production stability; avoids leaks |
| Control patterns | Who decides when each primitive is invoked | Governs safety and intentionality |

---

## Connections to Other Courses

- **MCP: Advanced Topics** — This course continues into: sampling, notifications, file system access, and transport implementations
- **Building with the Claude API** — Section 5 of that course covers MCP from the API-consumer perspective; this course is the builder perspective
- **Introduction to Subagents** — Subagents and MCP servers are complementary patterns for modular AI architecture
- **Claude Code in Action** — MCP is shown integrated into Claude Code; this course shows how to build the server side

---

## How to Operationalise in Our Workflow

### Decision framework: when to build an MCP server
Build an MCP server when:
- You have a data source or service you want Claude to access in multiple different contexts (Claude Chat, Claude Code, your own application)
- You want to reuse an integration across different projects or teams
- The integration logic is complex enough to warrant isolating it
- You want the integration to be invokable by Claude autonomously (tools) vs. deliberately by the user (prompts)

Don't build an MCP server when:
- The integration is one-off and only used in one place
- You're just formatting data to pass to Claude — do that inline

### MCP server architecture patterns

**Pattern 1: Data access server**
```python
# Tools: query_database, search_records, get_record
# Resources: expose_collection (all records), expose_record (single record)
# Prompts: summarise_record, compare_records
```

**Pattern 2: Action server**
```python
# Tools: create_item, update_item, delete_item, trigger_workflow
# Resources: expose_status, expose_logs
# Prompts: standard_operation_workflows
```

**Pattern 3: Search server**
```python
# Tools: semantic_search, keyword_search, hybrid_search
# Resources: expose_index_metadata
# Prompts: research_workflow, literature_review
```

### Practical setup steps
1. **Install MCP SDK:** `pip install mcp`
2. **Start with a simple tool server** — one tool, test it with MCP Inspector before adding complexity
3. **Add resources only when needed** — start with tools only; add resources when you want Claude to have passive access to browseable data
4. **Implement prompts for standard workflows** — if your team runs the same kind of analysis repeatedly, encode it as a prompt
5. **Use MCP Inspector throughout development** — don't test by connecting to Claude directly until the server works in Inspector

### Integration with Claude Code
Claude Code natively supports MCP servers. Once your server is running:
```bash
# Add to Claude Code config
claude mcp add my-server -- python server.py
```
Now Claude Code can use all your server's tools during development sessions.

### For our specific context
- Building an MCP server for our primary data sources is a high-ROI investment — it gives Claude access to our data across every context (chat, code, custom apps)
- Prioritise tools over resources initially — tools are what make Claude actually useful; resources are for browsing
- The document management project in this course maps directly to setting up an MCP server for our document/knowledge base
