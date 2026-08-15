# 6T SRAM Cell Design & Write Performance Analysis

## Overview

Designed and simulated a conventional 6T CMOS SRAM cell using LTspice and 180-nm CMOS transistor models. The project focuses on transistor-level memory-cell design, data retention, write operations, and timing characterization.

## Objectives

- Design a 6T CMOS SRAM cell.
- Understand cross-coupled inverter based data storage.
- Verify HOLD operation.
- Verify WRITE-0 and WRITE-1 operations.
- Perform transient SPICE analysis.
- Measure SRAM write delay.
- Study the effect of transistor sizing on cell operation.

## SRAM Architecture

The SRAM cell consists of:

- 2 PMOS pull-up transistors
- 2 NMOS pull-down transistors
- 2 NMOS access transistors

The two CMOS inverters are cross-coupled to form the bistable storage element.

## Technology and Simulation Parameters

| Parameter | Value |
|---|---:|
| Technology | 180 nm CMOS |
| Supply Voltage | 1.8 V |
| Temperature | 27 °C |
| Simulator | LTspice |
| Device Model | 180-nm BSIM |
| Initial transistor length | 180 nm |

## Operations

### HOLD

The word line is disabled, isolating the storage cell from the bit lines. The cross-coupled inverters maintain the stored logic state.

### WRITE-0

The bit lines are driven such that:

BL = 0 V

BLB = 1.8 V

WL = 1.8 V

The cell transitions to:

Q = 0

QB = 1

### WRITE-1

The complementary bit-line condition is applied:

BL = 1.8 V

BLB = 0 V

WL = 1.8 V

The cell transitions to:

Q = 1

QB = 0

## Write Delay Measurement

Write delay was measured between the 50% VDD crossing of the word line and the 50% VDD crossing of the storage node.

For VDD = 1.8 V:

50% VDD = 0.9 V

Measured WRITE-0 delay:

≈ 0.305 ns

## Key Learnings

- CMOS SRAM architecture
- Cross-coupled inverter based memory
- NMOS/PMOS transistor operation
- Word-line and bit-line control
- SRAM write operation
- SPICE transient analysis
- Propagation and write-delay measurement
- Transistor sizing and design trade-offs

## Tools

- LTspice
- SPICE
- 180-nm CMOS BSIM model

## Project Structure

```text
6T-SRAM-Design-LTspice/
│
├── LTspice/
│   └── 6T_SRAM.asc
│
├── Results/
│   ├── hold_operation.png
│   ├── write_0.png
│   ├── write_1.png
│   └── timing_results.txt
│
└── README.md
