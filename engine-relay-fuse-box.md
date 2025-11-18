# Engine Management Relay & Fuse Box

## Overview

This document describes an external relay and fuse box used to support the engine management system. This is a dedicated enclosure separate from the main chassis electrical system, specifically for managing power distribution to critical engine components controlled by the AEM Infinity-6 ECU.

## Purpose

The relay/fuse box provides switched power and circuit protection for:
- Fuel pump(s)
- Cooling fan(s)
- Ignition coil power
- Fuel injector power
- Other engine management accessories

This box integrates with the [AEM Mini Flying Lead Harness](AEM-Mini-Flying-Lead-Harness.md) to provide proper power management and protection for the engine management system documented in the [main README](README.md).

## Components

### Relay Specifications
- **Quantity:** 6 relays
- **Type:** 5-pin automotive relay
- **Rating:** 30/40A @ 12VDC
- **Model:** EPS131R
- **Pin Configuration:** 85, 86, 87a, 87, 30

### Fuse Specifications
- **Quantity:** 6 fuse holders
- **Type:** ATO/ATC blade-style fuses
- **Available Ratings:** 10A, 20A, 25A, 35A

### Hardware Included
- Spade wire terminators for custom wire assembly
- Waterproof enclosure

## Product Information

### Relay & Fuse Box
**Product:** True Mods 12V DC Auto Waterproof Fuse 5-Pin Relay Box
**Description:** 6 ATC/ATO Fusible Holder with 6 Bosch Style Universal Relay Block Holder
**Link:** [Amazon - B08KHVHLL5](https://www.amazon.com/dp/B08KHVHLL5)

### Power Distribution Blocks
**Product:** 12V 150A 1/4" Stud Marine Bus Bar (Pair)
**Quantity:** 2 (1 positive/red, 1 ground/black)
**Specifications:**
- Max Operating Voltage: 48V DC
- Max Continuous Amperage: 150A
- Terminal Stud: 1 x 1/4" (M6) with nut
- Terminal Screws: 12 x M4 stainless steel screws
- Material: Thick tinned copper plate busbar with ABS base
- Features: Insulated, heat resistant, flame resistant

**Included:**
- 1 x positive 12V bus bar (red)
- 1 x ground 12V bus bar (black)
- 2 x protective covers
- 2 x 2 AWG 1/4" copper lugs
- 24 x terminals

## Potential Applications

Based on the [wiring harness recommendations](wiring-harness-recommendations.md), this relay/fuse box can address several power distribution needs:

### Relay 1: ECU Main Power Relay
- **Pin 85:** ECU relay control (from AEM C1-47)
- **Pin 86:** Battery +12V
- **Pin 30:** Battery +12V (30A fused at battery)
- **Pin 87:** Switched power to ECU + injector bus
- **Fuse:** 30A (at relay output)

### Relay 2: Fuel Pump Relay
- **Pin 85:** Fuel pump control (from AEM C1-41 Lowside 0)
- **Pin 86:** Battery +12V
- **Pin 30:** Battery +12V (40A fused for dual pumps)
- **Pin 87:** To dual Walbro fuel pumps (parallel)
- **Fuse:** 35A (for dual pump protection)

### Relay 3: Ignition Coil Power Relay
- **Pin 85:** Switched from ECU main relay or ignition
- **Pin 86:** Battery +12V
- **Pin 30:** Battery +12V (30A fused at battery)
- **Pin 87:** Main coil power bus (10 AWG)
- **Fuse:** 30A

### Relay 4: Cooling Fan Relay
- **Pin 85:** Fan control (from AEM C1-4 Lowside 7)
- **Pin 86:** Battery +12V
- **Pin 30:** Battery +12V (30A fused)
- **Pin 87:** To dual cooling fans (parallel)
- **Fuse:** 25A or 30A

### Relay 5: Idle Air Controller & EBCS (Electronic Boost Control Solenoid) Power
- **Pin 85:** Switched from ECU main relay output
- **Pin 86:** Battery +12V
- **Pin 30:** From ECU main relay Pin 87
- **Pin 87:** Combined IAC + EBCS power (split with inline fuses)
- **Fuse:** 10A (splits to 5A each for IAC and EBCS)

### Relay 6: Spare/Future Use
- Available for additional accessories
- Options: Secondary fuel pump, water injection, nitrous solenoid, etc.
- **Fuse:** TBD based on application

## Wire Gauge Recommendations

Based on the relay/fuse configuration above:

| Circuit | Wire Gauge | Notes |
|---------|-----------|-------|
| Battery to relay Pin 30 | 10-12 AWG | Heavy-duty main feeds |
| Relay Pin 87 outputs | 14-16 AWG | Based on fuse rating |
| Control wires (Pin 85) | 18-22 AWG | Low current signal |
| Ground returns | Match power wire | Minimize voltage drop |

## Power Distribution Architecture

### Bus Bar Integration
The power distribution blocks serve as the main power input hub for the entire engine management system:

**Positive Bus Bar (Red):**
- Main input: 2 AWG wire from chassis switched power (through amp gauge) connected to 1/4" stud
- Outputs: 12 x M4 terminals distribute power to relay Pin 30 inputs (fuse side)
- Central +12V distribution point for all relays

**Ground Bus Bar (Black):**
- Main input: 2 AWG wire to chassis ground connected to 1/4" stud
- Outputs: 12 x M4 terminals for component ground returns
- Centralized grounding point reduces ground loops and voltage drop

### Wiring Strategy
The architecture separates power into two categories:

1. **Heavy Power Feeds (from chassis):**
   - Switched +12V → Red bus bar 1/4" stud (through amp gauge)
   - Chassis ground → Black bus bar 1/4" stud
   - These remain in the engine bay, connected to the relay/fuse box

2. **Relay Outputs (to components):**
   - High-current circuits: Individual heavy-gauge wiring
   - Low-current circuits: Can be bundled or use multi-pin connector

## Connector Recommendations

### For High-Current Relay Outputs
Individual circuits that require heavy-gauge wire (14 AWG or larger) should use dedicated connectors:

**Option 1: Weatherpack Connectors (Recommended)**
- **2-pin Weatherpack:** For fuel pump, fan, coil power feeds
- **Wire Capacity:** 12-16 AWG
- **Rating:** 25A per circuit
- **Advantage:** Waterproof, reliable automotive-grade connections
- **Source:** Delphi/Aptiv Weatherpack series

**Option 2: Deutsch DT Series**
- **2-pin or 4-pin Deutsch DT:** Premium automotive connectors
- **Wire Capacity:** 12-20 AWG (depends on pin size)
- **Rating:** 13A (DT) or 25A (DTM series)
- **Advantage:** Superior environmental sealing, common in motorsports
- **Source:** TE Connectivity Deutsch connectors

### For Low-Current Relay Outputs
The existing 10-pin connector can handle low-current circuits:

**Suitable for:**
- Idle Air Controller (typically 2-3A)
- EBCS solenoid (typically 1-2A)
- Relay control signals (milliamps)
- Sensor power feeds

**Wire Capacity:** 20-22 AWG (confirm your specific connector rating)

### Suggested Connector Layout

**Individual Heavy-Gauge Circuits:**
1. ECU Main Power → 2-pin Weatherpack (14 AWG)
2. Fuel Pump Power → 2-pin Weatherpack (14 AWG)
3. Ignition Coil Power → 2-pin Weatherpack (12-14 AWG)
4. Cooling Fan Power → 2-pin Weatherpack (14-16 AWG)

**10-Pin Connector Bundle:**
- Pin 1-2: IAC Power & Ground
- Pin 3-4: EBCS Power & Ground
- Pin 5-6: Fuel Pump Relay Control & Ground
- Pin 7-8: Fan Relay Control & Ground
- Pin 9-10: Spare/Future Use

**Alternative: Combined Power Connector**
If you prefer a single multi-pin solution for power outputs, consider:
- **AMP Superseal 1.5 Series:** 6-pin, handles 13-16 AWG, 25A per circuit
- **Molex MX150 Series:** 6-8 pin, handles 14-18 AWG, 16A per circuit

## Integration Notes

This relay/fuse box serves as the central power distribution hub for the engine management system, addressing the power distribution requirements outlined in [wiring-harness-recommendations.md](wiring-harness-recommendations.md) Section 4.1.

The power distribution blocks provide a clean, centralized connection point for main power and ground, with the relay/fuse box handling the switching and protection. This architecture separates the heavy chassis wiring (which stays in the engine bay) from the relay outputs (which can be routed as needed).

The 5-pin relay configuration (with Pin 87a) provides flexibility for normally-closed circuits if needed, though most applications will use Pin 87 (normally-open) configuration.

## Related Documentation

- [AEM Mini Flying Lead Harness Pinout](AEM-Mini-Flying-Lead-Harness.md)
- [Wiring Harness Recommendations & Gap Analysis](wiring-harness-recommendations.md)
- [Main Project README](README.md)
- [Ignition System](ignition/README.md)
- [Fuel System](fuel-system/README.md)
