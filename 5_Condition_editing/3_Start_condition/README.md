# 5.3 Welding Start condition


When the arc welding settings are digital and the cursor is placed on the command line `arcon cnd=_`, pressing the [property] key will bring up the editing screen for the welding start conditions.

 
<p align="center">
 <img src="../../_assets/5_3_1.png" width="70%"></img>
 <em><p align="center">Figure 5.3.1. Hyosung welder setting</p></em>
</p>  


<p align="center">
 <img src="../../_assets/5_3_2.png" width="70%"></img>
 <em><p align="center">Figure 5.3.2. Fronius welder setting</p></em>
</p>  

 
<p align="center">
 <img src="../../_assets/5_3_3.png" width="70%"></img>
 <em><p align="center">Figure 5.3.3. EWM welder setting</p></em>
</p>

 

After editing the conditions, pressing the [**ESC**] key will close the dialog box without saving the changes, while pressing [**OK**] key will save the settings and close the dialog box.

The following items apply to all welder in common. For model-specific settings, please refer to the following chapter.

The contents of common items may vary in name, unit, and range for each welder. Please refer to the respective table for model-specific differences.

</br>

---

### (1)	Condition Number  
Specifies the welding start condition number to be edited.(Max: 32) 

<center>

| Item | Name | Range |
| :---: | :---: | :---: |
| Common to all welders | Condition Number | 1 ~ 32 |

</center>

</br>  

### (2)	Description  
Records the description for the specified welding start condition.

<center>

| Supported Welder | Name |
| :---: | :---: |
| Common to all welders | Comment |

</center>

</br>  
    
### (3)	Synergic Code  
Sets the synergic code to b transmitted to the welder. The code value is configured in a separate synergic selection screen. The synergic selection screen can be accessed by pressing the [**Synergic Selection**] button on the welding start condition creen.

<center>

| Supported Welder | Name | Unit | Range | Default |
| :---: | :---: | :---: |:---: | :---: |
| Hyosung | Synergic Code | - |- | 040 |
| Fronius </br>(Not supported) |-|-|-|-|
| EWM | JOB Nr.(synergic) | - |- | 185|

</center>
    
</br>  

### (4)	Welding Current / Welding Power / Wire Feed Speed  
Set the welding current value. This is the current used during the welding process. The current of the initial and final conditions is determined as a ratio of this value.
<center>

| Supported Welder | Name | Unit | Range | Default |
| :---: | :---: | :---: |:---: | :---: |
| Hyosung | Welding Current | A |0.0 ~ 500.0 | 100 |
| Fronius | Welding Power | % | 0.0 ~ 100.0 | 10 |
| EWM | Wire Feed Speed |  m/min | 0.0 ~ 25.0 | 3.1 |

</center>
    
</br>

### (5)	Welding voltage / Arc length correction  
In digital welding, the welding voltage is often not entered directly, but instead selected automatically based on welding current from the synergic data. If you wish to modify the welding voltage automatically selected by the synergic data, set the offset value for the voltage to be adjusted based on the selected welding voltage.
<center>

| Supported Welder | Name | Unit | Range | Default |
| :---: | :---: | :---: |:---: | :---: |
| Hyosung | Welding voltage | % | 50.0 ~ 150.0 | 100 |
| Fronius | arc length correction | % | -30.0 ~ 30.0 | 0 |
| EWM | Welding voltage Correction | V | -10.0 ~ 10.0 | 0 |
</center>
    
</br>

### (6)	Gas preflow
Set the time to preflow shileld gas before starting the arc welding to isolate and prepare the welding area.

<center>  

| Supported Welder | Name | Unit | Range | Default |
| :---: | :---: | :---: |:---: | :---: |
| Common to all welders | gas preflow | sec | 0.0 ~ 10.0 | 0.5 |  

</center>

</br>  

### (7)	WCR Wait Time  
Indicates the time waiting for the WCR input. If the WCR signal is not received within this time, a retry will be performed. However, if the retry count is set to 0, an error will be displayed, and the robot will stop. Retry methods and retry counts can be configured in the welding auxiliary conditions. (Refer to [5.5 Welding Auxiliary condition](../5_Aux_condition/README.md))

