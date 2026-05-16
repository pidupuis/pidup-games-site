# pidup-games-site

Marketing site and public pages for [pidup-games](https://github.com/pidupuis/pidup-games) mobile apps, hosted via [GitHub Pages](https://pidupuis.github.io/pidup-games-site/).

This repository is included as a **git submodule** at `apps/site/` in the main pidup-games monorepo.

## Site structure

```
index.html / index.fr.html          ← Studio landing page (EN / FR)
cipher-academy.html / .fr.html      ← Cipher Academy marketing page
goose-academy.html / .fr.html       ← Goose Academy placeholder
cipher-academy-*.html                ← Legal pages (privacy, ethics, credits)
goose-academy-*.html                 ← Legal pages (privacy, ethics, credits)
images/
  cipher-academy/
    icon.png                         ← App icon
    home.jpeg                        ← Screenshot: home screen
    levels-morse.jpeg                ← Screenshot: level selector
    learn-morse.jpeg                 ← Screenshot: learning Morse
    learn-braille.jpeg               ← Screenshot: learning Braille
    learn-pigpen.jpeg                ← Screenshot: learning Pigpen
    play-modes.jpeg                  ← Screenshot: play game modes
    decode-words.jpeg                ← Screenshot: Decode Words game
    find-the-symbol.jpeg             ← Screenshot: Find the Symbol game
    morse-tap.jpeg                   ← Screenshot: Morse Tap game
    braille-touch.jpeg               ← Screenshot: Braille Touch game
```

### Navigation flow

```
index.html → cipher-academy.html → cipher-academy-privacy-policy.html
                                  → cipher-academy-ethical-design.html
                                  → cipher-academy-credits.html
           → goose-academy.html  → goose-academy-privacy-policy.html
                                  → ...
```

Every page has a FR/EN language toggle and back navigation.

## Pages

### Cipher Academy

- [Marketing page](https://pidupuis.github.io/pidup-games-site/cipher-academy.html) · [Page marketing](https://pidupuis.github.io/pidup-games-site/cipher-academy.fr.html)
- [Privacy Policy](https://pidupuis.github.io/pidup-games-site/cipher-academy-privacy-policy.html) · [Politique de confidentialité](https://pidupuis.github.io/pidup-games-site/cipher-academy-privacy-policy.fr.html)
- [Ethical Design](https://pidupuis.github.io/pidup-games-site/cipher-academy-ethical-design.html) · [Design éthique](https://pidupuis.github.io/pidup-games-site/cipher-academy-ethical-design.fr.html)
- [Credits](https://pidupuis.github.io/pidup-games-site/cipher-academy-credits.html) · [Crédits](https://pidupuis.github.io/pidup-games-site/cipher-academy-credits.fr.html)

### Goose Academy

- [Placeholder page](https://pidupuis.github.io/pidup-games-site/goose-academy.html) · [Page provisoire](https://pidupuis.github.io/pidup-games-site/goose-academy.fr.html)
- [Privacy Policy](https://pidupuis.github.io/pidup-games-site/goose-academy-privacy-policy.html) · [Politique de confidentialité](https://pidupuis.github.io/pidup-games-site/goose-academy-privacy-policy.fr.html)
- [Ethical Design](https://pidupuis.github.io/pidup-games-site/goose-academy-ethical-design.html) · [Design éthique](https://pidupuis.github.io/pidup-games-site/goose-academy-ethical-design.fr.html)
- [Credits](https://pidupuis.github.io/pidup-games-site/goose-academy-credits.html) · [Crédits](https://pidupuis.github.io/pidup-games-site/goose-academy-credits.fr.html)

## How pages are generated

**Home page** (`index.html`, `index.fr.html`, `index.es.html`) is hand-crafted and uses a **split background**: the left half is **fantome** (`#E6EAF5`) for Cipher Academy, the right half is **graphite** (`#343434`) for Goose Academy, joined by a tight ~5% horizontal `linear-gradient` band centered on the split. On narrow screens (`max-width: 700px`) the layout stacks vertically and the gradient flips to top-to-bottom (Cipher on top).

The "pidup games" wordmark sits across the gradient with each half rendered in the **opposite** background's color ("pidup" graphite on fantome, "games" fantome on graphite). The lang toggle stays entirely on the Cipher (fantome) side in indigo.

Each side's card matches its app's in-app neuromorphic style:

- **Cipher** card: **convex** fantome pillow (outer light/dark shadows) — indigo accent `#3228D0`.
- **Goose** card: **concave** graphite well (inset shadows) — corail accent `#FF5151`.

**App hub pages** (`cipher-academy[.locale].html`, `goose-academy[.locale].html`) are generated from templates in `_templates/` by [scripts/generate-docs-from-i18n.mjs](../../scripts/generate-docs-from-i18n.mjs). Cipher uses the fantome/indigo theme; Goose uses the graphite/corail theme.

**Legal & info pages** (privacy policy, ethical design, credits, scientific references, changelog) are auto-generated from `lib/i18n/` in each app:

```
apps/<app>/lib/i18n/  →  apps/<app>/docs/  (markdown)
                      →  apps/site/        (HTML, per-app theme)
```

Per-app sub-page themes are defined by the `APP_THEME` map in [scripts/generate-docs-from-i18n.mjs](../../scripts/generate-docs-from-i18n.mjs) (only tokens that differ between apps are tracked there; everything else is shared template).

To regenerate everything, run from the pidup-games root:

```bash
node scripts/generate-docs-from-i18n.mjs
node scripts/validate-docs-sync.mjs   # check i18n + structure parity
```

## Images

Screenshots and icons are stored in `images/<app>/`. Add new screenshots there with descriptive filenames (e.g. `learn-morse.jpeg`, not `IMG_1234.jpeg`).

## Purpose

These pages serve as:

- The public marketing site for pidup games
- Privacy policies, ethical design statements, and credits required by app stores (Google Play)
- Pages linked from within each app
