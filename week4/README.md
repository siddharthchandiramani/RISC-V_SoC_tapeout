# SPICE Simulation

Firstly, we will clone the repository 
```bash
# Clone the repository
git clone https://github.com/kunalg123/sky130CircuitDesignWorkshop.git

# Navigate into the cloned directory
cd sky130CircuitDesignWorkshop/design
```
## Id vs Vds curve for different values of Vgs
```
siddharthac@siddharthac:~/sky130CircuitDesignWorkshop/design$ vim day1_nfet_idvds_L2_W5.spice 
```
<img width="486" height="698" alt="Screenshot from 2025-10-19 19-57-35" src="https://github.com/user-attachments/assets/77174aa6-4de7-4748-ba11-ac1c4898c62c" />

### Simulation
Steps for simulation:
```
siddharthac@siddharthac:~/sky130CircuitDesignWorkshop/design$ ngspice day1_nfet_idvds_L2_W5.spice
```
### Id vs Vds plot
<img width="732" height="576" alt="1st_id_vs_vds" src="https://github.com/user-attachments/assets/602b23cf-cc6d-4ba0-8cae-61f9af8e3d38" />

## ID–VDS Characteristics of NMOS Transistor

The plot above shows the drain current (ID) versus drain-to-source voltage (VDS) characteristics of an NMOS transistor for multiple gate-to-source voltages (VGS).

As VDS increases, the drain current initially rises linearly in the ohmic (linear) region, and then gradually saturates in the saturation region.
Higher VGS values result in higher ID due to the increased channel inversion strength, which enhances carrier flow through the channel.

This behavior validates the expected MOSFET operation — linear region at low VDS and saturation at higher VDS — consistent with the square-law model of the NMOS device.

## Id vs Vds curve for different values of Vgs for short channel

```
siddharthac@siddharthac:~/sky130CircuitDesignWorkshop/design$ vim day2_nfet_idvds_L015_W039.spice 
```
<img width="541" height="721" alt="image" src="https://github.com/user-attachments/assets/666bdf6c-cb1b-4f5f-b0e8-1f1781585ce5" />

### Simulation
Steps for simulation:
```
siddharthac@siddharthac:~/sky130CircuitDesignWorkshop/design$ ngspice day2_nfet_idvds_L015_W039.spice 
```
<img width="541" height="241" alt="image" src="https://github.com/user-attachments/assets/2f19c3a1-36f9-49f5-b6ea-8d2945dd252a" />

### Id vs Vds plot
<img width="732" height="576" alt="2nd_id_vds_0 15_0 39" src="https://github.com/user-attachments/assets/a4c8d233-64d8-4ae1-a4fe-594a2828bcfb" />

## Id vs Vgs plot
```
siddharthac@siddharthac:~/sky130CircuitDesignWorkshop/design$ vim day2_nfet_idvgs_L015_W039.spice 
```
<img width="541" height="674" alt="image" src="https://github.com/user-attachments/assets/f384153a-e3cb-45d0-a475-dedd1751ff03" />

### Simulation
Steps for simulation:
```
siddharthac@siddharthac:~/sky130CircuitDesignWorkshop/design$ ngspice day2_nfet_idvgs_L015_W039.spice 
```
<img width="642" height="248" alt="image" src="https://github.com/user-attachments/assets/7c92d8aa-7ece-461a-96e1-a49d5605dd45" />

### plot
<img width="732" height="576" alt="3rd_id_vgs" src="https://github.com/user-attachments/assets/bab03adb-6d2e-4c3c-9bde-5fa92ebb2d00" />
Vt(Threshold voltage) = 0.77V

## ID–VGS Characteristics of NMOS Transistor
The ID–VGS curve shows how the drain current (ID) varies with the gate-to-source voltage (VGS) for a fixed drain-to-source voltage (VDS). The behavior of the MOSFET can be divided into three main regions:

Cutoff Region (VGS < Vth):
When the gate voltage is below the threshold voltage (Vth), no inversion channel is formed between the drain and source. The transistor remains OFF, and the drain current (ID) is approximately zero, except for a small subthreshold leakage current.

Linear (Ohmic) Region (VGS > Vth and VDS < VGS – Vth):
When VGS exceeds Vth, a conductive channel forms. For small VDS, the MOSFET behaves like a voltage-controlled resistor, and the drain current increases almost linearly with VDS.
The current is given by:
I 
D
​
 =μ 
n
​
 C 
ox
​
  
L
W
​
 [(V 
GS
​
 −V 
T
​
 )V 
DS
​
 − 
2
1
​
 V 
DS
2
​
 ]

Saturation (Active) Region (VGS > Vth and VDS ≥ VGS – Vth):
When VDS increases beyond VGS – Vth, the channel near the drain end pinches off, and the current becomes almost independent of VDS.
The drain current is given by the square-law equation:

This region is mainly used for amplification in analog circuits.



