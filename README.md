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

**Marketing pages** (`index`, `cipher-academy`, `goose-academy`) are hand-crafted HTML with a light neumorphic theme.

**Legal pages** (privacy policy, ethical design, credits) are auto-generated from `lib/i18n.ts` in each app:

```
apps/<app>/lib/i18n.ts  →  apps/<app>/docs/  (markdown)
                        →  apps/site/        (HTML)
```

To regenerate legal pages, run from the pidup-games root:

```bash
node scripts/generate-docs-from-i18n.mjs
```

## Images

Screenshots and icons are stored in `images/<app>/`. Add new screenshots there with descriptive filenames (e.g. `learn-morse.jpeg`, not `IMG_1234.jpeg`).

## Purpose

These pages serve as:

- The public marketing site for pidup games
- Privacy policies, ethical design statements, and credits required by app stores (Google Play, Apple App Store)
- Pages linked from within each app
