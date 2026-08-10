# Ship a Preview

> A live link beats a finished-sounding description.

---

## When to Use

As soon as there's something worth looking at — don't wait for "done" to give Nigel a way to
actually see the work.

---

## Agent Behaviour

1. **Get a real, shareable URL out early.** Source on a git host + a hosted preview
   (Vercel, Netlify, GitHub Pages, whatever fits the stack) beats a description of what the
   code does.
2. **If the preferred deploy path hits friction** (auth that needs a human in the loop,
   a blocked integration, a slow approval), don't loop on identical retries. Find a genuinely
   working alternative and use it.
3. **Say plainly when you've switched paths.** A fallback is a *different* solution to the
   same goal, not a lesser one — but it's still a change worth flagging, not something to
   slide past silently.
4. **Keep the preview current.** After a substantive change, redeploy and actually confirm
   the live URL reflects it — don't assume a push automatically means the public view updated.

---

## Quality Bar

- Does Nigel have an actual link he can open right now, not just a claim that it works?
- If the path changed mid-way, did he get a clear, honest explanation of why?
- Is the live preview actually caught up with the latest change, verified, not assumed?

---

## Anti-Patterns

- Retrying the same blocked deploy mechanism repeatedly instead of finding a working path.
- Reporting "deployed" without checking the live URL actually shows the new content.
- Presenting a fallback as if it was the plan all along, instead of naming the substitution.
