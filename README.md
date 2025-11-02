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

## Cable Specifications

### Power Supply to Thermostats
- **Cable Type**: 2-core + earth (Twin & Earth)
- **Size**: 2.5mm² or 1.5mm²
- **Cores**: Live (Brown), Neutral (Blue), Earth (Green/Yellow)
- **Standard**: BS 6004 or equivalent

### Thermostat to Actuator
- **Cable Type**: 2-core cable
- **Size**: 0.75mm² to 1.5mm²
- **Cores**:
  - Wire 1: Switched Live from A1
  - Wire 2: Neutral/Common from A2
- **Max Length**: Up to 50m (low current - 2W per actuator)

### Recommended Cable Setup
```
Mains 230V Supply
    ↓ (2.5mm² Twin & Earth)
[Junction Box]
    ↓ (1.5mm² Twin & Earth)
neoStat v2 Thermostat
    ↓ (0.75-1.5mm² 2-core)
TA230 Actuator
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
- Room thermostats independently control their zones
- When thermostat calls for heat, it provides 230V to actuator
- Actuator opens manifold valve, allowing hot water to radiator
- Cube S Net manages overall boiler operation and scheduling
- Bathroom zones may require manual switching or timer control

## System Optimization Recommendations

### Priority 1: High Impact Improvements

#### 1. Manifold Flow Balancing
**Why Needed:**
- Different room sizes require different flow rates
- Prevents some rooms being too hot while others are too cold
- Optimizes radiator efficiency and energy usage
- Ensures balanced heat distribution across all zones

**Check Your Manifold:**
Your Henco UFH-0605MDSS0X manifold should have built-in flow meters (glass tubes showing flow rate 0-5 L/min).

**If Flow Meters Missing - What to Buy:**
- **Product**: Replacement Flow Meters (compatible with Henco manifolds)
- **Thread Size**: 1/2" MBSP (check your manifold - may be 3/8")
- **Range**: 0-5 L/min
- **Quantity**: 6 units (one per zone)
- **Cost**: £8-15 per unit | Total: £48-90
- **Where to Buy**:
  - Underfloor heating specialists
  - Amazon (search "Henco manifold flow meter")
  - Compatible brands: Watts, Myson, Prowarm, Rehau

**How to Balance (If You Have Flow Meters):**
1. **Identify longest pipe loop** (furthest room) - open 100%
2. **Adjust each zone** by turning black adjustment screw:
   - Clockwise = decrease flow
   - Anti-clockwise = increase flow
   - No tools needed - adjust by hand
3. **Read flow rate** in glass tube
4. **Target flow rates:**
   - Large Room (20m²): 2-3 L/min
   - Medium Room (15m²): 1.5-2 L/min
   - Small Room (10m²): 1-1.5 L/min
   - Bathroom (5m²): 0.8-1.2 L/min
5. **Target temperature drop:** 7-10°C across each loop

**Cost:** £0 (if meters exist) or £48-90 (new meters) | **Annual Savings:** £80-150 | **Payback:** Immediate

### Priority 2: Recommended Upgrades

#### 2. Add Bathroom Thermostats
**Current Issue:** Bathrooms lack individual temperature control

**Solutions:**
- Add 2x neoStat v2 for bathrooms (full smart control)
- Add timer switches (cheaper, less precise)
- Wire to main boiler schedule (basic control)

**Best Option:** Add neoStats for comfort + energy savings

**Cost:** £200 | **Annual Savings:** £60-100 | **Payback:** 2-3 years

#### 3. Floor Temperature Sensors
**For rooms with tile/stone floors:**
- Connects to neoStat RT1/RT2 terminals
- 10kΩ NTC thermistor sensors
- Prevents floor overheating
- Improves temperature regulation

**Cost:** £60-100 (4 sensors) | **Annual Savings:** £40-60 | **Payback:** 2 years

### Priority 3: Optional Improvements

#### 4. Wiring Centre Consolidation
**Alternative to direct wiring:** Heatmiser UH8 Wiring Centre
- Centralizes all wiring in one location
- Easier troubleshooting and maintenance
- Cleaner cable management
- Built-in pump control

**Cost:** £180-220 | **Benefit:** Convenience, not energy savings

#### 5. Boiler Optimization
**Settings to Check:**
- **CH Temperature**: Set to 60-70°C for radiators (not 80°C+)
- **Pump Speed**: Adjust based on system resistance
- **Weather Compensation**: Enable if available (10-15% savings)
- **Anti-Cycling**: Set minimum run times

## Optimization Action Plan

### Immediate (Do Now)
1. ✅ **Check if flow meters exist** on your Henco manifold
2. ✅ **Purchase flow meters** if missing (£48-90 for 6 units)
3. ✅ **Balance manifold** flow rates per zone
4. ✅ **Optimize boiler settings** (temperature, pump speed)

### Short Term (1-3 months)
5. 🎯 Add bathroom thermostats for complete zone control
6. ⚙️ Install floor sensors (if tile/stone floors)

### Long Term (Future)
7. 🔧 Consider wiring centre during major rewiring
8. 💰 Monitor and optimize based on usage data

## Cost-Benefit Summary

| Upgrade | Cost | Annual Savings | Payback Period | Priority |
|---------|------|----------------|----------------|----------|
| Flow Meters + Balancing | £0-90 | £80-150 | Immediate | **HIGH** |
| Bathroom Thermostats | £200 | £60-100 | 2-3 years | Medium |
| Floor Sensors | £60-100 | £40-60 | 2 years | Medium |
| Wiring Centre | £180-220 | N/A | N/A | Low |
| Boiler Optimization | £0 | £50-100 | Immediate | **HIGH** |
