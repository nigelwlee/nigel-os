# Learnings

> A running, dated log of general lessons worth not re-learning on the next project. One
> entry per lesson. General only — no project names, client names, or project-specific
> facts. If a lesson is really about a specific tool/library quirk, it can live here or in
> `skills/` if it's substantial enough to deserve its own file.

Add new entries at the top, dated, in one short paragraph. Prune anything that stops being
true (tools change).

---

**2026-08-10 — Headless Chrome doesn't reliably respect `--window-size` for narrow widths.**
Requesting a small width (e.g. 375px) via the launch flag can still lay the page out at a
larger effective width — Chrome enforces some minimum in headless mode. A screenshot taken
this way looks cropped to the requested width, but the underlying layout rendered wider,
which reads exactly like a horizontal-overflow bug without being one. Fix: force the layout
viewport via the DevTools Protocol's `Emulation.setDeviceMetricsOverride`, independent of the
window/screenshot dimensions.

**2026-08-10 — Vite (and similar) dev-server module caches can go stale in a way that looks
like the fix didn't work.** After editing a source file and confirming the change is correct
on disk, the browser can keep computing old styles/behaviour for a surprisingly long time on
a long-running dev server. Confirmed by inspecting actual computed styles/loaded modules, not
just re-eyeballing the page. Fix: kill the dev server, clear its cache directory
(`node_modules/.vite`, `.astro`, or equivalent), restart clean — before spending time
debugging code that's actually already correct.
