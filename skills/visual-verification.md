# Visual Verification

> Never call visual or layout work done unless you've actually looked at it rendered.

---

## When to Use

Any time you change CSS, layout, a component's markup, an animation, or anything else that
affects what a page or screen looks like — before telling Nigel it's done.

---

## Agent Behaviour

1. **Screenshot it.** Use a real browser (headless Chrome via the DevTools Protocol, a
   Playwright/Puppeteer script, whatever the project already has) against a running dev or
   preview server. Read the resulting image before reporting the change as finished.
2. **Check more than one width.** At minimum a desktop width and a narrow mobile width
   (~375px). Layout bugs hide at the width you didn't check.
3. **Zoom in on the specific thing you changed** if it's small or subtle (an icon, a border,
   spacing) — a full-page screenshot at normal scale can miss exactly the defect you're
   trying to confirm is fixed.
4. **Re-screenshot after every real fix**, not just the first attempt. A plausible-looking
   diff is not the same as a correct render — confirm the specific defect is actually gone.

---

## Known Gotchas (worth remembering across projects)

- **Headless Chrome `--window-size` doesn't reliably constrain narrow layouts.** Requesting
  a small width (e.g. 375px) can still lay the page out at a larger effective width (Chrome
  enforces some minimum), silently invalidating a "mobile" screenshot — the output image
  looks cropped rather than actually narrow. Force the layout viewport independently via the
  DevTools Protocol's `Emulation.setDeviceMetricsOverride`, not just the launch flag.
- **If a change doesn't seem to take effect despite the source file being correct**, suspect
  a stale dev-server module cache (Vite and similar) before suspecting the code. Verify what
  computed style/markup is actually being served, and if it's stale, clear the cache
  (`node_modules/.vite`, `.astro`, or equivalent) and restart clean before debugging further.
- **A cropped screenshot can look identical to a real overflow bug.** If something looks like
  it's clipping, verify the actual rendered width/viewport before assuming the CSS is wrong.

---

## Quality Bar

- Did you actually read the screenshot, or just assume the CSS change would work?
- Did you check the width where the bug was originally reported, specifically?
- If the fix didn't visibly change anything, did you notice that, or did you move on anyway?

---

## Anti-Patterns

- Declaring a visual fix done based on reading the CSS alone.
- Screenshotting once at one width and calling it verified everywhere.
- Assuming a second attempt worked without re-checking, because the code "should" work now.
