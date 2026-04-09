# Mobile Agentic Coding

> Ship code from an iPhone using Working Copy, GitHub, Claude Code Remote, and Vercel.

---

## Purpose

Enable full development workflow from mobile when away from desktop. Covers code editing, AI-assisted development, and deployment.

## Trigger

Manual — whenever you need to code, review, or deploy from mobile.

## Steps

1. **Open Working Copy on iOS**
   - Pull latest from GitHub repo
   - Make edits directly or review changes

2. **Push to GitHub**
   - Commit changes in Working Copy
   - Push to remote branch

3. **Trigger Claude Code Remote**
   - Open Claude Code session targeting the repo
   - Prompt Claude with the task (bug fix, feature, refactor)
   - Review and approve changes

4. **Auto-deploy via Vercel**
   - Vercel picks up the push automatically
   - Preview deployment generates on branch pushes
   - Production deploys on merge to main

5. **Verify**
   - Check Vercel preview URL on mobile
   - Confirm deployment status in Vercel dashboard or GitHub checks

## Verification

- Vercel preview URL is live and functional
- Changes reflect correctly in the deployed version

## Troubleshooting

- **Working Copy sync fails:** Check GitHub auth token hasn't expired
- **Claude Code Remote not responding:** Verify session is active; may need to restart
- **Vercel build fails:** Check build logs in Vercel dashboard — usually dependency or env var issues

---

> See also: [[Knowledge/Engineering/_Briefing-engineering|Engineering]] | [[SOPs/_Map-sops|SOPs]]
