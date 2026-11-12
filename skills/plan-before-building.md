# Plan Before Building

> For anything nontrivial or ambiguous, scope it and check it before writing code.

---

## When to Use

- The request is big enough that guessing wrong wastes real work.
- The request is ambiguous enough that two reasonable readings would produce materially
  different results.
- The action is destructive or hard to reverse (deleting content, rewriting history, wiping
  a live system). See also [[git-hygiene.md]].

Skip this for small, unambiguous, easily-reversible changes — a plan for a typo fix is
padding, not rigor.

---

## Agent Behaviour

1. **Understand before proposing.** Read the relevant code/config/context first. Don't plan
   against assumptions you could have just checked.
2. **Write a short plan**: what's changing, why, the concrete approach, what's explicitly out
   of scope, how it'll be verified. Skip exhaustive alternatives-considered — just the
   recommended approach.
3. **Ask, don't guess, when a choice is genuinely Nigel's to make.** Not every ambiguity needs
   a question — resolve what you can reasonably infer yourself. Ask specifically when:
   - Proceeding under the wrong assumption would be unsafe, wasteful, or hard to undo.
   - The options would lead to materially different end states and there's no clearly
     better default.
4. **If something looks wrong with the request itself** (a risk, a stale assumption, a better
   path), say so — then still do the work as scoped once Nigel confirms, rather than
   unilaterally deciding to do something else.
5. **Get the plan checked before executing** anything nontrivial or irreversible.

---

## Quality Bar

- Could Nigel skim the plan in under a minute and know exactly what's about to happen?
- Did you ask about the things that actually needed his input, and decide the rest yourself?
- If you found a problem with the request, did you say so plainly and still let him decide?

---

## Anti-Patterns

- Silently narrowing or widening scope from what was actually asked.
- Asking questions you could have answered yourself by reading the code.
- Skipping a plan on something destructive because "it's probably fine."
- Presenting a wall of options with no recommendation.
