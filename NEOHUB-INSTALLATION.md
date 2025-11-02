# Heatmiser neoHub Gen 2 - Installation Guide

## Where to Install the neoHub

### Recommended Locations

**Best Locations:**
1. **Near your router** - Minimizes Ethernet cable length and ensures stable network connection
2. **Central location in home** - Optimizes RF signal distribution to all thermostats
3. **Away from metal objects** - Metal can interfere with RF signals
4. **Avoid damp areas** - Keep away from bathrooms, kitchens, or areas with high humidity
5. **Room temperature areas** - Avoid extreme temperatures (boiler room, attic)

**Ideal Spots:**
- Living room near router
- Home office or study
- Hallway with router access
- Under stairs cupboard (if router is there)
- Utility room (if dry and temperature-controlled)

**Avoid:**
- ❌ Inside metal cabinets or enclosures
- ❌ Behind large metal appliances
- ❌ In boiler cupboards (too hot)
- ❌ Bathrooms or wet areas
- ❌ Direct sunlight exposure
- ❌ Near sources of RF interference (microwaves, baby monitors)

### Mounting Options

The neoHub can be:
- Placed on a shelf or desk
- Wall-mounted (small, discreet: 170 x 91 x 25.5mm)
- Hidden in a cupboard (ensure adequate ventilation)

## Distance Requirements

### RF Range Specifications

**Maximum Range:**
- **Direct range**: 50 meters from neoHub to neoStat
- **Mesh networking**: Virtually unlimited through mesh network

### How Mesh Networking Works

The neoHub uses **intelligent mesh networking**:

```
neoHub (50m range)
    ↓
neoStat Room 1 (acts as repeater)
    ↓ (50m range)
neoStat Room 2 (acts as repeater)
    ↓ (50m range)
neoStat Room 3
    ↓
And so on...
```

**Key Points:**
- Each mains-powered neoStat automatically acts as a signal repeater
- Signal strength is maintained as it bounces between devices
- Virtually zero chance of weak signal with multiple neoStats
- The more neoStats you have, the stronger the overall network

### Your System (4 Rooms)

With 4 neoStats in different rooms:
- Each acts as a repeater for the others
- Creates a robust mesh network
- neoHub can be placed anywhere within 50m of at least one neoStat
- Other neoStats will connect through the mesh

**Example Layout:**
```
Router/neoHub (Living Room)
    ↓ 15m
neoStat Room 1 ─→ 20m ─→ neoStat Room 2
    ↓ 25m                    ↓ 15m
neoStat Room 3 ─→ 18m ─→ neoStat Room 4
```

All devices will communicate reliably through the mesh.

### Range Extenders (If Needed)

If you have weak signals in certain areas:
- **neoPlug**: Smart plug that acts as RF repeater
- **Boost Module**: Dedicated range extender
- **Additional neoStat**: Any mains-powered neoStat extends range

## Power Over Ethernet (PoE)

### PoE Support: ❌ **NOT SUPPORTED**

The Heatmiser neoHub Gen 2 **does not** support native Power over Ethernet (PoE).

### Power Requirements

**Standard Setup:**
- **Power**: USB 5V via included Mini USB power lead
- **Network**: Separate Ethernet cable (RJ45)
- **Included**: Power adapters for UK, EU, and Australia

**What You Need:**
1. USB power adapter (included) → Power socket
2. Ethernet cable (included) → Router

### PoE Alternative Solution

If you want to use PoE for a cleaner installation:

**Use a PoE Splitter:**
```
PoE Switch/Injector
    ↓ (Single Ethernet cable with PoE)
PoE Splitter
    ├─→ RJ45 (Data) → neoHub
    └─→ USB 5V (Power) → neoHub
```

**Recommended PoE Splitter:**
- Input: 802.3af/at PoE
- Output: USB 5V + RJ45 Ethernet
- Example: TP-Link TL-POE10R or similar
- Cost: ~£15-25

