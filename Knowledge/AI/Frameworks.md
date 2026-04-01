# AI Frameworks

Mental models and patterns for building with AI. Reference when designing systems, debugging agent behaviour, or evaluating model choices.

---

## Prompting Patterns

**System / User / Assistant Structure**
System prompt: defines persona, constraints, output format. User: the input. Assistant: the output. The system prompt is the most leveraged piece of writing in any AI product. Treat it like a contract.

**Chain-of-Thought (CoT)**
Ask the model to reason step by step before giving an answer. Dramatically improves accuracy on multi-step reasoning, math, and logic tasks. Simplest form: add "Think step by step" or "Let's work through this." More structured: provide explicit reasoning steps in a few-shot example.

**Few-Shot Prompting**
Include 2-5 examples of input → output pairs in the prompt. The fastest way to shift output format, tone, or structure without fine-tuning. Works best when examples are representative of the actual distribution of inputs.

**ReAct (Reason + Act)**
Interleave reasoning ("I need to find X, so I should call Y") with tool calls. The model explains its reasoning, calls a tool, observes the result, then continues. This is the standard pattern for tool-using agents.

**Self-Consistency**
Run the same prompt multiple times and take the majority answer. Reduces variance on ambiguous reasoning tasks. Expensive but useful for high-stakes outputs where accuracy matters more than cost.

---

## Agent Architecture Patterns

**Single Agent + Tools**
One LLM with a set of tool definitions. The model decides which tools to call and when. Best for: most tasks, anything that can be described as a single goal. Failure mode: context gets too long, model loses track.

**Orchestrator + Subagents**
One orchestrator agent breaks down a task and delegates to specialist subagents. Each subagent has a focused context. Best for: long-horizon tasks, parallel workstreams, tasks that exceed context limits. Failure mode: communication overhead, error propagation.

**Human-in-the-Loop (HITL)**
Agent runs autonomously but pauses at defined checkpoints for human review or approval. Best for: high-stakes actions, irreversible decisions, tasks where trust isn't yet established. Most real-world agents should start here and remove checkpoints as confidence builds.

**Plan-Execute-Verify**
Agent produces a plan, executes it step by step, and verifies each step before continuing. More reliable than pure ReAct for complex tasks. Slows down simple tasks — apply selectively.

**Memory Architecture**
- In-context memory: recent history in the prompt (fast, limited)
- External memory: vector store or file store (scalable, requires retrieval)
- Semantic compression: periodically summarise older context to free space
- Structured memory: key-value store for facts that need exact retrieval (names, dates, preferences)

---

## Evaluation Patterns

**Vibe Eval**
Read 20-50 outputs manually. Build intuition before building automated evals. Always the first step. Skip it and you'll build the wrong metrics.

**LLM-as-Judge**
Use a stronger model to evaluate outputs from a weaker or faster model. Define a rubric (e.g., accuracy, completeness, tone) and have the judge model score each output. Scales better than human eval, but needs calibration against human judgement.

**Regression Testing**
Maintain a fixed test set of inputs with known-good outputs. Run every time you change the prompt or model. The test set is the real asset — curate it carefully.

**A/B Prompt Testing**
Run two prompt variants on the same input set. Compare outputs using a consistent rubric. Even small prompt changes can have large output effects — test before shipping.

---

## Model Selection Heuristics

| Task Type | Recommended Tier | Why |
|-----------|-----------------|-----|
| Complex reasoning, ambiguous instructions | Frontier (Opus 4.6, GPT-4o) | Worth the cost; errors are expensive |
| Most agent tasks, summarisation, writing | Mid-tier (Sonnet 4.6) | Best quality/cost ratio |
| Classification, routing, simple extraction | Fast/cheap (Haiku) | Overkill to use frontier |
| Local/private data, offline use | Local model (Llama, Mistral) | Privacy or latency constraints |

---

## Infrastructure Patterns

**Streaming**
Always stream output for user-facing applications. Users perceive streaming as faster even at the same total latency. Critical for latency budgets >2s.

**Caching**
Cache identical prompt+context combinations. Prompt caching (now native in most APIs) reduces latency and cost for repeated system prompts. Worth implementing early.

**Rate Limiting & Fallbacks**
Design for API failures. Primary model fails → fallback to a different provider or model. Especially important if you're building on a single model provider.

---

> See also: [[Knowledge/AI/_Briefing|AI Briefing]] | [[Knowledge/_Map|Knowledge]] | [[SOUL]]
