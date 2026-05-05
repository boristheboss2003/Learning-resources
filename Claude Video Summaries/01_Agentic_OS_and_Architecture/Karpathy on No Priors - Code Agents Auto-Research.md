**Karpathy on Code Agents, Auto-Research, and the Loopy Era of AI**

*No Priors Podcast --- 66-Minute Wide-Ranging Conversation*

**Comprehensive Reference Document**

Source: youtube.com/watch?v=kwSVtQ7dziU

*Prepared: May 2026*

**Headline Quotes**

> *Code\'s not even the right verb anymore. I have to express my will to my agents for 16 hours a day. Manifest.*
>
> *In December, something flipped --- I went from 80/20 writing code myself versus delegating, to 20/80, and I don\'t think I\'ve typed a line of code since December.*
>
> *I\'m in this perpetual state of AI psychosis trying to figure out what\'s possible, trying to push it to the limit. Everything is a skill issue.*

**Topic Coverage**

-   Code agents and the future of engineering.

-   Auto-research as a new primitive.

-   How more people can contribute to AI research.

-   Robotics.

-   How agents reach out into the real world.

-   Education in this next age.

**The December Inflection**

Karpathy walks Sarah through what changed in December 2025 / early 2026. Before: he was bottlenecked by typing speed. After: agents do almost everything; he \'manifests\' rather than codes.

**The \'Just-in-Time\' Era**

Multiple parallel sessions of Claude Code, Codex, agent harnesses. Not just one --- many. With instructions for each. With optimization OVER the instructions. Recursive.

**Why It Hurts**

> *This is why it gets to the psychosis --- it\'s like infinite, and everything is a skill issue.*

The opportunity cost feels infinite. There\'s always something more to optimize. Always a new pattern to try. Karpathy describes feeling \'antsy he\'s not at the forefront.\'

**Code Models --- The Jaggedness Problem**

> *I simultaneously feel like I\'m talking to an extremely brilliant PhD student who\'s been a systems programmer for their entire life --- AND a 10-year-old.*

Models have improved enormously, but jaggedness --- the gap between brilliance and stupidity --- remains larger than humans. Sometimes Claude/Codex returns something completely wrong, gets in a loop, wastes compute on obvious issues.

**Why the Jaggedness**

Hypothesis: RL training improves verifiable domains (code that works, math that\'s correct). But softer domains --- nuance of intent, when to ask clarifying questions --- aren\'t being optimized.

**The Joke Test**

Same joke ChatGPT told 4 years ago is the same joke it tells today: \'Why do scientists not trust atoms? Because they make everything up.\' Outside of RL, things stay stuck. Models can move mountains agentically yet have a stupid joke library because no one\'s optimizing it.

**Auto-Research as a New Primitive**

Karpathy\'s auto-research package: minimal repo, single GPU, 5-min training cycles, AI agent iterates on training code based on validation loss.

**Why This Matters Beyond ML**

The pattern --- clear metric + iterative loop + AI agent --- applies anywhere you have:

-   Score (objective measurement).

-   Cheap iteration (minutes, not weeks).

-   API to deploy changes.

**From the Episode**

-   Auto-research is the cleanest example of the agent loop pattern.

-   \'The code is almost irrelevant. The architecture and mindset is everything.\'

-   Karpathy expects this to scale to multi-agent collaboration, like a research community.

-   Current architecture: one git branch grows. Future: thousands of branches, all agent-coordinated.

**AgentHub --- Karpathy\'s Next Project**

Released alongside auto-research. \'Bare git repo / message board for swarm of agents working on same codebase.\' No main branch, no PRs, no merges. Sprawling DAG of commits in every direction. Message board for agents to coordinate.

> *GitHub is for humans. AgentHub is for agents.*

**Robotics Coming Next**

Karpathy on robotics:

-   LLMs are generalist --- robotics models still task-specific.

-   Bottleneck: real-world data collection.

-   Sim-to-real gap is closing fast.

-   Once it crosses, expect rapid generalization.

**Education in This Era**

Karpathy founded Eureka Labs after leaving OpenAI and Tesla. View on AI education:

-   Personalized tutoring at scale.

-   Knowledge graphs over textbooks.

-   LLMs as Socratic tutors, not lecture replacements.

-   First course: LLM 101n --- teaching LLMs end-to-end.

**Claude vs GPT --- Karpathy\'s Take**

He uses both. Doesn\'t have strong preference between them --- both have moments where one is dramatically better than the other for a given task. Tip: try both for any non-trivial work.

**The Productivity Divide**

> *If you ask a normal person, they don\'t realize what happened in December. Like, find a random software engineer at their desk --- their default workflow of building software is completely different now. The gap between people doing this and people not is enormous.*

**Closing Predictions**

-   Voice-driven dictation will replace typing. Whisper Flow + similar tools.

-   Multi-claude / multi-codex / multi-anything is the dominant pattern.

-   \'Skill issue\' becomes the dominant frame --- every limitation is now an instruction-design problem.

-   People who learn to design good instructions will compound advantage.

-   Education will shift from \'learn to code\' to \'learn to manifest agents.\'

**Source**

Skill Issue: Andrej Karpathy on Code Agents, AutoResearch, and the Loopy Era of AI by No Priors --- <https://www.youtube.com/watch?v=kwSVtQ7dziU>
