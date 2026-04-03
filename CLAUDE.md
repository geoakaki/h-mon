# H-MON — Home Heating Monitoring System

Documentation repo for a 6-room home heating system. No application code — only docs, diagrams, and device specs.

## Current System (Planned)

**12V low-voltage** Heatmiser setup with Giacomini manifolds and two separate Ariston boilers.

**Boilers:** Ariston Clas ONE System 24 kW (heating only) + Ariston Clas ONE Combi 24 kW (DHW only, no cylinder)
**Control:** Heatmiser UH8-N (8-zone, 12V) + neoHub G3 + 4x neoStat 12V V3
**Distribution:** Giacomini R559NY005 manifold group (5 circuits) + R553ZY005 brass manifold (5 outlets)
**Actuators:** Giacomini R473X221 (230V NC thermo-electric) x10
**Wiring diagram:** "UH8-N – neoStat-12v and Hot Water Zone" from UH8-N manual

## Rooms (6 total, 5 manifold circuits needed)

| # | Room | Heating Type |
|---|------|-------------|
| 1 | Bedroom 1 | Radiator |
| 2 | Bedroom 2 | Radiator |
| 3 | Bedroom 3 | Radiator |
| 4 | Bathroom 1 | Towel Rail (Manual TRV) |
| 5 | Bathroom 2 | Towel Rail (Manual TRV) |
| 6 | Studio | Underfloor |

## Device List

| # | Brand | Device | Qty | Status |
|---|-------|--------|-----|--------|
| 1 | Ariston | Clas ONE System 24 kW — Heating boiler | 1 | To Buy |
| 2 | Ariston | Clas ONE Combi 24 kW — DHW boiler | 1 | To Buy |
| 3 | Heatmiser | UH8-N - 8 Zone 12v Wiring Centre | 1 | Have |
| 4 | Heatmiser | neoStat 12v V3 - Smart Thermostat | 4 | Have |
| 5 | Heatmiser | neoHub G3 | 1 | Have |
| 6 | Giacomini | R559NY005 — Pre-assembled manifold group, 5 circuits | 1 | To Buy |
| 7 | Giacomini | R553ZY005 — Pre-assembled brass manifold, 5 outlets | 1 | To Buy |
| 8 | Giacomini | R473X221 — Thermo-electric actuator, 230V NC | 10 | To Buy |
| 9 | Giacomini | R500Y222 — Flush-mount cabinet | 1 | To Buy |
| 10 | Giacomini | R179AM — Pipe adapters, Base 18 (16×2mm) | 20 | To Buy |

## Repo Structure

- `README.md` — Main docs with room descriptions, device list, and system overview
- `device-list.md` — Current device inventory with buy status
- `rooms.md` — Room list with heating types
- `diagrams/` — draw.io files: `heating-system.drawio`, `wiring-diagram.drawio`, `wiring-diagram-v2.drawio`
- `docs/` — Manufacturer PDFs: Giacomini R553D, R559N-1 manifold docs, Heatmiser UH8-N manual
- `images/` — Exported wiring diagram PNGs (dark/light themes)

## Key Context

- 4 neoStat thermostats for 4 zones: 3 bedrooms + 1 studio (UFH). Bathrooms use manual TRVs on towel rails
- 5 manifold circuits match 5 rooms with piped heating (Studio UFH uses separate circuits)
- The 10 actuators (2 per circuit) provide redundancy on the Giacomini manifold (flow + return)
- Two-boiler setup: Ariston Clas ONE System 24kW for heating, Ariston Clas ONE Combi 24kW for DHW (no cylinder)
- DHW combi operates independently — no UH8-N connection needed, heats water on demand when tap opens
- Heating boiler connected to UH8-N Heat Enable (volt-free) output
