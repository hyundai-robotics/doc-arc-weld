# 8.8.2 TCP-Sensor Calibration  


Before using the LPS function, calibration between the TCP and the sensor must be performed.
The following section describes how to perform TCP-to-sensor calibration.

<br/>

### (1) Preparation of the Calibration Specimen

When a license is purchased through our company, a calibration specimen for automatic calibration is provided.

<br/>


### (2) Preparation  

Before performing calibration, the tool must be perfectly aligned with the calibration plane.
Teach the tool manually in the X and Y directions based on the tool coordinate system, and check that the laser output remains constant (with the error kept within 0.5 or less). Adjust the RX and RY values as necessary.  

Once the tool is aligned, position the wire tip at the edge of the calibration plane.
When teaching in the tool-based X–Y directions, adjust the RZ value so that the laser point moves along the edge corner.  

<br/>

<p align="center">
  <img src="../../_assets/8_8_2_1.png" width="60%"></img>
  <em><p align="center">Figure 8.8.2.1 Preparation before calibration</p></em>
</p><br/>  

After completing the above steps, all preparations required for performing calibration are complete.


### (3) Performing Automatic Calibration

Position the wire tip at one vertex of the calibration plane.
In addition, ensure that the laser point is located inside the calibration plane.  

<br/>

<p align="center">
 <img src="../../_assets/8_8_2_2.png" width="50%"></img>
 <em><p align="center">Figure 8.8.2.2 Start of calibration</p></em>
</p><br/>  

From the lower panel, select `[F6: cmd. input] – arcweld – lps` and insert the following command.

```py
  lps auto_calib, cnd=<Condition Number>, Tx=<Movement Distance in the X-dir based on the tool>, Ty=<Movement Distance in the Y-dir based on the tool
```

At this time, the movement distance must be set greater than the distance the laser is required to travel.
If detection fails within the specified parameters, a calibration error will occur.  

When executed in automatic method, calibration is performed through the following sequence of operations:  

1. The laser point moves in the Tx and Ty directions, initially moving toward the tool tip direction.
2. The robot is lifted in the +Z direction based on the robot coordinate system, and the same process as in Step 1 is performed.
3. The robot moves downward in the –Z direction based on the robot coordinate system, while interpolation is performed toward the transmitter/receiver direction of the sensor (current bracket specification Tx).  

Once calibration is fully completed, an execution mark appears on the left side of the step, and all motion stops.  


### (4) Calbration Information

Navigate to `[F2: System] – 4: Application Parameters – 6: Laser Point Sensing – 2: Calibration` to check the calibration results.
When the value in the **Calibration done** field changes to "2", it indicates that all calibration processes, including interpolation, have been completed.  
Calibration information is stored per tool number, which is useful when using tool change functions.
If the tool information is the same but a different tool number is to be used, the calibration data can be copied and reused.

<br/>

<p align="center">
 <img src="../../_assets/8_8_2_3.png" width="80%"></img>
 <em><p align="center">Figure 8.8.2.3 Calibration Result</p></em>
</p><br/>  


