# OTA_Operational.Transconductance.Amplifier

**Given specifications**: 
- Gain ≥ 35dB
- Vdd = 1.8V
- Load capacitance = 10pF
- Unity Gain Frequency ≥ 5MHz
- Power ≤ 100μW
- Phase Margin ≥ 60 degrees
- Slew Rate ≥ 5V/μs
- ICMR+ = 1.6V
- ICMR- = 0.8V

## Contents
- [1. Extracting device parameters](#1-Finding-out-Device-parameters)
  - [1.1 Values for NMOS](#11-NMOS)
  - [1.2 Values for PMOS](#12-PMOS)
- [2. Determining the DC current](#2-Determining-the-DC-current)
- [3. Determining the dimensions of MOSFETs](#3-Determining-the-dimensions-of-MOSFETs)
  - [3.1 Input pair NMOS](#31-Input-pair-NMOS) 
  - [3.2 Current mirror PMOS](#32-Current-mirror-PMOS)
  - [3.3 Current mirror NMOS](#33-Current-mirror-NMOS)
- [4. Initial analysis](#4-Initial-analysis)
- [5. Final Transistor dimensions](#5-Final-Transistor-dimensions)
- [6. Final Analysis](#6-Final-Analysis)

## 1. Finding out Device parameters
For that I have used this circuit :
- ![Screenshot-19](https://github.com/user-attachments/assets/1e8682b9-c2ed-4d30-be35-24e386dc2c6e)

By DC Analysis we are finding out the values:

### 1.1 NMOS
- ![Screenshot-15](https://github.com/user-attachments/assets/1d5b48ae-801f-494d-ad39-3dd7ba28a2fb)
- μnCox = 293.5 μA/V²
- ![Screenshot-16](https://github.com/user-attachments/assets/a8b7c525-ec87-45f6-8662-8e406125f7b5)
- Vth = 0.18V

### 1.2 PMOS
- ![Screenshot-17](https://github.com/user-attachments/assets/aad44e37-1b1b-45bd-bc08-1bf7d33d4f35)
- μpCox = 136 μA/V²
- ![Screenshot-18](https://github.com/user-attachments/assets/08b5badc-70c3-4be0-868a-1fc5db023c5b)
- Vth = - 0.16V

## 2. Determining the DC current  
- Lower Limit : It is calculated by the slew rate of the OTA and it came to be 50μA.
- Upper Limit : it is calculated from the maximum power consumption of the circuit and it came to be 55.55μA.
- So, I chose the DC current to be **55μA** as it satisfies both criterias.
- 
## 3. Determining the dimensions of MOSFETs
We are considering the **Length(L)** of all mosfets as 1µm.
### 3.1 Input pair NMOS 
Its dimensions were calculated from UGF. The calculated value of (W/L) was 6. But by not getting the expected gm from this W/L ratio in the simulation, I changed it to **7**.
### 3.2 Current mirror PMOS 
Its dimensions were calculated from ICMR+ value. The calculated value was (W/L) = **7**.
### 3.3 Current mirror NMOS
Its dimensions were calculated from ICMR- value and the calculated value was (W/L) = **5.87**

## 4. Initial analysis
### At ICMR = 0.8V
- ![Screenshot](https://github.com/user-attachments/assets/7aa7f112-9508-4afa-8250-f48ceebdc3fe)
- ![Screenshot-1](https://github.com/user-attachments/assets/459ecb4e-d831-4714-9618-14f39dd1a5f8)
- Gain = 38.5dB and UGF = 5.04 MHz
### At ICMR = 1.6V
- ![Screenshot-4](https://github.com/user-attachments/assets/c2f19236-3c48-4963-8041-36b2338b3b24)
- ![Screenshot-3](https://github.com/user-attachments/assets/6876d200-7ac2-4e22-9dcd-96a14a0d876f)
- Gain = 34.2 dB and UGF = 5.07 MHz
The gain is slightly low at ICMR = 1.6V and the ouput DC voltage level is slightly low than calculated. So the circuit is tuned accordingly.
### Power consumption
- I have observed the changed of Io w.r.t change in ICMR voltage.
- ![Screenshot-12](https://github.com/user-attachments/assets/4e422a9d-b032-4374-bcf0-c21548ef38c7)
It has been observed that Io increases linearly w.r.t Input common mode voltage. And at ICMR = 1.6V, Io = 57.42 μA. But the maximum limit is 55.55 μA. So, the value of current in current source of current mirror is tuned accordingly.

## 5. Final Transistor tunings
- **Current mirror PMOS** : (W/L) = **8**
- **Input pair NMOS** : (W/L) = **9**
- **Current mirror NMOS** : (W/L) = **5.87**
- **Value of DC current of the OTA** : Io = 53 μA. This is the value of current at current source of the current sink of the OTA structure.
  
## 6. Final Analysis

### At ICMR = 0.8V
- ![Screenshot-23](https://github.com/user-attachments/assets/a069651c-288f-46e1-9a2b-d3c1daef6bc6)
- ![Screenshot-22](https://github.com/user-attachments/assets/285d222e-ef93-499d-a1ed-3e5ad554fd5d)
- Gain = 39.31 dB and UGF = 5.53 MHz
### At ICMR = 1.6V
- ![Screenshot-24](https://github.com/user-attachments/assets/3f17c8c8-970e-4c72-a5d9-a10e58455ce1)
- ![Screenshot-25](https://github.com/user-attachments/assets/0232898c-6317-4f67-8e71-e2ca38a8478c)
- Gain = 36.18 dB and UGF = 5.61 MHz
### Power consumption
- The value of Io is measured w.r.t change in Input common mode voltage.
![Screenshot-21](https://github.com/user-attachments/assets/72766050-c5f7-4564-95a5-205155611bea)
- Io increases linearly w.r.t ICM voltage and 52.97 μA ≤ Io ≤ 55.37 μA.
- So, Power consumption, P ranges between 95.346 μW ≤ P ≤ 99.66 μW.


## 7. Final design
- **FInal ciecuit design**
- ![Screenshot-13](https://github.com/user-attachments/assets/fa32796b-d7de-4ee7-af8a-40fb99170104)
- **Symbol creation**
- ![Screenshot-14](https://github.com/user-attachments/assets/a7de3671-85b2-4648-b4b1-8fa6e819db6d)




