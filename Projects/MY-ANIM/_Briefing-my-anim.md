# MY-ANIM — Anima Pet

> **Status:** Active — Phase 1 complete (Swift port), Phase 2 next (local LLM)
> **Type:** Owned product (iOS app)
> **Started:** ~February 2026
> **Platform:** iOS 16+, SwiftUI

---

## Overview

Anima Pet is a native iOS virtual creature app. A living digital pet with a genome-driven personality, behavioural state machine, and (planned) LLM-powered conversation. Nigel is sole builder.

Originally prototyped in JavaScript (Vite+React), fully ported to Swift/SwiftUI.

---

## Architecture

**14 Swift files across 4 layers:**
- **Creature layer (7 files):** Genome, Palette, Body, Eyes, Limbs, Particles, Glow, Patterns
- **Brain layer (3 files):** DrivesSystem, StateMachine, CreatureBrain
- **Views layer (2 files):** CreatureView, ContentView
- **Root:** App entry

**Rendering:** Canvas + TimelineView at 60fps (better than SpriteKit for SwiftUI-native). Mulberry32 PRNG, Catmull-Rom splines, 12 palettes, 3 pupil styles, screen-blend particles, bioluminescent patterns.

**Intelligence:** 5 decaying drives, 10 behavioural states, mood system (energy/valence). State machine at 10Hz with probabilistic transitions.

**Genome → Personality mapping:**
- eyeSize = curiosity
- glowIntensity = warmth
- bodyAsymmetry = irritability
- tailLength = energy
- bodyRoundness = contentment

Each trait affects drive decay rates, producing unique behaviour per creature.

**SwiftUI pitfall discovered:** `Color.opacity()` returns `some View` (not `Color`), breaking `GraphicsContext` usage. Solved with palette alpha helpers.

---

## Roadmap

| Phase | Description | Status |
|---|---|---|
| 1 | Swift UI + genome port + state machine | **Done** |
| 2 | Local LLM (Phi-3 Mini or Gemma 2B via Core ML) for reactions/emotes | Next |
| 3 | On-device memory (SQLite) | Planned |
| 4 | Cloud LLM + subscriptions (Claude API @ $3.99/mo) | Planned |
| 5 | Polish, notifications, App Store launch | Planned |

---

## Business Model

- **Free tier:** Living creature + local LLM
- **Paid tier ($3.99/mo):** Claude-powered conversations + memory + personality evolution

---

## Key Decisions

- Canvas+TimelineView over SpriteKit — native SwiftUI, better integration
- 10Hz state machine — fast enough for natural behaviour, cheap enough on battery
- Local-first LLM before cloud — privacy story, works offline, reduces ongoing cost

---

## Working Notes

- Xcode project: iOS 16+, SwiftUI lifecycle
- Next step: Core ML integration for creature vocalisation
- Expand interaction layer (feeding, petting, talking)

---

> See also: [[Projects/_Map-projects|Projects]] | [[Knowledge/AI/_Briefing-ai|AI]] | [[Knowledge/Engineering/_Briefing-engineering|Engineering]] | [[SOUL]]
