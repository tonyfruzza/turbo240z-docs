# TODO: AEM Infinity-6 Harness Wiring Additions

## Available Wiring Materials

### From Ignition Wiring Kit (Molex MX123 80-pin compatible terminals):
- **2x Shielded 4-wire bundles** containing:
  - White wire
  - Black wire
  - Red wire
  - Green wire
- **10x Unlabeled white wires** (general purpose)

All wires have proper Molex MX123 pin termination pre-installed.

---

## Priority 1: IGN-1A Coil Logic Ground Connections (CRITICAL)

### Why This Is Critical:
IGN-1A coils require a clean signal ground reference (Pin B) for proper trigger operation. Without this connection, coils will not fire reliably or at all.

### Task: Use 2x Shielded 4-Wire Bundles

**Bundle 1 - Coils 1, 2, 3:**
1. **White wire:**
   - MX123 connector end → Insert into **C1-23** or **C1-24** (Analog Sensor Ground)
   - Other end → IGN-1A Coil 1, Pin B (Logic Ground)

2. **Black wire:**
   - MX123 connector end → Insert into **C1-23** or **C1-24** (Analog Sensor Ground)
   - Other end → IGN-1A Coil 2, Pin B (Logic Ground)

3. **Red wire:**
   - MX123 connector end → Insert into **C1-23** or **C1-24** (Analog Sensor Ground)
   - Other end → IGN-1A Coil 3, Pin B (Logic Ground)

4. **Green wire (common return):**
   - Route alongside bundle for strain relief
   - Can be left disconnected or used as spare

**Bundle 2 - Coils 4, 5, 6:**
1. **White wire:**
   - MX123 connector end → Insert into **C1-23** or **C1-24** (Analog Sensor Ground)
   - Other end → IGN-1A Coil 4, Pin B (Logic Ground)

2. **Black wire:**
   - MX123 connector end → Insert into **C1-23** or **C1-24** (Analog Sensor Ground)
   - Other end → IGN-1A Coil 5, Pin B (Logic Ground)

3. **Red wire:**
   - MX123 connector end → Insert into **C1-23** or **C1-24** (Analog Sensor Ground)
   - Other end → IGN-1A Coil 6, Pin B (Logic Ground)

4. **Green wire (common return):**
   - Route alongside bundle for strain relief
   - Can be left disconnected or used as spare

### Installation Notes:
- The shield on these bundles provides EMI protection from ignition spark discharge
- Connect shield drain wire to ECU ground at connector end only (one end grounded)
- Do NOT ground shield at coil end (creates ground loop)
- Label each wire at coil end: "Coil 1 Logic GND", "Coil 2 Logic GND", etc.
- Route away from spark plug wires and high-voltage coil outputs

---

## Priority 2: Crankshaft & Camshaft Position Sensors (CRITICAL)

### Task: Use 2x White Wires from 10-Wire Pack

**Driftmotion V2 Digital CPS Pinout:**
- Pin 1 (NE): Crank sensor signal
- Pin 2 (G1): Cam sensor signal
- Pin 3 (G): Ground
- Pin 4 (G2): +12V ignition-switched power

**Wire 1 - Crankshaft Position Sensor:**
1. **White wire #1:**
   - MX123 connector end → Insert into **C1-25** (Crankshaft Position Sensor Hall)
   - Other end → Driftmotion CPS Pin 1 (NE - Crank signal)

**Wire 2 - Camshaft Position Sensor:**
2. **White wire #2:**
   - MX123 connector end → Insert into **C1-26** (Camshaft Position Sensor 1 Hall)
   - Other end → Driftmotion CPS Pin 2 (G1 - Cam signal)

### Additional Wiring Required (NOT from kit):
You will need to source these separately:
- **18 AWG red wire** for CPS Pin 4 (12V power) - From ignition switch or relay
- **18 AWG black wire** for CPS Pin 3 (Ground) - To battery/chassis ground

