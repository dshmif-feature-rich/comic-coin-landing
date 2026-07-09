# Comic Coin Landing Page

Static marketing site for **Comic Coin** — comic book price tracking with style.

Designed for **GitHub Pages**: no build step. Single-page layout plus a public privacy policy.

## Contents

| Path | Purpose |
|------|---------|
| `index.html` | Landing page (markup, CSS, JS) |
| `privacy.html` | Public privacy policy (store URL target) |
| `assets/icon.png` | App icon |
| `assets/hero-bg.webp` | Golden Age hero backdrop |
| `assets/screens/ios/` | iOS screenshots (search, results, history) |
| `assets/screens/android/` | Android shots (SVG placeholders until real PNGs land) |

## Local preview

```bash
cd comic-coin-landing
python3 -m http.server 8080
# open http://localhost:8080
```

Or open `index.html` directly in a browser (fonts load from Google Fonts when online).

## GitHub Pages

1. Push this repo to GitHub.
2. **Settings → Pages →** Deploy from branch `main` (or `master`), folder `/` (root).
3. Site URL will be `https://<user>.github.io/<repo>/` (or a custom domain if configured).
4. Point App Store / Play **Marketing** and **Privacy Policy** URLs here:
   - Marketing: `https://…/index.html` (or site root)
   - Privacy: `https://…/privacy.html`

## Content checklist

### Store links

In `index.html`, search for `TODO` / `data-store=` and set real URLs:

- Apple App Store
- Google Play

Remove `aria-disabled="true"`, `is-soon`, and “Coming soon” labels when live.

### Screenshots

**iOS** (already copied from `comics-flutter`):

- `assets/screens/ios/search.png`
- `assets/screens/ios/results.png`
- `assets/screens/ios/history.png`

**Android** — replace placeholders with real captures (same three screens, matching order):

- `assets/screens/android/search.png` (or keep `.svg` names and update `data-android-src` in HTML)
- `assets/screens/android/results.png`
- `assets/screens/android/history.png`

If you use `.png`, update every `data-android-src` in `index.html` from `.svg` to `.png`.

### Platform toggle

- Defaults to **iOS**
- Switch in the sticky nav swaps all `[data-screen]` images
- Choice is stored in `localStorage` under `comic-coin-platform`

### Copy notes

- Do **not** use the word “free” for the trial path
- PriceCharting is always **BYOK** (bring your own key)
- Hero “power” uses POW comic styling — one impact moment only

## Source product

App repo: [comics-flutter](https://github.com/dshmif/comics-flutter)  
Support: [issues](https://github.com/dshmif/comics-flutter/issues)
