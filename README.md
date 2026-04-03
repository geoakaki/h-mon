# H-MON — Home Heating Monitoring System

Multi-zone hydronic heating system for a 6-room home, with individual room temperature control via Heatmiser smart thermostats and Giacomini manifold distribution. Two separate Ariston boilers — one dedicated to central heating, one dedicated to domestic hot water (DHW).

## Rooms

### 1. Bedroom 1 — Radiator

Primary bedroom with panel radiator. Requires individual temperature control via dedicated thermostat and manifold circuit. One actuator on the manifold controls water flow to the radiator.

### 2. Bedroom 2 — Radiator

Second bedroom with panel radiator. Requires individual temperature control via dedicated thermostat and manifold circuit. One actuator on the manifold controls water flow to the radiator.

### 3. Bedroom 3 — Radiator

Third bedroom with panel radiator. Requires individual temperature control via dedicated thermostat and manifold circuit. One actuator on the manifold controls water flow to the radiator.

### 4. Bathroom 1 — Towel Rail with Manual TRV

Bathroom with heated towel rail. Not connected to the Giacomini manifold — plumbed directly to the heating circuit as a standalone radiator. Temperature is controlled by a manual thermostatic radiator valve (TRV) attached directly to the towel rail. No actuator, no UH8-N zone, no neoStat thermostat. The towel rail heats whenever the heating boiler is running and the TRV is open.

### 5. Bathroom 2 — Towel Rail with Manual TRV

Second bathroom with heated towel rail. Same setup as Bathroom 1 — direct connection to the heating circuit with a manual TRV on the towel rail. Not part of the manifold system. No actuator, no UH8-N zone, no neoStat thermostat.

### 6. Studio — Underfloor Heating

Open workspace with underfloor heating loops. Requires dedicated thermostat with floor temperature sensor (10k NTC on RT1/RT2 terminals) to prevent floor overheating. Lower water temperature needed — the Giacomini R559NY005 mixing group regulates supply temperature before distribution. UH8-N Zone 8 should be set to UFH mode to enable pump/valve outputs.

## Devices

### Boilers

| # | Device | Purpose | Status |
|---|--------|---------|--------|
| 1 | Ariston Clas ONE System 24 kW | Central Heating | To Buy |
| 2 | Ariston Clas ONE Combi 24 kW | Domestic Hot Water | To Buy |

**Ariston Clas ONE System 24 kW** — Dedicated heating-only system boiler. Provides hot water to the manifold circuit for radiators and underfloor heating. Does not produce domestic hot water. Built-in expansion vessel and circulation pump simplify installation. Modulating burner adjusts output from ~8 kW to 24 kW based on demand. Connected to the Heatmiser UH8-N via volt-free Heat Enable contacts (LS/E/LR terminals) — the UH8-N signals this boiler to fire whenever any heating zone calls for heat. 24 kW is sufficient for 6 rooms (3 radiator circuits on manifold + 1 underfloor circuit on manifold + 2 towel rails direct-plumbed).

**Ariston Clas ONE Combi 24 kW** — Dedicated domestic hot water boiler, used only for its instantaneous DHW capability. Delivers mains-pressure hot water on demand at ~11 L/min (35C rise) — enough for one shower at a time. No hot water cylinder or tank needed. The central heating side of this combi is not used (capped off). Operates independently — heats water instantly when a tap is opened, no signal from the UH8-N required. If two simultaneous showers are needed, upgrade to the 30 kW variant (~13 L/min).

### Control

| # | Device | Qty | Status |
|---|--------|-----|--------|
| 3 | Heatmiser UH8-N — 8 Zone 12V Wiring Centre | 1 | Have |
| 4 | Heatmiser neoStat 12V V3 — Smart Thermostat | 4 | Have |
| 5 | Heatmiser neoHub G3 — Smart Hub | 1 | Have |

**Heatmiser UH8-N** — Central wiring hub that connects all thermostats and controls all actuators. Accepts 230V mains input and provides 12V power to up to 8 neoStat thermostats. When a thermostat calls for heat, the UH8-N switches 230V to the corresponding zone actuator on the manifold. Only zones 1-4 are used (3 bedrooms + 1 studio UFH); bathrooms are direct-plumbed with TRVs and don't use UH8-N zones. The volt-free Heat Enable output (LS/E/LR terminals) signals the Ariston Clas ONE System boiler to fire whenever any zone demands heat. The DHW combi boiler operates independently and does not need a UH8-N connection. Has dedicated UFH pump and UFH valve outputs for underfloor heating zones. Zone 8 has a RAD/UFH switch — set to UFH to enable pump and valve control for the studio's underfloor circuit. Wiring follows the "UH8-N – neoStat-12v and Hot Water Zone" diagram from the UH8-N manual.

