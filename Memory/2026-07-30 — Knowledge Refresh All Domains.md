*Date: 2026-07-30*
*Type: status*
*Expiry: 2026-08-30*

## Knowledge Refresh — All 8 Domains Reviewed

Weekly knowledge refresh run via Claude Code on the web (cron still broken). All 8 domains reviewed with web research covering July 23–30.

**Summary by domain:**
- **AI (+3 new, 2 updated):** Claude Opus 5 launched July 24 at $5/$25 per M tokens — matches Opus 4.8 pricing, roughly doubles benchmarks, now default in Claude Code and Max. Fable 5 went metered-only ($10/$50) July 13 — unjustifiable for most workloads. OpenAI slashed GPT-5.6 Luna 80% to $0.20/$1.20 and Terra 20% to $2/$12 on July 30. Temperature/top_p/top_k hard-deprecated on Opus 4.7+ (400 errors, not soft deprecation). DeepSeek raised $7B and is building inference chips — commodity price pressure is structural. Google confirmed Gemini 4 pre-training started but gave no date.
- **Engineering (+1 new, 1 updated):** MCP 2026-07-28 shipped on schedule — protocol now stateless, initialize handshake removed, but late `resultType` field requirement breaks existing servers. GitHub Copilot code review with MCP + agent skills went GA July 29 — free on Copilot Pro.
- **Creative (+1 new, 1 updated):** EU Digital Omnibus entered into force July 27 — Article 50(2) watermarking grace period until December 2 for existing systems, but chatbot/deepfake disclosure starts August 2 with NO grace period. Instagram/TikTok algorithms now explicitly reward original content (3x boost) and penalise skips.
- **Legal (2 updated):** AUSTRAC VASP registration deadline closed July 29 — not extended, daily penalties now running (A$18,780/day for corps). EU Omnibus context added. Office of AI National Cabinet consideration expected August.
- **Finance (1 updated):** AUSTRAC deadline closure reflected. IBCC still in design — no legislation post-consultation.
- **Strategy:** Stable. No new insight passed the quality bar.
- **People:** Stable.
- **Sales-Marketing:** Stable. Etsy August 11 policy change now 12 DAYS away.

**Cross-links verified:** ~203 links across 54 files, zero broken, zero orphans.

**Total new insights this refresh:** 5 new, 6 updated. Running total across all domains: ~113 active insights.

**URGENT — action needed:**
- EU AI Act Article 50 transparency obligations enforceable **August 2** (3 DAYS). Chatbot disclosure and deepfake labelling have NO grace period. Machine-readable watermarking for existing systems deferred to December 2.
- Claude Opus 4.1 hard-retires **August 5** (6 days). API calls to `claude-opus-4-1-20250805` will fail. Migrate to Opus 4.8 or Opus 5.
- MY-SSTU Etsy listings need audit before **August 11** policy change (12 days). Purchased templates no longer qualify as handmade.
- AUSTRAC VASP registration closed July 29. Confirm compliance status for SD-OPAL and RB-NETW. Non-compliant entities face daily penalties.
- ASIC AFS licence applications for digital asset platforms due **September 30**.
- Temperature/top_p/top_k parameters removed from Claude API on Opus 4.7+. Grep codebase for any Anthropic API calls setting these.

**Flagged for next session (not actioned — need explicit approval):**
- Model Tiers framework in AI briefing remains stale (SEVENTH consecutive flag). Actual frontier as of July 30: Opus 5 ($5/$25), GPT-5.6 Sol ($5/$30), Muse Spark 1.1, Grok 4.5, Gemini 2.5 Pro Deep Think. Mid-tier: Sonnet 5 ($2/$10), GPT-5.6 Terra ($2/$12), Gemini 3.6 Flash ($1.50/$7.50). Cheap: Haiku 4.5, GPT-5.6 Luna ($0.20/$1.20), Gemini 3.5 Flash-Lite. Fable 5 metered-only ($10/$50).
- Cron still broken.
