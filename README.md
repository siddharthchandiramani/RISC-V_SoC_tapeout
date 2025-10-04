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

## 2. BabySoC: A Simplified SoC Model
**BabySoC** is a minimal SoC design used for learning and experimentation. Its simplified structure allows beginners to:

- Understand the key components of a SoC without the complexity of a full-scale design.
- Learn how data flows between CPU, memory, and peripherals.
- Practice functional modeling and simulation before moving to more advanced RTL or physical design stages.

## 3. Importance of Functional Modeling
Before designing the actual hardware:

- **Functional modeling** helps validate system behavior at a high level.
- It ensures that the SoC architecture meets the design requirements.
- Helps identify design flaws early, saving time and effort in later RTL and physical design stages.

## 4. Waveform Simulation
The BabySoC design has been simulated, and the following key signals were observed:

- `clk` – System clock
- `reset` – Reset signal
- `RV_TO_DAC[9:0]` – Data output to DAC
- `OUT` – System output  

Below is a snapshot of the simulation waveform:

![Waveform](Week2_Waveform.png)

## Reference
- [Fundamentals of SoC Design Notes](https://github.com/hemanthkumardm/SFAL-VSD-SoCJourney/tree/main/11.%20Fundamentals%20of%20SoC%20Design)

---

**Deliverable:** A concise understanding of SoC fundamentals and the role of BabySoC in learning SoC concepts.

