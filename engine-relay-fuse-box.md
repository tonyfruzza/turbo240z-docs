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

**Product:** True Mods 12V DC Auto Waterproof Fuse 5-Pin Relay Box  
**Description:** 6 ATC/ATO Fusible Holder with 6 Bosch Style Universal Relay Block Holder  
**Link:** [Amazon - B08KHVHLL5](https://www.amazon.com/dp/B08KHVHLL5)

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

### Relay 5: Idle Air Controller & EBCS Power
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

## Integration Notes

This relay/fuse box serves as the central power distribution hub for the engine management system, addressing the power distribution requirements outlined in [wiring-harness-recommendations.md](wiring-harness-recommendations.md) Section 4.1.

The 5-pin relay configuration (with Pin 87a) provides flexibility for normally-closed circuits if needed, though most applications will use Pin 87 (normally-open) configuration.

## Related Documentation

- [AEM Mini Flying Lead Harness Pinout](AEM-Mini-Flying-Lead-Harness.md)
- [Wiring Harness Recommendations & Gap Analysis](wiring-harness-recommendations.md)
- [Main Project README](README.md)
- [Ignition System](ignition/README.md)
- [Fuel System](fuel-system/README.md)
