# Component & Design References

> Sources for UI patterns and inspiration — use these as reference material for the *idea*,
> not as a CLI to run blindly. See [[../skills/stack-matching.md]] first.

---

## 21st.dev

Community-curated React/Tailwind/shadcn component gallery. Good source of interesting
interaction patterns (gradient sweeps, hover effects, animated backgrounds, layout ideas).

**How to use it:** browse for the *effect* Nigel wants, then port the underlying CSS/JS logic
into whatever the current project's actual stack is. Only run the `npx shadcn add ...`
install command if the project is genuinely already React + Tailwind + shadcn.

## shadcn/ui

The component system many 21st.dev snippets are built on top of. Same rule applies — a great
reference for how a component should behave and look, not an automatic dependency.

---

## Adding to this file

When Nigel mentions a new source he likes pulling references from, add it here with the same
two things: what it's good for, and the one rule for using it without dragging in a mismatched
stack.
