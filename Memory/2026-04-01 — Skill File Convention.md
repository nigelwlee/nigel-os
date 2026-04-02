*Date: 2026-04-01*
*Type: decision*

## Skill File Convention

Standard structure for all skill files in `/Skills/`:

1. **Name** — what the skill is called
2. **When to Use** — triggers and contexts
3. **Agent Behaviour / Posture** — how the agent should act
4. **How-to / Output Format** — steps and expected output shape
5. **Quality Bar** — what good looks like
6. **Anti-Patterns** — what to avoid

Skills are **agent-agnostic** — no references to specific models or tools. Any LLM reads the file and executes.

Jam (divergent) and Synthesis (convergent) are complementary. Diverge with Jam, converge with Synthesis. Jam explicitly tells the agent not to narrow down.

Target length: ~55 lines per skill. Detailed enough to follow, short enough to not be annoying.
