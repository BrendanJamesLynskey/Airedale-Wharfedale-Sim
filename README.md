# Airedale & Wharfedale Line — Class 333 Driver Simulator

A browser-based train driver simulator for the Airedale and Wharfedale lines
in West Yorkshire, England. v1 covers the full **Leeds → Skipton** Airedale
service (11 stations, 41.8 km) driving a **British Rail Class 333** EMU.

[Play it here](https://brendanjameslynskey.github.io/Airedale-Wharfedale-Sim/)

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
| Q | AWS reset |
| E | DSD reset |
| L | Headlights |
| V | Wipers |
| P / Esc | Pause |
| F + drag | Look around the cab |

On mobile, on-screen pads provide power, brake, horn, AWS reset and pause.

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
- The river Aire is rendered as a meandering blue ribbon parametrised by lateral offset from the track, with its offset crossing zero at three stone-arch bridges (Apperley Bridge, Shipley, Steeton). The water surface samples the same undulation function as the terrain so it sits at local grade rather than a fixed Y. Bridge locations are approximations.

## Roadmap

- v2: Wharfedale branch (Shipley → Ilkley) selectable from the menu
- Additional rolling stock: Class 195, Class 331/0
- Real audio recordings (CC-BY) replacing synthesised audio
- Better cab fidelity using CC-licensed cab reference photos
- Day / night / weather presets
- Save best-time leaderboard (local storage)

## Repo

[BrendanJamesLynskey/Airedale-Wharfedale-Sim](https://github.com/BrendanJamesLynskey/Airedale-Wharfedale-Sim)

## Licence

MIT.
