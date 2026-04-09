# Engineering Briefing

> Last synthesized: 2026-04-09
> Insight count: 6 (updated from Inbox synthesis)

---

## Core Thesis

Engineering literacy for a vibe coder is not about writing code — it is about understanding architecture, trade-offs, and system boundaries well enough to direct AI coding agents with precision. You need to know what good code looks like (clean interfaces, minimal coupling, clear data flow) and what good systems look like (reliable, observable, scalable where it matters) so you can evaluate what an AI produces and course-correct before compounding mistakes. The highest-leverage skill is not syntax — it is the ability to decompose a problem into well-scoped units of work that an AI agent can execute independently and correctly.

---

## Key Frameworks

**Fowler's Architecture Decision Spectrum.** Martin Fowler's core insight is that architecture is not a blueprint you draw once — it is the set of decisions that are expensive to change later. Good architecture minimises irreversibility. For a vibe coder, this means every time you prompt an AI to scaffold a new service, choose a database, or define an API contract, you are making an architectural decision whether you realise it or not. The question is never "what is the best architecture?" but "what decisions can I defer, and which ones do I need to get right now?" Fowler's emphasis on evolutionary architecture — designing systems that can change cheaply — is the single most important principle for someone building iteratively with AI tools. Use for: evaluating whether a technical choice locks you in or keeps options open; deciding when to refactor vs. when to extend.

**Beck's Four Rules of Simple Design.** Kent Beck distilled good design into four rules, in priority order: the code passes all tests, reveals intention, contains no duplication, and has the fewest elements possible. This is your quality checklist when reviewing AI-generated code. AI agents are prone to over-engineering — generating abstractions nobody asked for, adding layers of indirection that obscure what the code actually does. Beck's rules give you a filter: does this code do what it should, can I read it and understand why, is there unnecessary repetition, and is there anything here that could be removed without loss? If the answer to any of those is wrong, send it back. Use for: code review of AI-generated output; deciding when code is "done enough" vs. when it needs another pass.

**The 12-Factor App.** Originally written by Heroku's Adam Wiggins, the 12-Factor methodology defines twelve principles for building modern, deployable, scalable web applications. The factors that matter most for a vibe coder are: store config in the environment (not hardcoded), treat backing services as attached resources (so you can swap databases or queues without code changes), keep build/run stages strictly separated, and treat logs as event streams. You do not need to memorise all twelve, but you need to know the philosophy: applications should be stateless, portable, and disposable. When you prompt an AI to build a backend, you should be checking that it is not baking secrets into source code, not writing to the local filesystem assuming persistence, and not coupling itself to a specific deployment target. Use for: reviewing backend architecture; ensuring AI-generated services are production-ready and deployable.

**Kleppmann's Data System Thinking.** Martin Kleppmann's "Designing Data-Intensive Applications" reframes every application as a data system — a composition of databases, caches, queues, and indexes that together provide guarantees about consistency, availability, and durability. The key mental model is that you are always making trade-offs between these properties (the CAP theorem is a simplification, but the intuition holds). For a vibe coder, the practical takeaway is: before you let an AI choose your database, you need to know your access patterns. Are you doing lots of reads or writes? Do you need transactions? Is eventual consistency acceptable? The wrong database choice is one of the most expensive architectural mistakes, and AI agents will default to whatever they have seen most in training data (usually PostgreSQL), which may or may not be right for your use case. Use for: choosing databases, caches, and message queues; understanding trade-offs in data consistency and availability.

**Google SRE Error Budgets.** Google's Site Reliability Engineering framework introduced the concept of error budgets: you define an acceptable level of unreliability (say, 99.9% uptime, meaning ~8.7 hours of downtime per year), and as long as you are within that budget, you prioritise feature velocity over stability. When you exhaust the budget, you stop shipping features and fix reliability. This is transformative for a solo builder because it replaces vague anxiety about "is my app reliable enough?" with a concrete, measurable threshold. It also prevents over-investment in reliability — if your users tolerate occasional errors and your budget is healthy, ship the next feature instead of gold-plating your monitoring. Use for: deciding how much to invest in reliability vs. features; setting SLOs for your products; knowing when downtime is acceptable and when it is a crisis.

**Karpathy's Software 2.0.** Andrej Karpathy's "Software 2.0" thesis argues that increasingly, the "source code" of software is not hand-written logic but learned weights in neural networks. The traditional stack (Software 1.0) is deterministic — you write explicit rules. The Software 2.0 stack is probabilistic — you provide data, define a loss function, and let optimisation find the program. As a vibe coder building with AI tools, you are living in the transition zone. Some parts of your system should be deterministic (auth, payments, data integrity) and some can be probabilistic (content generation, recommendations, search). Knowing which is which is a critical architectural judgment. Use for: deciding where to use AI/ML vs. traditional logic in your products; understanding the reliability and testing implications of probabilistic components.

---

## Active Insights

**AI agents compound architectural mistakes faster than humans do.** When a human developer makes a poor structural decision, the damage accrues slowly as they write code on top of it. An AI agent generating hundreds of lines per prompt will build an entire subsystem on a flawed foundation in minutes. This means architectural review at the beginning of a task — before generation starts — is more valuable than code review after the fact.

