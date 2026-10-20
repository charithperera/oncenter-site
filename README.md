# oncenter-site

The support and privacy site for the OnCenter iOS app, at https://oncenter.charithp.com, served by Cloudflare Pages.

## Pages

- `index.html`: a short holding page with the wordmark, the blade and its ruler, three points, and "Coming soon to the App Store". The full landing page, with the screenshot gallery, comes with the App Store screenshots (build_notes Phase 14).
- `support.html`: served at `/support`, which Settings › Support opens.
- `privacy.html`: served at `/privacy`, which Settings › Privacy and the App Store listing link to.
- `styles.css`: shared by all three.

There is no `_redirects` file. Cloudflare Pages serves `/privacy` for `privacy.html` itself, and a redirect file loops (PLAYBOOK Phase 8).

## Local preview

```sh
python3 -m http.server 4000
```

Then visit http://localhost:4000. The clean URLs (`/support`) work only on Cloudflare, so open `support.html` locally.

## Deploy

1. Cloudflare Pages is connected to `github.com/charithperera/oncenter-site`, branch `main`.
2. Framework preset: None. Build command: empty. Output directory: `/`.
3. The custom domain is `oncenter.charithp.com`.
4. Every push to `main` deploys.

Email `oncenter@charithp.com` forwards through Cloudflare Email Routing.

## Look

The site follows the app's design language (`OnCenter/OnCenter/DESIGN.md`), not the other portfolio sites' cream and serif:

- **Colours:** ink `#121212` on white (dark `#F2F2F2` on `#121212`). One yellow blade band `#F7C600` holds the example answer. Red (`#D7261E` / `#FF4A3D`) is only the 16 badge and the ruler's tick.
- **Type:** Big Shoulders Display (Google Fonts) for the wordmark, the answer and page titles, and the system font for text.
- **Links:** ink and underlined, never blue.
- **The ruler:** its ticks use the app's heights (whole, half, quarter, eighth, sixteenth), drawn by a few lines of script in `index.html`.
- **Prices:** none appear anywhere on the site (consistency checklist §8). It says "one-time purchase".

Before launch, replace `.soon` in `index.html` with the App Store link.
