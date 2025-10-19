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

### ID–VDS Characteristics of NMOS Transistor

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

### ID–VDS Characteristics for Short-Channel MOSFET (Velocity Saturation)

In short-channel MOSFETs, as the channel length decreases, the electric field along the channel increases rapidly for a given VDS. When this field becomes very high, the carrier velocity no longer increases linearly with the field but instead saturates at a maximum value called the saturation velocity (vsat).

As a result:

The drain current (ID) increases linearly with VDS at low voltages (linear region).

Once the carriers reach velocity saturation, further increase in VDS causes very little change in ID, leading to early saturation compared to long-channel devices.

The ID–VDS curve thus becomes flatter, and the square-law relation of current with VGS no longer holds.

This phenomenon limits the current drive but improves the switching speed, making it a key effect in deep submicron and nanometer technologies.

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

### ID–VGS Characteristics of NMOS Transistor
The ID–VGS curve shows how the drain current (ID) varies with the gate-to-source voltage (VGS) for a fixed drain-to-source voltage (VDS). The behavior of the MOSFET can be divided into three main regions:

Cutoff Region (VGS < Vth):
When the gate voltage is below the threshold voltage (Vth), no inversion channel is formed between the drain and source. The transistor remains OFF, and the drain current (ID) is approximately zero, except for a small subthreshold leakage current.

Linear (Ohmic) Region (VGS > Vth and VDS < VGS – Vth):
When VGS exceeds Vth, a conductive channel forms. For small VDS, the MOSFET behaves like a voltage-controlled resistor, and the drain current increases almost linearly with VDS.
The current is given by:
<img width="345" height="49" alt="image" src="https://github.com/user-attachments/assets/1dcfb13f-6b60-44aa-9ac2-dc7fe5bed1d6" />


Saturation (Active) Region (VGS > Vth and VDS ≥ VGS – Vth):
When VDS increases beyond VGS – Vth, the channel near the drain end pinches off, and the current becomes almost independent of VDS.
The drain current is given by the square-law equation:
<img width="280" height="49" alt="image" src="https://github.com/user-attachments/assets/20f8e2df-5cdf-41db-b092-356340184d51" />

This region is mainly used for amplification in analog circuits.

## VTC Characteristics of CMOS Inverter
```
siddharthac@siddharthac:~/sky130CircuitDesignWorkshop/design$ vim day3_inv_vtc_Wp084_Wn036.spice 
```

<img width="564" height="730" alt="image" src="https://github.com/user-attachments/assets/af011cb0-7931-4db8-8674-5b217e8194d6" />

### Simulation
Steps for simulation:
```
siddharthac@siddharthac:~/sky130CircuitDesignWorkshop/design$ ngspice day3_inv_vtc_Wp084_Wn036.spice 
```
<img width="654" height="311" alt="image" src="https://github.com/user-attachments/assets/562f25a1-1564-4bb7-b2e7-d35a4eec8fa9" />

### VTC Plot
<img width="732" height="576" alt="4th_vtc_p_2_n" src="https://github.com/user-attachments/assets/a7043b74-9f2d-4727-ae50-5013beb24d03" />

### Voltage Transfer Characteristics (VTC) of CMOS Inverter

The Voltage Transfer Characteristic (VTC) of a CMOS inverter shows the relationship between the input voltage (Vin) and the output voltage (Vout). It illustrates how the inverter transitions from a logic high to a logic low state as the input voltage varies from 0 V to VDD.

The VTC curve can be divided into three distinct regions:

Region I – NMOS OFF, PMOS ON (Vin < Vthn):

When the input voltage is low, the NMOS transistor is OFF and the PMOS transistor is ON.

The output is connected to VDD through the PMOS, so Vout ≈ VDD (logic high).

Region II – Transition Region (Vthn < Vin < VDD - |Vthp|):

Both NMOS and PMOS are partially ON.

This is the switching region, where a small change in input causes a large change in output.

The inverter exhibits high gain, and the point where Vin = Vout is the switching threshold (Vm).

Region III – NMOS ON, PMOS OFF (Vin > VDD - |Vthp|):

The NMOS transistor is fully ON, and the PMOS transistor is OFF.

The output is pulled down to ground, so Vout ≈ 0 V (logic low).

The ideal VTC curve is steep in the transition region, indicating good noise margins and strong switching characteristics. The noise margins (NMH and NML) define how much noise the circuit can tolerate without logic errors.



