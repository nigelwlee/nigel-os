# AI Briefing

> Last synthesized: 2026-05-07
> Insight count: 7 (updated from MY-MYST processing)

---

## Core Thesis

We are in the agentic transition: AI is moving from answering questions to taking actions. The value is shifting from the model itself (commodity) to the context, memory, and tooling layered on top. For a builder: the moat is not the model — it is the workflow, the data, and the speed of iteration.

---

## Key Frameworks

**The Context Window is the Computer**
Everything an LLM can do in a given interaction is bounded by what's in its context. Designing what goes in context — and what doesn't — is the core engineering problem. Implication: curated, structured context beats raw data at any scale.

**Agent = LLM + Memory + Tools + Loop**
An agent is not just a prompt. It is: a model that reasons, memory that persists state, tools that take actions, and a loop that keeps going until the task is done. Each component has design choices. Getting all four right is hard; most "agents" only have one or two. The Personal OS is an implementation of this pattern — see [[SOUL]] for the identity layer.

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

**On-device LLMs via Core ML are viable for personality-driven interactions.** From [[Projects/MY-ANIM/_Briefing-my-anim|Anima Pet]]: Phi-3 Mini or Gemma 2B running locally via Core ML can power creature reactions and emotes without API costs or latency. Local-first AI preserves privacy and works offline — cloud LLM (Claude API) becomes the premium upgrade path.

**Hermes pattern: Telegram + OpenRouter + structured vault = working personal agent.** The Personal OS agent architecture is: Telegram as command interface → OpenRouter for model access (Claude Sonnet) → symlinked vault for context. VPS pulls vault hourly from GitHub. This is a minimal but functional agent loop (LLM + Memory + Tools + Loop).

**Claude Projects with pre-loaded vault files are a lightweight RAG substitute.** Instead of building a full RAG pipeline, loading key vault files (SOUL.md, briefings) as persistent context in a Claude Project gives 80% of the benefit at 0% of the infrastructure cost. Good enough until the knowledge base exceeds context window limits.

**The ADHD thought-org app was the precursor to the Personal OS.** The Jan 2026 web app for thought organization (121-message session) was the original second-brain concept. The current agent-native OS is its evolved successor. Pattern: tools built for personal frustration become the best products.

**Multi-model cross-validation is a novel application of AI diversity.** From [[Projects/MY-MYST/_Briefing-my-myst|Mystic Scientist]]: running the same structured prompt across 5 frontier models (ChatGPT, Claude, Grok, DeepSeek, Qwen) and looking for convergent patterns in their independent outputs. When multiple models trained on different data agree on something, the signal is stronger than any single model's output. Pattern is generalizable beyond mysticism — useful for any domain where confidence matters more than speed.

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

---

> See also: [[Knowledge/AI/Frameworks|AI Frameworks]] | [[Knowledge/_Map-knowledge|Knowledge]] | [[SOUL]]
