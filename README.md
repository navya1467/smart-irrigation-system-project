Smart Irrigation System Using 8051

1. Introduction

The Smart Irrigation System is an embedded-systems project designed to monitor soil moisture and automatically control a water pump. An 8051 microcontroller reads the soil-moisture input, calculates the approximate moisture percentage, and displays the readings and pump status on a 16×2 LCD.

This project is developed using software simulation in EWSIM. A potentiometer is used to simulate the soil-moisture sensor input.

2. Problem Statement

Manual irrigation may lead to water wastage when plants receive more water than required. This project demonstrates an automatic irrigation system that controls a pump according to the soil-moisture level.

3. Objectives

- To monitor soil moisture using a simulated sensor input.
- To calculate the approximate moisture percentage.
- To automatically control the water pump.
- To display ADC readings and pump status on an LCD.
- To understand 8051 microcontroller programming and interfacing.

4. Components and Software Required

Simulation Components

- AT89C51 microcontroller
- 16×2 LCD display
- ADC interface
- Potentiometer to simulate soil moisture
- Pump or relay driver
- LED indicator
- Connecting wires and power supply connections

Software

- Keil µVision 5
- EWSIM simulator
- Embedded C programming language

5. Block Diagram

Potentiometer (Simulated Soil-Moisture Sensor)
↓
ADC Interface
↓
AT89C51 Microcontroller
↓
├── 16×2 LCD Display
├── Pump Control Circuit
└── LED Indicator

6. Pin Connections

- ADC digital outputs D0–D7 → Port 1 (P1.0–P1.7)
- LCD data pins D0–D7 → Port 2 (P2.0–P2.7)
- LCD RS → P3.3
- LCD EN → P3.4
- LCD RW → GND
- Pump driver control → P3.5
- LED indicator → P2.0 (current configuration)

Note: The LCD uses all eight pins of Port 2, including P2.0. Sharing P2.0 with the LED may cause interference with LCD operation. The LED connection needs to be checked or moved to an unused output pin.

7. Working Principle

1. The potentiometer provides an adjustable input representing the soil-moisture level.
2. The ADC converts the analog input into an 8-bit digital value.
3. The 8051 microcontroller reads the ADC value through Port 1.
4. The program calculates the approximate moisture percentage.
5. The LCD displays the ADC value, moisture percentage, and pump status.
6. The pump is controlled according to the moisture level.

The moisture percentage is calculated using:

Moisture (%) = ((255 − ADC Value) × 100) / 255

Pump Control Logic

- Moisture below 40%: Pump ON.
- Moisture above 60%: Pump OFF.
- Moisture between 40% and 60%: The pump retains its previous state.

This method is called hysteresis control and helps prevent frequent switching when the moisture level fluctuates near a threshold.

8. Circuit Design

The ADC digital output pins are connected to Port 1 of the AT89C51. The LCD data pins are connected to Port 2, while the RS and EN control pins are connected to P3.3 and P3.4, respectively.

The pump driver is controlled through P3.5. The LED is intended to act as an indicator, but it is not functioning correctly in the current simulation.

All required ground and power connections must be properly connected.

In a real hardware implementation, a suitable driver circuit is required because an 8051 output pin cannot directly drive a water pump.

9. Software Implementation

The program is written in Embedded C using Keil µVision 5.

The software performs the following operations:

1. Initializes the LCD.
2. Reads the digital ADC value.
3. Calculates the moisture percentage.
4. Compares the percentage with the defined thresholds.
5. Controls the pump output.
6. Displays the readings and pump status on the LCD.
7. Repeats the process continuously.

10. Simulation Procedure

1. Open the project in Keil µVision 5.
2. Compile the Embedded C program.
3. Ensure that the program builds without errors.
4. Generate the HEX file.
5. Load the newly generated HEX file into the AT89C51 in EWSIM.
6. Run the simulation.
7. Adjust the potentiometer to change the simulated moisture level.
8. Observe the LCD readings and pump status.

11. Expected Results

Moisture Level| Expected Pump Status
30%| ON
50%, after starting at 30%| Remains ON
70%| OFF
50%, after starting at 70%| Remains OFF

The exact ADC readings depend on the potentiometer setting and the ADC model used in EWSIM.

The LED indicator is intended to provide a visual indication, but it is currently not functioning correctly in the simulation.

12. Advantages

- Demonstrates automatic irrigation control.
- Helps illustrate moisture-based water management.
- Displays simulated moisture readings and pump status.
- Provides practical experience with microcontroller programming.
- Can be demonstrated without physical irrigation hardware.

13. Applications

- Garden irrigation systems
- Greenhouse irrigation concepts
- Plant-watering automation prototypes
- Agricultural automation demonstrations
- Embedded-systems laboratory projects

14. Future Scope

- Use a calibrated soil-moisture sensor.
- Add a water-level sensor to prevent dry running.
- Introduce scheduled irrigation.
- Add wireless monitoring and control.
- Store moisture readings for analysis.
- Extend the system to control multiple irrigation zones.
- Correct and integrate the LED indicator.

15. Conclusion

The Smart Irrigation System using the 8051 microcontroller demonstrates automatic pump control based on a simulated soil-moisture input. It combines ADC interfacing, LCD interfacing, and Embedded C programming to display moisture readings and control the pump according to predefined thresholds.

The project provides practical experience in embedded-system development and simulation using Keil µVision 5 and EWSIM.

16. Limitations

1. The LED indicator is not working correctly in the current simulation.
2. A potentiometer is used to simulate the soil-moisture sensor.
3. The moisture percentage is an estimate and may require calibration for real-world applications.
4. The project has been tested using software simulation and requires hardware testing before practical implementation.
5. The LED and LCD may interfere with each other because both currently use P2.0. The connections should be checked before further testing.

---

Project Name: Smart Irrigation System Using 8051
Microcontroller: AT89C51
Programming Language: Embedded C
IDE: Keil µVision 5
Simulation Software: EWSIM
Project Type: Software Simulation
