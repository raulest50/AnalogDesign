# Boost Converter Design
## Problem
A 2.4 KW inverter was purchased to work with existing solar panels and batteries. It were not notice beoforehand that inverter requiered at least 
90v at the input to charge the batteries. To gain some time and avoid batterie damage during the time to buy new solar panels, a boost converter
was implemented to allow the new inverter to work with the existing panels, which produced beetwen 40v - 60v. The boost converte has to increased from 2 to 3 times
depending on demanded current and solar radiation.

full schematic:

<img src="https://github.com/raulest50/AnalogDesign/blob/main/BoostConverter/full.PNG" alt="drawing" width="1000"/>

## Notes on the solution
Because of this changing conditions, open loop boost is of no use, since the inverter at the starting demands around 0.13 A and when operating demanded from 0.5 A 
onwards. the some sort of regulation was needed.

A not too ambitious PI control with op amps were implemented with sucess, while not perfect, solved the problem. In reality worked a litle different than
in simulation regarding overshot and stabilization time. But it was enough to do the job. FRED diode and Mosfet maxium voltage was 200v, so limiting overshot was
very important.

<img src="https://github.com/raulest50/AnalogDesign/blob/main/BoostConverter/Regulation.PNG" alt="drawing" width="650"/>

---

<img src="https://github.com/raulest50/AnalogDesign/blob/main/BoostConverter/differential.PNG" align="left" alt="drawing" width="600"/> using op amp regular substractor circuit gave some problems, not sure why, but using differential op amp configuration as sugested in lm2904 datasheet solved the problem and the error did not showed erratic values anymore, so for analog control i think is better to use differential op amp config for the error. using lm2904 was also key since single voltage supply operation was required and lm2904 can get to low rail (0v), very important for the error signal and control signal

(https://www.st.com/resource/en/datasheet/lm2904.pdf).

---

To generate PWM the tl494 was used. the pwm level has to be injected in pin 4 (usually is used for death time control but here was used different) with max pwm level around 2.4v, to limit PI op amp controlo output and avoid short circuit the las 2 op amps were supplied with a voltage regulator built with tl431 and 
npn bjt transistor. For lm2904 upper rail is Vcc-1.5v . The pwm were fedded to ir2110 to drive the mosfet.

<img src="https://lh3.googleusercontent.com/pw/AL9nZEWIVkoqk1lIAakfzorLLkE86uBhEUKCPSZe0emOKSFL1qP_5EYbd1ZXMbAv3KJ5-MY1-079HihNx0UVwj2IsXXjjM5BCo7vXh0YfEl-Aw_TsYm6Bd-UeSc3cX3OsRIOTsA4m38rgS6mQlXSYDlwzrTf=w1218-h914-no?authuser=0" alt="drawing" width="500"/><img src="https://lh3.googleusercontent.com/pw/AL9nZEVT-nTZszFp_f7IxkIEJf2rT_7IChCnvpoKwjRqJAI2VOxXGRItJiGje9JMxYQ4_326YOrFfRMOudrREQVWMvAY_rugoOO4rwV4i1W2wYacGnwa15PAJXW7Avp6zoFyNir43qYV7KbbW42m5xkXN3Aj=w1218-h914-no?authuser=0" alt="drawing" width="500"/>
