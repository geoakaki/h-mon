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
- **Wiring Centre**: Heatmiser UH4 (4-zone, 230V, up to 6 actuators per zone)
- **Room Thermostats**: Heatmiser neoStat v2 (3 units for radiator zones + 1 for UFH zone)

### Distribution
- **Manifold**: Henco UFH-0605MDSS0X stainless steel manifold with flow meters (4 zones, 0-5 L/min per zone)
- **Actuators**: Heatmiser TA230 (230V AC, normally closed, 2-wire)

### Heating Output
- **Radiators**: Stelrad Classic Compact Panel Radiators (3 zones)
- **Underfloor Heating**: 1 zone with underfloor heating circuits

## Zone Configuration

The system manages 4 independent heating zones:

### Zone 1-3: Radiator Zones (with thermostats)
Each radiator zone includes:
- Heatmiser neoStat v2 room thermostat
- Heatmiser TA230 actuator on manifold
- Stelrad Classic Compact Panel Radiator
- Connected to UH4 wiring centre (Zones 1-3)

### Zone 4: Underfloor Heating Zone (with thermostat)
- Heatmiser neoStat v2 room thermostat
- Multiple Heatmiser TA230 actuators on manifold (for UFH circuits)
- Underfloor heating loops
- Connected to UH4 wiring centre (Zone 4)

## System Architecture

### Water Distribution
```
Ariston Alteas ONE Net Boiler
    ↓ (hot water supply/return)
Henco Stainless Steel Manifold (4 zones)
    ↓ (4 independent circuits)
TA230 Actuators (mounted on manifold)
    ↓ (controlled water flow)
Zone 1-3: Radiators (Stelrad Classic Compact Panel)
Zone 4: Underfloor Heating Loops
```

### Electrical Control
```
230V AC Mains Supply
    ↓
Heatmiser UH4 Wiring Centre (4 zones)
    ↓
4x neoStat v2 Thermostats (Zone 1-4)
    ↓ (switched 230V control via UH4)
TA230 Actuators (1 per radiator zone, multiple for UFH zone)
    ↓ (open/close manifold valves)
Individual zone heating control

Ariston Cube S Net ←→ Boiler (BUS connection)
    ↑
UH4 Volt-Free Output (boiler call for heat)
```

## Wiring Details

### Heatmiser UH4 Wiring Centre
**Power Supply:**
- **L** - Live input (230V AC, fused at 5A)
- **N** - Neutral input

**Zone Connections (4 zones):**
- **Zone 1-4 Thermostat Inputs**: L, N, Call (from neoStat)
- **Zone 1-4 Actuator Outputs**: Live and Neutral (230V, 3A max per zone)
- Each zone can connect up to 6 actuators

**Boiler Control:**
- **Volt-Free Output**: 2-wire connection to Cube S Net or boiler
- **Function**: Triggers boiler when any zone calls for heat

**System Connections:**
- **Pump**: Optional 230V pump control output
- **Hot Water**: Optional cylinder thermostat input

**Specifications:**
- Total Load: 5A maximum
- Dimensions: 384 x 148 x 60mm
- IP20 protection
- DIN rail or wall mountable

### Heatmiser neoStat v2 Connections
- **L** - Live input (230V AC)
- **N** - Neutral input
- **Call** - Switched output to UH4 wiring centre
- **RT1, RT2** - Optional floor sensor (10kΩ NTC, for UFH zone)

### Heatmiser TA230 Actuator
- **2-Wire Connection**: Live and Neutral from UH4 zone output
- **Operation**: Normally Closed (NC) - opens when 230V applied
- **Response Time**: ~3 minutes to fully open
- **Mounting**: M30 x 1.5 thread on manifold port

### Ariston Cube S Net
- **Connection**: 2-wire BUS to boiler
- **Protocol**: BridgeNet (proprietary, not OpenTherm)
- **Function**: Controls boiler operation based on UH4 call for heat
- **Connectivity**: WiFi for Ariston NET app
- **Input from UH4**: Volt-free contacts trigger boiler demand

## Diagrams

### Wiring Diagram

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="images/wiring-diagram.dark.png">
  <source media="(prefers-color-scheme: light)" srcset="images/wiring-diagram.light.png">
  <img alt="Heating System Wiring Diagram" src="images/wiring-diagram.light.png">
</picture>

### Editable Source Files

- **heating-system.drawio** - Overall system architecture showing water and electrical connections
- **wiring-diagram.drawio** - Detailed wiring specifications and terminal connections

