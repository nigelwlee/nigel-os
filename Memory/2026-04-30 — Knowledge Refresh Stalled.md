*Date: 2026-04-30*
*Type: context*
*Expiry: 2026-08-01*
*Updated: 2026-06-11*

## Knowledge Refresh Cron Still Stalled

All 8 domains manually refreshed 2026-06-11 via Claude Code web session. Cron automation remains broken — no automated refreshes have landed since April 10.

The [[SOPs/Knowledge-Refresh-Cron|Knowledge-Refresh Cron]] should run every Sunday 08:00 AEST via Hermes on the Hetzner VPS. No refresh commits visible in git history from the cron.

**Domain status (as of 2026-06-11):** All 8/8 current — manually refreshed. Strategy, Finance, Sales-Marketing, Engineering, People, Legal all updated 2026-06-11. AI updated 2026-05-07, Creative updated 2026-05-21.

**Likely causes:** Hermes cron not firing, git push credentials expired on VPS, or Hermes search failing silently.

**Action:** SSH into VPS, check `crontab -l`, review `/root/logs/knowledge-refresh.log`, and test `hermes` manually. Fix and verify one successful cycle. This is blocking [[Memory/2026-04-01 — Capture Phase 2 Roadmap|Capture Phase 2]] — no point adding more inputs until the automated loop is restored.
