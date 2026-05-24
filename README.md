# Airedale & Wharfedale Line — Driver Simulator

A browser-based train driver simulator for the Airedale and Wharfedale lines
in West Yorkshire, England. v1 covers the full **Leeds → Skipton** Airedale
service (11 stations, 41.8 km), with selectable **Class 333** or **Class 331/0**
EMUs.

[Play it here](https://brendanjameslynskey.github.io/Airedale-Wharfedale-Sim/)

## Rolling Stock

The menu lets you pick which unit to drive. Each is modelled with its own
physics, full cab interior and audio signature:

| Unit | Cars | Length | Mass | Cab style |
|------|------|--------|------|-----------|
| **Class 333** | 4 | 96.4 m | 167 t | Classic CAF cab — analogue speedometer, duplex BC/BP pressure gauge, MR pressure gauge, paperwork shelf, monochrome TMS screen |
| **Class 331/0** | 3 | 72.0 m | 120 t | Modern Civity cab — flat-panel TMS / large central DMI / ETCS DMI, CCTV monitor strip above the windscreen, illuminated pushbuttons, lighter pearl-grey palette |

Both share the same UK-standard safety kit (AWS sunflower, DRA mushroom, TPWS+
unit, emergency brake plunger, GSM-R cab radio) and the same master controller
layout, since both are CAF Civity family.

## Service

**2L42 LEEDS → SKIPTON** — calling at:

| # | Station | Code | km | Sched |
|---|---------|------|----|-------|
| 1 | Leeds | LDS | 0.00 | 00:00 |
| 2 | Kirkstall Forge | KLF | 6.40 | 08:00 |
| 3 | Apperley Bridge | APY | 10.60 | 12:00 |
| 4 | Shipley | SHY | 14.45 | 17:00 |
| 5 | Saltaire | SAE | 15.65 | 19:00 |
| 6 | Bingley | BIY | 19.50 | 23:00 |
| 7 | Crossflatts | CFL | 20.85 | 25:00 |
| 8 | Keighley | KEI | 25.45 | 29:00 |
| 9 | Steeton & Silsden | SON | 28.55 | 32:00 |
| 10 | Cononley | CEY | 32.50 | 35:00 |
| 11 | Skipton | SKI | 41.80 | 43:00 |

Shipley is signed with a **4 CAR stop marker** (yellow plate + painted stripe on
the platform). Halt with the cab beside the marker for a perfect stop.

## Cab Controls

| Key | Action |
|-----|--------|
| ↑ / W | Power up one notch |
| ↓ / S | Power down one notch |
| ← / A | Brake increase |
| → / D | Brake decrease |
| Space | Emergency brake (B6) |
| H | Horn (high tone) |
| J | Horn (low tone) |
| Q | AWS reset / TPWS reset (when stopped) |
| E | DSD reset |
| R | DRA — set / cancel (inhibits traction when set) |
| L | Headlights |
| V | Wipers |
| P / Esc | Pause |
| F + drag | Look around the cab |

On mobile, on-screen pads provide power, brake, horn, AWS reset and pause.

## Cab Fittings — Class 333

The Class 333 cab is modelled on the real CAF Civity Mk1 cab fitted to
Northern's 4-car EMUs (in service since 2000), and includes:

- **Speedometer** with chrome bezel and a **digital LCD speed readout** below
- **Duplex pressure gauge** — red needle for brake-cylinder, black needle for brake-pipe
- **Main reservoir** pressure gauge
- **AWS sunflower** with reset mushroom
- **DRA** (Driver's Reminder Appliance) — large illuminated red mushroom; when set, prevents traction
- **TPWS panel** — yellow-trimmed unit with TRAIN STOP OVERRIDE, BRAKE DEMAND (illuminates on intervention) and TEMPORARY ISOLATION buttons
- **Emergency Brake Plunger** — large red shrouded mushroom right of the master controller
- **GSM-R cab radio** with green LCD and 4×4 keypad on the left bulkhead
- **Door release** L / R buttons, **reverser key switch** (R / N / F), **sander** and **pantograph** buttons
- **Headlights / wipers / cab-light** toggle switches
- **Yellow horn paddle** on the left dashboard
- **Master controller** lever with detented strip showing P1–P4 / OFF / B1–B5 / EB
- **TMS / driver display** screen on the left of the dash showing service info
- **Paperwork shelf** above the gauges with the printed schedule card
- **Grab handle** on the cab side, sun visors, A-pillars, headliner and side-window frames

## Cab Fittings — Class 331/0

The Class 331/0 cab is a complete ground-up rebuild reflecting Northern's
newer CAF Civity DMU/EMU (in service since 2019). The dashboard is fully
flat-panel; there are no analogue gauges. It includes:

- **TMS status panel** (left flat screen) — service code, unit length, brake
  test status, doors, pantograph, traction state
- **Main DMI** (large central flat screen) — big digital MPH readout, live
  speed-vs-limit bar, brake-cylinder and main-reservoir pressure bars, next
  station and live schedule
- **ETCS DMI** (right flat screen) — placeholder showing ERTMS level (the
  real unit is fitted but not active on Northern's network)
- **CCTV monitor strip** above the windscreen — four small platform-view
  displays, mimicking the DOO CCTV fitted to Class 331 cabs
- **AWS sunflower** with reset mushroom (UK-standard safety kit)
- **DRA** — large illuminated red mushroom; inhibits traction when set
- **TPWS+ panel** — yellow-trimmed unit beside the central DMI
- **Emergency Brake Plunger** — right of the master controller
- **GSM-R cab radio** on the left bulkhead
- **Flat illuminated pushbuttons** for headlights / wipers / cab light
  (replacing 333's physical toggle switches)
- **Door release L / R** in a chrome-trimmed recessed plate
- **Reverser key switch** (R / N / F), **sander** and **pantograph** buttons
- **Master controller** with the same P1–P4 / OFF / B1–B5 / EB lever as the
  333, mounted on a wider chrome plinth
- Lighter pearl-grey palette throughout — visible chrome trim, cooler
  headliner and rear bulkhead than the 333

## Demo Mode

The menu's **DEMO RUN ×2** button starts an autopilot that drives the route end-to-end at 2× sim speed: target speed at any km is the lower of the legal limit and `sqrt(2·a·d)` braking distance to the next platform centre, notch is chosen by velocity error, station dwell is shortened, and DSD/AWS escalation is bypassed. Useful for showing the route without driving it.

## Driving Notes

- Combined master controller has **5 power notches (P1–P4) and 6 brake notches (B1–B6)**, with **OFF** in the middle. B6 is emergency.
- Observe **speed limits** shown in the top bar and approach signals.
- **AWS** sounds a bell on green and a buzzer on yellow/red — press **Q** within ~2.7 seconds to acknowledge or you'll get an emergency brake application.
- **DSD** (Driver's Safety Device) requires a press of **E** at least every 60 seconds.
- **Stop accuracy** is scored: ±5 m perfect, ±12 m good, ±25 m OK. Schedule adherence also adds to score.

## Tech

- Single-file `index.html`, no build step. Three.js r160 loaded from CDN.
- All scenery, track, OHLE, signals, stations, cab and instruments are **procedurally built in code** — no external image or model assets ship with the repo, so there are no asset licensing complications.
- All audio is **synthesised in the browser via WebAudio** (traction whine, brake hiss, AWS bell/buzzer, two-tone horn). Hooks in the audio code allow real Freesound CC-licensed recordings to be slotted in later.
- Designed to run on desktop and mobile (touch overlay, responsive HUD).
- Route geometry follows the real Airedale Line — station GPS positions plus ~10 intermediate shape points are projected (equirectangular, rotated to the mean Leeds→Skipton bearing) and interpolated with Catmull-Rom curves. Shape-point coordinates are educated approximations of the Aire valley meander; refine with OSM way data for higher fidelity. Gradient profile and lineside features remain stylised.
- The river Aire is rendered as a meandering blue ribbon parametrised by lateral offset from the track. The line crosses the Aire only once on the real Airedale route — at Apperley Bridge — and the river stays on the south side from there through Saltaire, Bingley, Crossflatts, Keighley, Steeton, Cononley to Skipton (Salts Mill sits between line and river at Saltaire). The water surface samples the same undulation function as the terrain so it sits at local grade rather than a fixed Y.

## Roadmap

- v2: Wharfedale branch (Shipley → Ilkley) selectable from the menu
- Additional rolling stock: Class 195 (DMU)
- Real audio recordings (CC-BY) replacing synthesised audio
- Day / night / weather presets
- Save best-time leaderboard (local storage)

## Repo

[BrendanJamesLynskey/Airedale-Wharfedale-Sim](https://github.com/BrendanJamesLynskey/Airedale-Wharfedale-Sim)

## Licence

MIT.