**Benefits:**
- Single cable from switch to neoHub location
- No need for nearby power socket
- Cleaner installation

## Installation Checklist

### Pre-Installation

- [ ] Identify optimal neoHub location (near router, central position)
- [ ] Ensure power socket available (or plan PoE splitter)
- [ ] Check Ethernet cable can reach router
- [ ] Verify all neoStat locations are within mesh range
- [ ] Test WiFi signal strength at intended location (if using WiFi)

### What's Included

- ✅ neoHub Gen 2 device
- ✅ Mini USB power lead
- ✅ 4x power adapters (UK, EU, AU)
- ✅ Ethernet cable (RJ45)
- ✅ Quick start guide

### Installation Steps

1. **Physical Setup:**
   - Place neoHub in chosen location
   - Connect Ethernet cable to router
   - Connect USB power adapter
   - Power on device

2. **Network Configuration:**
   - Wait for LED indicators
   - Download Heatmiser Neo app (iOS/Android)
   - Create account or log in
   - Follow in-app setup wizard

3. **neoStat Pairing:**
   - Each neoStat will automatically discover neoHub
   - Confirm pairing in app
   - Name each zone (Room 1, Room 2, etc.)
   - Set initial temperatures

4. **Testing:**
   - Test each zone independently
   - Verify RF signal strength in app
   - Check all neoStats are responding
   - Test scheduling features

## Troubleshooting

### Weak Signal Issues

**Symptoms:** neoStat shows disconnection or slow response

**Solutions:**
1. Relocate neoHub to more central position
2. Move neoHub away from metal objects
3. Add neoPlug or additional neoStat as repeater
4. Check for RF interference sources

### Connection Issues

**Symptoms:** neoHub not connecting to network

**Solutions:**
1. Check Ethernet cable is securely connected
2. Verify router has available DHCP addresses
3. Try WiFi setup if Ethernet fails
4. Restart router and neoHub
5. Check firewall settings

## Specifications Summary

| Specification | Details |
|---------------|---------|
| **Dimensions** | 170 x 91 x 25.5mm (W x H x D) |
| **Power** | USB 5V (Mini USB) |
| **Network** | Ethernet (RJ45) or WiFi |
| **RF Protocol** | 868MHz |
| **RF Range** | 50m (direct), unlimited (mesh) |
| **Max Devices** | 32 zones/devices |
| **PoE Support** | No (use PoE splitter if needed) |
| **Operating Temp** | 0°C to 40°C |
| **Weight** | ~200g |

## For Your System (4 Rooms + 2 Bathrooms)

### Recommended Setup

**neoHub Location:**
- Place near router in central location
- Living room, hallway, or study recommended
- Ensure within 50m of at least one neoStat

**Current Setup:**
- 4 neoStats (rooms) = Excellent mesh network
- Future: Add 2 more neoStats for bathrooms
- Total: 6 devices = Very robust mesh

**Expected Coverage:**
- All rooms will have excellent RF connectivity
- Mesh networking ensures no dead zones
- No range extenders needed

**Power:**
- Standard: USB power adapter to nearest socket
- Alternative: PoE splitter for cleaner installation

### Installation Time

- **Physical setup**: 10-15 minutes
- **App configuration**: 15-20 minutes
- **neoStat pairing**: 5 minutes per device
- **Total**: ~1 hour for complete system

## Additional Resources

- Heatmiser official manual: https://www.heatmiser.com/wpfd_file/neohub-gen-2-manual/
- Heatmiser Neo app: iOS App Store / Google Play Store
- Technical support: +44 (0)1254 669090
- Email: support@heatmiser.com

## Next Steps

After successful installation:
1. Configure heating schedules for each zone
2. Set up geo-location features
3. Enable voice control (Alexa/Google/HomeKit)
4. Monitor energy usage via app
5. Create Smart Profiles for different scenarios
