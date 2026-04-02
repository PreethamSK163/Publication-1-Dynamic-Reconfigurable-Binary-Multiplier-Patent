# Patent - Dynamic Reconfigurable Binary Multiplier System and Method Thereof

> A high-speed, low-power, dynamically reconfigurable binary multiplier architecture using quadrant decomposition and adaptive row bypassing — synthesised and physically implemented on TSMC 180nm and 90nm CMOS technology nodes using Cadence EDA tools.

![Status](https://img.shields.io/badge/Status-Patent%20Published-brightgreen)
![Type](https://img.shields.io/badge/Type-Indian%20Patent-blue)
![Application](https://img.shields.io/badge/Application%20No-202541080342-orange)
![Published](https://img.shields.io/badge/Published-19%20September%202025-green)
![Tool](https://img.shields.io/badge/Tool-Cadence%20Genus-blue)
![Tool](https://img.shields.io/badge/Tool-Cadence%20Innovus-blue)
![PDK](https://img.shields.io/badge/PDK-TSMC%20180nm%20%2F%2090nm-orange)
![Language](https://img.shields.io/badge/Language-Verilog%20HDL-purple)

## 📄 Patent Details

| Field | Details |
|:---|:---|
| **Title** | Dynamic Reconfigurable Binary Multiplier System and Method Thereof |
| **Application Number** | 202541080342 |
| **Application Type** | Ordinary Application |
| **Date of Filing** | 25 August 2025 |
| **Publication Date (U/S 11A)** | 19 September 2025 |
| **Applicant** | Vellore Institute of Technology, Chennai |
| **Patent Attorney** | Khurana & Khurana, Advocates and IP Attorneys |
| **Field of Invention** | Computer Science / Digital VLSI Design |
| **Status** | Published — Under Examination |

## 👥 Inventors

| Name | Affiliation |
|:---|:---|
| Dr. S. Umadevi | Associate Professor (Senior), CNVD, School of Electronics Engineering, VIT Chennai |
| **Preetham SK** | School of Electrical Engineering, VIT Chennai |
| Nakul S | School of Electrical Engineering, VIT Chennai |
| Sumit Kumar | School of Electronics Engineering, VIT Chennai |


## 🔍 Overview

Binary multipliers are fundamental building blocks in Digital Signal Processors (DSPs), Arithmetic Logic Units (ALUs), cryptographic engines, and AI hardware accelerators. Conventional binary multiplier architectures are designed for a fixed operand bit-width, requiring separate hardware implementations for different input sizes. This leads to increased silicon area, redundant computation, and poor scalability in modern embedded and edge AI systems.

This invention presents a **generalized, dynamically reconfigurable binary multiplier** that automatically scales its internal structure for any input size of 16 bits or greater — eliminating the need for separate designs for different bit-widths. The architecture employs a **quadrant decomposition strategy** combined with an **adaptive row bypassing scheme** to simultaneously achieve scalability, power efficiency, and area optimisation.


## 🧠 Problem Addressed

Existing binary multiplier architectures exhibit three critical limitations:

**1. Fixed Bit-Width Design:** Conventional array and Wallace tree multipliers are designed for a specific operand size. Scaling to a different bit-width requires redesigning the entire multiplier from scratch — an inefficient and inflexible approach for modern variable-precision applications.

**2. Unnecessary Switching Activity:** Traditional multipliers compute partial products for all rows regardless of whether the corresponding multiplicand bits are zero. This results in unnecessary switching activity in the adder tree, directly increasing dynamic power consumption even when the computation is redundant.

**3. No Automatic Reconfiguration:** Existing architectures lack the ability to dynamically adapt their internal structure based on the operand size at runtime, preventing efficient operation across heterogeneous data widths in the same hardware instance.


## 💡 Proposed Architecture

The proposed architecture introduces three core innovations working together:

### 1. Quadrant Decomposition
Each 2^N × 2^N multiplication is decomposed into four independent sub-multiplications operating in parallel. For a 16×16 input (N=4), each operand is divided into upper (MSB) and lower (LSB) 8-bit segments — P, Q from operand A and R, S from operand B — generating four partial products P×R, Q×R, P×S, and Q×S simultaneously using 8×8 multiplier units as the fundamental building block.

### 2. Adaptive Row Bypassing Scheme
A dedicated bypassing logic unit monitors each operand segment for zero-valued bits. When a multiplicand segment is detected as zero, the corresponding partial product rows in the multiplier array are selectively disabled — suppressing unnecessary switching activity and gate transitions in the adder tree. This directly reduces dynamic power consumption without affecting computational accuracy.

### 3. Automatic Scalability
The architecture is parameterized by N and automatically reconfigures its structure and basic cells for any input size ≥ 16 bits without requiring architectural modification. For non-power-of-two input sizes, a zero-padding module ensures seamless compatibility by aligning inputs to the nearest supported width.

### 4. Dual Adder Configuration
Two adder configurations are supported — a **Ripple Carry Adder (RCA)** variant prioritising area and power efficiency, and a **Carry Lookahead Adder (CLA)** variant prioritising timing performance — allowing vendors to select the most suitable option based on application constraints.

## ⚙️ Implementation

| Parameter | Details |
|:---|:---|
| **HDL** | Verilog HDL |
| **Functional Verification** | Cadence® NC Launch |
| **Logic Synthesis** | Cadence® Genus 21.14 |
| **Physical Design** | Cadence® Innovus |
| **Technology Nodes** | TSMC 180nm and 90nm CMOS |
| **Operating Target** | 100 MHz |
| **Operand Size** | 16×16 bits (N=4), scalable to any 2^N × 2^N |
| **Architecture** | Quadrant decomposition + adaptive row bypassing |
| **Adder Variants** | RCA (area-optimised) and CLA (speed-optimised) |

## 📊 Key Results

Both RCA and CLA variants were synthesised and physically implemented across TSMC 180nm and 90nm technology nodes using Cadence Genus and Cadence Innovus. Results demonstrate:

- **Significant power reduction** through the row bypassing scheme — dynamic switching activity is reduced by selectively disabling partial product rows for zero-valued multiplicand bits
- **Area efficiency** — quadrant decomposition enables modular reuse of the 8×8 multiplier block across all four partial product computations
- **Technology scaling** — both variants scale consistently from 180nm to 90nm, with the 90nm implementation achieving notably lower power and area due to reduced parasitic capacitances
- **Timing performance** — CLA variant achieves lower critical path delay at the cost of increased area and power; RCA variant is optimal for power-sensitive applications
- **Fabrication-ready GDSII layout** generated through complete RTL-to-GDSII physical design flow


## 🎯 Applications

The proposed multiplier architecture is directly applicable in:

- **Digital Signal Processing (DSP)** — FFT, FIR/IIR filter banks, convolution engines
- **AI Hardware Accelerators** — Multiply-Accumulate (MAC) units in CNN inference engines
- **Edge Computing** — Variable-precision arithmetic for IoT and embedded ML
- **Cryptographic Hardware** — Modular multiplication in elliptic curve and RSA processors
- **Communication Systems** — Baseband signal processing for 5G/6G MIMO


## 🔗 Related Work

| Output | Details |
|:---|:---|
| **Patent** | Application No. 202541080342 — Published 19 September 2025 |
| **SCI Journal** | Manuscript under review in SCI-indexed journal |
| **Research Supervisor** | Dr. S. Umadevi, CNVD, VIT Chennai |
| **Research Centre** | Centre for Nanoelectronics and VLSI Design (CNVD), VIT Chennai |


## 🤝 Connect

| **Author** | Preetham SK |
|:---|:---|
| **Programme** | B.Tech. Electrical and Electronics Engineering, VIT Chennai |
| **LinkedIn** | [linkedin.com/in/preethamsk16](https://www.linkedin.com/in/preethamsk16) |
| **GitHub** | [github.com/PreethamSK163](https://github.com/PreethamSK163) |
| **Portfolio** | [preethamsk163.github.io](https://preethamsk163.github.io) |
| **Email** | preethamsk163@gmail.com |
