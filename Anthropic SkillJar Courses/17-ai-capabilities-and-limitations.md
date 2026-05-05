# AI Capabilities and Limitations — Research Notes
**Source:** https://anthropic.skilljar.com/ai-capabilities-and-limitations  
**Date captured:** 2026-05-05  
**Status:** Registration required  
**Type:** Conceptual/technical foundation course — mental models for AI behaviour  

---

## Overview

The technical companion to "AI Fluency: Framework & Foundations." Where the Fluency course teaches human competencies for AI collaboration, this course teaches the machine properties those competencies are responding to. The goal: give learners a mental model of what's happening inside an AI system, so unexpected outputs feel diagnosable rather than random.

Organised around four core properties that shape what an AI can and can't do: Next Token Prediction, Knowledge, Working Memory, and Steerability. Each is treated as a spectrum from capability to limitation, paired with a hands-on exercise.

**Target audience:** Anyone who uses AI and wants to understand why it behaves the way it does; complements the AI Fluency course for a complete picture  
**Prerequisites:** None  
**Cost:** Registration required  

---

## The Four Properties — Core Content

### Property 1: Next Token Prediction
*Where AI answers come from*

**The capability:** LLMs predict the most plausible next token given the preceding context. This produces fluent, coherent text across almost any domain — it works by pattern-matching on a vast training corpus.

**The limitation:** This is statistical plausibility, not reasoning. Claude isn't "thinking" in the human sense — it's predicting what a good answer would look like. This means:
- Outputs that sound authoritative may be statistically plausible but factually wrong
- The model will produce a confident-sounding answer even when it doesn't "know" the answer
- Unusual or out-of-distribution questions are handled by extrapolation, not retrieval

**Hands-on exercise:** Experience the seams of next-token prediction by asking Claude questions designed to produce "plausible-sounding-but-wrong" outputs — e.g., invented statistics, confident wrong dates, made-up citations.

**Operationalisation:** Any factual claim in a Claude output should be treated as a hypothesis to verify, not a fact. The fluency of the language is not correlated with the truth of the content.

---

### Property 2: Knowledge
*What the model actually knows, and why it can be confidently wrong*

**The capability:** Claude has absorbed vast amounts of human knowledge during training — science, history, code, culture, language, professional domains. For well-documented topics, its outputs are often excellent.

**The limitations:**
- **Knowledge cutoff:** Training ended at a specific date; Claude doesn't know about events after that
- **Knowledge gaps:** Rare, specialised, or regional topics may be poorly represented in training data
- **Hallucination:** Claude can produce false information with the same confidence and fluency as accurate information — it has no internal "uncertainty flag" it shows you
- **Source quality:** Claude learned from the internet, which includes misinformation, biased content, and errors

**Hands-on exercise:** Ask Claude about topics you're an expert in, including edge cases and recent developments. Where does it fail? What does it confidently get wrong?

**Operationalisation:** 
- Use Claude's knowledge where it's well-established (e.g., well-documented frameworks, widely-published facts)
- Always verify where stakes are high or topics are niche
- Provide current information explicitly when the topic is time-sensitive

---

### Property 3: Working Memory
*What it's paying attention to right now, and what falls off the edge*

**The capability:** The context window is Claude's "working memory" — everything in the current conversation. Within this window, Claude can reason, reference, and connect information quite effectively.

**The limitations:**
- **Context window limits:** There is a maximum context length; very long documents or conversations can exceed it
- **Attention degradation:** Even within the window, Claude's attention isn't uniform — content in the middle of very long contexts is attended to less reliably than content at the beginning or end ("lost in the middle" problem)
- **No persistent memory by default:** Without Projects or explicit persistence mechanisms, Claude has no memory between conversations
- **Recency bias:** Recent parts of the conversation often have more influence than earlier parts

**Hands-on exercise:** Provide a very long document and ask questions about details buried in the middle; observe how accuracy varies by position.

**Operationalisation:**
- Keep important context at the top (system prompt) or explicitly referenced in each message
- Don't assume Claude "remembers" something from earlier in a long conversation — restate it
- Use Projects or CLAUDE.md to persist important context across sessions
- For very long documents: chunk, summarise, or use RAG rather than pasting everything

---

### Property 4: Steerability
*How much control your instructions really give you*

**The capability:** Claude is highly steerable — you can give it a persona, a format, a tone, a set of constraints, and it will follow them reliably. Instruction-following is a core trained capability.

**The limitations:**
- **Instruction conflict:** If instructions conflict (between system prompt and user message, or within a long prompt), Claude resolves this probabilistically — you don't fully control which instruction "wins"
- **Instruction decay:** Very long conversations can cause earlier instructions to have less influence
- **Underspecification:** "Write a good summary" leaves enormous latitude; Claude fills that space with its own defaults, which may not match your intent
- **Emergent behaviour:** Very complex instruction sets can produce unexpected interactions between rules

**Hands-on exercise:** Write a prompt with subtle conflicts in the instructions; observe how Claude resolves the ambiguity.

**Operationalisation:**
- Be explicit about format, length, tone, and audience — don't rely on Claude's defaults
- If an instruction is critical, put it in the system prompt AND restate it in the user message
- Shorter, clearer system prompts often outperform long, complex ones
- When Claude doesn't follow an instruction: first check if the instruction was genuinely clear; don't assume disobedience

---

## Full Curriculum

