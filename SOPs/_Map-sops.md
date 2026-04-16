# SOPs

> Repeatable operational procedures. Step-by-step instructions for recurring tasks that are too complex to hold in memory.

[[SOUL]]

## Convention

Each SOP is a single file. Filename: `{Verb}-{Topic}.md` (e.g., `Knowledge-Refresh-Cron.md`).

### Format

- **Purpose**: what this SOP does and when to run it
- **Trigger**: manual, scheduled, or event-driven
- **Steps**: numbered, specific, executable
- **Verification**: how to confirm it worked
- **Troubleshooting**: common failure modes

## Contents

- [[SOPs/Knowledge-Refresh-Cron|Knowledge-Refresh-Cron]] — weekly Hermes cron to refresh Knowledge domain briefings
- [[SOPs/Etsy-Listing-Generation|Etsy-Listing-Generation]] — repeatable Cricut SVG listing workflow for Sleepy Studios
- [[SOPs/Mobile-Agentic-Coding|Mobile-Agentic-Coding]] — ship code from iPhone via Working Copy → GitHub → Claude Code Remote → Vercel
