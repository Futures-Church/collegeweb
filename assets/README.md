# Brand assets to drop in

The site works right now without these — but it's using fallbacks. Drop these
files in and it becomes fully on-brand. Filenames must match exactly.

## 1. Logos (`assets/`)

From Google Drive → **BRANDING / LOGOS**

| Save as                          | Use it for                                        | Which Drive file |
|----------------------------------|---------------------------------------------------|------------------|
| `assets/futures-logo-white.png`  | Header nav (sits on the dark violet hero)         | `Futures1white.png` (or whichever white lockup you prefer) |
| `assets/futures-logo.png`        | Footer (sits on the Laser Lemon panel)            | `Futures1.png` (the colour/dark version) |

Until they exist, the header and footer fall back to the words "FUTURES /
CHURCH" set in the brand sans. That's a **type-set placeholder, not a redrawn
logo** — Brand Guidelines V1.0 §02 says the logo must never be redrawn, so the
real PNG is the only thing that should ship publicly. The fallback disappears
automatically the moment the file is in place.

Horizontal lockups work best in the header. If you use a vertical lockup,
reduce `.brand img { height }` in `index.html`.

## 2. Typefaces (`assets/fonts/`)

From Google Drive → **BRANDING / FONTS**

```
assets/fonts/GalGothic-Regular.otf
assets/fonts/GalGothic-Light.otf
assets/fonts/GalGothic-Italic.otf
assets/fonts/Rhymes Display Light.ttf
assets/fonts/Rhymes Display Light Italic.ttf
```

The page already declares these via `@font-face`, and tries `local()` first so
it picks them up automatically if they're installed on the viewer's machine.

**Licensing worth checking before you publish:** the Drive files are desktop
OTF/TTF. Serving them from a web server is a separate *webfont* licence with
Maxitype (rhymes → https://maxitype.com/typeface/rhymes/). Until that's sorted,
the page falls back to **Times New Roman** and **Arial** — which are the free
alternatives the Brand Guidelines themselves nominate (§04), so it stays
compliant either way.

## Colour palette in use

All from Brand Guidelines V1.0 §03, as CSS custom properties in `index.html`:

| Token       | Hex       | Role on this page |
|-------------|-----------|-------------------|
| Electric Violet | `#5d1fec` | Primary brand surface, hero, headings |
| Laser Lemon | `#ffff5f` | Primary CTA, highlights, footer, pull-quote |
| Orange      | `#ff8432` | Section labels, timeline markers |
| Sky Blue    | `#62b4ff` | Numbered list, "runway" callout, pillar 1 |
| Pink        | `#e444b9` | Hero glow, pillar 4 |
| Copper      | `#c45236` | Subheads, figures |

Two-colour pairings throughout, per §03 "Colour Combinations".