<center>

| Supported Welder | Name | Unit | Range | Default |
| :---: | :---: | :---: |:---: | :---: |
| Common to all welders | WCR Wait Time | sec | 0.0 ~ 10.0 | 2 |


</center>
    
</br>

### (8)	Robot delay time  
After the arc welding has started normally, sets the time the robot will wait before moving along the welding line to perform the welding. This is independent of the initial conditions, and the robot can move even while processing initial conditions.
<center>

| Supported Welder | Name | Unit | Range | Default |
| :---: | :---: | :---: |:---: | :---: |
| Common to all welders | Robot delay time | sec | 0.0 ~ 10.0 | 0 |

</center>
    
</br>

### (9) Initial condition maintain time  
Sets the time for maintaining the initial current value at the start of arc welding.
<center>

| Supported Welder | Name | Unit | Range | 
| :---: | :---: | :---: |:---: |
| Common to all welders | Initial condition maintain time | sec | 0.0 ~ 10.0 | 

</center>
    
</br>

### (10) Initial Welding Current / Welding Power / Wire Feed Speed  
Sets the welding current to be output during the initial condition hold time at the start of arc welding.
This is set as a percent(%) relative to the welding current of the main condition.
<center>

| Supported Welder | Name | Unit | Range | Default |
| :---: | :---: | :---: |:---: | :---: |
| Hyosung | Initial Welding Current | % | 20 ~ 200 | 120 |
| Fronius | Initial Welding Power | % | 20 ~ 200 | 120 |
| EWM | Initial Wire Feed Speed | % | 20 ~ 200 | 120 |

</center>
    
</br>

### (11) Initial Welding voltage / Arc length correction  
Sets the welding voltage to be output during the initial condition hold time at the start of arc welding.
This is set as a correction value relative to the synergic voltage.  
<center>

| Supported Welder | Name | Unit | Range | Default |
| :---: | :---: | :---: |:---: | :---: |
| Hyosung | Initial Welding voltage | % | 50.0 ~ 150.0 | 100 |
| EWM | Initial Welding voltage | V | -10.0 ~ 10.0 | 0 |
| Fronius | Initial Arc length correction | %| -30.0 ~ 30.0 | 0 |

</center>
    
</br>

### (12) Slope Time  
Sets the time to process the current change between the initial condition and this condition as a slope.
<center>

| Supported Welder | Name | Unit | Range | 
| :---: | :---: | :---: |:---: |
| Common to all welders | Slope Time | 초 | 0.0 ~ 10.0 | 


</center>
    
</br>

### (13) Excess Allowed Time  
Sets the allowable time for exceeding the welding voltage/current and feed motor current limits. If the welding voltage/current or feed motor current exceeds the limits for longer than this time, a restart will be performed. However, If the restart count is set to 0, an error will be displayed, and the robot will stop. The restart method and restart count, as well as other restart-related features, can be configured in the welding auxiliary conditions. If this time is set to 0 seconds, the arc limits monitoring function will not be used.
<center>

| Supported Welder | Name | Unit | Range | Default | 
| :---: | :---: | :---: |:---: |:---: |
| Common to all welders | Excess Allowed Time | 초 | 0.0 ~ 10.0 | 0 | 


</center>
    
</br>

### (14) Welding Voltage upper/lower limit  
Sets the upper and lower voltage limits during welding. If the limits are exceeded for longer than the allowed time, an error will occur.
<center>

| Supported Welder | Name | Unit | Range | 
| :---: | :---: | :---: |:---: |
| Common to all welders | Welding Voltage upper/lower limit | V | 0.0 ~ 100.0 | 


</center>
    
</br>

### (15) Welding Current upper/lower limit  
Sets the upper and lower current limits during welding. If the limits are exceeded for longer than the allowed time, an error will occur.
<center>

| Supported Welder | Name | Unit | Range | 
| :---: | :---: | :---: |:---: |
| Common to all welders | Welding Current upper/lower limit | A | 0.0 ~ 1000 | 


</center>
    
</br>
    
</br>