# Nucleares Dynamic Dashboard

## Overview
A full‐screen, interactive SVG‐based dashboard that visualizes plant equipment status (pumps, valves, turbines) in real time. Equipment highlights change color and blink to reflect live data polled from a local server.

## Features
- **Real‐time polling**: Fetches variables every second from `http://localhost:8785/?variable=<NAME>`.
- **Dynamic color coding**:
  - Gray for off/inactive
  - Limegreen for active/normal operation
  - Orange for maintenance alert (speed deviation)
  - Red + blinking for overload alarm
  - Yellow for intermediate states (e.g., partially open valves)
- **SVG pan & zoom**: Use mouse drag to pan, scroll to zoom (inverted direction: scroll‐down → zoom in).
- **Label updates**: On‐SVG text labels display current pump speed or valve opening percentage.
- **Blink animation**: Overloaded pumps flash using CSS keyframes.

## How It Works
1. **Load**: `dashboard.html` embeds a `<svg id="myplant">` of the plant layout.
2. **Initialize**: On DOMContentLoaded, `svgPanZoom` is configured and the first call to `update()` runs.
3. **Update loop**: Every 1 s, JavaScript fetches each required variable, computes a color (green/orange/red/yellow/gray), calls either `highlightPumpBg(...)` or `highlightGroupBg(...)` to draw/update a colored `<rect>` behind the relevant SVG group, toggles `.blink` if overload, and updates on‐SVG text labels.
4. **Interact**: Use mouse drag to pan, scroll wheel to zoom (custom inverted behavior).

## Dependencies
- [svg-pan-zoom v3.6.1](https://github.com/svg-pan-zoom/svg-pan-zoom) (loaded via CDN).
- A local HTTP endpoint on port 8785 that returns plain text for requests like `/?variable=PUMP_SPEED`.

## Usage
1. Clone this repo.
2. Run your local data server on port 8785, serving variables like `COOLANT_CORE_CIRCULATION_PUMP_0_SPEED`.
3. Open `dashboard.html` in a modern browser.
4. Watch as pump and valve statuses update live, with color‐coded highlights and blinking alarms.

## Extending
- Add new `<g id="new_equipment">…</g>` to the SVG and write matching logic inside `update()`.
- Modify CSS `.blink` for different animation effects.
- Adjust polling interval via `setInterval(update, <ms>)`.

---
