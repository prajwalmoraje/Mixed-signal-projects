
# 4-bit R-2R DAC using Two-Stage CMOS Op-Amp

This project demonstrates the design and simulation of a 4-bit R-2R Digital-to-Analog Converter (DAC) realized using a two-stage CMOS operational amplifier. The implementation uses Cadence Virtuoso on the 180 nm CMOS process (gpdk180).

---

## Project Summary  
- **Title:** Design & Implementation of a 4-bit R-2R DAC using a Two-Stage Op-Amp  
- **Tool Used:** Cadence Virtuoso  
- **Technology:** 180 nm CMOS (gpdk180)  
- **Objective:** Develop a compact, low-power, high-gain mixed-signal circuit that converts digital bits into proportional analog voltages.  
- **Domain:** Analog / Mixed-Signal VLSI Design

---

## Introduction  
An R-2R ladder DAC is a classic architecture that uses only two resistor values—R and 2R—in a repeated ladder structure. Each input bit switches the corresponding resistor leg between the reference voltage (Vref) and ground (GND). The resulting current is fed into a two-stage op-amp which converts it into a voltage and provides the necessary gain and accuracy.

### Two-Stage Op-Amp Structure  
1. **Input Stage (Differential Amplifier):** Amplifies the input difference and rejects common-mode signals.  
2. **Output Stage (Common-Source Amplifier):** Provides high gain and large output swing.  
Together, they deliver a stable and linear analog output suitable for mixed-signal applications.

---

## Operation Principle  
The DAC works based on voltage division and current summation through the R-2R ladder. The equation for output is:

\[
V_{\text{out}} = V_{\text{ref}} \times \left(\frac{b_3}{2} + \frac{b_2}{4} + \frac{b_1}{8} + \frac{b_0}{16} \right)
\]

where \(b_3\)–\(b_0\) are the digital input bits (MSB to LSB). The op-amp translates the summed current into a proportional analog voltage.

---

## Design Methodology  
### 1. Flow in Cadence Virtuoso  
- Technology: gpdk180 (180 nm CMOS)  
- Create schematic using analogLib / gpdk180 components  
- Size transistors for desired gain, bandwidth and output swing  
- Perform layout and post-layout simulation (including parasitics)  
- Validate design via transient and AC analyses  
### 2. Two-Stage Op-Amp Design  
The op-amp consists of:  
- Differential input stage for high common-mode rejection ratio (CMRR) and initial gain  
- Common-source output stage for high gain and drive capability  
- Compensation via Miller capacitor to ensure phase margi
