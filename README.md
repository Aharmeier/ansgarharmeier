# Ansgar Harmeier — Portfolio

A single-page personal portfolio for Ansgar Harmeier, a HubSpot CRM, Automation, AI & Agents consultant based in Düsseldorf, Germany.

No build step — it's a self-contained static site. Open it through a local web server (not `file://`, since the design panel is fetched at runtime).

## Features

- **Sections** — Hero, About, Skills, Experience, Education, Interests, Contact.
- **Light / dark theme** — toggled via the `data-theme` attribute on `<html>`.
- **Font switching** — three typeface sets (`grotesk`, `serif`, `plex`) via `data-font`.
- **Bilingual (EN / DE)** — text swaps through `data-i18n` / `data-i18n-html` attributes and a language toggle.
- **Live design tweaks panel** — an in-page React panel for adjusting design tokens.
- **Fillable portrait slot** — a drag-and-drop `<image-slot>` web component for the hero photo.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The full page — markup, design tokens, styles, i18n strings, and behavior. |
| `image-slot.js` | `<image-slot>` web component: a user-fillable image placeholder (drag/drop or click to browse). |
| `tweaks-panel.jsx` | Reusable design "Tweaks" panel + form-control helpers (React, loaded via Babel standalone). |

`image-slot.js` and `tweaks-panel.jsx` are scaffolding from a design prototyping runtime; the image slot and tweaks panel are fully interactive only inside that host. The portfolio itself renders and works standalone.

## Run locally

The page loads `tweaks-panel.jsx` via Babel standalone (`<script type="text/babel" src=...>`), which fetches over HTTP — so serve it rather than opening the file directly:

```bash
python3 -m http.server 8765
# then open http://localhost:8765/
```

## Dependencies

Loaded from CDNs at runtime (no install needed):

- React 18 + ReactDOM (UMD, unpkg)
- Babel standalone (to transpile the `.jsx` panel in the browser)
- Google Fonts: Schibsted Grotesk, Libre Franklin, Newsreader, Space Grotesk, IBM Plex Sans/Mono

## Contact

- Email: mail@ansgarharmeier.de
