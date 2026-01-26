# 8.8.3 Using the LPS Function  


{% hint style="warning" %}
If tool-to-sensor calibration (ref. 8.8.2) has not been performed before using this function, invalid poses may be stored.
{% endhint %}

### Property Window

The properties of the LPS command are as follows.  
<br/>

<p align="center">
  <img src="../../_assets/8_8_3_0.png" width="80%"></img>
  <em><p align="center">Figure 8.8.3.0 LPS Property</p></em>
</p><br/>  

#### Gap Coefficient

  This parameter is used to detect step differences in **Step mode (stepp)** and allows the user to specify the detected height difference.
  However, this parameter is not used during the calibration process, as a separate calibration specimen is used.

#### Step Sensitivity

  This parameter sets the data processing sensitivity based on repeatability.
  In most cases, users can use the default value, and no additional adjustment is required.

#### Slope Threshold (Slope Degree)

  This parameter is used to detect edges.
  In addition to the step coefficient, it can be configured during tool-to-sensor calibration operations and step detection.
  Since edges are not always vertical, this parameter allows the system to respond to sloped surfaces.

#### Pose Coordinates / Shift Coordinates

  This setting specifies the coordinate system in which data is stored when each mode is executed.
  In particular, Shift Coordinates are used when Master mode is enabled.

<br/>

### (1) Spot Mode  

**Spot mode** is used to verify calibration results or to obtain the pose of the position currently indicated by the laser.  

<br/>

<p align="center">
  <img src="../../_assets/8_8_3_1.png" width="60%"></img>
  <em><p align="center">Figure 8.8.3.1 Spot Mode</p></em>
</p><br/>  

```py
  var p10=cpo()
  lps spot,cnd=1,pose=p10
  move L,tg=p10,spd=10%,acc=0,tool=0
```

{% hint style="warning" %}
  In this case, only the position is recorded in the pose specified by the sp parameter.
  The tool orientation (Rx, Ry, Rz) prior to sensing is not preserved.
{% endhint %}

<br/>


### (2) Step Mode

**Step Mode** is used to detect positions where a height difference occurs on the base material.
Depending on whether the height difference is lower or higher, the scan direction should be reserved accordingly.  

<br/>

<p align="center">
  <img src="../../_assets/8_8_3_2.png" width="60%"></img>
  <em><p align="center">Figure 8.8.3.2 Step Mode</p></em>
</p><br/>  

```py
  var p10=cpo()
  lps stepp,cnd=1,Tx=50,spd=5,pose=p10
  move L,tg=p10,spd=10%,acc=0,tool=0
```


The system moves by the specified distance in the X or Y direction based on the tool while searching for a step difference.
If no step is detected within the specified distance, a detection error occurs.  

<br/>


### (3) Scan Mode

<p align="center">
 <img src="../../_assets/8_8_3_3.png" width="80%"></img>
 <em><p align="center">Figure 8.8.3.3 Scan Mode on various geometries</p></em>
</p><br/>  

```py
  var p10=cpo()
  lps scan,cnd=1,Ty=50,spd=5,pose=p10
  move L,tg=p10,spd=10%,acc=0,tool=0
```

Scan mode detects weld points while moving by the specified distance in the X or Y direction based on the tool.
It can be executed with a single command regardless of the joint geometry, such as fillet, V-groove, or butt joints.
Detection results can be retrieved via the REST API, or verified by registering and using the application provided by our company.  

For instructions on how to register and use the application, please refer to the following link: [Software Development Kit (SDK)](https://hrbook-hrc.web.app/#/view/doc-hi6-sdk/en/README?cont_model=${cont_model})  


{% hint style="warning" %}
  Set the movement distance sufficiently to include the weld seam, and ensure that the tool motion is not parallel to the scanned surface.
{% endhint %}  


#### (3-1) Monitoring Screen  

<p align="center">
  <img src="../../_assets/8_8_3_4.png" width="80%"></img>
  <em><p align="center">Figure 8.8.3.4 LPS Graph</p></em>
</p><br/>  

After registering the application, the monitoring screen can be accessed through the following method: `[Pane layout] - select - LPS Graph` 

<br/>

<p align="center">
  <img src="../../_assets/8_8_3_5.png" width="80%"></img>
  <em><p align="center">Figure 8.8.3.5 Example screen - V-groove</p></em>
</p><br/>  

<p align="center">
  <img src="../../_assets/8_8_3_6.png" width="80%"></img>
  <em><p align="center">Figure 8.8.3.6 Example screen - Butt joint</p></em>
</p><br/>  


When the function is executed, results can be viewed as shown in the figure above.
The currently provided screen offers the following features:  

1. The screen can be refreshed by clicking the Refresh button in the upper-left corner.
2. The numeric value displayed in the upper-right corner represents the real-time output value of the laser sensor.
3. The calculated weld point is indicated by a red dot.