**Heatmiser neoStat 12V V3** — Room thermostat powered by 12V from the UH8-N (via +/- terminals). Measures room temperature and sends a call for heat signal (A1/A2 terminals) back to the UH8-N when heating is needed. Supports an optional floor temperature sensor (RT1/RT2 terminals, 10k NTC) for underfloor heating zones to limit floor surface temperature. Communicates wirelessly with the neoHub for smart scheduling, app control, and remote access. 4 units cover 4 zones: 3 bedrooms + 1 studio. Bathrooms use manual TRVs instead.

**Heatmiser neoHub G3** — Smart hub that connects to all neoStat thermostats wirelessly (mesh network, up to 50m range). Provides smartphone app control, smart scheduling, geolocation-based heating, and voice assistant integration (Alexa, Google Home, HomeKit). Connects to the home network via Ethernet or WiFi. Placed near the router. Enables monitoring and control of all heating zones from anywhere.

### Distribution

| # | Device | Qty | Status |
|---|--------|-----|--------|
| 6 | Giacomini R559NY005 — Mixing Group, 5 circuits | 1 | To Buy |
| 7 | Giacomini R553ZY005 — Brass Manifold, 5 outlets | 1 | To Buy |
| 8 | Giacomini R473X221 — Thermo-electric Actuator, 230V NC | 10 | To Buy |
| 9 | Giacomini R500Y222 — Flush-mount Cabinet | 1 | To Buy |
| 10 | Giacomini R179AM — Pipe Adapters, Base 18 (16x2mm) | 20 | To Buy |

### UFH Components

| # | Device | Qty | Status |
|---|--------|-----|--------|
| 11 | UFH Circulation Pump (230V) | 1 | To Buy |
| 12 | UFH Zone Valve with Endswitch (230V) | 1 | To Buy |
| 13 | Heatmiser F-PROBE — Floor Temperature Sensor, 10k NTC | 1 | To Buy |

**UFH Circulation Pump** — 230V pump that circulates water through the studio's underfloor heating loops. Controlled by the UH8-N UFH PUMP output (L/E/N terminals) — the UH8-N switches the pump on when Zone 4 (Studio) calls for heat. Mounts on the Giacomini R559NY005 mixing group circulator connection point. Should be a variable-speed pump sized for the UFH circuit flow rate.

**UFH Zone Valve with Endswitch** — 230V motorized zone valve that opens to allow water flow into the UFH circuit. Controlled by the UH8-N UFH VALVE output (L/E/N terminals). The endswitch is a built-in contact that signals back to the UH8-N when the valve is fully open — this prevents the pump from running before the valve is ready. Normally closed for safety.

**Heatmiser F-PROBE** — 10k NTC thermistor floor probe that connects to the Studio neoStat RT1/RT2 terminals. 3m cable with sensor tip, embedded in the floor screed between heating loops. Limits floor surface temperature to prevent overheating (typically capped at 27-29C). Set the neoStat sensing mode to "Air + Floor" so it uses both room air temperature and floor temperature to control the UFH zone.

### Heat Emitters

| # | Device | Qty | Status |
|---|--------|-----|--------|
| 14 | Panel Radiator — Bedroom 1 | 1 | To Buy |
| 15 | Panel Radiator — Bedroom 2 | 1 | To Buy |
| 16 | Panel Radiator — Bedroom 3 | 1 | To Buy |
| 17 | Heated Towel Rail — Bathroom 1 | 1 | To Buy |
| 18 | Heated Towel Rail — Bathroom 2 | 1 | To Buy |
| 19 | Manual Thermostatic Radiator Valve (TRV) | 2 | To Buy |

**Panel Radiators** — Standard panel radiators for the three bedrooms. Each connects to one manifold circuit via 16x2mm pipes. Size (height, length, panel type) depends on room heat loss calculations. Flow is controlled by the Giacomini R473X actuators on the manifold — the radiator itself has no valve.

**Heated Towel Rails** — Bathroom towel rail radiators for Bathroom 1 and Bathroom 2. Plumbed directly to the heating circuit (not through the manifold). Each towel rail has a manual TRV for local temperature control. Heats whenever the heating boiler is running and the TRV is open.

**Manual Thermostatic Radiator Valves (TRV)** — One per bathroom towel rail. Mounts directly on the towel rail inlet. Contains a wax capsule that expands/contracts with temperature — automatically opens and closes the valve to maintain the set temperature. No electricity, no wiring. Typically set to 3-4 (approx 20-22C) for bathrooms.

