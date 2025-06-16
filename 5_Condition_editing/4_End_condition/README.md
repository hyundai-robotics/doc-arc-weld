# 5.4 Welding End condition

When the arc welding settings are digital and [End condition] tab is pressed in the welding start condition dialog box, the following welding end condition editing screen appears.


<p align="center">
 <img src="../../_assets/5_4_1.png" width="70%"></img>
 <em><p align="center">Figure 5.4.1. Welding End Condition Setting (e.g. EWM)</p></em>
</p> 


After editing the welding end conditions, pressing the [**ESC**] key will close the dialog box without saving the changes, while pressing [**OK**] key will save the settings and close the dialog box.

</br>

---

The descriptions for each item are as follows:


</br>

### (1)	Condition Number: [1] (Range: changes not allowed)  
Displays the welding start condition number. In digital arc welding, the end condition number and start condition number are managed as one. Therefore, to change the end condition number, the start condition number must also be changed.  

### (2)	End Welding Current / Welding Power / Wire Feed Speed  
Set the current value to be output during crater treatment. This is set as a percentage(%) relative to the current welding conditions (welding current, welding power, and wire feed speed). However, for EWM welders, this is set in m/min, the same as the welding conditions.
<center>

| supported Welder | Name | Unit | Range | Default |
| :---: | :---: | :---: |:---: | :---: |
| HRWI | End Welding Current | % |10 ~ 100 | 70 |
| Fronius | End Welding Power | % | 10 ~ 100 | 70 |
| EWM | End Wire Feed Speed | m/min | 0.0 ~ 25.0 | 7.0 |

</center>



### (3)	End Welding voltage/ Arc length correction  
Set the voltage value to be output during crater treatment. The voltage is specified and output according to the set value.
<center>

| supported Welder | Name | Unit | Range | Default |
| :---: | :---: | :---: |:---: | :---: |
| HRWI | End Welding voltage | % | 50.0 ~ 150.0| 100 |
| EWM | End Welding voltage | V | -10.0 ~ 10.0 | 0 |
| Fronius | End Arc length correction |  % | -30.0 ~ 30.0 | 0 |

</center>

### (4)	Downslope Time(Crate Time): [0] sec (Range: 0.0 ~ 10.0)  
Sets the time for processing the current change between the main condition and the end condition as a slope.

<p align="center">
 <img src="../../_assets/5_4_2.png" width="30%"></img>
 <em><p align="center">Figure 5.4.2. DownSlope Time and Crate Time Chart</p></em>
</p>

### (5)	조건유지시간: [1] second (Range: 0.1 ~ 10.0)   
용접종료조건의 ‘전류비율’ 항목에서 지정된 출력 값을 유지하는 시간을 설정합니다.

### (6)	Burnback 조정: [  0] % (Range: -20 ~ 20)  
Configures burnback processing.

### (7)	Gas Post Flow: [ 0] second (Range: 0.0 ~ 10.0)  
Arc가 꺼진 후에도 보호가스를 계속 출력하는 시간을 설정합니다.

### (8)	Crater move time: [ 0 ] second (Range: 0.0 ~ 10.0) / Crater move distance : [0] mm (Range: 0.0 ~ 100.0)
During crater treatment, sets the distance the robot will move backward during the DownSlope time and condition hold time. The speed is automatically determined based on the distance and time.

크레이터 처리 과정 중 DownSlope시간+조건유지시간 동안 로봇이 후진할 거리를 설정합니다. 속도는 거리와 시간에 의해 자동으로 결정됩니다.

### (9) Retract Time: [ 0 ] second (Range: 0.0 ~ 10.0)  
After the welding end process is completed, sets the time for the robot to rewind the wire while performing the next move. This is used to prevent the wire from bending due to interference or to avoid starting the welding with wire contact when moving to the next step.

### (10) Retract 속도: [  0] (Range: 0 ~ 100)  
용접 종료 시 와이어를 되감는 처리를 할 때 와이어 송급속도를 지정합니다. 용접기의 최대 전류에 대한 비율로 설정합니다.
