# Feedback Control of Brine Solution Concentration using Arduino

A closed-loop feedback control system for real-time regulation of brine concentration using Arduino, conductivity (TDS) sensing, and pump actuation.

This repository contains the Arduino control code, project documentation, and a detailed report describing the design, implementation, and validation of a brine concentration control system based on fundamental process control principles.

<pre>
PDC-Brine-Control/
│── PPM_Mixing_Controller.ino       # Arduino control code
│── README.md                       # Project documentation
└── group_4_pdc_project_report.pdf  # Detailed project report
</pre>

## Project Overview

The objective of this project is to maintain a desired salt (NaCl) concentration in a mixing tank by dynamically adjusting dilution and concentration streams. The system uses real-time conductivity measurements as feedback and actuates pumps accordingly to achieve and maintain the specified setpoint.

The control strategy demonstrates a practical implementation of feedback control concepts commonly used in chemical and process industries.

## System Description

- Two input streams:
  - Pure water (dilution source)
  - Concentrated NaCl solution (concentration source)
- One mixing tank equipped with:
  - Magnetic stirrer for homogeneity
  - TDS (conductivity) sensor for real-time concentration measurement
- Arduino microcontroller acting as the controller
- Peristaltic pumps driven via a motor driver module

## Control Strategy

- User-defined concentration setpoint in Arduino code
- Real-time measurement of brine concentration using a TDS sensor
- Error computed as the difference between setpoint and measured value
- On–off / deadband-based control logic:
  - If concentration < setpoint → add concentrated brine
  - If concentration > setpoint → add pure water
- Deadband implemented to prevent excessive switching and ensure stability

## Features

### Feedback Control Implementation

- Closed-loop control of brine concentration
- Real-time sensor feedback and actuation
- Stable convergence to setpoint under continuous mixing

### Hardware–Software Integration

- Arduino-based controller
- TDS sensor interfacing
- Dual pump actuation using motor driver
- LCD display for real-time monitoring (if enabled)

### Simulation and Validation

- Circuit and control logic simulated using Tinkercad
- Potentiometer used as a proxy for the TDS sensor during simulation
- Experimental validation with physical setup

## Notes and Limitations

- TDS sensor measurement range is limited to approximately 650 ppm
- Recommended operating concentration around 500 ppm for accuracy
- Actuation delay included to ensure adequate mixing
- Deadband used to reduce oscillations and pump wear

## Future Improvements

- Integrate level sensors for overflow protection
- Add temperature compensation for conductivity measurements
- Implement PID control for smoother dynamic response
- Add alarm indicators for sensor or system faults

## Reference

Detailed system design, circuit diagrams, experimental setup, and analysis are available in the accompanying project report:

**group_4_pdc_project_report.pdf**
