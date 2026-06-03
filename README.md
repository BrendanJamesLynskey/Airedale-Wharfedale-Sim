# Yorkshire Train Simulator

A browser-based train driver simulator covering passenger lines in
West Yorkshire, England. The menu picks the route — the full **Leeds →
Skipton** Airedale service (11 stations, 41.8 km) or the **Shipley →
Ilkley** Wharfedale branch (7 stations, 17.0 km) — and the unit, either
**Class 333** or **Class 331/0**.

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

## Maps

The menu has a **Select Map** panel that lists every route defined in the
in-memory `MAPS` table. Picking a map swaps the active `ROUTE`, reprojects
the track centreline against the new lat/lon waypoints, tears down the
previous world meshes (terrain, river, track, OHLE, stations, signals,
scatter, landmarks) and rebuilds them against the new route. The cab's
printed schedule card and any "N CAR" stop markers repaint with the new
station list.

Currently shipped maps:

| Map | Biome | Stations | Length | Service |
|-----|-------|----------|--------|---------|
| **Airedale Line** | Countryside | 11 | 41.8 km | 2L42 Leeds → Skipton |
| **Wharfedale Line** | Moorland | 7 | 17.0 km | 2L72 Shipley → Ilkley |

The Wharfedale branch climbs out of the Aire valley via Shipley Curve,
traverses the moorland edge to Guiseley and Menston, then descends into
the Wharfe valley through Burley-in-Wharfedale, Ben Rhydding and Ilkley.
The River Wharfe joins the line at Burley and runs alongside it on the
north side through to Ilkley. The line is 25 kV AC electrified so the
same Class 333 / 331 stock applies.

Adding a built-in route is a single `MAP_XXX` literal + an entry in
`MAPS` — the menu picks it up automatically and the world rebuild path
is shared.

## Custom Maps — load your own line

The menu has two **LOAD…** buttons beneath the map picker:

- **LOAD FROM FILE…** opens a file picker for a JSON file on your
  device.
- **LOAD FROM URL…** prompts for a URL (pre-filled with the bundled
  `sample-line.json`). Same-origin URLs work directly; cross-origin
  URLs need the source to send a permissive `Access-Control-Allow-
  Origin` header. `file://` URLs are blocked by the browser when the
  page is served over `http(s)://` — use the file picker for local
  files.

A loaded map appears as a new button in the picker and is selected
automatically. The whole world rebuilds against it (track, terrain,
river, OHLE, stations, signals, scatter, landmarks) and the cab is
rebuilt so the printed schedule card / "N CAR" stop markers track the
new route. If the loaded `key` collides with an existing map the
existing entry is replaced (a green "Replaced …" message confirms);
malformed JSON or missing required fields produce a red error message
and leave the active map untouched.

A bundled sample line — the fictional **Bumblethorpe Valley Line** —
ships at [`sample-line.json`](./sample-line.json): 10 stations
(Bumblethorpe Central, Lower Snoring, Pratt's Bottom Halt, Steeple
Bumpstead, Nether Wallop, Crackpot Junction, Upper Dumpling, Great
Mumbling, Wetwang Cross, Pity-Me Terminus), 26 km, 3 river crossings,
2 tunnels (Crackpot, Mumbledon), 2 viaducts (Snoring, Wetwang) and a
mill. Use it as a template when writing your own.

### Graphical editor

