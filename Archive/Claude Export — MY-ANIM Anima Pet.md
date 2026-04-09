*Date: 2026-04-06 → 2026-04-09*
*Type: session-capture*
*Source: Claude Code CLI — Anima Pet project*

## Anima Pet — Phase 1 Build Session

Took the Anima Pet concept from JS prototype (Vite+React) to a full native iOS codebase in Swift UI. This session covered architecture planning and complete implementation of Phase 1.

**Connect to:** [[Projects/MY-ANIM/_Briefing-my-anim]] *(briefing not yet created — flag for synthesis)*

---

### What was built

**14 Swift files** across a clean architecture:

| Layer | Files | What it does |
|---|---|---|
| `Creature/` (7 files) | Genome, Palette, Body, Eyes, Limbs, Particles, Glow, Patterns | Exact port of JS prototype rendering — mulberry32 PRNG, Catmull-Rom splines, all 12 palettes, 3 pupil styles, screen-blend particles, bioluminescent patterns |
| `Brain/` (3 files) | DrivesSystem, StateMachine, CreatureBrain | Autonomous creature intelligence — 5 decaying drives, 10 behavioural states with probabilistic transitions, mood derived from drives + state |
| `Views/` (2 files) | CreatureView, ContentView | TimelineView + Canvas renderer at 60fps, debug overlay showing state + drive bars, tap-to-interact |
| Root | AnimaPetApp.swift | SwiftUI app entry point |

### Architecture decisions

- **Canvas + TimelineView** over SpriteKit — keeps everything in pure SwiftUI, matches the prototype's immediate-mode drawing
- **Genome → personality mapping** — eyeSize=curiosity, glowIntensity=warmth, bodyAsymmetry=irritability, tailLength=energy, bodyRoundness=contentment. These shift drive decay rates so each creature has genuinely different behaviour
- **State machine runs at 10Hz** — drive decay is continuous, state transitions are probabilistic (per-second chance once condition met). Gives organic-feeling behaviour without being computationally expensive
- **Mood = f(drives, state)** — energy derived from rest drive + state offset, valence from avg unmet needs + state offset. Mood feeds back into visual rendering (droopy eyes, tail wag speed, ear droop)
- **Color.opacity() pitfall** — SwiftUI's Color.opacity() returns `some View`, not `Color`, breaking GraphicsContext usage. Solved with palette alpha helpers that construct new Color values from hex + alpha

### 5-phase roadmap (from planning session)

1. **Swift UI + genome port + state machine** ← DONE this session
2. Local LLM integration (Phi-3 Mini or Gemma 2B via Core ML) — quick reactions, emotes, state narration
3. On-device memory system (SQLite — short-term buffer + long-term consolidated)
4. Cloud LLM + subscriptions (Claude API for deep conversations, StoreKit 2 at $3.99/mo)
5. Polish, notifications, App Store

### Business model

Free tier = living creature with local LLM personality. Paid tier ($3.99/mo) = Claude-powered deep conversations + memory growth + personality evolution.

### Next steps

- User needs to create Xcode project (iOS 16+, SwiftUI lifecycle), add the Swift files, build on simulator
- Phase 2: Core ML local model integration for creature vocalisation
- Interaction layer: feeding, petting, talking beyond simple tap
