# Model Context Protocol: Advanced Topics — Research Notes
**Source:** https://anthropic.skilljar.com/model-context-protocol-advanced-topics  
**Date captured:** 2026-05-05  
**Status:** Registration required  
**Type:** Advanced technical course — production MCP implementation  

---

## Overview

The advanced sequel to "Introduction to Model Context Protocol." Where the intro course covers the three core primitives (tools, resources, prompts), this course goes into the implementation details required for production deployment: sampling, notifications, file system access via the roots model, stdio vs. HTTP transports, stateless server configurations, and debugging message flows.

**Target audience:** Developers who've completed the MCP intro course and are building or deploying production MCP servers  
**Prerequisites:** "Introduction to Model Context Protocol" (strongly implied); async programming patterns; familiarity with MCP servers and clients  
**Cost:** Registration required  
**Format:** Video + code examples  

---

## Full Curriculum

### Learning Objectives (verbatim)
1. Implement MCP servers with tool functions, logging, and progress notifications
2. Handle bidirectional communication between MCP clients and servers
3. Configure file system access using the roots permission model
4. Work with both stdio and HTTP transports for local and remote deployments
5. Implement sampling callbacks to enable server-initiated LLM requests
6. Debug message flows using JSON-RPC message types
7. Deploy scalable MCP servers using stateless HTTP configurations
8. Troubleshoot common issues when transitioning from development to production

### Prerequisites (verbatim)
- Basic understanding of MCP servers and clients
- Familiarity with async programming patterns

---

## Course Sections

### Section 1 — Core MCP Features

#### Tool functions, logging, and progress notifications
- **Tool functions in depth** — Advanced tool implementation patterns: optional parameters, input validation, complex return types, error handling strategies
- **Server-side logging** — Emitting structured log messages from an MCP server that clients can receive and display; useful for long-running tools
- **Progress notifications** — Sending incremental progress updates during long-running tool calls; the `notifications/progress` message type; how to implement a progress token

#### Bidirectional communication
- MCP is not purely request-response; servers can also initiate communication back to clients
- **Sampling callbacks** — The mechanism by which an MCP server can ask the client to make an LLM call; the server sends a `sampling/createMessage` request; the client runs the LLM and returns the result. This enables server-initiated reasoning.
- Why bidirectional matters: enables servers to use Claude themselves, creating recursive AI workflows

#### File system access via roots
- **The roots permission model** — Rather than giving MCP servers arbitrary filesystem access, clients declare "roots" (allowed directories); servers can only access files within those roots
- Implementing roots in a server: reading root configurations, respecting scope, error handling for out-of-scope requests
- This is the MCP approach to capability scoping — minimise blast radius of a compromised or buggy server

### Section 2 — Transports and Communication

#### stdio transport (local)
- **Standard input/output** — The default transport for local MCP servers; server communicates via stdin/stdout; simple to implement and debug
- When to use: development, local tools, integrations where server and client run on the same machine
- Debugging with stdio: reading the raw JSON-RPC message flow; using MCP Inspector

#### HTTP transport (remote)
- **HTTP/SSE transport** — For servers that run remotely or need to serve multiple clients; uses HTTP for requests and Server-Sent Events for streaming
- Stateful vs. stateless HTTP:
  - **Stateful**: server maintains session state between requests; simpler but doesn't scale horizontally
  - **Stateless**: server processes each request independently; enables horizontal scaling, load balancing, and production deployment
- Implementing stateless HTTP MCP: all context must be in the request; no in-memory session state

#### JSON-RPC message debugging
- MCP uses JSON-RPC 2.0 as its wire protocol
- Understanding message types: requests, responses, notifications, errors
- Reading raw message flows to diagnose issues
- Common failure patterns: message format errors, ID mismatch, missing capabilities in handshake

#### Production deployment
- Stateless HTTP configuration for scalability
- Environment considerations: authentication, rate limiting, monitoring
- Transitioning from development (stdio) to production (HTTP) — the common failure points

---

## Key Concepts

| Concept | What it is | Why it matters |
|---|---|---|
| Sampling callbacks | Server-initiated LLM requests | Enables server-side reasoning; recursive AI workflows |
| Progress notifications | Incremental updates during tool execution | UX for long-running operations |
| Roots permission model | Scoped filesystem access | Security boundary for file-touching servers |
| stdio transport | Local stdin/stdout communication | Simple, debuggable local deployment |
| HTTP/SSE transport | Remote HTTP-based communication | Production, multi-client deployment |
| Stateless HTTP | No session state between requests | Horizontal scalability; production readiness |
| JSON-RPC 2.0 | Wire protocol | Foundation of all MCP communication |

---

## Advanced Architecture: Sampling Callbacks in Depth

Sampling is the most sophisticated concept in this course. It enables "recursive" AI workflows:

```
Standard MCP flow:
Claude (client) → calls tool → MCP server executes → returns result → Claude

Sampling flow:
Claude (client) → calls tool → MCP server needs to reason → 
sends sampling request to client → Claude processes → 
returns LLM result to server → server continues tool → returns final result → Claude
```

**Use cases for sampling:**
- Server needs to classify or route an input before acting
- Server needs to synthesise multiple data sources
- Server needs to check if an action is appropriate before executing
- Building multi-agent systems where servers have their own reasoning

**Key implementation detail:** The client decides whether to honour sampling requests and which model to use. The server can request sampling but the client has final authority.

---

## Connections to Other Courses

- **Introduction to MCP** — Prerequisite: builds on the three core primitives
- **Building with the Claude API** — Section 5 covers MCP from the consumer side; this course is the implementation side
- **Introduction to Subagents** — Sampling callbacks create patterns similar to subagent delegation

---

## How to Operationalise in Our Workflow

### When to add each advanced feature

| Feature | Add when... |
|---|---|
| Progress notifications | Tool takes > 5 seconds; user needs status feedback |
| Logging | Tool has side effects you need to audit; complex execution paths |
| Sampling callbacks | Tool needs to reason about inputs; server-side decision-making required |
| Roots permission | Server touches the filesystem; security is a concern |
| HTTP transport | Multiple clients need to connect; server needs to be remote |
| Stateless HTTP | Production deployment; horizontal scaling required |

### Production readiness checklist
Before deploying an MCP server to production:
- [ ] All tools have comprehensive error handling and return structured errors
- [ ] Logging implemented for all tool calls (inputs, outputs, duration)
- [ ] If filesystem access: roots model configured and enforced
- [ ] Progress notifications for all long-running tools (>5s)
- [ ] Transport selected: stdio for local, HTTP for remote
- [ ] If HTTP: stateless implementation verified (no in-memory session state)
- [ ] Authentication layer on HTTP endpoint
- [ ] Rate limiting implemented
- [ ] MCP Inspector testing complete on all tools
- [ ] Raw JSON-RPC message flow reviewed for correctness

### Debugging workflow
When an MCP tool behaves unexpectedly:
1. Open MCP Inspector → connect to server → call tool directly
2. Check raw JSON-RPC messages: is the request format correct? Is the response well-formed?
3. Add logging to the tool function → re-run → check what was actually received and processed
4. Verify error handling: what happens when inputs are invalid? Is the error structured correctly?
5. If HTTP: check if state is leaking between requests (stateless requirement)

### For our specific context
- If we're building internal MCP servers: start with stdio (simpler), migrate to HTTP when we need multiple clients or remote access
- Sampling callbacks are worth understanding even if not implementing immediately — they enable a class of server-side reasoning workflows that's hard to achieve otherwise
- The roots permission model is how we should gate filesystem access in any MCP server that touches sensitive files