**Giacomini R559NY005** — Pre-assembled mixing group that sits between the Ariston Clas ONE System heating boiler and the distribution manifold. Regulates and lowers the water temperature from the boiler before it enters the manifold circuits — essential for underfloor heating which requires lower temperatures (30-45C) than the boiler outputs (60-80C). Includes a 3-way mixing valve, primary and secondary lockshield valves for balancing, delivery temperature probe housing, circulator pump connection point, manual air vents, charge/discharge cocks, and immersion thermometer housings. Connects to boiler supply/return on one side and to the R553Z manifold on the other.

**Giacomini R553ZY005** — Pre-assembled brass distribution manifold with 5 outlet circuits. The supply side has lockshield valves with flow regulation (adjustable with R558 key) to balance water flow between circuits. The return side has thermostatic valve connections where the R473X actuators mount (M30x1.5 thread). 4 of 5 outlets are used (3 bedrooms + 1 studio UFH); the 5th outlet is spare. Bathrooms are not connected to the manifold — they are plumbed directly to the heating circuit with manual TRVs. Adapters R178 or R179 (base 18mm) connect the 16x2mm pipes to the manifold ports.

**Giacomini R473X221** — Thermo-electric actuator (230V, normally closed). Mounts on the return side of the R553Z manifold via M30x1.5 thread. When the UH8-N sends 230V to a zone output, the actuator heats a wax element that pushes the valve open, allowing water to flow through that circuit. Normally closed means the valve stays shut when power is off — a safety feature that prevents uncontrolled heating. Response time is approximately 3 minutes. With 4 manifold circuits, 8 actuators are needed (2 per circuit for flow + return); the remaining 2 of 10 are spares.

**Giacomini R500Y222** — Flush-mount wall cabinet that houses the R559N mixing group and R553Z manifold assembly. Recessed into the wall for a clean installation. Provides access for maintenance and flow adjustment while keeping the manifold protected and out of sight.

**Giacomini R179AM** — Pipe adapters with 18mm base for connecting 16x2mm multilayer (PEX-AL-PEX) pipes to the R553Z manifold outlets. Each manifold circuit needs 2 adapters (supply + return), and with 4 active circuits that's 8 minimum — 20 units provide spares for the mixing group connections, the 5th manifold outlet, and any future extensions.

## Diagrams

Editable source files in `diagrams/` — open with [draw.io](https://app.diagrams.net):

- `heating-system.drawio` — Overall system architecture
- `wiring-diagram.drawio` — Wiring connections (v1)
- `wiring-diagram-v2.drawio` — Wiring connections (v2)
- `wiring-diagram-v3.drawio` — Wiring connections (v3, current) — customized for H-MON setup with 2 boilers, 4 manifold zones, and direct-plumbed bathroom towel rails

Exported images in `images/`:

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="images/wiring-diagram.dark.png">
  <source media="(prefers-color-scheme: light)" srcset="images/wiring-diagram.light.png">
  <img alt="Heating System Wiring Diagram" src="images/wiring-diagram.light.png">
</picture>

## UH8-N Wiring Diagram Version

The UH8-N manual includes four wiring configurations. The correct one for this system is marked below:

| Diagram | Description | For This System? |
|---------|-------------|-----------------|
| UH8-N – Slimline-N and Hot Water Zone | Slimline-N thermostats with hot water cylinder control | No — we use neoStat 12V, not Slimline-N |
| UH8-N – neoStat-12v and Radiator Zone | neoStat 12V thermostats, heating only, no hot water zone | No — we have a separate DHW boiler that needs the H Water zone |
| **UH8-N – neoStat-12v and Hot Water Zone** | **neoStat 12V thermostats with radiator, UFH, and hot water zones** | **Yes — matches our setup** |
| Wiring Diagram – Connecting Multiple UH8-N's | Linking two or more UH8-N units together | No — we have a single UH8-N with 8 zones |

**Why "neoStat-12v and Hot Water Zone":**
- We use **neoStat 12V V3** thermostats (not Slimline-N)
- We have **two boilers** — the heating boiler connects to UH8-N Heat Enable, and the DHW combi boiler can be wired to the H Water zone for on/off scheduling via neoHub
- We have **radiator zones** (3 bedrooms on manifold) and a **UFH zone** (studio on manifold); bathrooms are direct-plumbed with TRVs
- We only need **one UH8-N** — 4 of 8 zones used

## Documentation

Manufacturer PDFs in `docs/`:

- `uh8-n-manual.pdf` — Heatmiser UH8-N installation manual and wiring diagrams
- `R559N-1.pdf` — Giacomini R559NY mixing group instructions and flow scheme
- `R553D.pdf` — Giacomini R553Z manifold technical sheet and regulation guide
