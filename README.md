# Good PSRR Low Dropout (LDO) Voltage Regulator in 0.33µm CMOS Technology

## Problem Statement
Design and Layout of a low dropout regulator (LDO) with an input voltage of 3.3V, an
output voltage of 3V, and a load current capacity of 50mA. The LDO should have a loop
gain of more than 60dB and phase margin above 45 degrees.


## Project Overview

This repository contains the design and layout for a high PSRR Low Dropout (LDO) voltage regulator implemented in UMC 0.33µm CMOS technology[cite: 5]. The LDO is designed to deliver a stable 3V output from a 3.3V supply, making it ideal for memory systems and other noise-sensitive applications[cite: 4, 6].The complete design was simulated in Cadence Virtuoso [cite: 5] and has successfully passed both DRC and LVS verification, confirming its manufacturability[cite: 8].

## Performance Summary

| Property                  | Result        |
| ------------------------- | ------------- |
| Technology                | UMC 0.33µm CMOS [cite: 35] |
| Input Voltage             |3.3V          | [cite: 141]
| Output Voltage            | 3V            | [cite: 141]
| Dropout Voltage           | 300mV         | [cite: 141]
| Load Current              | 50mA          | [cite: 141]
| Reference Voltage         |1.2V          | [cite: 141]
| Loop Gain                 | 65.58dB       | [cite: 141]
| Phase Margin              |53.78 deg     | [cite: 141]
| Unity Gain Bandwidth (UGB)| 2.78 MHz      | [cite: 141]

## Circuit Architecture

The LDO consists of four fundamental blocks that work together in a negative feedback loop to ensure a stable output voltage:

1.  **Bandgap Reference (BGR)**: This circuit generates a stable 1.2V reference voltage that is highly insensitive to changes in power supply and temperature[cite: 38, 141]. It achieves this by combining PTAT (Proportional to Absolute Temperature) and CTAT (Complementary to Absolute Temperature) voltage components[cite: 44].
2.  **Error Amplifier**: A two-stage differential amplifier compares the reference voltage with a scaled version of the output voltage from the feedback network[cite: 23, 34, 96].It then produces an error signal that drives the gate of the pass transistor[cite: 17].
3.  **Pass Device (PassFET)**: A PMOS transistor is used as the pass element to control the current flowing from the input to the output[cite: 119, 120]. The PMOS is controlled by the error amplifier to dynamically adjust its resistance and regulate the output voltage[cite: 115].
4.  **Feedback Network**: A resistive divider samples the output voltage and feeds a scaled portion back to the non-inverting input of the error amplifier, closing the feedback loop[cite: 14, 16].

## Layout and Verification

* **Layout Tool**: Cadence Virtuoso Layout Suite.
* **Layout Area**: The total layout size is 53,648.37 units square.
* **Layout Techniques**: The physical design uses analog layout methods such as common-centroid and interdigitated structures to improve device matching and minimize offset in the error amplifier and bias circuits[cite: 148].
* **Verification**: The design has successfully passed Design Rule Check (DRC) and Layout Versus Schematic (LVS) verification with no violations, ensuring its functional accuracy and readiness for manufacturing[cite: 8, 135].

## Authors

This project was designed and authored by:
* Akash Biradar 
* Rohit Mandalollu 
* Krishna Sebani
* Raju Barker

From the Department of Electronics and Communication at KLE Technological University, Hubballi.
