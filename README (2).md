# Pacific Hazard Console

Live, self-contained tools that pull public feeds into one honest view of the Pacific — a **Wind & Water** weather/marine forecast running alongside an **Earth & Fire** seismic, volcanic, and tsunami hazard track.

No build step, no API keys, no backend. Each page is a single HTML file that fetches live data directly in the browser. Open `index.html` to start.

> **What this is — and isn't.** These pages *display and forecast* conditions; they are **not** an authoritative warning service. For any safety decision the official sources are the truth: NWS / NHC (US), JMA 気象庁 (Japan), and the Pacific Tsunami Warning Center. This console is how you *notice* something and go look.

## Pages

- **`index.html`** — Landing page linking the three tools, with data-source credits.
- **`ring-of-fire-map.html`** — Pacific-centered Leaflet map. Live USGS seismicity (global M4.5+, full US detail to M2.5+), JMA 防災 Japan quakes (with 震度 intensity), 57 active Ring-of-Fire volcanoes including Mt. Fuji, the NDBC/NOWPHAS buoy network, offshore oil platforms + the Coal Oil Point natural seep, a lat/lon graticule, the International Date Line, live ADS-B aircraft, and a Hisayama (久山町) 防災 forecast marker. Toggleable layers.
- **`pacific-hazard.html`** — The actual weather forecast for Hawaii, S. California, Kyushu & Honshu. Transparent risk score from pressure, wind, the vertical air column (CAPE / inversion / shear), marine waves & swell, tides, and moon phase (spring/neap → coastal-flooding flag). Plus a global geomagnetic Kp gauge and a recent-major-quakes strip. Includes a per-feed diagnostics panel.
- **`coastal-chart-plot.html`** — Nautical-style lat/lon chart plot of 41 buoys across the Pacific coasts, colored by **live significant wave height**. Overview + regional tabs (Hawaiʻi / S. California / Japan·Okinawa / Guam·Marianas) and a live cursor coordinate readout.

## Data sources

| Feed | Source |
|---|---|
| Earthquakes (global + US detail) | USGS Earthquake Hazards Program |
| Japan earthquakes / forecast (防災) | JMA 気象庁 — via P2P地震情報 and JMA *bosai* JSON |
| Weather + marine forecast | Open-Meteo |
| Tide predictions (US) | NOAA CO-OPS Tides & Currents |
| Buoy network | NOAA NDBC (US) · NOWPHAS/JMA (Japan, approximate) |
| Geomagnetic Kp | NOAA SWPC |
| Volcano alert levels (US) | USGS Volcano Hazards (HANS) |
| Offshore platforms | BOEM / BSEE (Pacific OCS) |
| Live aircraft | airplanes.live (ADS-B) |
| Basemap tiles | OpenStreetMap · CARTO |

## How it reads

- **Wind & Water** — pressure, wind, the air column, swell, tides, and moon legitimately combine into a forecast. This is the predictive part.
- **Earth & Fire** — quakes, volcanoes, and geomagnetic activity are a **separate** hazard track. A large undersea quake is a real tsunami precursor, but none of these predict weather, so they never feed the forecast.
- **Context** — aircraft, buoy positions, platforms, and islands show *where*, not *what's coming*.

## Hosting

Drop all the files into a GitHub Pages repo (or any static host) and open over **https** — the live feeds require it. Hawaii volcanoes are drawn as a hotspot (not subduction); the Ring-of-Fire outline and International Date Line are schematic; and Japan/Okinawa buoy positions and the California platform positions are approximate (authoritative coordinates: NDBC, NOWPHAS, BOEM/BSEE).

## Notes

Built as a personal situational-awareness aid. All data is fetched client-side and credited to the sources above; nothing is stored. Respect each provider's terms and rate limits.
