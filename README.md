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

## 5. Final Transistor dimensions
- **Current mirror PMOS** : (W/L) = **8**
- **Input pair NMOS** : (W/L) = **9**
- **Current mirror NMOS** : (W/L) = **5.87**
  
## 6. Final Analysis

### At ICMR = 0.8V
- ![Screenshot-11](https://github.com/user-attachments/assets/a7a093a3-1394-4c71-a15e-9fb26329e387)
- ![Screenshot-10](https://github.com/user-attachments/assets/e0267008-6929-4a65-ad24-9fd8e554bc8b)
- Gain = 39.22 dB and UGF = 5.63 MHz
### At ICMR = 1.6V
- ![Screenshot-9](https://github.com/user-attachments/assets/e9eb05dd-d601-412a-921e-ea9f1a5891d8)
- ![Screenshot-8](https://github.com/user-attachments/assets/532b2bd9-4337-4e1b-b480-558b898559d5)
- Gain = 35.87 dB and UGF = 5.71 MHz

## 7. Final design
- **FInal ciecuit design**
- ![Screenshot-13](https://github.com/user-attachments/assets/fa32796b-d7de-4ee7-af8a-40fb99170104)
- **Symbol creation**
- ![Screenshot-14](https://github.com/user-attachments/assets/a7de3671-85b2-4648-b4b1-8fa6e819db6d)




