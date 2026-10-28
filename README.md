<p align="center"><img src="logo.svg" alt="बसaarah logo" width="300"></p>

# बसaarah

**बसaarah** (Smart College Bus Tracking and Availability System) is a map-first bus tracking web app for **ARKA JAIN University (AJU), Jamshedpur** students — built to answer one question at any bus stop: *has my bus already passed, or is it still coming?*

Open the site in the morning and you see your bus moving live on a real street map towards your stop, when it will arrive, how many buses have already passed your stop, how many are still to come, and whether it is better to keep waiting or go another way.

## What it does

- **Live map (Leaflet + OpenStreetMap)** — your stop, every bus coming to it, and the selected route drawn along real roads
- **"Your earliest bus"** — across all routes serving your stop: bus number, route, arrival time, minutes away, and where the bus is now
- **Passed / still coming counts** per stop, with a wait-vs-go-ahead recommendation
- **Missed-bus intercept** — if your bus just passed, it names the nearest stop ahead where you can still catch it, with road distance and a plain verdict
- **Any bus, any student** — no bus is assigned to a student; board any bus that stops at your stop. Bus numbers are allotted to routes per day (Admin view)
- **Driver view** — fully automatic: stops mark themselves reached, next stop and on-time status update on their own
- **Admin view** — fleet status, daily bus allotment, and a delay override that shifts student ETAs
- **"Use my location"** — finds your nearest stop automatically (location is never stored or sent)

## Data

Routes 1–10 + Ghatshila (Morning, Morning 2nd Trip, Afternoon) from the official **AJU Transport Chart 2026–27**, ending at Gamaharia Campus. Lal Building is a stop on every route. Route lines follow real driving roads (geometry baked in at build time — no API key and no routing calls at runtime).

> **Demo note:** bus positions are currently *simulated* from the chart schedule — the site replays the morning service on a simulated clock and is labelled as simulated in the header. No real GPS feed is connected yet.

## Run it

Everything is in a single self-contained file — just open `index.html` in a browser. No build step, no server, no API keys.

## Tech

Plain HTML/CSS/JavaScript in one file, with [Leaflet](https://leafletjs.org/) bundled in, OpenStreetMap map tiles (with free mirror and offline fallbacks), and road geometry from OSRM baked into the page.
