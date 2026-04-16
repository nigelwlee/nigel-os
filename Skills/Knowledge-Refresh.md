# Knowledge-Refresh

> Search, evaluate, and update a knowledge domain briefing. Keep the vault's Active Insights current without noise.

---

## When to Use

- Weekly scheduled run (automated via Hermes cron)
- On demand: "refresh the [domain] briefing" or "what's changed in [domain] lately"
- After a significant industry event that affects a domain

---

## Agent Behaviour

### 1. Target
Identify which domain(s) to refresh. Default: all 8 (Strategy, AI, Creative, Legal, Sales & Marketing, Finance, People, Engineering). On demand: the specified domain only.

### 2. Research
For each domain, search for recent developments using these lenses:
- **New frameworks or models** that have gained traction in the last 3-6 months
- **Shifts in consensus** — things the field used to believe that are now disputed
- **New data or case studies** that change the calculus on existing insights
- **Emerging debates** that belong in Open Questions

Search using: domain name + "2025 2026", leading practitioner blogs and substacks, recent conference talks, and the reading queue sources already listed in each briefing.

### 3. Evaluate
For each candidate insight, ask:
- Is this **non-obvious**? If any smart person would already know it, skip it.
- Is this **decision-relevant**? Does it change what Nigel should do or how he should think?
- Is it **durable**? Will this still be true in 6 months, or is it a news item?

Only proceed if all three pass.

### 4. Update the Briefing
Edit the `_Briefing-{domain}.md` file:
- **Active Insights**: add new passing insights. Mark stale ones with ~~strikethrough~~ and a note, or remove them if clearly obsolete.
- **Open Questions**: add new questions that emerged. Remove or move to resolved any that have clear answers now.
- **Metadata**: bump `> Last synthesized:` to today's date. Update `> Insight count:` to reflect total active insights.
- **Do not touch**: Core Thesis, Key Frameworks. These are stable. Only change them with explicit approval.

### 5. Report
After updating, produce a short summary:
- Which domains were refreshed
- What was added, what was removed, and why
- Any domain where nothing changed (and why — is the field stable, or did the search turn up nothing useful?)

Send summary to Nigel via Telegram (Hermes) or output directly (Claude Code/claude.ai).

---

## Quality Bar

- **One insight per real development.** Don't pad. Three sharp insights beat seven generic ones.
- **Cite the signal.** Each new insight should reference what prompted it — a paper, a case study, a practitioner post. One line is enough.
- **Preserve voice and format.** The briefings have a consistent style: **Bold claim.** followed by 1-2 sentences. Match it exactly.
- **When in doubt, leave it out.** A false positive (adding noise) damages the vault more than a false negative (missing something).

---

## Anti-Patterns

- **Rewriting the whole briefing.** You're refreshing Active Insights and Open Questions only. Everything else stays.
- **News vs. insight.** "OpenAI launched X" is not an insight. "X changes the cost structure of Y in a way that makes Z viable for solo builders" is.
- **Touching the Core Thesis.** This is a considered position. It doesn't change weekly. Flag it separately if you think it needs updating.
- **Adding insights that are already implied.** If the insight is just a restatement of an existing framework, it doesn't belong in Active Insights.

---

## Automation Setup

See [[SOPs/_Map-sops|SOPs]] → [[SOPs/Knowledge-Refresh-Cron|Knowledge-Refresh Cron]] for the Hermes VPS cron configuration.

---

> See also: [[Jam]] | [[Synthesis]] | [[Knowledge/_Map-knowledge|Knowledge]] | [[Skills/_Map-skills|Skills]]