### Installation Notes:
- The Driftmotion CPS has built-in pull-up resistors
- **MUST DISABLE** internal ECU pull-ups in AEM software (Setup Wizard → Cam/Crank page)
- Keep wires away from ignition coils and spark plug wires
- Verify air gap: 0.020"–0.045" (approximately 0.025")
- Label wires: "CRANK SENSOR" and "CAM SENSOR"

---

## Priority 3: Knock Sensor Wiring (CRITICAL FOR TURBO)

### Task: Use 2x White Wires from 10-Wire Pack

**Bosch Knock Sensors (0 261 231 006) EV1 Connector Pinout:**
- Pin 1: Signal
- Pin 2: Ground

**Wire 3 - Knock Sensor 1:**
1. **White wire #3:**
   - MX123 connector end → Insert into **C1-44** (Knock Sensor 1)
   - Other end → Knock Sensor 1, EV1 Pin 1 (Signal)

**Wire 4 - Knock Sensor 2:**
2. **White wire #4:**
   - MX123 connector end → Insert into **C1-45** (Knock Sensor 2)
   - Other end → Knock Sensor 2, EV1 Pin 1 (Signal)

### Additional Wiring Required (NOT from kit):
You will need coaxial shielded cable instead of plain wire for best EMI rejection:
- **2x 20-22 AWG coaxial cable** (RG174 or similar) recommended over plain white wires
- If using white wires, add ferrite beads near sensors

**Ground Wires for Knock Sensors:**
- **2x 20 AWG black wire** for EV1 Pin 2 (Ground) - To engine block or chassis ground

### Installation Notes:
- Knock sensors are extremely sensitive to EMI
- Keep wires away from alternator, ignition coils, spark plug wires
- If using coax: ground shield at ECU end only (avoid ground loops)
- Torque sensors to block: 15-20 Nm (11-15 ft-lb) for M8 threads
- Label wires: "KNOCK 1 SIGNAL" and "KNOCK 2 SIGNAL"
- Configure in AEM Setup Wizard → Knock Setup (frequency window: 5-8 kHz)

---

## Priority 4: Idle Air Controller & Boost Control Solenoid

### Task: Use 2x White Wires from 10-Wire Pack

**Wire 5 - Idle Air Controller Control Signal:**
1. **White wire #5:**
   - MX123 connector end → Insert into **C1-1** (Lowside 4) or **C1-4** (Lowside 7)
   - Other end → Driftmotion ISC control wire (PWM input)

**Wire 6 - Electronic Boost Control Solenoid Control Signal:**
2. **White wire #6:**
   - MX123 connector end → Insert into **C1-21** (Lowside 2) - reassigned from "FAN"
   - Other end → EBCS control wire (PWM input)

### Additional Wiring Required (NOT from kit):
**For IAC:**
- **16 AWG red wire** from main relay output (with 5A inline fuse) to IAC +12V power

**For EBCS:**
- **18 AWG red wire** from main relay output (with 5A inline fuse) to EBCS +12V power

### Installation Notes:
- Both devices are PWM-controlled lowside switches
- IAC PWM frequency: 300-400 Hz (configure in AEM software)
- EBCS operates up to 120 PSI
- Label wires: "IAC CONTROL" and "BOOST CTRL"
- Configure in Setup Wizard → Output Function Assignment

---

## Priority 5: Optional Sensors (If Installing)

### Remaining White Wires Allocation:

**Wire 7 - Oil Pressure Sensor Signal:**
- MX123 connector end → Insert into **C1-73** (Analog 13 - Default Oil Pressure input)
- Other end → Oil pressure sensor signal pin (0-5V analog)

**Wire 8 - Oil Temperature Sensor Signal:**
- MX123 connector end → Insert into **C1-40** (Analog Temp 3 - Default Oil Temp input)
- Other end → Oil temperature sensor (thermistor type)

**Wire 9 - Fuel Pressure Sensor Signal:**
- MX123 connector end → Insert into **C1-53** (Analog 9 - Default Fuel Pressure input)
- Other end → Fuel pressure sensor signal pin (0-5V analog)

**Wire 10 - Flex Fuel Sensor Signal (Optional):**
- MX123 connector end → Insert into **C1-28** (Dig3 [Hz] - Frequency input)
- Other end → Continental/GM flex fuel sensor signal wire (50-150 Hz)

### Additional Wiring Required for Analog Sensors:
Each 0-5V analog sensor needs:
- +5V power from C1-49 or C1-50
- Ground from C1-23 or C1-24
- Signal wire (provided by white wire above)

**You will need to add:**
- **3x red 22 AWG** for +5V sensor power
- **3x black 22 AWG** for sensor ground

### Installation Notes:
- Use twisted pair or shielded cable for analog sensor signals if possible
- Keep sensor wiring away from high-current power wires
- Label all sensor wires clearly
- Configure in Setup Wizard → Input Function Assignments

---

## Priority 6: Cooling Fan Relay Control (Relocated)

### Task: Use Final White Wire OR Reuse Existing Harness Wire

The AEM flying lead harness originally assigned C1-21 to "FAN" but we've reassigned it to EBCS.

**Option A - Use Last White Wire:**
- **White wire #11 (if available):**
  - MX123 connector end → Insert into **C1-4** (Lowside 7)
  - Other end → Cooling fan relay control pin 85

**Option B - Modify Existing Harness:**
- The existing PNK 22 AWG wire labeled "FAN" goes to C1-21
- Remove it from C1-21 and move to C1-4
- No additional wire needed from kit

### Additional Wiring:
- Fan relay Pin 86: +12V battery
- Fan relay Pin 30: +12V battery (30A fused)
- Fan relay Pin 87: To dual cooling fans (parallel wired)

---

## Wire Labeling Scheme

Use heat shrink labels or label maker at BOTH ends of each wire:

| Wire # | Color | MX123 Pin | Function | Label Text |
|--------|-------|-----------|----------|------------|
| 1 | Shld-White | C1-23/24 | Coil 1 Logic GND | "COIL1-GND" |
| 2 | Shld-Black | C1-23/24 | Coil 2 Logic GND | "COIL2-GND" |
| 3 | Shld-Red | C1-23/24 | Coil 3 Logic GND | "COIL3-GND" |
| 4 | Shld-White | C1-23/24 | Coil 4 Logic GND | "COIL4-GND" |
| 5 | Shld-Black | C1-23/24 | Coil 5 Logic GND | "COIL5-GND" |
| 6 | Shld-Red | C1-23/24 | Coil 6 Logic GND | "COIL6-GND" |
| 7 | White | C1-25 | Crank Position Sensor | "CRANK-SIG" |
| 8 | White | C1-26 | Cam Position Sensor | "CAM-SIG" |
| 9 | White | C1-44 | Knock Sensor 1 | "KNOCK1-SIG" |
| 10 | White | C1-45 | Knock Sensor 2 | "KNOCK2-SIG" |
| 11 | White | C1-1 or C1-4 | IAC Control | "IAC-CTRL" |
| 12 | White | C1-21 | EBCS Control | "BOOST-CTRL" |
| 13 | White | C1-73 | Oil Pressure | "OIL-PRESS" |
| 14 | White | C1-40 | Oil Temperature | "OIL-TEMP" |
| 15 | White | C1-53 | Fuel Pressure | "FUEL-PRESS" |
| 16 | White | C1-28 | Flex Fuel Sensor | "FLEX-FUEL" |

---

## Wiring Order Recommendation

Complete in this order to get engine running ASAP:

1. **IGN-1A Logic Grounds** (Priority 1) - Engine won't run without proper coil trigger
2. **Crank/Cam Sensors** (Priority 2) - Engine won't start without position sensing
3. **Knock Sensors** (Priority 3) - Critical for turbo safety
4. **IAC & EBCS** (Priority 4) - For idle control and boost control
5. **Optional Sensors** (Priority 5) - For monitoring and safety
6. **Cooling Fan** (Priority 6) - Prevents overheating

---

## Post-Installation Checklist

After inserting all wires into MX123 connector:

- [ ] Verify each pin is fully seated (listen/feel for click)
- [ ] Gently tug each wire to confirm retention
- [ ] Check pin retention clip is engaged on connector
- [ ] Route wires with proper strain relief
- [ ] Secure bundles with zip ties every 6-8 inches
- [ ] Keep wire bundles away from:
  - [ ] Exhaust manifold and turbo
  - [ ] Moving parts (throttle linkage, belts)
  - [ ] Sharp edges
  - [ ] Ignition coil high-voltage outputs
- [ ] Apply heat shrink labels to both ends of each wire
- [ ] Document final pin assignments in `AEM-harness-custom-wiring.md`
- [ ] Take photos of completed connector for future reference

---

## AEM Infinity Software Configuration

After wiring is complete, configure in AEM Infinity Tuner:

### Setup Wizard → Cam/Crank:
- [ ] Sensor type: Hall Effect (both crank and cam)
- [ ] **DISABLE internal pull-ups** (Driftmotion CPS has built-in pull-ups)
- [ ] Trigger pattern: Select Toyota 7M-GTE pattern
- [ ] Verify trigger scope shows clean signals

### Setup Wizard → Knock Setup:
- [ ] Enable knock sensor 1 (C1-44)
- [ ] Enable knock sensor 2 (C1-45)
- [ ] Frequency window: 5-8 kHz
- [ ] Configure knock retard strategy

### Setup Wizard → Output Function Assignment:
- [ ] C1-1 or C1-4: Idle Air Controller (PWM 300-400 Hz)
- [ ] C1-21: Electronic Boost Control Solenoid
- [ ] C1-41: Fuel Pump Relay (already assigned)
- [ ] C1-2: Tachometer (already assigned)
- [ ] C1-4 or alternate: Cooling Fan Relay

### Setup Wizard → Input Function Assignments:
- [ ] C1-73: Oil Pressure Sensor (if installed)
- [ ] C1-40: Oil Temperature Sensor (if installed)
- [ ] C1-53: Fuel Pressure Sensor (if installed)
- [ ] C1-28: Flex Fuel Sensor (if installed)

### Ignition Configuration:
- [ ] Coil type: Smart coil (IGN-1A)
- [ ] Trigger type: Falling edge (0-5V)
- [ ] Dwell time: 3.0 ms nominal (IGN-1A spec)
- [ ] Max dwell: 9.0 ms
- [ ] Duty cycle limit: 40%
- [ ] Firing order: 1-5-3-6-2-4

---

## Additional Wire/Components Still Needed (Not in Kit)

Purchase separately:

1. **CPS Power & Ground:**
   - 18 AWG red wire (12V switched)
   - 18 AWG black wire (ground)

2. **Knock Sensor Grounds:**
   - 2x 20 AWG black wire
   - Optional: 2x RG174 coaxial cable (replaces white wires for better EMI rejection)

3. **IAC & EBCS Power:**
   - 16 AWG red wire + 5A fuse holder (IAC)
   - 18 AWG red wire + 5A fuse holder (EBCS)

4. **Sensor Power Distribution:**
   - 3x 22 AWG red wire (+5V sensor power)
   - 3x 22 AWG black wire (sensor ground)

5. **Optional:**
   - Oil pressure sensor (AEM 30-2131-100 or similar)
   - Oil temperature sensor (AEM 30-2013 or similar)
   - Fuel pressure sensor (AEM 30-2131-50 or similar)
   - Flex fuel sensor (Continental/GM P/N 13577429)

---

## Documentation to Create After Completion

- [ ] Create `AEM-harness-custom-wiring.md` with final pin assignments
- [ ] Update `wiring-harness-recommendations.md` to mark tasks complete
- [ ] Create wiring diagram showing all custom additions
- [ ] Take photos and add to documentation
- [ ] Create backup documentation in case harness needs rebuild

---

**CRITICAL SAFETY REMINDER:**
- Always disconnect battery before working on harness
- Use proper crimping tools for any additional connections
- Test continuity of each wire before powering up
- Double-check all pin assignments before applying power
- Start with ignition off, key on - verify no shorts or excessive current draw
- First start should be with laptop connected to monitor all sensors
