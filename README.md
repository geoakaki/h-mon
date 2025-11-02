# Heating System Documentation

## System Overview

This repository contains documentation and monitoring tools for a multi-zone underfloor heating system.

## Hardware Components

### Boiler
- **Model**: Ariston Alteas ONE Net 30 kW Combi
- **Type**: Combination boiler

### Control Systems
- **Boiler Thermostats**: Ariston Cube S Net
- **Room Thermostats**: Heatmiser neoStat v2 (one per zone)

### Distribution
- **Manifold**: Henco UFH-0605MDSS0X stainless steel manifold
- **Actuators**: Heatmiser TA230 (230 V, normally closed)

## Zone Configuration

The system manages 6 independent heating zones:
- 4 room zones
- 2 bathroom zones

Each zone is equipped with:
- Individual Heatmiser neoStat v2 thermostat
- Dedicated Heatmiser TA230 actuator on the manifold

## System Architecture

```
Ariston Alteas ONE Net Boiler
    ↓
Ariston Cube S Net (Boiler Control)
    ↓
Henco Stainless Steel Manifold
    ↓
6x Heatmiser TA230 Actuators (one per zone)
    ↓
6x Zones (4 rooms + 2 bathrooms)
    ↑
6x Heatmiser neoStat v2 Thermostats
```

## Notes

- All actuators are 230V, normally closed (NC) type
- Each zone operates independently via its own thermostat and actuator
- System designed for underfloor heating distribution
