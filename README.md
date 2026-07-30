# Repo update — July 30 2026

Matches your existing layout. Copy these over your repo root; they overwrite in place.

**`index.html` and `desktop.html` are deliberately NOT in this package** — nothing here
touches your landing page or the desktop build.

| File | Action |
|---|---|
| `mobile.html` | overwrite — current mobile guide |
| `guide-data.js` | overwrite — **shared by both guides**, see below |
| `fonts-local.css` | overwrite — points at `assets/fonts/` |
| `support.js` | overwrite — runtime |
| `assets/` | merge — includes `assets/fonts/` (four OTFs) and new brand marks |

`_ds/` paths are left intact. Your `.nojekyll` already stops Pages from stripping
underscore folders, so no rename is needed.

---

## What changed

### `guide-data.js` — brand-rule violation removed (affects desktop too)

This file is read by both guides, so overwriting it fixes desktop's data at the same time.

- Removed the journal field `"Batch Number / COA Reference"`. It was on by default, so it
  landed in every patient's copied and downloaded journal template.
- Removed `recentCoaDate` and `coaCount` — 102 fields across 51 strains, all carrying dates.
- Removed the `coas` array — 53 entries of batch IDs with test dates.

Nothing rendered these, but they were one binding away from resurfacing, and the rule is
absolute: no test dates or batch identifiers anywhere, since this is not a living document.

Left alone on purpose: the glossary definitions of "Batch Number" and "Certificate of
Analysis (COA)". Those are educational prose, which the rule allows — only dates and real
identifiers are banned.

Also corrected: Amnesia Fast now carries `24.4% – 30.5%` (previously had no THC fields).

### `mobile.html`

- Amendment citation fixed. Amendment 89 is Arkansas's usury / interest-rate amendment and
  has nothing to do with cannabis. Replaced with Amendment 98 copy under a retitled singular
  "The amendment".
- Carries everything from today's earlier passes (dark-mode hardening, footer edits, hero CTA,
  duration-bar color, extraction bars, recipe index and sheet, journal certificate).

---

## Desktop still needs eight hand edits

Overwriting `guide-data.js` fixes desktop's **data**, but not its markup. Desktop's HTML has
diverged from mobile enough that find-and-replace does not match — of six changes I tried
mechanically, only one anchor hit.

Outstanding on `desktop.html`:

1. **Dark-mode hardening** — no `color-scheme` meta at all; Android renders the cream
   surfaces brown-olive. Needs the three metas, `forced-color-adjust: none`, and a
   `@media (prefers-color-scheme: dark)` block re-asserting the five palette vars with
   `!important`. The metas alone are not enough.
2. **Footer** — permit line is an inline flex row (~line 2483), not mobile's paragraph.
   Remove it; add `"DO NOT EAT" also, I guess.` after "…prevent any disease."
3. **Amendment citation** — same factual error as mobile had.
4. **Home-grow note** — drop "Strictly hypothetical."
5. **Joint Journal** — remove the NSM / Permit 00088 line.
6. **Hero CTA** — `Skip the theory, meet the flower`
7. **Duration bar** — recolor to `linear-gradient(90deg, #cdb074, rgba(183,149,80,0.45))`
8. **Laozi quote** — remove the flower logo above it.

Exact replacement copy for each is in `desktop-changes.md`.

> Faster option: open the desktop project in Claude and I can make all eight directly in the
> file, the way they were made for mobile.

---

## Do not port to desktop

Small-viewport solutions desktop does not need: recipe index + full-screen sheet, extraction
mini-bars, wayfinder dot rail, per-step `object-position` crops, the A/A text-size control.

---

## Still open on both

Chapters 09–12 carry no photography, so the last third reads drier than the first. Art
direction, not code — needs photo picks.
