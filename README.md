# OTA_Operational.Transconductance.Amplifier

*Given specifications*: 
Gain ≥ 35dB, Vdd = 1.8V, output swing = 1V p-p, Load capacitance = 10pF, Unity Gain Frequency ≥ 5MHz, Power ≤ 100uW, Phase Margin ≥ 60 degrees, Slew Rate ≥ 5V/μs


# At first we have to find out the device parameters.
For that I have used this circuit :
- ![image](https://github.com/user-attachments/assets/0bb2df2c-5164-4ed3-8f08-c4d04d6aff7c)

By DC Analysis we are finding out these values:
- **NMOS**
- ![Screenshot-5](https://github.com/user-attachments/assets/4ac88d3b-cd66-40f5-bd22-d436f10e01d5)
- μnCox = 297.362 μA/V²
- ![Screenshot-6](https://github.com/user-attachments/assets/fdf30312-c01c-48d6-9b10-6c8e30406f07)
- Vth = 0.19V
- ![Screenshot-10](https://github.com/user-attachments/assets/799ad688-e9e5-4317-ba04-e044fb56e24d)
- ro = 24kohm

**PMOS**
- ![Screenshot-7](https://github.com/user-attachments/assets/e88810d2-dbfb-4c14-b2b8-77e3cf23b2c3)
- μpCox = 135 μA/V²
- ![Screenshot-8](https://github.com/user-attachments/assets/060af715-0957-4381-88ea-0388a2082071)
- Vth = - 0.18V
- ![Screenshot-9](https://github.com/user-attachments/assets/d4fed133-a97e-4713-aed2-e9979a3215f9)
- ro = 33.165 kohm

