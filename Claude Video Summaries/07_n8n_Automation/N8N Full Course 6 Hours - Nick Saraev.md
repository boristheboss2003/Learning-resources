**N8N Full Course 6 Hours**

*Nick Saraev --- Build & Sell AI Automations + Agents*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=2GZ2SNXWK-c

*Prepared: May 2026*

**Course Overview**

Most comprehensive n8n course on YouTube --- 6 hours. Goal: take a complete beginner to a master capable of building automations for themselves AND selling them to clients. Host scales his own automation agency to \$72,000/month using no-code tools (Make, n8n).

> *This is the most comprehensive resource on n8n that you will find on YouTube --- at least as of the time of recording. I\'ve checked.*

**What This Course Covers**

-   Module 1 --- Setup, dashboard, builder, canvas, nodes.

-   Module 2 --- Three simple workflows for hands-on basics.

-   Module 3 --- Cold email automation in depth (his \$72K/mo system).

-   Module 4 --- JSON, expressions, data manipulation.

-   Module 5 --- AI agent fundamentals.

-   Module 6 --- Sub-workflows, error handling, retries.

-   Module 7 --- Webhooks, HTTP requests, custom integrations.

-   Module 8 --- Advanced functions: hashing, quote, encoding.

-   Module 9 --- Selling automations to clients.

**Module 1 --- n8n Setup**

**Sign-Up**

1.  Visit n8n.io.

2.  Click \'Get Started.\'

3.  Enter full name, company email, password, account name.

4.  Decline newsletter (optional).

5.  Cloud trial: 14 days, 1,000 executions.

**Cloud vs Self-Host**

-   Cloud --- easiest. \$20/mo after trial.

-   Self-host with Docker --- most technical.

-   Self-host on VPS (Hostinger) --- sweet spot. One-click n8n template.

**Module 2 --- Three Practical Workflows**

Same as the Futurepedia course but extended:

-   Daily weather email (foundational).

-   Sponsorship form intake routing (form-driven, branching, sheet logging).

-   AI personal assistant (agent with tools and sub-workflows).

**Module 3 --- Cold Email Automation (Host\'s \$72K/mo System)**

Real production system. Setup:

**Architecture**

6.  Lead source --- scraping data on people who fulfill criteria (CEO, VP marketing, etc.).

7.  Google Sheet --- fields per person: full name, summary, company, location, title, industry, website.

8.  AI agent (OpenAI GPT-4o) --- personalize emails per lead.

9.  Output: 5 templates with placeholders for: subject line, icebreaker, elevator pitch, call to action, postscript.

**AI Personalization Prompt Structure**

-   System prompt: \'You are a helpful intelligent writing assistant.\'

-   User prompt 1 (instructions): \'Personalize an email by editing 5 templates: subject, icebreaker, elevator pitch, CTA, postscript.\'

-   Templates included with placeholders.

-   Guidelines included.

-   Response format: JSON with named fields.

**Dynamic Data via Expressions**

Critical concept: switch from \'fixed\' to \'expression\' field type. Then drag-and-drop columns from sheet → variables embed dynamically. {{\$json.full_name}} replaces \'Amy Webby\' with each prospect\'s actual name.

**Module 4 --- JSON & Expressions Deep Dive**

**Why JSON Matters**

Data moves between nodes as JSON. Knowing how to read it = knowing how to debug. Common patterns:

-   \$json.field --- reference field from immediately previous node.

-   \$(\'Node Name\').item.json.field --- reference from earlier node by name.

-   Square brackets for array indexing: \$json.items\[0\].

-   Dot notation through nested objects: \$json.address.city.

**Common Expression Helpers**

-   Math.round() --- clean integers from decimals.

-   .toLowerCase(), .toUpperCase() --- case fixes.

-   .trim() --- strip whitespace.

-   .replace() --- substitution.

-   parseInt(), parseFloat() --- type coercion.

-   DateTime functions for date math.

**Set Node --- Reshape Data**

-   Strip dollar signs from budget fields.

-   Concatenate first/last names.

-   Add computed fields.

-   Format dates.

**Module 5 --- AI Agent Fundamentals**

Three required components for every agent:

-   Brain --- LLM (OpenAI, Claude, Gemini).

-   Memory --- simple (last N messages) or vector store.

-   Tools --- actions the agent can take.

**System Prompt Anatomy**

-   Role definition.

-   Tool list with usage rules.

-   Context about user/business.

-   Restrictions.

**Module 6 --- Sub-Workflows, Errors, Retries**

Sub-workflows = trigger \'When Executed by Another Workflow.\' Inputs from defined fields. Use cases:

-   Calendar agent (read/write events).

-   Gmail agent (compose/send/triage).

-   Reddit curator.

-   Web scraper with retries.

**Error Handling**

-   Configure retries on critical nodes.

-   Error workflow: separate workflow that runs when main one fails --- alerts via Slack/email.

-   Continue on fail option for non-critical steps.

**Module 7 --- Webhooks & HTTP Requests**

**Webhooks (Receive Data)**

-   Public URL n8n provides.

-   External services POST data to it (form submissions, payment webhooks, etc.).

-   Authentication options: header, basic, none.

**HTTP Requests (Send Data)**

-   GET --- retrieve.

-   POST --- submit.

-   PUT/DELETE --- modify/remove.

-   Authentication: API key, OAuth, basic auth.

-   Body: JSON, form-urlencoded, multipart.

**Connecting to Custom APIs**

When n8n has no native node for a service: read API docs, get API key, build HTTP request node manually.

**Module 8 --- Advanced Functions**

**Hashing**

MD5, SHA-1, SHA-256, SHA-512, RIPE-MD-160, base64 --- for password hashing or data integrity. Rare in business automations but useful in security workflows.

**Quote (String Escaping)**

Wraps strings in quotes, escapes embedded quotes with backslash. Useful when sending data through HTTP requests or webhooks where unsafe characters break parsers.

**Encoding**

Base64 encode/decode for binary-in-text scenarios. URL encoding for query parameters.

**Module 9 --- Selling Automations to Clients**

Host has scaled his agency to \$72K/mo by selling automation services. Key patterns:

**Common Client Builds**

-   Cold email outreach systems (\$3K-\$15K).

-   Lead enrichment pipelines.

-   CRM data sync between tools.

-   Customer onboarding sequences.

-   Reporting and dashboard generation.

-   Personal assistants for executives.

**Pricing**

-   Setup fee + monthly retainer is the most common model.

-   Setup: \$1,000-\$10,000 depending on complexity.

-   Monthly: \$500-\$3,000 for maintenance, monitoring, iteration.

**Discovery Call Framework**

-   Identify their highest-leverage repetitive task.

-   Quantify time/money currently spent.

-   Demo a similar build from your portfolio.

-   Propose scoped engagement with clear deliverables.

**Source**

N8N FULL COURSE 6 HOURS by Nick Saraev --- <https://www.youtube.com/watch?v=2GZ2SNXWK-c>