Open these files with [draw.io](https://app.diagrams.net) for viewing and editing.

## Cable Specifications

### Power Supply to UH4 Wiring Centre
- **Cable Type**: 3-core + earth (Twin & Earth)
- **Size**: 2.5mm²
- **Cores**: Live (Brown), Neutral (Blue), Earth (Green/Yellow)
- **Protection**: 5A fuse or MCB
- **Standard**: BS 6004 or equivalent

### Thermostats to UH4 Wiring Centre
- **Cable Type**: 3-core cable
- **Size**: 0.75mm² to 1.5mm²
- **Cores**:
  - Wire 1: Live (L)
  - Wire 2: Neutral (N)
  - Wire 3: Call/Switched Live
- **Max Length**: Up to 50m

### UH4 to Actuators
- **Cable Type**: 2-core cable
- **Size**: 0.75mm² to 1.5mm²
- **Cores**: Live and Neutral (230V zone output)
- **Max Length**: Up to 50m
- **Load**: 2W per actuator, max 6 actuators per zone

### UH4 to Boiler (Volt-Free)
- **Cable Type**: 2-core cable
- **Size**: 0.5mm² to 1.0mm²
- **Connection**: Volt-free contacts to Cube S Net input
- **Max Length**: Up to 100m (low voltage signal)

### Recommended Cable Setup
```
Mains 230V Supply
    ↓ (2.5mm² Twin & Earth, 5A fused)
Heatmiser UH4 Wiring Centre
    ├─ (0.75-1.5mm² 3-core) → 4x neoStat v2 Thermostats
    ├─ (0.75-1.5mm² 2-core) → TA230 Actuators (4 zones)
    └─ (0.5-1.0mm² 2-core) → Ariston Cube S Net (volt-free)
```

## Important Notes

⚠️ **Safety and Installation**
- All electrical work must be performed by a qualified electrician
- System operates on 230V AC - disconnect power before any work
- Actuators are normally closed - valves close when power is removed
- Each thermostat requires dedicated 230V supply (L + N)
- All installations must comply with local electrical regulations
- Always connect earth to thermostat backplate
- Keep low voltage and mains cables separated

**System Operation**
- Room thermostats (neoStat v2) independently control their zones
- When thermostat calls for heat, it sends signal to UH4 wiring centre
- UH4 provides 230V to zone actuator(s), opening manifold valve
- Hot water flows to radiator (Zones 1-3) or UFH loops (Zone 4)
- UH4 volt-free output signals Cube S Net to activate boiler
- Cube S Net manages overall boiler operation via BridgeNet protocol

## System Optimization Recommendations

### Priority 1: High Impact Improvements

#### 1. Floor Temperature Sensors
**For rooms with tile/stone floors:**
- Connects to neoStat RT1/RT2 terminals
- 10kΩ NTC thermistor sensors
- Prevents floor overheating
- Improves temperature regulation

**Cost:** £60-100 (4 sensors) | **Annual Savings:** £40-60 | **Payback:** 2 years

### Priority 2: Optional Improvements

#### 2. Smart Hub Integration (Optional)
**Heatmiser neoHub Gen 2:**
- Centralized control of all neoStat thermostats via smartphone app
- Smart scheduling, geo-location, and remote access
- Voice control (Alexa, Google Home, HomeKit)
- Energy monitoring and usage tracking per room
- **Requirements**: Ethernet or WiFi connection, USB 5V power (PoE not supported)
- **Placement**: Near router, within 50m of at least one neoStat (mesh networking extends range)
- **Cost**: £120-150

**Cost:** £120-150 | **Annual Savings:** £100-200 | **Payback:** 1-2 years

#### 3. Wiring Centre Consolidation
**Alternative to direct wiring:** Heatmiser UH8 Wiring Centre
- Centralizes all wiring in one location
- Easier troubleshooting and maintenance
- Cleaner cable management
- Built-in pump control

**Cost:** £180-220 | **Benefit:** Convenience, not energy savings

#### 4. Boiler Optimization
**Settings to Check:**
- **CH Temperature**: Set to 60-70°C for radiators (not 80°C+)
- **Pump Speed**: Adjust based on system resistance
- **Weather Compensation**: Enable if available (10-15% savings)
- **Anti-Cycling**: Set minimum run times

## Optimization Action Plan

### Immediate (Do Now)
1. ✅ **Optimize boiler settings** (temperature, pump speed)
2. ✅ **Balance manifold** flow rates using built-in flow meters

### Short Term (1-3 months)
3. ⚙️ Install floor sensors (if tile/stone floors)

### Long Term (Future)
4. 🔧 Consider smart hub integration for remote control
5. 🔧 Consider wiring centre during major rewiring
6. 💰 Monitor and optimize based on usage data

## Cost-Benefit Summary

| Upgrade | Cost | Annual Savings | Payback Period | Priority |
|---------|------|----------------|----------------|----------|
| Floor Sensors | £60-100 | £40-60 | 2 years | **HIGH** |
| Boiler Optimization | £0 | £50-100 | Immediate | **HIGH** |
| Smart Hub (neoHub) | £120-150 | £100-200 | 1-2 years | Medium |
| Wiring Centre | £180-220 | N/A | N/A | Low |
