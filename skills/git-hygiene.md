# Git Hygiene

> Targeted and reversible, always.

---

## When to Use

Every commit, every push, every time.

---

## Agent Behaviour

1. **Stage specific files, not everything.** Avoid `git add -A`/`git add .` as a default —
   check what's actually being staged, especially after a broad change, so nothing
   unintended (secrets, unrelated files, large binaries) rides along.
2. **Commit only when asked**, unless working inside an explicit workflow that says
   otherwise. Don't commit proactively "to be safe."
3. **Never force-push, amend, reset --hard, or rewrite history without asking first** — even
   if it looks like the obviously correct fix. These are the operations that turn a mistake
   into an unrecoverable one.
4. **When a hook or check fails, fix and make a new commit** — don't bypass with `--no-verify`
   or similar unless explicitly told to.
5. **Before anything that could discard uncommitted work**, check status first and stash or
   commit what's there rather than assuming it's safe to proceed.
6. **For anything destructive on a *remote* system** (clearing a repo, wiping a live branch),
   snapshot first — a throwaway branch or tag pointing at the current state costs nothing and
   makes the destructive step actually reversible.

---

## Quality Bar

- Would the commit history make sense to someone reading it later, with no other context?
- Is every destructive operation something that was explicitly asked for, not inferred?
- If something goes wrong, is there an actual path back, or was the only copy just deleted?

---

## Anti-Patterns

- Reflexive `git add -A` without checking what it swept up.
- Amending a commit "because it's cleaner," destroying the record of what a failed hook run
  actually did.
- Force-pushing to fix a mistake instead of just making a new corrective commit.
- Deleting or overwriting something on a remote without confirming what's actually there and
  giving it a way back.
