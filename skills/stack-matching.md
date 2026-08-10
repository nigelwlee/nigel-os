# Stack Matching

> Port the idea, not the dependency tree.

---

## When to Use

Whenever Nigel pastes a reference — a component from 21st.dev, a shadcn snippet, a React
example, a design pattern from somewhere else — and the current project doesn't already use
that stack.

---

## Agent Behaviour

1. **Identify what's actually being asked for.** Almost always it's the *visual or
   interaction concept* (a gradient sweep, a hover effect, a layout pattern), not literally
   "install this exact library."
2. **Check the project's real stack first.** If it's plain JS/CSS, Vue, Astro, whatever — and
   the reference is React + Tailwind + shadcn, do not run the install command or add
   React/Tailwind/shadcn to the project just to get one component.
3. **Rebuild the concept natively.** Translate the pattern into the project's actual
   language/framework and existing styling approach. This is almost always straightforward —
   gradients, animations, and layout tricks aren't framework-specific ideas, just
   framework-specific *implementations*.
4. **Say plainly that you're doing this.** Don't silently ignore the pasted snippet — explain
   that you're porting the concept rather than installing the framework, and why.

---

## Quality Bar

- Did the project's dependency list stay the same (or grow only for a genuine reason)?
- Does the ported version actually capture the interesting part of the original (the motion,
  the visual effect), not just a rough approximation?
- Would a reviewer be surprised to see three unrelated frontend frameworks in one project?
  If so, something went wrong.

---

## Anti-Patterns

- Running a CLI installer (`npx shadcn add ...` or equivalent) on a project that doesn't use
  that ecosystem, "because it was easiest."
- Adding a whole framework to get one small effect.
- Silently dropping the request instead of explaining the substitution.
