# Diploma of Church Planting Leadership — interest site

Single-page scrolling site for the Diploma of Church Planting Leadership,
built to the Futures Church Brand Guidelines V1.0 and accredited/delivered by
Alphacrucis University College.

**Primary call to action:** every "Register your interest" button opens the
visitor's mail client to `david.begley@futures.church` with a pre-filled
subject and an enquiry template (name, church, role, location, phone, context).

## Structure

```
index.html                 entire site — inline CSS + JS, no dependencies, no build
netlify.toml               publish settings + cache headers
assets/
  futures-logo-white.png       horizontal lockup, white  (nav)
  futures-logo.png             horizontal lockup, colour (footer)
  futures-logo-stacked-white.png  vertical lockup (spare)
  fonts/                   Gal Gothic + Rhymes Display
  photos/                  optimised photography
  README.md                where each brand asset came from
```

## Local preview

No build step. Either open `index.html` directly, or:

```bash
python3 -m http.server 4400
```

## Deploying to Netlify

Connect the repo and accept the defaults — `netlify.toml` sets `publish = "."`
with no build command. All asset paths are relative, so it works from any
domain or deploy preview without changes.

## Photography

Photos live in `assets/photos/`, resized to a 1800–2400px long edge at ~70%
JPEG quality (each 200–740KB, down from 3–11MB originals). Every `<img>` has
explicit `width`/`height` to prevent layout shift, and everything below the
fold is `loading="lazy"`.

These are photographs of identifiable people. Confirm usage consent before the
site goes public, and keep this repository **private** unless that has been
cleared.

## Fonts

Gal Gothic and Rhymes Display are licensed typefaces, self-hosted from
`assets/fonts/`. The files in this repo are the desktop OTF/TTF releases —
**serving them from a public web server needs a separate webfont licence from
Maxitype** (https://maxitype.com/typeface/rhymes/). Until that is in place the
page falls back to Times New Roman and Arial, which are the free alternatives
nominated in Brand Guidelines V1.0 §04.

## Accessibility / performance notes

- Reveal animations are rect-based on a single rAF loop, so content can never
  be stranded invisible if an observer misfires.
- `prefers-reduced-motion` disables all animation, drift and parallax.
- Scrim over the hero photograph keeps headline contrast above 4.5:1.
