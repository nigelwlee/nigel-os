# nigel-os

Portable context for AI-assisted coding projects — how I like to work, a handful of
behavioural skills, and reference material. Point any new AI coding project at this repo
instead of starting from scratch each time.

**Deliberately general.** Nothing here names a specific project, client, or company. If
you're adding something, keep it that way — that's what makes this safe to reuse and share.

## What's here

- **`SOUL.md`** — read this first. How I think, communicate, and want AI to build software
  with me.
- **`skills/`** — specific behavioural guidance, one file per situation (visual verification,
  matching a project's stack, planning before big changes, shipping a preview, verifying
  facts before publishing them, git hygiene).
- **`references/`** — tools and component sources I like pulling from, and the one rule for
  using each without dragging in a mismatched dependency.
- **`LEARNINGS.md`** — a running log of general lessons, so the same gotcha doesn't get
  re-discovered on every project.

## How to use this on a new project

1. Point your AI tool at this repo (clone it, or just paste the relevant file contents into
   context) at the start of a new coding project.
2. Have it read `SOUL.md` first.
3. Skim `skills/` and `references/` for anything relevant to the work at hand.
4. Check `LEARNINGS.md` for anything already learned the hard way.
5. Using Claude Code specifically? You can copy any `skills/*.md` file into your project's
   `.claude/skills/` if you want it available as an invokable skill there — the content is
   plain instructions either way, so it works read-as-context or wired in more formally.

## Keeping it current

When something worth remembering happens on a project — a decision, a lesson, a gotcha — add
it here, generalized (no project specifics), rather than letting it live only in that one
project's history. A short entry in `LEARNINGS.md` is enough; promote it to its own file in
`skills/` only if it's substantial and keeps coming up.
