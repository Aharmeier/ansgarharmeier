# CLAUDE.md — ansgarharmeier

Personal portfolio site for Ansgar Harmeier (HubSpot CRM / Automation / AI & Agents consultant, Düsseldorf).

- **Live:** https://ansgarharmeier.vercel.app · **Repo:** https://github.com/Aharmeier/ansgarharmeier · **Vercel scope:** `ansgarhs-projects`
- **Stack:** plain static site — no framework, no build step. React 18 + Babel standalone are loaded from CDNs only for the in-page design tweaks panel.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The whole site — markup, design tokens, CSS, EN/DE i18n strings, and behavior (theme/font/lang toggles). |
| `image-slot.js` | `<image-slot>` web component (design-runtime scaffold). No longer used by the hero. |
| `tweaks-panel.jsx` | Reusable design "Tweaks" panel (React via Babel standalone). Fully interactive only inside its design-runtime host. |
| `portrait.jpg` | Hero portrait photo, rendered via a plain `<img class="portrait-photo">` with `object-fit: cover`. |

## Working notes

- **Run locally:** `python3 -m http.server 8765` → http://localhost:8765/ . Don't open via `file://` — Babel fetches `tweaks-panel.jsx` over HTTP.
- **Deploy:** `vercel --prod` from this dir (project is linked; scope `ansgarhs-projects`). Deploys upload local files directly — not yet wired to auto-deploy from GitHub.
- `image-slot.js` / `tweaks-panel.jsx` carry `@ds-adherence-ignore` headers from the prototyping runtime; raw hex/px in those files is by design.
