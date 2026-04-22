# pidup-games-site

Public-facing pages for [pidup-games](https://github.com/pidupuis/pidup-games) mobile apps, hosted via [GitHub Pages](https://pidupuis.github.io/pidup-games-site/).

This repository is included as a **git submodule** at `apps/site/` in the main pidup-games monorepo.

## Pages

### Cipher Academy

- [Privacy Policy](https://pidupuis.github.io/pidup-games-site/cipher-academy-privacy-policy.html) · [Politique de confidentialité](https://pidupuis.github.io/pidup-games-site/cipher-academy-privacy-policy.fr.html)
- [Ethical Design](https://pidupuis.github.io/pidup-games-site/cipher-academy-ethical-design.html) · [Design éthique](https://pidupuis.github.io/pidup-games-site/cipher-academy-ethical-design.fr.html)
- [Credits](https://pidupuis.github.io/pidup-games-site/cipher-academy-credits.html) · [Crédits](https://pidupuis.github.io/pidup-games-site/cipher-academy-credits.fr.html)

### Goose Academy

- [Privacy Policy](https://pidupuis.github.io/pidup-games-site/goose-academy-privacy-policy.html) · [Politique de confidentialité](https://pidupuis.github.io/pidup-games-site/goose-academy-privacy-policy.fr.html)
- [Ethical Design](https://pidupuis.github.io/pidup-games-site/goose-academy-ethical-design.html) · [Design éthique](https://pidupuis.github.io/pidup-games-site/goose-academy-ethical-design.fr.html)
- [Credits](https://pidupuis.github.io/pidup-games-site/goose-academy-credits.html) · [Crédits](https://pidupuis.github.io/pidup-games-site/goose-academy-credits.fr.html)

## How pages are generated

Pages are generated from markdown source files in the main monorepo:

```
apps/<app>/docs/en/<doc>.md  →  <app>-<doc>.html
apps/<app>/docs/fr/<doc>.md  →  <app>-<doc>.fr.html
```

To regenerate, run from the pidup-games root:

```bash
node scripts/generate-public-pages.mjs
```

## Purpose

These pages serve as publicly accessible privacy policies, ethical design statements, and credits required by app stores (Google Play, Apple App Store) and linked from within each app.
