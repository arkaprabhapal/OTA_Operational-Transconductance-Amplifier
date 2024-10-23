# OTA_Operational.Transconductance.Amplifier

*Given specifications*: 
Gain ≥ 35dB, Vdd = 1.8V, output swing = 1V p-p, Load capacitance = 10pF, Unity Gain Frequency ≥ 5MHz, Power ≤ 100uW, Phase Margin ≥ 60 degrees, Slew Rate ≥ 5V/μs, ICMR+ = 1.6V, ICMR- = 0.8V


# At first we have to find out the device parameters.
For that I have used this circuit :
- ![Screenshot-19](https://github.com/user-attachments/assets/1e8682b9-c2ed-4d30-be35-24e386dc2c6e)


By DC Analysis we are finding out these values:
- **NMOS**
- ![Screenshot-15](https://github.com/user-attachments/assets/1d5b48ae-801f-494d-ad39-3dd7ba28a2fb)
- μnCox = 293.5 μA/V²
- ![Screenshot-16](https://github.com/user-attachments/assets/a8b7c525-ec87-45f6-8662-8e406125f7b5)
- Vth = 0.18V

**PMOS**
- ![Screenshot-17](https://github.com/user-attachments/assets/aad44e37-1b1b-45bd-bc08-1bf7d33d4f35)
- μpCox = 136 μA/V²
- ![Screenshot-18](https://github.com/user-attachments/assets/08b5badc-70c3-4be0-868a-1fc5db023c5b)
- Vth = - 0.16V

  
