*Date: 2026-04-01*
*Source: Claude Code session*

## What We Built

- Created first two skill files in `/Skills/`:
  - **[[Synthesis]]** — convergent mode. Takes messy input (notes, transcripts, research, threads) and produces tight, actionable output. Pyramid principle, recommendation-first, MECE. Output format: TL;DR, Key Insights, Options (if applicable), Next Steps.
  - **[[Jam]]** — divergent mode. Solo sparring partner for creative ideation. Agent posture is bold, opinionated, brings case studies and cross-industry analogies. Expands option space, doesn't converge.
- Established skill file convention: Name → When to Use → Agent Behaviour/Posture → How-to/Output Format → Quality Bar → Anti-Patterns

## Design Decisions

- Skills are agent-agnostic — no references to specific models or tools. Any LLM reads the file and executes.
- Synthesis and Jam are complementary: diverge with Jam, converge with Synthesis. Jam explicitly tells the agent not to narrow down — that's what Synthesis is for.
- Anti-patterns section in each skill encodes Nigel's quality bar and pet peeves (no hedging, no facilitation, no fluff).
- Kept files tight (~55 lines each). Detailed enough to follow, short enough to not be annoying.

## What's Next

- [ ] Test-drive both skills in a live session to calibrate
- [ ] Add more skills as patterns emerge (e.g., writing, GTM planning, due diligence)
- [ ] Add skill files to Claude Project on claude.ai for persistent context alongside SOUL.md