**The best prompt for an AI coding agent is an Architecture Decision Record.** ADRs (context, decision, consequences) map almost perfectly to what an AI needs to generate good code: what problem are we solving, what approach are we taking, and what are the constraints. If you write a clear ADR before prompting, the output quality jumps dramatically because you have eliminated the ambiguity that causes AI to make arbitrary choices.

**Most AI-generated code is over-abstracted.** Large language models have been trained on open-source codebases that skew toward library and framework code — code designed for reuse and extension. When you ask for application code, AI tends to produce the same patterns: unnecessary interfaces, premature abstraction layers, factory patterns for things that will only ever have one implementation. You need to actively prompt for simplicity and be willing to flatten the output.

**Database schema is the highest-leverage review point.** If you review nothing else in AI-generated code, review the database schema. Tables, columns, indexes, and relationships define the shape of your application more than any other artifact. A bad schema is expensive to migrate away from, and AI agents frequently get indexing wrong, over-normalise for simple use cases, or under-normalise for complex ones.

**Tests are prompts for future AI agents.** A well-written test suite is not just a safety net — it is a specification that future AI coding sessions can use to understand what the system is supposed to do. When you ask an AI to modify existing code, the tests tell it what must not break. Investing in clear, intention-revealing tests pays compound returns every time you prompt an AI to change something.

**The "just ship it" instinct needs a circuit breaker for auth and payments.** Move fast and iterate works for UI, content, and most features. It does not work for authentication, authorisation, payment processing, or data deletion. These are domains where a single mistake can be catastrophic and where AI-generated code is most likely to have subtle, non-obvious vulnerabilities. Use established libraries (not AI-generated implementations) for these concerns.

**Canvas + TimelineView > SpriteKit for SwiftUI-native rendering.** From [[Projects/MY-ANIM/_Briefing-my-anim|Anima Pet]]: when your app is SwiftUI-native, using Canvas with TimelineView at 60fps integrates better than SpriteKit. SpriteKit's `UIViewRepresentable` bridging adds complexity and state-sync issues. Direct Canvas rendering with `GraphicsContext` is simpler and composable with SwiftUI state.

**SwiftUI's `Color.opacity()` returns `some View`, not `Color`.** This breaks `GraphicsContext` usage where you need actual `Color` values. Workaround: palette alpha helpers that construct colours with alpha directly rather than using `.opacity()` modifier.

**Shared component systems prevent game-per-game technical debt.** From [[Projects/MY-DIDIT/_Briefing-my-didit|Did·It]]: extracting `GameShell`, `SuccessScreen`, `Confetti`, `Toast`, and `useSoundManager` as shared components means each new game is a content problem, not an engineering problem. The component system is the product's internal API.

**Mobile agentic coding is production-viable.** From Personal OS Build: Working Copy → GitHub push → Claude Code Remote → Vercel auto-deploy is a working mobile-first development pipeline. This means you can ship from an iPhone. See [[SOPs/Mobile-Agentic-Coding|Mobile Agentic Coding SOP]].

---

## Open Questions / Active Debates

- **How much automated testing is enough when AI can regenerate code from scratch?** If it is cheaper to re-prompt than to maintain a test suite, does the traditional testing pyramid still apply — or do you only need integration tests and acceptance tests at the boundaries?
- **Should a vibe coder learn to read stack traces and debug, or is "describe the error to the AI" sufficient?** There is an argument that basic debugging literacy (reading logs, understanding HTTP status codes, interpreting error messages) is table stakes even if you never fix the code yourself.
- **When does an AI-built prototype need to be thrown away and re-architected?** Prototypes built through iterative prompting accumulate structural debt in ways that are invisible until they suddenly are not. What are the warning signs that a codebase has crossed the threshold from "iterate on this" to "start over with a proper design"?
- **Is monolith-first still the right advice when AI agents can scaffold microservices so easily?** The conventional wisdom is to start with a monolith and extract services when you have clear boundaries. But if AI can generate service boilerplate in seconds, does the calculus change — or do the operational costs of distributed systems still dominate?

---

## Reading / Watching Queue

- *Designing Data-Intensive Applications* — Martin Kleppmann (the single best book on understanding data systems trade-offs; essential for choosing the right database and architecture)
- *A Philosophy of Software Design* — John Ousterhout (short, opinionated book on what makes code complex vs. simple; directly applicable to reviewing AI output)
- *The Pragmatic Programmer* — David Thomas & Andrew Hunt (timeless principles on building software well; the "tracer bullet" and "broken windows" mental models are especially useful)
- *Site Reliability Engineering* — Betsy Beyer et al. / Google (free online; read the chapters on SLOs, error budgets, and monitoring to understand production reliability)
- *Software 2.0* — Andrej Karpathy (blog post; foundational framing for understanding where AI fits in a software stack)
- *Fundamentals of Software Architecture* — Mark Richards & Neal Ford (practical guide to architectural patterns and trade-offs; good reference for directing AI agents on system design)

---

> See also: [[Knowledge/Engineering/Frameworks|Engineering Frameworks]] | [[Knowledge/_Map-knowledge|Knowledge]] | [[SOUL]]
