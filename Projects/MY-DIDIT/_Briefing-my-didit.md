# MY-DIDIT — Did·It

> **Status:** Active — 4 games shipped, landing page live, targeting first 100 users
> **Type:** Owned product (educational toddler games)
> **Started:** ~January 2026
> **Domain:** didit.games
> **Tech:** React + Vercel + Firebase (`did-it-e306e`)

---

## Overview

Did·It is an educational toddler games app. Each game teaches a real-world professional/academic concept through play. Core philosophy: "connection time, not screen time" — co-play between parent and child is the mechanic.

Brand tagline: "We packed big concepts and real-world skills into tiny games."

---

## Design Principles

- No text in games
- No fail states
- One concept per game
- Celebration-first design
- Large tap targets
- Co-play as core mechanic

---

## Games Shipped

| Game | Concept | Notes |
|---|---|---|
| Little DJ | Music/rhythm | First game |
| Little Shopper | Financial literacy | Money, counting, transactions |
| Little Engineer | Circuits/switches | 3 levels with replayability |
| Little Scientist | Science exploration | Experimentation |

---

## Shared Component System

- `GameShell` — wrapper for all games
- `SuccessScreen` — celebration after completion
- `Confetti` — `triggerMilestone()` particle system
- `Toast` — in-game notifications
- `useSoundManager` — audio hook

---

## GTM Strategy

- **Target:** First 100 users via Facebook parenting groups + personal WhatsApp
- **Content strategy:** No-face co-play content ("look what we did together")
- **Email:** Firebase custom domain configured
- **Reddit:** Deferred until karma established
- **Brand differentiator:** Physical co-play angle — parents and kids building together

---

## Key Decisions

- React + Vercel over native — speed to market, web-first distribution
- No-face content strategy — brand safety, co-play focus
- One concept per game — clarity over feature density
- Codebase at `/Users/dannelim/App 2/didit-app/` (never use legacy `/Users/dannelim/App/`)

---

## Working Notes

- Landing page live with physics dots, SVG squiggles, founder story
- Email list started
- Replayable mechanics: 3-level structure per game
- Brand evolved from MYLO → Did·It

---

> See also: [[Projects/_Map-projects|Projects]] | [[SOUL]]
