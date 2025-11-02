# Heating System Documentation

## System Overview

This repository contains documentation and monitoring tools for a multi-zone radiator heating system with individual zone control.

## Hardware Components

### Boiler
- **Model**: Ariston Alteas ONE Net 30 kW Combi
- **Type**: Combination boiler
- **Connectivity**: BUS BridgeNet protocol (proprietary)

### Control Systems
- **Boiler Controller**: Ariston Cube S Net (WiFi-enabled, controls boiler via BUS)
- **Room Thermostats**: Heatmiser neoStat v2 (one per room zone, 4 total)
- **Bathroom Control**: Manual or always-on (no thermostats)

### Distribution
- **Manifold**: Henco UFH-0605MDSS0X stainless steel manifold (6 zones)
- **Actuators**: Heatmiser TA230 (230V AC, normally closed, 2-wire)

### Radiators
- **Room Radiators**: Stelrad Classic Compact Panel Radiators (4 units)
- **Bathroom Radiators**: Standard bathroom radiators (2 units)

## Zone Configuration

The system manages 6 independent heating zones:

### Room Zones (4 zones with thermostats)
Each room zone includes:
- Heatmiser neoStat v2 room thermostat
- Heatmiser TA230 actuator on manifold
- Stelrad Classic Compact Panel Radiator

### Bathroom Zones (2 zones without thermostats)
Each bathroom zone includes:
- Heatmiser TA230 actuator on manifold
- Bathroom radiator
- Manual or always-on control

## System Architecture

### Water Distribution
```
Ariston Alteas ONE Net Boiler
    ↓ (hot water supply/return)
Henco Stainless Steel Manifold
    ↓ (6 independent circuits)
6x TA230 Actuators (mounted on manifold)
    ↓ (controlled water flow)
4x Room Radiators + 2x Bathroom Radiators
```

### Electrical Control
```
230V AC Mains Supply
    ↓
Ariston Cube S Net ←→ Boiler (BUS connection)
    ↓
4x neoStat v2 Thermostats (rooms only)
    ↓ (switched 230V control)
6x TA230 Actuators
    ↓ (open/close manifold valves)
Individual zone heating control
```

## Wiring Details

### Heatmiser neoStat v2 Connections
- **L** - Live input (230V AC)
- **N** - Neutral input
- **A1** - Switched Live output (to actuator)
- **A2** - Common/Neutral output (to actuator)
- **RT1, RT2** - Optional floor sensor (10kΩ NTC)

### Heatmiser TA230 Actuator
- **2-Wire Connection**: Live and Neutral from thermostat
- **Operation**: Normally Closed (NC) - opens when 230V applied
- **Response Time**: ~3 minutes to fully open
- **Mounting**: M30 x 1.5 thread on manifold return port

### Ariston Cube S Net
- **Connection**: 2-wire BUS to boiler
- **Protocol**: BridgeNet (proprietary, not OpenTherm)
- **Function**: Controls boiler operation, NOT individual zones
- **Connectivity**: WiFi for Ariston NET app

## Diagrams

- **heating-system.drawio** - Overall system architecture showing water and electrical connections
- **wiring-diagram.drawio** - Detailed wiring specifications and terminal connections

Open these files with [draw.io](https://app.diagrams.net) for viewing and editing.

## Important Notes

⚠️ **Safety and Installation**
- All electrical work must be performed by a qualified electrician
- System operates on 230V AC - disconnect power before any work
- Actuators are normally closed - valves close when power is removed
- Each thermostat requires dedicated 230V supply (L + N)
- All installations must comply with local electrical regulations

**System Operation**
- Room thermostats independently control their zones
- When thermostat calls for heat, it provides 230V to actuator
- Actuator opens manifold valve, allowing hot water to radiator
- Cube S Net manages overall boiler operation and scheduling
- Bathroom zones may require manual switching or timer control
