# 7M-GTE Powered Datsun 240Z Engine Wiring

Engine management system is by AEM Infinity 6 (30-7106) including 30-3706 universal wiring kit with a 5 wire wide band UEGO sensor AVM-30-2002

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

[Driftmotion Universal Remote Mount ISC](https://www.driftmotion.com/Driftmotion-Universal-Remote-Mount-ISC-p/dm3328.htm)

Specs
* Uses a Supra check valve
* Ford type 2-wire idle speed control solenoid
* Attached to intake plenum over a AN-10 male fitting
* Uses Viton o-ring
* A PWM output of 2 amps or higher is best, the minimum would be about 1.5 amps
* Recommended PWM frequency is between 300hz and 400hz.

### Cam Position Sensor

[Driftmotion V2 Digital CPS](https://www.driftmotion.com/Driftmotion-Digital-CPS-Upgrade-for-7M-GTE-p/dm3528.htm)

* Dual hall effect sensors in stainless housings
* 150°C temperature rating
* Air gap: 0.020"–0.045" (approximately 0.025")
* Requires ignition-switched 12v power (not 5v)
* Built-in pull-up resistors (disable pull-up in ECU software)
* Signal output: ~0.5v low, ~11.5v high
* Pin 1 (NE): Crank sensor
* Pin 2 (G1): Cam sensor
* Pin 3 (G): Ground
* Pin 4 (G2): 12v ignition-switched power

**Note:** AEM Infinity requires cam and crank wires to be moved in the jumper harness for hall sensor inputs.

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

AEM Electronics MAP Sensor Kits 30-2130-50
* Rated for up to 3.5 Bar (0-50PSI)
* Voltage range 0.50v - 4.50v
* Pin A: Ground Input
* Pin B: +5.0v Input
* Pin C: Signal Output


### Electronic Boost Control Solenoid Valve

* Pulse width modulation (PWM) driven.
* Specs: 5.4W, 25.4ohm coil, operates from vacuum to 120 PSI.
* Uusing a 3-port solenoid.

### Throttle Position Sensor

Ford 3-wire rotary potentiometer from 1998-2002 E-Series 5.4L V8 (Motorcraft DY-967)

* Type: Linear sweep potentiometer, 4–6 kΩ total resistance
* Signal range: ~0.6–0.9v at closed throttle → 4.3–4.7v at WOT
* Requires 5v reference supply
* Pin A (left): Sensor ground → ECU sensor ground
* Pin B (middle): Signal output → ECU analog TPS input
* Pin C (right): 5v reference → ECU 5v sensor supply