### Section 1 — Getting Started
- The problem: "delight and confusion" — why AI outputs feel inconsistent
- The solution: a mental model of what's happening
- How this course relates to AI Fluency: Framework & Foundations (companion, not prerequisite)

### Section 2 — Next Token Prediction
- How LLMs work: the prediction mechanism
- Statistical plausibility vs. logical correctness
- Hands-on: experiencing hallucination and plausible-but-wrong outputs

### Section 3 — Knowledge
- What the model knows and doesn't know
- Knowledge cutoffs and their implications
- Hallucination: why it happens and how to mitigate it
- Hands-on: probing knowledge limits in your domain

### Section 4 — Working Memory
- The context window explained
- Attention patterns within the context window
- Persistent memory solutions (Projects, CLAUDE.md, external retrieval)
- Hands-on: observing "lost in the middle" and context decay

### Section 5 — Steerability
- How instruction-following works
- Common instruction problems: conflicts, underspecification, decay
- Practical prompt design for reliable steering
- Hands-on: diagnosing and fixing instruction failures

### Section 6 — Putting It All Together and Next Steps
- When properties collide: real-world complexity (long document + knowledge gap + vague instruction → compound failure)
- The diagnostic framework:
  1. Identify which property is causing the unexpected output
  2. Locate where on the capability-to-limitation spectrum your task landed
  3. Apply a targeted fix (not a generic retry)
- The targeted fix toolkit:
  - Next Token Prediction issue → verify claims; provide examples of correct format
  - Knowledge issue → provide the information explicitly; tell Claude what it doesn't know
  - Working Memory issue → restate key information; restructure to keep important content accessible
  - Steerability issue → clarify or consolidate instructions; resolve conflicts explicitly

---

## Key Concepts

| Concept | What it is | Diagnostic implication |
|---|---|---|
| Next Token Prediction | Statistical plausibility | "Sounds right" ≠ "Is right" |
| Knowledge cutoff | Training end date | Time-sensitive queries → verify |
| Hallucination | Confident wrong information | Verify any claim that matters |
| Context window | Claude's working memory | Keep important content prominent |
| Lost in the middle | Reduced attention to middle-context | Restate; don't bury key info |
| Instruction conflict | Competing instructions → probabilistic resolution | Be explicit; resolve conflicts yourself |
| Underspecification | Vague instructions → Claude fills gaps with defaults | Specify format, length, tone, audience |

---

## The Diagnostic Framework (the most operationally valuable output)

When Claude produces an unexpected output, ask:

```
1. Which property is involved?
   □ Sounds fluent but wrong → Next Token Prediction
   □ Missing recent info or confidently wrong on specifics → Knowledge
   □ Seems to have forgotten something earlier → Working Memory
   □ Didn't follow instructions → Steerability

2. What targeted fix applies?
   - NTP: verify the claim; provide correct examples in the prompt
   - Knowledge: explicitly provide the correct information; tell it what you know it doesn't know
   - Working Memory: restate the forgotten info; put critical info at the top of the prompt
   - Steerability: simplify and clarify instructions; check for conflicts
```

---

## Connections to Other Courses

- **AI Fluency: Framework & Foundations** — This course and that are designed together as companions:
  - Fluency → human competencies (Delegation, Description, Discernment, Diligence)
  - This course → machine properties those competencies respond to
  Together they form a complete model of human-AI collaboration
- **Claude 101** — Practical tool knowledge; this course gives the mental model behind the tool
- **Building with the Claude API** — For developers: these properties are what you're engineering around
- **AI Fluency for Educators** — Teaching this course alongside the 4D Framework gives a complete curriculum

---

## How to Operationalise in Our Workflow

### Daily practice: apply the diagnostic
Every time Claude produces a bad output, spend 30 seconds running the diagnostic before retrying:
1. Which of the four properties is this?
2. What's the targeted fix?

This replaces generic "try again" with targeted interventions — dramatically better results.

### Practical rules from each property

**From Next Token Prediction:**
- Treat all Claude factual claims as drafts to verify
- Provide examples of correct output format — shows Claude what "plausible" looks like in your context

**From Knowledge:**
- For any recent event (< 2 years): verify independently
- Provide Claude with the facts it doesn't know ("As of [date], the situation is X")
- For niche domain knowledge: test Claude's accuracy in that domain before relying on it

**From Working Memory:**
- For any multi-document task: summarise/chunk rather than paste everything
- Critical instructions → system prompt AND message
- In long conversations: restate key context periodically ("As we agreed earlier, the goal is...")

**From Steerability:**
- For any output where format matters: specify format explicitly with an example
- For complex instruction sets: test with simpler cases first; verify each rule behaves correctly
- When Claude doesn't follow an instruction: check if the instruction was actually clear to a fresh reader

### Building organisational prompting standards
This course provides the conceptual foundation for a prompting standards guide:
- Section 1 of the guide: what Claude is and isn't (Next Token Prediction)
- Section 2: what Claude knows and doesn't know (Knowledge)
- Section 3: how to manage context (Working Memory)
- Section 4: how to write clear instructions (Steerability)

### For our specific context
- This course is the missing "why" behind every prompting tip — understanding properties means you can reason about new situations rather than memorising rules
- The diagnostic framework is immediately applicable in day-to-day work
- For anyone training others to use Claude: this course should be mandatory alongside the practical tool courses
