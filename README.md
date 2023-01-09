# AnalogDesign
 
 ## DC and Parameter Sweep
 
<img src="https://github.com/raulest50/AnalogDesign/blob/main/img/dc_sweep.PNG" alt="drawing" width="400"/>

<img src="https://github.com/raulest50/AnalogDesign/blob/main/img/step_param.PNG" alt="drawing" width="400"/><img src="https://github.com/raulest50/AnalogDesign/blob/main/img/step_param2.PNG" alt="drawing" width="400"/>


## Measure Statement

```
.meas Pin AVG -V(IN)*I(V1)
.meas Pout AVG V(OUT)*I(I1)
.meas Eff param Pout/Pin
```
