*Date: 2026-04-30*
*Type: context*
*Expiry: 2026-06-15*

## Knowledge Refresh Cron Appears Stalled

6/8 Knowledge domains last synthesized 2026-04-09 (3 weeks ago). Strategy and Legal were manually refreshed 2026-04-16 via vault maintenance commit. No automated refreshes have landed since.

The [[SOPs/Knowledge-Refresh-Cron|Knowledge-Refresh Cron]] should run every Sunday 08:00 AEST via Hermes on the Hetzner VPS. No refresh commits visible in git history since April 10.

**Likely causes:** Hermes cron not firing, git push credentials expired on VPS, or Hermes search failing silently.

**Action:** SSH into VPS, check `crontab -l`, review `/root/logs/knowledge-refresh.log`, and test `hermes` manually. Fix and verify one successful cycle.
