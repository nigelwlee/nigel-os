# AI Briefing

> Last synthesized: 2026-04-01
> Insight count: 0 (seed version)

---

## Core Thesis

We are in the agentic transition: AI is moving from answering questions to taking actions. The value is shifting from the model itself (commodity) to the context, memory, and tooling layered on top. For a builder: the moat is not the model — it is the workflow, the data, and the speed of iteration.

---

## Key Frameworks

**The Context Window is the Computer**
Everything an LLM can do in a given interaction is bounded by what's in its context. Designing what goes in context — and what doesn't — is the core engineering problem. Implication: curated, structured context beats raw data at any scale.

**Agent = LLM + Memory + Tools + Loop**
An agent is not just a prompt. It is: a model that reasons, memory that persists state, tools that take actions, and a loop that keeps going until the task is done. Each component has design choices. Getting all four right is hard; most "agents" only have one or two.

**Model Tiers (2026 landscape)**
- Frontier reasoning: Claude Opus 4.6, GPT-4o, Gemini 1.5 Pro — use for complex reasoning, ambiguous instructions, high-stakes outputs
- Mid-tier / fast: Claude Sonnet 4.6, Gemini Flash — use for most tasks, good quality at lower latency/cost
- Cheap / local: Haiku, Mistral, Llama — use for classification, routing, simple extraction

**RAG vs. Fine-Tuning**
RAG (Retrieval-Augmented Generation): inject relevant context at runtime. Fine-tuning: bake knowledge into model weights. Use RAG for: frequently changing information, large knowledge bases, transparency. Use fine-tuning for: style/tone, fixed formats, domain-specific reasoning patterns. Most real-world cases need RAG first, fine-tuning later if at all.

**Prompt Engineering Hierarchy**
System prompt → Few-shot examples → Chain-of-thought → Tool definitions. Each layer shapes model behavior. The system prompt sets the persona and constraints. Few-shot examples are the fastest way to shift output format or style. Chain-of-thought ("think step by step") improves accuracy on reasoning tasks.

**Evals are the Moat**
You can't improve what you can't measure. A good eval suite (test cases with expected outputs) is what separates teams that iterate quickly from teams that guess. Building evals is boring and most people skip it — that is the opportunity.

---

## Active Insights

**The interface layer is being rebuilt.** Chat is not the final form of AI interaction. Voice, ambient agents, and inline agents (inside existing tools) will be the primary surfaces within 2-3 years. Build for the current interface but design for portability.

**Context quality > model quality.** A well-structured prompt with the right context beats a frontier model with a bad prompt. Invest in prompt engineering before chasing model upgrades.

**Agents fail at the edges.** Most agent failures happen at tool boundaries (wrong API call), memory boundaries (forgetting earlier context), and ambiguity (when the user's intent wasn't clear). Design for these failure modes explicitly.

**OpenAI is infrastructure, not a destination.** The model providers are commoditising. The value is in the application layer: the workflow, the memory architecture, the UI. Build products, not wrappers.

**The cheapest eval is a human in the loop.** Before you automate the QA, make sure a human has validated the output at least 50 times. Most premature automation fails because the definition of "correct" was never tested.

**Latency is a UX problem.** Users tolerate ~2-3 seconds before they assume something is broken. Streaming output is not optional for user-facing AI products. Design latency budgets explicitly.

---

## Open Questions / Active Debates

- When is multi-agent better than single-agent? What are the actual coordination costs?
- How do you build a memory system that degrades gracefully (old info doesn't pollute new reasoning)?
- At what point does a personal AI system need its own dedicated model vs. a well-prompted frontier model?
- What is the right architecture for a personal OS agent that reads from a structured knowledge vault?

---

## Reading / Watching Queue

- Anthropic model cards and system prompt documentation
- LangGraph documentation (state machines for agents)
- Simon Willison's blog (pragmatic AI practitioner perspective)
- *The Bitter Lesson* — Rich Sutton (why scale beats clever algorithms)
- Latent Space podcast (AI engineering deep dives)
