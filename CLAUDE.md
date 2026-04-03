# H-MON — Home Heating Monitoring System

Documentation repo for a 6-room home heating system. No application code — only docs, diagrams, and device specs.

## Current System (Planned)

**12V low-voltage** Heatmiser setup with Giacomini manifolds and two separate Ariston boilers.

**Boilers:** Ariston Clas ONE System 24 kW (heating only) + Ariston Clas ONE Combi 24 kW (DHW only, no cylinder)
**Control:** Heatmiser UH8-N (8-zone, 12V) + neoHub G3 + 4x neoStat 12V V3
**Distribution:** Giacomini R559NY005 manifold group + R553ZY005 brass manifold (5 outlets, 4 used)
**Actuators:** Giacomini R473X221 (230V NC thermo-electric) x10
**Wiring diagram:** "UH8-N – neoStat-12v and Hot Water Zone" from UH8-N manual

## Rooms (6 total, 4 on manifold + 2 direct-plumbed)

| # | Room | Heating Type |
|---|------|-------------|
| 1 | Bedroom 1 | Radiator |
| 2 | Bedroom 2 | Radiator |
| 3 | Bedroom 3 | Radiator |
| 4 | Bathroom 1 | Towel Rail (Manual TRV) |
| 5 | Bathroom 2 | Towel Rail (Manual TRV) |
| 6 | Studio | Underfloor |

## Device List

See `device-list.md` for full inventory with buy status. See `README.md` for detailed device descriptions.

## Repo Structure

- `README.md` — Main docs with room descriptions, device list, and system overview
- `device-list.md` — Current device inventory with buy status
- `rooms.md` — Room list with heating types
- `diagrams/` — draw.io files: `heating-system.drawio`, `wiring-diagram.drawio`, `wiring-diagram-v2.drawio`, `wiring-diagram-v3.drawio` (current)
- `docs/` — Manufacturer PDFs: Giacomini R553D, R559N-1 manifold docs, Heatmiser UH8-N manual
- `images/` — Exported wiring diagram PNGs (dark/light themes)

## Key Context

- 4 neoStat thermostats for 4 zones: 3 bedrooms + 1 studio (UFH). Bathrooms use manual TRVs on towel rails
- 4 manifold circuits: 3 bedrooms (radiators) + 1 studio (UFH). 5th outlet is spare
- Bathrooms are direct-plumbed to heating circuit with TRVs — no manifold, no actuators, no UH8-N zones
- The 10 actuators: 8 needed (2 per circuit for flow + return) + 2 spares
- Two-boiler setup: Ariston Clas ONE System 24kW for heating, Ariston Clas ONE Combi 24kW for DHW (no cylinder)
- DHW combi operates independently — no UH8-N connection needed, heats water on demand when tap opens
- Heating boiler connected to UH8-N Heat Enable (volt-free) output
