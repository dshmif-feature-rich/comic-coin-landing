# Comic Coin Landing Page

Static marketing site for **Comic Coin** — comic book price tracking with style.

Designed for **GitHub Pages**: no build step. Single-page layout plus a public privacy policy.

## Contents

| Path | Purpose |
|------|---------|
| `index.html` | Landing page (markup, CSS, JS) |
| `privacy.html` | Public privacy policy (store URL target) |
| `assets/comic-coin-icon.png` | App icon |
| `assets/hero-bg.webp` | Golden Age hero backdrop |
| `assets/screens/ios/light/` · `…/dark/` | iOS screenshots (search, results, history) |
| `assets/screens/android/light/` · `…/dark/` | Android shots (SVG placeholders until real PNGs land) |

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

**iOS** (light + dark, from `comics-flutter`):

- `assets/screens/ios/light/{search,results,history}.png`
- `assets/screens/ios/dark/{search,results,history}.png`

**Android** — replace placeholders with real captures (same three screens × light/dark):

- `assets/screens/android/light/{search,results,history}.svg` (placeholders)
- `assets/screens/android/dark/{search,results,history}.svg` (placeholders)

If you use `.png`, update every `data-android-light` / `data-android-dark` path in `index.html`.

### Preview toggles

- **Platform:** defaults to **iOS** (`localStorage`: `comic-coin-platform`)
- **Theme:** defaults to **Light** (`localStorage`: `comic-coin-theme`) — swaps **app screenshots only**, not site styling
- Both nav switches combine: all `[data-screen]` images use `data-{ios|android}-{light|dark}`

### Copy notes

- Do **not** use the word “free” for the trial path
- PriceCharting is always **BYOK** (bring your own key)
- Hero “power” uses POW comic styling — one impact moment only

## Source product

App repo: [comics-flutter](https://github.com/dshmif/comics-flutter)  
Support: [issues](https://github.com/dshmif/comics-flutter/issues)
