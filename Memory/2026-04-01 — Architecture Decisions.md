*Date: 2026-04-01*
*Type: decision*

## Architecture Decisions — Personal OS v1

- **GitHub is single source of truth.** All knowledge lives in `nigelwlee/nigel-os`. Platform-agnostic — Obsidian, Claude, Hermes all read from the same repo.
- **Obsidian is the writing interface, not the storage layer.** Git plugin auto-syncs every 10 minutes. Working Copy on iOS for manual push.
- **Media files stay in Google Drive.** Only text derivatives (transcripts, summaries) go to GitHub.
- **Hermes reads vault via symlink.** `/root/.hermes/SOUL.md → /root/nigel-os/SOUL/SOUL.md`. No duplicate files.
- **VPS pulls hourly from GitHub.** Crontab on Hetzner (5.161.86.178) keeps Hermes' copy current.
- **Claude.ai access via Claude Project** with key vault files pre-loaded as persistent context.

These decisions are foundational. Revisit only if the sync model breaks or a new tool replaces a layer.
