# Ignition System Wiring - IGN-1A Coils

This guide covers the complete wiring installation for six IGN-1A inductive smart coils on a 7M-GTE engine, including power distribution, grounding strategy, and ECU signal connections.

**Wiring reference guide**: https://www.youtube.com/watch?v=mFzkFPengT8

## IGN-1A Coil Pinout Reference

Each IGN-1A coil has 5 pins:

* **Pin A** (Leftmost): Trigger signal from ECU (~5V logic)
* **Pin B**: Logic ground (ECU 0V reference)
* **Pin C**: Spark ground to cylinder head (coil discharge ground)
* **Pin D**: Engine block (main) ground
* **Pin E** (Rightmost): +12V power (ignition-switched)

## 7M-GTE Firing Order & Cylinder Pairing

Firing order: **1-5-3-6-2-4**

To optimize wiring and minimize voltage drop, pair cylinders that fire 180 degrees apart:

* **Pair 1**: Cylinders 1 & 6
* **Pair 2**: Cylinders 5 & 2
* **Pair 3**: Cylinders 3 & 4

This pairing strategy means you'll have **three separate pairs** of wires for power and ground distribution, rather than combining all six coils into a single feed.

## Wire Gauge Requirements

Based on the IGN-1A maximum primary current of ~19-20A per coil:

### Individual Coil Connections
* **19 AWG wire** for each coil's power (Pin E) and grounds (Pins C & D) - crimped directly into coil connector
* **20-22 AWG wire** for ECU trigger signals (Pin A) and logic ground (Pin B)

### Main Power & Ground Distribution
* **10 AWG wire** for main power feed to coil pairs
* **10 AWG wire** for main ground runs to engine block/head

## Wiring Strategy by Pin

### Pin A - ECU Trigger Signal (20-22 AWG)
* Individual wire from each coil to corresponding ECU ignition output
* Route: Coil → ECU (one wire per coil)
* No combining or splitting

### Pin B - Logic Ground (20-22 AWG)
* Individual wire from each coil to ECU sensor ground
* Route: Coil → ECU sensor ground
* Can be combined at ECU ground point

### Pin C - Spark Ground to Cylinder Head (19 AWG white w/black stripe)
* Connect to clean ground point on cylinder head
* Use cylinder pairing strategy:
  * Cylinders 1 & 6 → Join with butt connector → 16 AWG black → 10 AWG black to head ground
  * Cylinders 5 & 2 → Join with butt connector → 16 AWG black → 10 AWG black to head ground
  * Cylinders 3 & 4 → Join with butt connector → 16 AWG black → 10 AWG black to head ground

### Pin D - Engine Block Ground (19 AWG yellow w/purple stripe)
* Connect to engine block ground
* Use same pairing strategy as Pin C:
  * Cylinders 1 & 6 → Join with butt connector → 16 AWG black → 10 AWG black to block ground
  * Cylinders 5 & 2 → Join with butt connector → 16 AWG black → 10 AWG black to block ground
  * Cylinders 3 & 4 → Join with butt connector → 16 AWG black → 10 AWG black to block ground

### Pin E - +12V Power (19 AWG orange w/blue stripe)
* Connect to ignition-switched +12V source
* Use pairing strategy:
  * Cylinders 1 & 6 → Join with butt connector → 16 AWG red → 10 AWG red to fused power source
  * Cylinders 5 & 2 → Join with butt connector → 16 AWG red → 10 AWG red to fused power source
  * Cylinders 3 & 4 → Join with butt connector → 16 AWG red → 10 AWG red to fused power source
* **Install 30A inline fuse on each 10 AWG main power feed**

## Recommended Parts & Connectors

### Wire
* 16 AWG automotive primary wire (power & ground to coils)
* 10 AWG automotive primary wire (main runs)
* 20-22 AWG shielded wire (ECU signals, optional shielding for noise immunity)

### Connectors & Terminals
* Bare crimp butt connectors (properly sized for 16→10 AWG transitions)
* Ring terminals for ground points (sized for mounting bolts)
* Inline ATO/ATC fuse holders (30A rating)
* 30A ATO/ATC blade fuses (one per power pair)

### Installation Materials
* Heat shrink tubing (various sizes)
* Wire loom or split conduit for protection
* Cable ties
* Dielectric grease for connectors

## Installation Notes

1. **Crimping**: Use a proper ratcheting crimp tool to ensure reliable connections
2. **Heat Shrink**: Cover all splices and crimp connections with heat shrink tubing for weatherproofing
3. **Fusing**: Install 30A inline fuse on each of the three main power feeds (one per cylinder pair)
4. **Ground Points**: Clean ground mounting points on head and block to bare metal for optimal conductivity
5. **Routing**: Keep high-current power/ground wires separated from low-level sensor wires to minimize electromagnetic interference
6. **Slack**: Leave adequate slack in wiring to allow for engine movement
7. **Protection**: Use wire loom or split conduit to protect wiring from heat and abrasion

## Electrical Requirements Summary

* **Per coil maximum current**: ~19-20A
* **Per cylinder pair maximum**: ~40A (two coils)
* **Fuse rating**: 30A per cylinder pair (allows headroom while providing protection)
* **Voltage**: 12V ignition-switched (coil operates up to 17V maximum)
