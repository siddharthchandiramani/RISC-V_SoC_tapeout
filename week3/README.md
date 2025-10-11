### GLS of BabySoC

## Week 3: Starting VSDBabySoC

### Steps to navigate and run Yosys

Open a terminal and follow these commands:

```bash
# Navigate to the VSDBabySoC repository
cd VSD/VSDBabySoC

# Launch Yosys to start synthesis or analysis
yosys

```

## VSDBabySoC Yosys Synthesis

### Steps performed in Yosys

```bash
yosys

# Read the main VSDBabySoC top module
read_verilog /home/siddharthac/VSD/VSDBabySoC/src/module/vsdbabysoc.v

# Read the RVMYTH processor module (with include directory for headers)
read_verilog -I /home/siddharthac/VSD/VSDBabySoC/src/include /home/siddharthac/VSD/VSDBabySoC/output/compiled_tlv/rvmyth.v

# Read the clock gating module
read_verilog -I /home/siddharthac/VSD/VSDBabySoC/src/include /home/siddharthac/VSD/VSDBabySoC/src/module/clk_gate.v

read_liberty -lib /home/siddharthac/VSD/VSDBabySoC/src/lib/avsdpll.lib
read_liberty -lib /home/siddharthac/VSD/VSDBabySoC/src/lib/avsddac.lib
read_liberty -lib /home/siddharthac/VSD/VSDBabySoC/src/lib/sky130_fd_sc_hd__tt_025C_1v80.lib

```
### Run Synthesis

```bash
synth -top vsdbabysoc
```
<img width="409" height="854" alt="Screenshot from 2025-10-11 09-11-02" src="https://github.com/user-attachments/assets/4d97ec61-5439-4892-98fe-1a8293da6709" />
<img width="409" height="973" alt="Screenshot from 2025-10-11 09-11-39" src="https://github.com/user-attachments/assets/3663b810-04e0-4237-b48a-475d75299b37" />
<img width="595" height="162" alt="Screenshot from 2025-10-11 09-12-05" src="https://github.com/user-attachments/assets/bb662f31-1734-47db-a1a4-582d2719def9" />

```bash
dfflibmap -liberty /home/siddharthac/VSD/VSDBabySoC/src/lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> opt
abc -liberty /home/siddharthac/VSD/VSDBabySoC/src/lib/sky130_fd_sc_hd__tt_025C_1v80.lib -script +strash;scorr;ifraig;retime;{D};strash;dch,-f;map,-M,1,{D}
```
<img width="717" height="450" alt="image" src="https://github.com/user-attachments/assets/aaee9b10-93a2-4a49-a625-1e672ef2922b" />

```bash
flatten
setundef -zero
clean -purge
rename -enumerate
```
<img width="868" height="172" alt="image" src="https://github.com/user-attachments/assets/1068b164-f1c8-4bdc-b688-c98b7d2aeac0" />

```bash
stat
```
<img width="401" height="976" alt="image" src="https://github.com/user-attachments/assets/9126a5ff-a476-488f-86c3-812247b66b8e" />
<img width="401" height="261" alt="image" src="https://github.com/user-attachments/assets/0b322816-7efe-4554-a4f3-efa688c43066" />

```bash
write_verilog -noattr /home/siddharthac/VSD/VSDBabySoC/output/post_synth_sim/vsdbabysoc.synth.v
```
<img width="401" height="149" alt="image" src="https://github.com/user-attachments/assets/3381df09-ad69-4a8d-b7e6-b0f23951c759" />

Exit yosys

### Post Synthesis Simulation and waveform

```bash
 iverilog -o /home/siddharthac/VSD/VSDBabySoC/output/post_synth_sim/post_synth_sim.out \
-DPOST_SYNTH_SIM -DFUNCTIONAL -DUNIT_DELAY=#1 -I /home/siddharthac/VSD/VSDBabySoC/src/include -I /home/siddharthac/VSD/VSDBabySoC/src/module /home/siddharthac/VSD/VSDBabySoC/src/module/testbench.v /home/siddharthac/VSD/VSDBabySoC/output/post_synth_sim/vsdbabysoc.synth.v

cd output/post_synth_sim/

./post_synth_sim.out

gtkwave post_synth_sim.vcd
```
## Waveform 
<img width="1632" height="183" alt="image" src="https://github.com/user-attachments/assets/6bab4eaa-caa7-4f11-ab02-54ddd199efa8" />


### Static Timing Analysis
STA is a method used in digital circuit design to verify that a design will meet its timing requirements without having to simulate all possible input combinations.

In other words, STA checks the timing correctness of a digital circuit based on its netlist, delays, and constraints, rather than by applying waveforms dynamically.

It's called “static” because it does not require input vectors or full simulation of the circuit’s operation.

It ensures signals propagate within the allowed clock period.
