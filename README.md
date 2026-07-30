# Natural State Medicinals — Education Guide (web build)

Static site. No build step, no dependencies, no server code. GitHub Pages serves
these files as-is.

## Deploying with GitHub Desktop

1. Copy **everything inside this folder** into the root of your repo
   (`Natural-State-Education-Guide`), replacing what is there.
2. GitHub Desktop will list the changes. Commit, then Push.
3. Pages redeploys in a minute or two.

If your repo currently holds a single large `index.html` (the inlined
standalone), delete it first — this replaces it.

## What each file is

| Path | Purpose |
| --- | --- |
| `index.html` | Router. Sends phones to `mobile.html`, everything else to `desktop.html`. |
| `desktop.html` | The full guide. |
| `mobile.html` | The mobile guide. |
| `support.js` | Runtime both guides need. Do not edit. |
| `guide-data.js` | All strain, product, terpene, recipe and glossary data. Shared by both guides. |
| `fonts-local.css` | Font declarations. |
| `assets/` | Photography and brand marks. |
| `_ds/overbuilt-design-system-3b59…/` | Design tokens, the four licensed `.otf` fonts, and the component bundle. |

**Keep the folder structure exactly as it is.** All references are relative, and
`fonts-local.css` points into that long `_ds/…/fonts/` path. Renaming or
flattening it silently drops the brand fonts back to fallbacks.

## Forcing a version

- `index.html?v=desktop` — always the full guide
- `index.html?v=mobile` — always the mobile guide

The choice is remembered for that browser session. The cut-off is `MOBILE_MAX`
(760px) near the top of `index.html`; change that one number to move it.

Deep links survive the redirect, so `index.html#strain/dogtown` lands on the
right strain in whichever version the visitor gets.

## Editing content later

Copy and data changes live in `guide-data.js` and the two HTML files. Because
these are small text files, future commits are a few KB rather than the ~29MB
that the single inlined file cost every time.

For Questions, Call Dedman. 
