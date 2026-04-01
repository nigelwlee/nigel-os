*Date: 2026-04-01*
*Source: Claude.ai session*

## What We Built

- Created private GitHub repo: `nigelwlee/nigel-os`
- Set up folder structure: SOUL, Skills, Memory, Knowledge, Projects, SOPs, Inbox, Archive, Media-Index
- Installed Obsidian on Mac, connected to GitHub repo via Git plugin
- Configured auto commit-and-sync every 10 minutes
- Wrote and committed SOUL.md — identity layer for all agents
- Created Claude Project with SOUL.md loaded for persistent context
- Cloned nigel-os vault onto Hetzner VPS at `/root/nigel-os`
- Replaced Hermes' local SOUL.md with symlink to vault version
- Set up hourly cron job on VPS to git pull from GitHub

## Architecture Decisions

- GitHub repo is single source of truth for all knowledge — platform agnostic
- Media files (audio/video) stay in Google Drive, text derivatives go to GitHub
- Obsidian is the writing interface, not the storage layer
- Hermes reads vault via symlink — no duplicate files
- Claude.ai access via Claude Project with key vault files pre-loaded

## Single Source of Truth Flow

Obsidian (Mac) → GitHub nigel-os → VPS pulls hourly → Hermes reads it

## What's Next (Phase 2 — Capture Inputs)

- [ ] Set up Readwise for article/link capture → exports to /Inbox
- [ ] Install MacWhisper (desktop) and Whisper Transcription (iOS) for voice
- [ ] Add /save command to Hermes for Telegram drops → /Inbox
- [ ] Establish Claude session note ritual (this file is the first one)
- [ ] YouTube transcript capture via Tactiq (Chrome extension)

## Tools Confirmed

- GitHub: nigelwlee/nigel-os (private)
- Obsidian + Git plugin (auto-sync every 10 min)
- Working Copy on iOS (manual push when needed)
- Hetzner VPS: 5.161.86.178
- Hermes v0.5.0 via OpenRouter

## Key File Locations

- Vault: ~/nigel-os (Mac) and /root/nigel-os (VPS)
- Hermes SOUL symlink: /root/.hermes/SOUL.md → /root/nigel-os/SOUL/SOUL.md
- Crontab: hourly git pull on VPS