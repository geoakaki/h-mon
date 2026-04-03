# H-MON — Home Heating Monitoring System

Documentation repo for a 6-room home heating system. No application code — only docs, diagrams, and device specs.

## Current System (Planned)

The system is being upgraded to a **12V low-voltage** Heatmiser setup with Giacomini manifolds.

**Control:** Heatmiser UH8-N (8-zone, 12V) + neoHub G3 + 4x neoStat 12V V3
**Distribution:** Giacomini R559NY005 manifold group (5 circuits) + R553ZY005 brass manifold (5 outlets)
**Actuators:** Giacomini R473X221 (230V NC thermo-electric) x10

> **NOTE:** README.md still describes the older 230V/UH4 4-zone configuration with Ariston boiler, Henco manifold, and TA230 actuators. It needs updating to match the current device list.

## Rooms (6 total, 5 manifold circuits needed)

| # | Room | Heating Type |
|---|------|-------------|
| 1 | Bedroom 1 | Radiator |
| 2 | Bedroom 2 | Radiator |
| 3 | Bedroom 3 | Radiator |
| 4 | Bathroom 1 | Bath Radiator |
| 5 | Bathroom 2 | Bath Radiator |
| 6 | Studio | Underfloor |

## Device List

| # | Brand | Device | Qty | Status |
|---|-------|--------|-----|--------|
| 1 | Heatmiser | UH8-N - 8 Zone 12v Wiring Centre | 1 | Have |
| 2 | Heatmiser | neoStat 12v V3 - Smart Thermostat | 4 | Have |
| 3 | Heatmiser | neoHub G3 | 1 | Have |
| 4 | Giacomini | R559NY005 — Pre-assembled manifold group, 5 circuits | 1 | To Buy |
| 5 | Giacomini | R553ZY005 — Pre-assembled brass manifold, 5 outlets | 1 | To Buy |
| 6 | Giacomini | R473X221 — Thermo-electric actuator, 230V NC | 10 | To Buy |
| 7 | Giacomini | R500Y222 — Flush-mount cabinet | 1 | To Buy |
| 8 | Giacomini | R179AM — Pipe adapters, Base 18 (16×2mm) | 20 | To Buy |

## Repo Structure

- `README.md` — Main docs (currently describes older 230V/UH4 system — needs rewrite)
- `device-list.md` — Current device inventory with buy status
- `rooms.md` — Room list with heating types
- `diagrams/` — draw.io files: `heating-system.drawio`, `wiring-diagram.drawio`, `wiring-diagram-v2.drawio`
- `docs/` — Manufacturer PDFs: Giacomini R553D, R559N-1 manifold docs, Heatmiser UH8-N manual
- `images/` — Exported wiring diagram PNGs (dark/light themes)

## Key Context

- 6 rooms but only 4 thermostats (neoStat) — likely some rooms share a zone or 2 rooms don't have individual control yet
- 5 manifold circuits match 5 rooms with piped heating (Studio UFH uses separate circuits)
- The 10 actuators (2 per circuit) provide redundancy on the Giacomini manifold (flow + return)
- Boiler details (Ariston Alteas ONE Net 30kW Combi) are in README.md but may change with the upgrade
