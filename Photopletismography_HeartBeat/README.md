
# Measuring Heart Rate with Ir Diodes

I have tried 3 different circuits found on the internet, both simulation and implementation.
only one was sucesfull. The keys are: 

- gain around 60db in the .1-10 Hz band
- Ir diodes integrated in single package (reflection preferably). This to prevent misalignments problems.  

It is also useful to use rail to rail op amps or at least able to get to de low rail like de lm2904 which is able to achieve 0v output with single supply.

<img src="drawing.jpg" alt="drawing" width="200"/>