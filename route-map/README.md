# Vietnam Route Map

Interactive map of the 17-day Vietnam route (Hanoi → Ninh Binh → Lan Ha → Phong Nha → Hue → Hoi An → Saigon → Mekong). Each stop is clickable and shows the transport leg — travel means, duration, and booking links.

## What it is

A single, self-contained `index.html`. All CSS and JavaScript are inline; there are **no build step, no dependencies, and no external assets**. The only outbound links are the booking sites referenced on each stop card. This means it can be served by any static host as-is.

## How it works

- `STOPS` — array of stops (coordinates, dates, transport leg, highlights).
- `LEGS` — connections between stops, color-coded by transport mode.
- The map outline and nodes are drawn as inline SVG; clicking a node renders that stop's detail card.

To edit the route, change the `STOPS` / `LEGS` arrays near the bottom of `index.html`.

## Serve it locally

```bash
cd route-map
python3 -m http.server 8000
# open http://localhost:8000
```

## Serve it on GitHub Pages

Commit this folder to the repo, then in **Settings → Pages** pick one of:

- **Source: `main` branch, `/root`** — and move/rename this file to `index.html` at the repo root, served at `https://<user>.github.io/<repo>/`.
- **Source: `main` branch, `/docs`** — rename this folder to `docs/`, served at the same root URL.
- **Keep as `route-map/`** — served at `https://<user>.github.io/<repo>/route-map/`.

No other configuration is needed; it is a plain static page.
