# OTA_Operational.Transconductance.Amplifier

**Given specifications**: 
- Gain ≥ 35dB
- Vdd = 1.8V
- Load capacitance = 10pF
- Unity Gain Frequency ≥ 5MHz
- Power ≤ 100uW
- Phase Margin ≥ 60 degrees
- Slew Rate ≥ 5V/μs
- ICMR+ = 1.6V
- ICMR- = 0.8V

## Contents
- [1. Extracting device parameters](#1-Finding-out-Device-parameters)
  - [1.1 Values for NMOS](#11-NMOS)
  - [1.2 Values for PMOS](#12-PMOS)
- [2. Analysis of MOSFET models](#2-Analysis-of-MOSFET-models)
  - [2.1 General MOS analysis](#21-General-MOS-analysis)
  - [2.2 Strong 0 and Weak 1](#22-Strong-0-and-Weak-1)
  - [2.3 Weak 0 and Strong 1](#23-Weak-0-and-Strong-1)
- [3. CMOS Inverter Design and Analysis](#3-CMOS-Inverter-Design-and-Analysis)
  - [3.1 Why CMOS Circuits](#31-Why-CMOS-Circuits) 
  - [3.2 CMOS Inverter Analysis(Pre-Layout)](#32-CMOS-Inverter-Analysis-Pre-Layout)
    - [3.2.1 DC Analysis and Important design parameters](#321-DC-Analysis-and-Important-design-parameters)
    - [3.2.2 DC Parametric Analysis](#322-DC-Parametric-Analysis)

## 1. Finding out Device parameters.
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

  
