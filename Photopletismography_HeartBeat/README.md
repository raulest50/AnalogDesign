
# Measuring Heart Rate with Ir Diodes

I have tried 3 different circuits found on the internet, both simulation and implementation.
only one was sucesfull. The keys are: 

- gain around 60db in the .1-10 Hz band
- Ir diodes integrated in single package (reflection preferably). This to prevent misalignments problems.  

It is also useful to use rail to rail op amps or at least able to get to de low rail like de lm2904 which is able to achieve 0v output with single supply.

<img src="https://github.com/raulest50/AnalogDesign/blob/main/Photopletismography_HeartBeat/bode_plot.PNG" alt="drawing" width="600"/>

<img src="https://lh3.googleusercontent.com/pw/AL9nZEWoscjE2BnHrexoNDsgeWOmbwbFA7URwD0EMIo_IIsNdzYtxfpk5pCtYdqDDCtXOO3UhpwgdUX570Ff1psF8KoRBxlkC8NzCpUm4xyi7WNouRQw7lutg6cfe2rEOcOCjiI4oz92lFk1xdXCBK5n1M5P=w1218-h914-no?authuser=0" alt="drawing" width="600"/>
