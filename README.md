# RISC-V_SoC_tapeout  

# Fundamentals of System-on-Chip (SoC) Design
This document summarizes the foundational concepts of System-on-Chip (SoC) design, outlining the key components, the overall design flow, and the significance of simplified learning models like BabySoC. This understanding forms the theoretical basis for the hardware development undertaken in this repository.

## 1. What is a System-on-Chip (SoC)?
A **System-on-Chip (SoC)** is an integrated circuit (IC) that integrates nearly all components of a computer or other electronic system onto a single chip. It is essentially a complete electronic system packaged into a single silicon die.

Before the SoC paradigm, a complete electronic system required multiple chips mounted on a printed circuit board (PCB), with one chip for the CPU, another for memory control, another for graphics, and so on. The SoC revolution consolidated these functionalities, offering several critical advantages:

- **Reduced Power Consumption:** Smaller distances for electrical signals to travel.
- **Improved Performance:** Faster communication between components via high-speed on-chip interconnects.
- **Lower Cost and Smaller Size:** Integrating everything onto one chip reduces manufacturing and assembly overhead.

SoCs are widely used in modern applications—from smartphones and smartwatches to automotive control units and high-performance computing—due to their **low power consumption**, **small size**, and **high integration**.

### Components of a Typical SoC
- **CPU (Central Processing Unit):** Executes instructions and controls the overall operation.
- **Memory:** Stores program instructions and data (e.g., RAM, ROM).
- **Peripherals:** Interfaces for communication with external devices (e.g., UART, GPIO, timers).
- **Interconnect/Bus:** Connects all components and enables data transfer between them.

## VSDBabySoC: A Compact RISC-V SoC

**VSDBabySoC** is a small but powerful **RISC-V-based System-on-Chip** designed for learning and experimentation.

### Key Features
- **RVMYTH Microprocessor:** The core processor that executes instructions and manages peripherals.  
- **8x PLL (Phase-Locked Loop):** Generates a stable clock for synchronized operation.  
- **10-bit DAC (Digital-to-Analog Converter):** Allows the SoC to interact with analog devices, such as televisions or mobile phones, producing audio or video output.

### Why VSDBabySoC is Useful
- Demonstrates how **digital and analog components** work together on a single chip.  
- Fully **open-source and well-documented**, making it ideal for **educational purposes**.  
- Fabricated using **Sky130 technology**, providing a practical, hands-on platform for understanding SoC design and integration.

### Learning Objectives
- Understand the **architecture and operation** of a small SoC.  
- Explore the **integration of multiple IP cores** in a compact design.  
- Learn how **digital signals interact with analog components** through the DAC.  

VSDBabySoC provides a practical example of a **fully functional, small-scale SoC** that helps students and researchers gain real-world experience in SoC design, testing, and experimentation.

# Part 2: VSDBabySoC Simulation and Waveform Analysis

This section documents the simulation workflow and the observations from the GTKWave waveforms for the VSDBabySoC project.

## Simulation Steps

1. **Create a working directory for Week 2**
   ```bash
   mkdir -p ~/week2_VSD
   cd ~/week2_VSD
   git clone https://github.com/manili/VSDBabySoC.git
   cd VSDBabySoC
   make pre_synth_sim
   gtkwave output/pre_synth_sim/pre_synth_sim.vcd

### pre_synth_sim Waveform
<img width="1638" height="340" alt="Screenshot from 2025-10-04 22-06-33" src="https://github.com/user-attachments/assets/bdaf2103-a742-4c50-973c-c4c914b860ea" />


