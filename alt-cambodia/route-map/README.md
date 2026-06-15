# Vietnam + Cambodia Route Map (alternative plan)

Interactive map of the 17-day alternative route (Hanoi → Ninh Binh → Lan Ha → ✈ Phnom Penh → Koh Rong Sanloem → Kampot → Kep → Ha Tien border → Mekong Delta → Saigon). Each stop is clickable and shows the transport leg — travel means, duration, and booking links.

## What it is
A single, self-contained `index.html`. All CSS and JavaScript are inline; there is **no build step, no dependencies, and no external assets**. The only outbound links are the booking sites on each stop card, so it can be served by any static host as-is.

## How it works
- `VN` / `KH` — schematic Vietnam and Cambodia landmass outlines (lng/lat), drawn as filled SVG paths via a shared `P()` projection.
- `STOPS` — array of stops (coordinates, dates, transport leg, highlights).
- `LEGS` — connections between stops, colour-coded by transport mode (`road`, `boat`, `flight`, `border`).
- Clicking a node renders that stop's detail card; the Saigon card also shows the international fly-out.

To edit the route, change the `STOPS` / `LEGS` arrays near the bottom of `index.html`. To adjust the map frame, change `LNG0/LNG1/LAT0/LAT1` and `W/H`.

## Differences vs. the original Vietnam map
- Adds a **Cambodia** landmass and four southern stops (Phnom Penh, Koh Rong Sanloem, Kampot, Kep).
- New leg types: an **internal flight** Hanoi → Phnom Penh and a **land border crossing** at Ha Tien.
- Central-Vietnam stops (Phong Nha, Hue, Hoi An) are removed; the open-jaw HAN-in / SGN-out framing is kept.

## Serve it locally
```bash
cd route-map
python3 -m http.server 8000
# open http://localhost:8000
```
It is a plain static page — drop the folder on any static host (e.g. GitHub Pages) with no extra configuration.
