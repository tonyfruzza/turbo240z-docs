# AEM Infinity-6 Pinout

| Infinity Pin | Hardware Ref. | Hardware Specification | Notes |
|---------------|---------------|-------------------------|--------|
| C1-1 | Lowside 4 | Lowside switch, 1.7A max, NO internal flyback diode. 12V pullup | See Setup Wizard Page "Output Function Assignment" for setup options. |
| C1-2 | Lowside 5 | Lowside switch, 6A max with internal flyback diode. Inductive load should NOT have full time power. 12V pullup | See Setup Wizard Page "Output Function Assignment" for setup options. |
| C1-3 | Lowside 6 | Lowside switch, 6A max with internal flyback diode. Inductive load should NOT have full time power. No pullup | See Setup Wizard Page "Output Function Assignment" for setup options. |
| C1-4 | Lowside 7 | Lowside switch, 6A max, NO internal flyback diode. No pullup | See Setup Wizard Page "Output Function Assignment" for setup options. |
| C1-5 | UEGO 1 Heat | Bosch UEGO controller | Lowside switch for UEGO heater control. Connect to pin 4 of Bosch UEGO sensor. NOTE that pin 3 of the sensor is heater (+) and must be powered by a fused/switched 12V supply. |
| C1-6 | UEGO 1 IA | | Trim Current signal. Connect to pin 2 of Bosch UEGO sensor. |
| C1-7 | UEGO 1 IP | | Pumping Current signal. Connect to pin 6 of Bosch UEGO sensor. |
| C1-8 | UEGO 1 UN | | Nernst Voltage signal. Connect to pin 1 of Bosch UEGO sensor. |
| C1-9 | UEGO 1 VM | | Virtual Ground signal. Connect to pin |
| C1-10 | Battery Perm Power | Dedicated power management CPU | Full time battery power. MUST be powered before the ignition switch input is triggered (See C1-48). |
| C1-11 | Coil 4 | 25 mA max source current | 0–5V Falling edge fire. DO NOT connect directly to coil primary. Must use an ignitor OR CDI that accepts a FALLING edge fire signal. |
| C1-12 | Coil 3 | 25 mA max source current | 0–5V Falling edge fire. DO NOT connect directly to coil primary. Must use an ignitor OR CDI that accepts a FALLING edge fire signal. |
| C1-13 | Coil 2 | 25 mA max source current | 0–5V Falling edge fire. DO NOT connect directly to coil primary. Must use an ignitor OR CDI that accepts a FALLING edge fire signal. |
| C1-14 | Coil 1 | 25 mA max source current | 0–5V Falling edge fire. DO NOT connect directly to coil primary. Must use an ignitor OR CDI that accepts a FALLING edge fire signal. |
| C1-15 | Coil 6 | 25 mA max source current | 0–5V Falling edge fire. DO NOT connect directly to coil primary. Must use an ignitor OR CDI that accepts a FALLING edge fire signal. |
| C1-16 | Coil 5 | 25 mA max source current | 0–5V Falling edge fire. DO NOT connect directly to coil primary. Must use an ignitor OR CDI that accepts a FALLING edge fire signal. |
| C1-17 | Crankshaft Position Sensor VR+ | Differential Variable Reluctance Zero Cross Detection | See Setup Wizard page Cam/Crank for options. |
| C1-18 | Crankshaft Position Sensor VR– | | See Setup Wizard page Cam/Crank for options. |
| C1-19 | Camshaft Position Sensor 1 VR– | Differential Variable Reluctance Zero Cross Detection | See Setup Wizard page Cam/Crank for options. |
| C1-20 | Camshaft Position Sensor 1 VR+ | | See Setup Wizard page Cam/Crank for options. |
| C1-21 | Lowside 2 | Lowside switch, 1.7A max, NO internal flyback diode. No pullup | See Setup Wizard Page "Output Function Assignment" for setup options. |
| C1-22 | Lowside 3 | Lowside switch, 6A max with internal flyback diode. Inductive load should NOT have full time power. No pullup | See Setup Wizard Page "Output Function Assignment" for setup options. |
| C1-23 | Analog Sensor Ground | Dedicated analog ground | Analog 0–5V sensor ground |
| C1-24 | Analog Sensor Ground | Dedicated analog ground | Analog 0–5V sensor ground |
| C1-25 | Crankshaft Position Sensor Hall | 10K pullup to 12V. Will work with ground or floating switches. | See Setup Wizard page Cam/Crank for options. |
| C1-26 | Camshaft Position Sensor 1 Hall | 10K pullup to 12V. Will work with ground or floating switches. | See Setup Wizard page Cam/Crank for options. |
| C1-27 | Digital 2 | 10K pullup to 12V. Will work with ground or floating switches. | See Setup Wizard page Cam/Crank for options. |
| C1-28 | Dig3 [Hz] / Dig3 Duty | 10K pullup to 12V. Will work with ground or floating switches. | See Setup Wizard page "Input Function Assignments" for setup options. |
| C1-29 | Dig4 [Hz] / Dig4 Duty | 10K pullup to 12V. Will work with ground or floating switches. | See Setup Wizard page "Input Function Assignments" for setup options. |
| C1-29 | RS232 Rx | RS232 Line Driver/Receiver | Future expansion |
| C1-30 | Digital 5 | 10K pullup to 12V. Will work with ground or floating switches. | See Setup Wizard page "Input Function Assignments" for setup options. |
| C1-30 | RS232 Tx | RS232 Line Driver/Receiver | Future expansion |
| C1-31 | Dig6 [Hz] / Dig6 Duty | 10K pullup to 12V. Will work with ground or floating switches. | See Setup Wizard page "Input Function Assignments" for setup options. |
| C1-32 | Digital 7 | 10K pullup to 12V. Will work with ground or floating switches. | See Setup Wizard page "Input Function Assignments" for setup options. |
| C1-33 | Battery Ground | Battery Ground | Connect directly to battery ground |
| C1-34 | CANL A | Dedicated High Speed CAN Transceiver | Recommend twisted pair (one twist per 2") with terminating resistor. Contact AEM for additional information. |
| C1-35 | CANH A | Dedicated High Speed CAN Transceiver | Recommend twisted pair (one twist per 2") with terminating resistor. Contact AEM for additional information. |
| C1-36 | CANL B | Dedicated High Speed CAN Transceiver | Not used, reserved for future expansion. |
| C1-37 | CANH B | Dedicated High Speed CAN Transceiver | Not used, reserved for future expansion. |
| C1-38 | Analog Temp 1 | 12 bit A/D, 2.49K pullup to 5V | Default Coolant Temperature Input |
| C1-39 | Analog Temp 2 | 12 bit A/D, 2.49K pullup to 5V | Default Air Temperature Input |
| C1-40 | Analog Temp 3 | 12 bit A/D, 2.49K pullup to 5V | Default Oil Temperature Input. See Setup Wizard page "Input Function Assignments" for setup options. |
| C1-41 | Lowside 0 | Lowside switch, 1.7A max, NO internal flyback diode. No pullup | See Setup Wizard Page "Output Function Assignment" for setup options. |
| C1-42 | Lowside 1 | Lowside switch, 6A max with internal flyback diode. Inductive load should NOT have full time power. No pullup | See Setup Wizard Page "Output Function Assignment" for setup options. |
| C1-43 | Battery Ground | Battery Ground | Connect directly to battery ground |
| C1-44 | Knock Sensor 1 | Dedicated knock signal processor | See Setup Wizard page Knock Setup for options. |
| C1-45 | Knock Sensor 2 | Dedicated knock signal processor | See Setup Wizard page Knock Setup for options. |
| C1-46 | Battery Ground | Battery Ground | Connect directly to battery ground |
| C1-47 | EFI Main Relay Switched Ground Output | 0.7A max ground sink for external relay control | Will activate at key on and at key off according to the configuration settings. |
| C1-48 | Ignition Switch | 10K pulldown | Full time battery power must be available at C1-10 before this input is triggered. |
| C1-49 | +5V Sensor Power | Regulated, fused +5V supply for sensor power | Analog sensor power |
| C1-50 | +5V Sensor Power | Regulated, fused +5V supply for sensor power | Analog sensor power |
| C1-51 | Analog 7 | 12 bit A/D, 100K pullup to 5V | Default primary Throttle Position sensor input. 0–5V analog signal. Use +5V Out pins as power supply and Sensor Ground pins as the low reference. Do not connect signals referenced to +12V as this can permanently damage the ECU. See Setup Wizard Set Throttle Range page for automatic min/max calibration. Monitor the Throttle [%] channel. Also DB1_TPSA [%] for DBW applications. |
| C1-52 | Analog 8 | 12 bit A/D, 100K pullup to 5V | Default Manifold Pressure Sensor input. 0–5V analog signal. Use +5V Out pins as power supply and Sensor Ground pins as the low reference. Do not connect signals referenced to +12V as this can permanently damage the ECU. |
| C1-53 | Analog 9 | 12 bit A/D, 100K pullup to 5V | Default Fuel Pressure Sensor Input. 0–5V analog signal. Use +5V Out pins as power supply and Sensor Ground pins as the low reference. Do not connect signals referenced to +12V as this can permanently damage the ECU. |
| C1-54 | VR+ 2 | Differential Variable Reluctance Zero Cross Detection | See Setup Wizard page "Input Function Assignments" for setup options. |
| C1-55 | VR- 2 | — | — |
| C1-56 | VR- 3 | Differential Variable Reluctance Zero Cross Detection | See Setup Wizard page "Input Function Assignments" for setup options. |
| C1-57 | VR+ 3 | — | — |
| C1-58 | Highside 0 | 2.6A max, High Side Solid State Relay | See Setup Wizard Page "Output Function Assignment" for setup options. |
| C1-59 | Stepper 1B | Automotive, Programmable Stepper Driver, up to 28V and ±1.4A | Be sure that each internal coil of the stepper motor are properly paired with the 1A/1B and 2A/2B ECU outputs. Supports Bi-Polar stepper motors only. |
| C1-60 | Stepper 2B | Automotive, Programmable Stepper Driver, up to 28V and ±1.4A | Be sure that each internal coil of the stepper motor are properly paired with the 1A/1B and 2A/2B ECU outputs. Supports Bi-Polar stepper motors only. |
| C1-61 | DBW1 Motor - | 5.0A max Throttle Control H-bridge Drive | +12V to close |
| C1-62 | DBW1 Motor + | 5.0A max Throttle Control H-bridge Drive | +12V to open |
| C1-63 | Main Relay Power Input | 12 volt power from relay | 12 volt power from relay. Relay must be controlled by +12V Relay Control signal, pin C1-47 above. |
| C1-64 | Injector 6 | Saturated (P/N 30-7108) or peak and hold, 3A max continuous (P/N 30-7106) | Injector 6 |
| C1-65 | Injector 5 | Saturated (P/N 30-7108) or peak and hold, 3A max continuous (P/N 30-7106) | Injector 5 |
| C1-66 | Injector 4 | Saturated (P/N 30-7108) or peak and hold, 3A max continuous (P/N 30-7106) | Injector 4 |
| C1-67 | Battery Ground | Battery Ground | Connect directly to battery ground |
| C1-68 | Main Relay Power Input | 12 volt power from relay | 12 volt power from relay. Relay must be controlled by +12V Relay Control signal, pin C1-47 above. |
| C1-69 | Analog 19 | 12 bit A/D, 100K pullup to 5V | 0–5V analog signal. Use +5V Out pins as power supply and Sensor Ground. |
| C1-70 | Analog 18 | 12 bit A/D, 100K pullup to 5V | 0–5V analog signal. Use +5V Out pins as power supply and Sensor Ground pins as the low reference. Do not connect signals referenced to +12V as this can permanently damage the ECU. See Setup Wizard page "Input Function Assignments" for setup options. |
| C1-71 | Analog 16 | 12 bit A/D, 100K pullup to 5V | 0–5V analog signal. Use +5V Out pins as power supply and Sensor Ground pins as the low reference. Do not connect signals referenced to +12V as this can permanently damage the ECU. See Setup Wizard page "Input Function Assignments" for setup options. |
| C1-72 | Flash Enable | 10K pulldown | Not usually needed for automatic firmware updates through Infinity Tuner. If connection errors occur during update, connect 12 volts to this pin before proceeding with upgrade. Disconnect the 12 volts signal after the update. |
| C1-73 | Analog 13 | 12 bit A/D, 100K pullup to 5V | Default Oil Pressure Sensor input. 0–5V analog signal. Use +5V Out pins as power supply and Sensor Ground pins as the low reference. Do not connect signals referenced to +12V as this can permanently damage the ECU. |
| C1-74 | Analog 11 | 12 bit A/D, 100K pullup to 5V | 0–5V analog signal. Use +5V Out pins as power supply and Sensor Ground pins as the low reference. Do not connect signals referenced to +12V as this can permanently damage the ECU. See Setup Wizard page "Input Function Assignments" for setup options. |
| C1-75 | Analog 10 | 12 bit A/D, 100K pullup to 5V | 0–5V analog signal. Use +5V Out pins as power supply and Sensor Ground pins as the low reference. pins as the low reference. Do not connect signals referenced to +12V as this can permanently damage the ECU. See Setup Wizard page "Input Function Assignments" for setup options. |
| C1-76 | Injector 3 | Saturated (P/N 30-7108) or peak and hold, 3A max continuous (P/N 30-7106) | Injector 3 |
| C1-77 | Injector 2 | Saturated (P/N 30-7108) or peak and hold, 3A max continuous (P/N 30-7106) | Injector 2 |
| C1-78 | Injector 1 | Saturated (P/N 30-7108) or peak and hold, 3A max continuous (P/N 30-7106) | Injector 1 |
| C1-79 | Stepper 2A | Automotive, Programmable Stepper Driver, up to 28V and ±1.4A | Be sure that each internal coil of the stepper motor are properly paired with the 1A/1B and 2A/2B ECU outputs. Supports Bi-Polar stepper motors only. |
| C1-80 | Stepper 1A | Automotive, Programmable Stepper Driver, up to 28V and ±1.4A | Be sure that each internal coil of the stepper motor are properly paired with the 1A/1B and 2A/2B ECU outputs. Supports Bi-Polar stepper motors only. |
