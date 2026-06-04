*Date: 2026-04-30*
*Type: context*
*Expiry: 2026-08-01*
*Updated: 2026-06-04*

## Knowledge Refresh Cron Still Stalled

6/8 Knowledge domains last synthesized 2026-04-09 (~8 weeks ago). Strategy and Legal were manually refreshed 2026-04-16. AI refreshed 2026-05-07, Creative refreshed 2026-05-21 — both via manual vault maintenance, not the cron. No automated refreshes have landed since April 10.

The [[SOPs/Knowledge-Refresh-Cron|Knowledge-Refresh Cron]] should run every Sunday 08:00 AEST via Hermes on the Hetzner VPS. No refresh commits visible in git history from the cron.

**Stale domains (as of 2026-06-04):** Sales-Marketing, Finance, People, Engineering (all 2026-04-09), Strategy, Legal (both 2026-04-16).

**Likely causes:** Hermes cron not firing, git push credentials expired on VPS, or Hermes search failing silently.

**Action:** SSH into VPS, check `crontab -l`, review `/root/logs/knowledge-refresh.log`, and test `hermes` manually. Fix and verify one successful cycle. This is blocking [[Memory/2026-04-01 — Capture Phase 2 Roadmap|Capture Phase 2]] — no point adding more inputs until the automated loop is restored.
