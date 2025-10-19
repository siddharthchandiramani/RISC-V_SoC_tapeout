# SPICE Simulation

Step1: Firstly, we will clone the repository 
```bash
# Clone the repository
git clone https://github.com/kunalg123/sky130CircuitDesignWorkshop.git

# Navigate into the cloned directory
cd sky130CircuitDesignWorkshop/design
```
```
.param temp=27

* Including sky130 library files
.lib "sky130_fd_pr/models/sky130.lib.spice" tt

* Netlist Description
XM1 Vdd n1 0 0 sky130_fd_pr__nfet_01v8 w=5 l=2

R1 n1 in 55

Vdd vdd 0 1.8V
Vin in 0 1.8V

* Simulation commands
.op
.dc Vdd 0 1.8 0.1 Vin 0 1.8 0.2

.control
run
display
setplot dc1
.endc

.end
```
