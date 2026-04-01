# Knowledge-Refresh Cron

> Automates the weekly Knowledge domain refresh via Hermes on the Hetzner VPS.

[[SOPs/_Map-sops|SOPs]]

---

## Purpose

Runs the [[Knowledge-Refresh]] skill across all 8 Knowledge domains every Sunday at 08:00 AEST. Commits updated briefings to GitHub and sends a summary to Nigel via Telegram.

**Trigger:** Scheduled — weekly, Sunday 08:00 AEST (22:00 UTC Saturday)

---

## Steps

### 1. Add the cron job on the VPS

SSH into Hetzner VPS and run `crontab -e`. Add:

```
0 22 * * 6 /root/scripts/knowledge-refresh.sh >> /root/logs/knowledge-refresh.log 2>&1
```

### 2. Create the script at `/root/scripts/knowledge-refresh.sh`

```bash
#!/bin/bash
set -e

VAULT=/root/nigel-os
LOG_DATE=$(date '+%Y-%m-%d %H:%M')

# Pull latest vault
cd $VAULT
git pull origin main

# Run Hermes with the Knowledge-Refresh prompt
# Hermes reads SOUL.md and the Knowledge-Refresh skill automatically
PROMPT="Run the Knowledge-Refresh skill across all 8 Knowledge domains. Search for recent developments in each domain, update Active Insights and Open Questions in each _Briefing file, bump the Last synthesized date and insight count. After updating, commit all changes to git with message 'knowledge refresh: $LOG_DATE' and push to origin main. Then send me a Telegram summary of what changed."

hermes "$PROMPT"
```

Make it executable: `chmod +x /root/scripts/knowledge-refresh.sh`

### 3. Create the log directory

```bash
mkdir -p /root/logs
```

---

## Verification

- Check `/root/logs/knowledge-refresh.log` after the first Sunday run
- Confirm a new commit appears in `nigelwlee/nigel-os` on GitHub with message `knowledge refresh: YYYY-MM-DD`
- Confirm Telegram message received with domain-by-domain summary

---

## Troubleshooting

**Hermes fails to push to GitHub:** Check that the VPS git config has push credentials. Run `git push origin main` manually to test.

**No changes committed:** Either nothing passed the quality bar (legitimate) or the search failed. Check the log for Hermes output.

**Cron not running:** Run `crontab -l` to verify the entry exists. Check `grep CRON /var/log/syslog` for execution logs.

---

> See also: [[Knowledge-Refresh]] skill | [[SOPs/_Map-sops|SOPs]]
