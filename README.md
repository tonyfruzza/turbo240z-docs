# 7M-GTE Powered Datsun 240Z Wiring

Engine management system is by AEM Infinity 30-7106 including 30-3706 with a 5 wire wide band UEGO sensor AVM-30-2002

## Electronic Engine Components

### Wideband UEGO Sensors

AEM Electronics Wideband UEGO Sensors 30-2001

* Response time of less than 100 milliseconds
* Measure from 11:1 AFR to atmospheric air
* Latest Nernst cell/oxygen pump hybrid technology
* Planar-configured zirconium dioxide sensor
* Integrated heater element warms up in less than 20 seconds
* PTFE insulators withstand temperatures of up to 1,400 degrees Fahrenheit (800 degrees Celsius)

### Idle Air Controller

Uses a Supra check valve for boosted engines, and a simple and reliable Ford type 2-wire idle speed control solenoid. The hose fitting is an AN-10 male. 3 Viton o-rings are included, no additional gaskets are needed. A PWM output of 2 amps or higher is best, the minimum would be about 1.5 amps. The recommended PWM frequency is between 300hz and 400hz.

https://www.driftmotion.com/Driftmotion-Universal-Remote-Mount-ISC-p/dm3328.htm


### Cam Position Sensor

Driftmotion V2 Digital CPS Upgrade for 7M-GTE!

Retrofited existing CPS with two digital hall effect sensors. These new sensors are fully encapsulated in stainless housings which are resistant to oil, heat, vibration. The Digital CPS has a factory Toyota CPS connector and plugs right into the original CPS connector on your engine harness. All you have to do to the wiring is change the 2nd cam sensor wire (G2) at the ECU connectror to be ignition 12v power for the new sensors. You will also need to set the air-gap on the new sensors to approximately .025". It may need a little adjustment, we found the range that works well is .020" to .045". The sensors are omni-directional, so only the gap is important, not the way the sensor is rotated. DO NOT twist the sensor wires when they are installed in the CPS, only turn the nuts.

Our V2 Digital CPS sensors have a 150c temp rating, they have a hex on the back of the sensor housing so it can be held with a wrench (rather than pliers), they use teflon jacketed wire, and they have stronger magnets so the adjustment range isn't as critical and can be done by eye. We set up a 7M Digital CPS in a CNC machine to spin it at high RPM, and it had a clean output signal all the way to 7000 rpm (the CNC machine wouldn't go any faster lol ), which would be equal to 14,000 rpm at the 7M crank!

*AEM Infinity uses different inputs for hall sensors, the cam and crank wires needs to be moved in the jumper harness.

These new CPS hall effect sensors have built in pull-up resistors, and they should be powered by ignition switched 12v. You need to disable pull-up resistors in the standalone software, or some standalones may require jumpers to be changed. If you were to use a 5v pull up resistor, it would drag down the 12v hall sensor output voltage, which could damage it, or at least work improperly. The hall sensor output voltages will be around 0.5V "low", and about 0.5v below the ignition voltage for "high" (eg 11.5V).

Pin layout:
1. NE - Crank Knurled Nut
2. G1 - Cam
3. G - Ground
4. G2 - 12v

### Knock Sensors

Bosch part number 0 261 231 006

* 1-20 kHz range
* Sensitivy at 5 kHz 26 ± 8 mV/g
* Impedance > 1 MΩ
* Maximum Vibration ≤ 800 m/s2
* -40 to 130°C Operating Temperature
* Integrated 'EV1' style connector
* Fits M8 bolt/stud

### MAP Sensor

AEM Electronics MAP Sensor Kits 30-2130-50, Bosch-Style, rated for up to 3.5 Bar

### Electronic Boost Control Solenoid Valve

* Precise Boost Control: Pulse width modulation (PWM) driven.
* Stable Boost Targeting: Ensures consistent boost levels with fast response and no fluctuations.
* High-Performance Specs: 5.4W, 25.4ohm coil, operates from vacuum to 120 PSI.
* Universal Fit: Works with most turbo and supercharged systems using a 3-port solenoid.

### Throttle Position Sensor

Ford 3-wire rotary potentiometer from 1998-2002 E-Series 5.4L V8 (Motorcraft DY-967)

* Type: Linear sweep potentiometer, 4–6 kΩ total resistance
* Signal range: ~0.6–0.9 V at closed throttle → 4.3–4.7 V at WOT
* Requires 5 V reference supply from ECU (not 12 V)
* Pin A (left): Sensor ground → ECU sensor ground
* Pin B (middle): Signal output → ECU analog TPS input
* Pin C (right): 5 V reference → ECU 5 V sensor supply

