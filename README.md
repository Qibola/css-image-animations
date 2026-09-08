# css-image-animations

Animating still images with pure CSS `@keyframes` — no JavaScript, no image files.

Every "image" in this project is an inline **SVG data URI**, so the repo stays
text-only and each card is easy to read and tweak in the browser dev tools.

## Run it

Open `index.html` in any browser. That's it — there is no build step and no
dependencies.

```bash
# macOS
open index.html
```

## Files

| File | What it does |
| --- | --- |
| `index.html` | The gallery markup: one `<figure>` card per animation demo |
| `style.css` | Layout, the card styling, and (later) all the `@keyframes` |
| `README.md` | This file |

## Roadmap

- [x] Day 1 — Scaffold: `index.html`, `style.css`, README, SVG data-URI artwork
- [x] Day 2 — Fade-in `@keyframes`
- [ ] Day 3 — Slide / `translate` animation
- [ ] Day 4 — Rotate / `scale` animation
- [ ] Day 5 — Hover-triggered animation
- [ ] Day 6 — Gallery layout + polish

## Notes

- The artwork is a small SVG (a sun over hills) encoded as a `url("data:image/svg+xml,...")`
  background. Because it is text, it diffs cleanly in git.
- Animations are added one per day, each in its own clearly-labelled block in
  `style.css`, so the commits stay small and readable.
- Each animation is opt-in via a modifier class (e.g. `.art--fade-in`) on the
  `.art` element, so cards can mix and match effects without touching the base
  styles.
- `animation-fill-mode: both` is what keeps the fade from flashing: it applies
  the `from` frame during the delay and holds the `to` frame afterwards.
- Every animation is disabled under `@media (prefers-reduced-motion: reduce)`.
