# 8.4 Height Sensing


This function is used in cases where the robot tool needs to maintain a constant distance from the workpiece, such as TIG welding. In TIG welding, the height is proportional to the arc length, which is why this function is called Arc Voltage Control(AVC). The distance from the workpiece is adjusted by the analog voltage input from the sensor, a correction parameter for the Arc length detected by the welder, and the welding current or voltage values.

<!-- 본 기능의 사용을 위해서는 센싱 기능을 위한 데이터 입력 설정을 ‘유효’로 선택해야 합니다.
센싱 기능을 위한 데이터 입력 설정의 세부 내용은 ‘1.3 Arc 용접 응용 조건 설정’을 참고하여 주십시오.  -- ???? -->

Once the setup for the sensing function input data is complete, the height sensing function can be used through the following procedure.

### (1) Command

To start height sensing, use the command `height on, cnd=1`.
The command is followed by the condition number. There are a total of 8 height sensing conditions.
To stop height sensing, use the command `height off`.
The stop command does not require any additional arguments.

An example of a job program with height sensing commands is as follows:

```python
    S1   move L,spd=100%,accu=1,tool=0
    S2   move L,spd=20%,accu=1,tool=0
    S3   move L,spd=100mm/s,accu=1,tool=0
         heightsen on, cnd=1		  # Start height sensing
         arcon cnd=2		       # Start Arc welding
    S4   move L,spd=10mm/s,accu=1,tool=0
         arcoff			       # End Arc welding
         heigghtsen off			  # End height sensing
    S5   move L,spd=20%,accu=1,tool=0
         END 
```

### (2) Height Sensing Function Operation Sequence

Height sensing begins after the ```arcon``` command is executed. Since the current and voltage are typically unstable at the start of welding, the input data is ignored until they stabilize.
Once the input data stabilizes, the average is calculated based on the method of setting the reference data. If the user manually enters the reference data, height sensing is performed immediately.  

The opration sequence of height sensing is as follows:


 
<p align="center">
 <img src="../../_assets/8_4_1.png" width="40%"></img>
 <em><p align="center">Figure 8.4.1. Height Sensing Function Operation Sequence</p></em>
</p>

