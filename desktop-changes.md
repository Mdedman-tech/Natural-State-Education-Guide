# Desktop changes — exact copy

Eight edits for `desktop.html`. Data is already handled by the new `guide-data.js`.

---

## 1. Dark-mode hardening

Add to `<head>`:

```html
<meta name="color-scheme" content="light only">
<meta name="supported-color-schemes" content="light">
<meta name="theme-color" content="#20253A">
```

In the style block:

```css
html { forced-color-adjust: none; }

@media (prefers-color-scheme: dark) {
  :root {
    --ns-arctic: #F5F4E1 !important;
    --ns-midnight: #20253A !important;
    --ns-bronze: #B79550 !important;
    --ns-cream: #F6E7D7 !important;
    --ns-haze: #EFD7C5 !important;
  }
}
```

The metas alone do not stop Android from re-tinting. The `!important` block is the part that
actually holds.

---

## 2. Footer

Remove the inline flex row (~line 2483) reading:

> Natural State Medicinals · Permit No. 00088 · Est. 2018 · Pine Bluff / White Hall, AR

Then, after "…prevent any disease." insert:

> "DO NOT EAT" also, I guess.

Full disclaimer reads:

> For use by qualified patients only. Keep out of reach of children. Marijuana is not approved
> by the FDA to treat, cure, or prevent any disease. "DO NOT EAT" also, I guess. This guide is
> education, not medical advice.

---

## 3. Amendment citation

Amendment 89 is Arkansas's usury / interest-rate amendment. It has nothing to do with
cannabis, so the citation is simply wrong.

Section label → **The amendment** (singular).
Disclosure label → **On the amendment & home grow**.

Replace the body with:

> Amendment 98 created the Arkansas medical program in 2016, and the rules written under it
> govern how the program runs day to day. One of those rules is worth knowing plainly: your
> medicine is registered to you. Passing it along, sharing it, or selling it to anyone else,
> patient or not, falls outside the program and puts your card at risk. When in doubt, confirm
> with your dispensary or the state program.

---

## 4. Home-grow note

Remove "Strictly hypothetical." Replace the whole passage with:

> Arkansas law does not permit qualified patients to grow at home, so nothing here should be
> read as encouragement. We would only note, as a matter of general literary awareness, that
> books like The Cannabis Grow Bible (Greg Green), Marijuana Horticulture (Jorge Cervantes),
> and the Cannabis Grower's Handbook (Rosenthal & Downs) exist, are widely available, and are
> said to be very thorough. Know your state law.

---

## 5. Joint Journal certificate

Remove the line:

> Natural State Medicinals · Permit No. 00088

---

## 6. Hero CTA

> Skip the theory, meet the flower

---

## 7. Duration bar

In the dosing / onset section, the fill is a near-invisible white gradient. Replace with:

```css
background: linear-gradient(90deg, #cdb074, rgba(183,149,80,0.45));
```

---

## 8. Laozi quote

Remove the flower logo image above the quote. The quote and attribution stay as they are.

---

## Typography rule, for reference

Esther (`--font-serif`) is accents only: philosopher quotes, strain "Best used for", and song
pairings. Reading copy and strain descriptions use the sans (Work Sans stack). Esther reads
poorly at length.

## Song pairings

Easter eggs, discovered inside an expanded strain card only. Never on collapsed rows, in
filters, or as a playlist feature.