The [**Yorkshire Line Editor**](https://brendanjameslynskey.github.io/Yorkshire-Line-Editor/)
([repo](https://github.com/BrendanJamesLynskey/Yorkshire-Line-Editor))
is a companion 2D plan-view editor: drag stations, scenery features,
river points and speed limits onto a canvas; export downloads a JSON
file shaped exactly like the schema below. It's the easier way to
build a line if you'd rather not hand-author the JSON.

### Map JSON schema

The file is a single JSON object with the same shape as a `MAPS`
entry. Required fields:

| Field | Type | Notes |
|-------|------|-------|
| `key` | string | unique table key (loaded keys may collide with bundled ones — that replaces) |
| `name` | string | human-readable line name |
| `totalKm` | number | route length, must be > 0 |
| `stations` | array | ≥ 2 entries, each with `km`, `name`, `code`, `plat`, `side` (`'L'`\|`'R'`\|`'I'`), `elev`, `lat`, `lon`. Each station may also carry optional `platforms` (1–6, defaults to 2 for `side: 'I'` else 1) and `type` (`'halt'`\|`'station'`\|`'terminus'`\|`'junction'`, defaults to `'station'`). Halts skip the canopy; counts above 2 add "wing" platforms further out laterally with `PLATFORM n` badges. Terminus / junction are recognised but currently render as a normal station. |
| `schedule` | array of numbers | cumulative seconds from departure, same length as `stations` |
| `limits` | array | ≥ 1 entry, each `{ km, mph }` (use `km: 0` for the starting limit) |

Optional fields (auto-defaulted if missing):

| Field | Default | Notes |
|-------|---------|-------|
| `displayName` | upper-cased `name` | menu h2 / cab schedule card header |
| `subtitle` | derived from station endpoints + km + count | menu service line |
| `biome` | `"countryside"` | mostly a metadata tag; `"coastal"` swaps the river ribbon for a sea + sand strip (see Biomes below). Other values (`moorland`, `urban`, `upland`) have no rendering effect yet. |
| `service` | derived from station codes | cab schedule card top line |
| `features` | `[]` | each `{ km, type: 'bridge'\|'tunnel'\|'viaduct'\|'mill', len?, side? }` |
| `riverPath` | `[]` | each `{ km, lat }` — `lat` is **metres lateral offset** from track centreline, not geographic latitude; smoothstep-interpolated between control points; cross zero at bridge km for a visible crossing |
| `shapePoints` | `[]` | each `{ km, lat, lon }` — geographic curve-control waypoints between stations |
| `version` | absent | reserved for future schema evolution |

The route is laid out by projecting station `lat`/`lon` (equi-
rectangular about Leeds, rotated to the Leeds → Skipton bearing) and
interpolating through them — plus any `shapePoints` — with Catmull-Rom
curves. The terrain plane, OHLE, signals and scatter all derive from
the resulting centreline, so any geographically-plausible set of
lat/lons will render a coherent line.

### Biomes

Most of the biome values are just menu metadata, but `coastal` is
wired up. When `biome: "coastal"`:

- The river ribbon is replaced by a wide sea plane plus a sand
  strip, on one side of the track.
- Which side is determined by the **sign** of the average `riverPath`
  `lat` offset — positive (south of track) puts the sea south,
  negative (north of track) puts it north. With no `riverPath` the
  sea defaults to the south.
- The local distance to the coast comes from `|riverLatAt(km)|`,
  clamped to 180–600 m so the sea is always visible from the cab
  (the editor's "river" tool tends to land coastline values further
  out than the visible terrain extends).
- The sea surface sits 25 m below the trackbed, so the cab looks
  down at the water like a real cliff-top line.

So the practical recipe when drawing a coastal line in the editor:
use the **＋ River pt** tool to sketch where the coast runs, on the
side of the track you want it. The exact distance you draw is a
suggestion — the sim clamps it to a visible band — but the side and
the shape both come through. Other features (bridges, viaducts,
tunnels) still render as expected; you can use a bridge to cross an
inlet.

## Roadmap

- Contrasting biomes: a coastal line (e.g. St Ives Bay) and an upland
  line (e.g. a Settle–Carlisle slice) to exercise the biome system
  beyond the current countryside/moorland pair
- In-browser map editor (form-based) on top of the JSON loader
- localStorage persistence for loaded / edited maps
- Additional rolling stock: Class 195 (DMU)
- Real audio recordings (CC-BY) replacing synthesised audio
- Day / night / weather presets
- Save best-time leaderboard (local storage)

## Repo

[BrendanJamesLynskey/Airedale-Wharfedale-Sim](https://github.com/BrendanJamesLynskey/Airedale-Wharfedale-Sim)

## Licence

MIT.
