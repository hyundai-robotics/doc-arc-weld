# 5.4 Welding End condition

When the arc welding settings are digital and [End condition] tab is pressed in the welding start condition dialog box, the following welding end condition editing screen appears.


![](../../_assets/5_4_1.png)<br>
*Figure 5.4.1. Welding End Condition Setting (e.g. EWM)* 


After editing the welding end conditions, pressing the `[ESC]` key will close the dialog box without saving the changes, while pressing `[OK]` key will save the settings and close the dialog box.

</br>

The descriptions for each item are as follows:

</br>

### (1)	Condition Number: [1] (Range: changes not allowed)  
Displays the welding start condition number. In digital arc welding, the end condition number and start condition number are managed as one. Therefore, to change the end condition number, the start condition number must also be changed.  

### (2)	End Welding Current / Welding Power / Wire Feed Speed  
Set the current value to be output during crater treatment. This is set as a percentage(%) relative to the current welding conditions (welding current, welding power, and wire feed speed). However, for EWM welders, this is set in m/min, the same as the welding conditions.

<center>

| supported Welder | Name | Unit | Range | Default |
| :---: | :---: | :---: |:---: | :---: |
| Hyosung | End Welding Current | % |10 ~ 100 | 70 |
| Fronius | End Welding Power | % | 10 ~ 100 | 70 |
| EWM | End Wire Feed Speed | m/min | 0.0 ~ 25.0 | 7.0 |

</center>

### (3)	End Welding voltage/ Arc length correction  
Set the voltage value to be output during crater treatment. The voltage is specified and output according to the set value.
<center>

| supported Welder | Name | Unit | Range | Default |
| :---: | :---: | :---: |:---: | :---: |
| Hyosung | End Welding voltage | % | 50.0 ~ 150.0| 100 |
| EWM | End Welding voltage | V | -10.0 ~ 10.0 | 0 |
| Fronius | End Arc length correction |  % | -30.0 ~ 30.0 | 0 |

</center>

### (4)	Downslope Time(Crate Time): [0] sec (Range: 0.0 ~ 10.0)  
Sets the time for processing the current change between the main condition and the end condition as a slope.

![](../../_assets/5_4_2.png)<br>
*Figure 5.4.2. DownSlope Time and Crate Time Chart*

### (5)	Condition Hold time: [1] sec (Range: 0.1 ~ 10.0)   
Set the time to maintain the output value specified in the 'current ratio' item under the welding end condition.

### (6)	Wire Burnback: [ 0 ] ms (Range: 0.0 ~ 200.0)  
Configures burnback processing. May vary depending on the welder.

### (7)	Gas Post Flow: [ 0 ] sec (Range: 0.0 ~ 10.0)  
Set the time to continue the shielding gas output even after the arc is turned off.

### (8)	Crater move time: [ 0 ] sec (Range: 0.0 ~ 10.0) / Crater move distance : [0] mm (Range: 0.0 ~ 100.0)
During crater treatment, sets the distance the robot will move backward during the DownSlope time and condition hold time. The speed is automatically determined based on the distance and time.

### (9) Auto Stick Release Count : [0] times (Range: 0 to 9) / Condition : [0] (Range: 0 to 32) / Time: [0] sec (Range: 0.0 to 10.0)  
During arc welding, the welding wire may stick to the base material at the end of welding. To prevent this, the welding power source temporarily increases the voltage at the end of welding as an anti-sticking process.
However, sticking may still occur even after this process. Therefore, the robot controller sends a post-weld sticking detection signal to the welding power source to check whether sticking has occurred.
The auto stick release function automaticllay performs a burnback release when sticking is detected after welding, allowing the robot to continue operation without stopping.
This process is repeated for the configured number of times. If the sticking is not released after the specified number of attempts is exceeded, the robot will stop.

* Count : [0] times (Range: 0 to 9)
    This parameter specifies the maximum number of burnback release attempts. If the sticking is not released within the configured number of attempts, an error will occur. 
    Exceptionally, when set to 0, the sticking check is skipped and the system proceeds directly to the next step.

* Condition : [0] (Range: 0 to 32)
    This parameter specifies the welding condition number used for the burnback release process. When set to 0, the burnback release is performed using the current welding start condition.

* Time: [0] sec (Range: 0.0 to 10.0)
    This parameter specifies the duration for which the burnback release condition output is maintained.