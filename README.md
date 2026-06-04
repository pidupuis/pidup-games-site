# pidup-games-site

Marketing site and public pages for [pidup-games](https://github.com/pidupuis/pidup-games) mobile apps, hosted via [GitHub Pages](https://pidupuis.github.io/pidup-games-site/).

This repository is included as a **git submodule** at `apps/site/` in the main pidup-games monorepo.

## Site structure

```
index.html / .fr.html / .es.html     ← Studio landing page (EN / FR / ES)
cipher-academy.html / .fr / .es      ← Cipher Academy marketing page
goose-academy.html / .fr / .es       ← Goose Academy marketing page

# Legal / info pages — each generated in .html / .fr.html / .es.html:
cipher-academy-privacy-policy.*
cipher-academy-ethical-design.*
cipher-academy-credits.*
cipher-academy-scientific-references.*
cipher-academy-changelog.*           ← Cipher only (has released versions)
goose-academy-privacy-policy.*
goose-academy-ethical-design.*
goose-academy-credits.*
goose-academy-scientific-references.*
# (no goose-academy-changelog.* — hidden until Goose's first release)

images/
  cipher-academy/
    icon.png                         ← App icon
    favicon-16.png / favicon-32.png / apple-touch-icon.png
    home.jpeg … braille-touch.jpeg   ← In-app screenshots
  goose-academy/
    icon.png                         ← App icon
    favicon-16.png / favicon-32.png / apple-touch-icon.png
```

### Navigation flow

```
index.html → cipher-academy.html → cipher-academy-privacy-policy.html
                                  → cipher-academy-ethical-design.html
                                  → cipher-academy-credits.html
                                  → cipher-academy-scientific-references.html
                                  → cipher-academy-changelog.html
           → goose-academy.html  → goose-academy-privacy-policy.html
                                  → goose-academy-ethical-design.html
                                  → goose-academy-credits.html
                                  → goose-academy-scientific-references.html
```

Every page has an EN/FR/ES language toggle and back navigation.

## Pages

Each page is published in three locales: `.html` (EN), `.fr.html` (FR), `.es.html` (ES).

### Cipher Academy

- Marketing page — [EN](https://pidupuis.github.io/pidup-games-site/cipher-academy.html) · [FR](https://pidupuis.github.io/pidup-games-site/cipher-academy.fr.html) · [ES](https://pidupuis.github.io/pidup-games-site/cipher-academy.es.html)
- Privacy Policy — [EN](https://pidupuis.github.io/pidup-games-site/cipher-academy-privacy-policy.html) · [FR](https://pidupuis.github.io/pidup-games-site/cipher-academy-privacy-policy.fr.html) · [ES](https://pidupuis.github.io/pidup-games-site/cipher-academy-privacy-policy.es.html)
- Ethical Design — [EN](https://pidupuis.github.io/pidup-games-site/cipher-academy-ethical-design.html) · [FR](https://pidupuis.github.io/pidup-games-site/cipher-academy-ethical-design.fr.html) · [ES](https://pidupuis.github.io/pidup-games-site/cipher-academy-ethical-design.es.html)
- Credits — [EN](https://pidupuis.github.io/pidup-games-site/cipher-academy-credits.html) · [FR](https://pidupuis.github.io/pidup-games-site/cipher-academy-credits.fr.html) · [ES](https://pidupuis.github.io/pidup-games-site/cipher-academy-credits.es.html)
- Scientific References — [EN](https://pidupuis.github.io/pidup-games-site/cipher-academy-scientific-references.html) · [FR](https://pidupuis.github.io/pidup-games-site/cipher-academy-scientific-references.fr.html) · [ES](https://pidupuis.github.io/pidup-games-site/cipher-academy-scientific-references.es.html)
- What's New — [EN](https://pidupuis.github.io/pidup-games-site/cipher-academy-changelog.html) · [FR](https://pidupuis.github.io/pidup-games-site/cipher-academy-changelog.fr.html) · [ES](https://pidupuis.github.io/pidup-games-site/cipher-academy-changelog.es.html)

### Goose Academy

- Marketing page — [EN](https://pidupuis.github.io/pidup-games-site/goose-academy.html) · [FR](https://pidupuis.github.io/pidup-games-site/goose-academy.fr.html) · [ES](https://pidupuis.github.io/pidup-games-site/goose-academy.es.html)
- Privacy Policy — [EN](https://pidupuis.github.io/pidup-games-site/goose-academy-privacy-policy.html) · [FR](https://pidupuis.github.io/pidup-games-site/goose-academy-privacy-policy.fr.html) · [ES](https://pidupuis.github.io/pidup-games-site/goose-academy-privacy-policy.es.html)
- Ethical Design — [EN](https://pidupuis.github.io/pidup-games-site/goose-academy-ethical-design.html) · [FR](https://pidupuis.github.io/pidup-games-site/goose-academy-ethical-design.fr.html) · [ES](https://pidupuis.github.io/pidup-games-site/goose-academy-ethical-design.es.html)
- Credits — [EN](https://pidupuis.github.io/pidup-games-site/goose-academy-credits.html) · [FR](https://pidupuis.github.io/pidup-games-site/goose-academy-credits.fr.html) · [ES](https://pidupuis.github.io/pidup-games-site/goose-academy-credits.es.html)
- Scientific References — [EN](https://pidupuis.github.io/pidup-games-site/goose-academy-scientific-references.html) · [FR](https://pidupuis.github.io/pidup-games-site/goose-academy-scientific-references.fr.html) · [ES](https://pidupuis.github.io/pidup-games-site/goose-academy-scientific-references.es.html)

_(Goose Academy has no “What's New” page yet — it stays hidden until the first release.)_

## How pages are generated

**Home page** (`index.html`, `index.fr.html`, `index.es.html`) is hand-crafted and **not** regenerated by the build. It is a plain white background with a centered `<h1>pidup games</h1>` wordmark and a two-card layout — one card per app. Each card sits inside its app's **stage** panel: `stage-cipher` is **fantôme** (`#E6EAF5`), `stage-goose` is **graphite** (`#343434`). The cards stack in a flex **column** below `640px` and switch to a **row** at `640px` and up. The lang toggle sits top-right. Favicons, social/canonical/hreflang metadata, and a `WebSite` JSON-LD block live in each page's `<head>`.

There is no split background, no `linear-gradient` band, and no two-tone wordmark — the `<h1>` is a single graphite wordmark.

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
