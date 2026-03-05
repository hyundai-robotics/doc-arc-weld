# 2.8 lps

### Description 

```lps``` command is used to perform functions such as obtaining the pose of the laser position using a laser distance sensor (Spot Mode), detecting step differences (Step mode), and searching for a weld seam (Scan mode).

<br/>

### Syntax

```python
    lps auto_calib, cnd=<Condition Number>, Tx=<Movement Distance in the X-dir based on the tool>, Ty=<Movement Distance in the Y-dir based on the tool>
    lps spot, cnd=<Condition Number>, sp=<Stored Pose>
    lps stepp, cnd=<Condition Number>, Tx=<Movement Distance in the X-dir based on the tool>, Ty=<Movement Distance in the Y-dir based on the tool>, spd=<Robot Speed>, sp=<Stored Pose>
    lps scan, cnd=<Condition Number>, Tx=<Movement Distance in the X-dir based on the tool>, Ty=<Movement Distance in the Y-dir based on the tool>, spd=<Robot Speed>, sp=<Stored Pose>
    # When Using Master / Production Mode
    lps scan, cnd=<Condition Number>, Tx=<Movement Distance in the X-dir based on the tool>, Ty=<Movement Distance in the Y-dir based on the tool>, spd=<Robot Speed>, sp=<Stored Pose>, mp=<Pose to save in Master Mode>, ms=<Shift Variable Calculated in Production Mode>
```  

### Parameter

<table>
  <thead>
    <tr>
      <th>Major Category</th>
      <th>Sub Category</th>
      <th>Meaning</th>
      <th>Remarks</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="5">lps</td>
      <tr>
      <td>auto_calib</td>
      <td>
        Performs automatic calibration between the tool and the sensor.
      </td>
      </tr>
      <tr>
      <td>spot</td>
      <td>
        In Spot mode, the pose of the position currently indicated by the laser is obtained.
      </td>
      </tr>
      <tr>
      <td>stepp</td>
      <td>
        In Step mode, the pose of the position where the output value changes abruptly while the laser is moving is obtained.
      </td>
      </tr>
      <tr>
      <td>scan</td>
      <td>
        In Scan mode, the pose of the position estimated to be a weld point along the laser movement path is obtained.
      </td>
      </tr>
    </tr>
    <tr>
      <td colspan="2">cnd</td>
      <td>
        Condition numbers (1 to 8) used when executing the LPS function.
        The information displayed in the command property window varies depending on the condition number.
        This information is used for sensitivity settings in Automatic Calibration and Step mode, and coordinate system configuration when storing poses.
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">Tx / Ty</td>
      <td>
        Sets the movement distance in the X or Y direction based on the tool.
        Except for auto_calib, only one of the two values must be entered.
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">spd</td>
      <td>
        Specifies the speed at which the robot moves while executing the operation.
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">sp</td>
      <td>
        Specifies the pose variable in which the current pose found by each command is stored.
      <td>Pose Variable</td>
    </tr>
    <tr>
      <td colspan="2">mp</td>
      <td>
        In Master mode, the sensing result is stored in mp (master pose).
        In Production mode, it is used to calculate ms (master shift).
      <td>Pose Variable</td>
    </tr>
    <tr>
      <td colspan="2">ms</td>
      <td>
        A shift variable used in Production mode.
        The difference between the master pose (mp parameter) and the currently sensed pose (sp parameter) is calculated and stored.
      <td>Shift Variable</td>
    </tr>
  </tbody>
</table>  


### Example

```python
    lps auto_calib, cnd=1, Tx=50, Ty=-100
    # Performs Automatic Calibration within the specified distance range of +50 in the X direction and -100 in the Y direction, based on the tool, using condition number 1
    lps spot, cnd=1, sp=p10
    # Using condition number 1, stores the pose of the current laser position in p10, based on the coordinate system defined in the condition settings.
    lps stepp, cnd=1, Tx=50, sp=p10
    # Using condition number 1, moves 50[mm] in the X direction based on the tool, stops immediately when a step difference is detected, and stores the pose in p10.
    lps scan, cnd=1, Tx=50, spd=10, sp=p10
    # Using condition number 1, moves 50[mm] in the X direction based on the tool at a speed of 10, detects the weld point upon completion of the movement, and stores it in p10.
    # 조건 번호 1번, 툴 기준 X 방향으로 50만큼 설정된 거리만큼 이동이 완료되면 용접점을 검출하여 p10에 저장
    
    lps scan, cnd=1, Tx=50, spd=10, sp=p10, mp=mp10, ms=ms10
    # When using Master mode: Using condition number 1, moves 50[mm] in the X direction based on the tool at a speed of 10, detects the weld point upon completion of the movement, stores it in p10, compares it with mp10, and saves the calculated shift value in ms10.
```  


{% hint style="info" %}
To use this function as an optional feature, please contact our company.
{% endhint %}


### Details

  Refer to [8.8 LPS(Laser Point Sensing)](../8_Application_function/8_LPS/README.md)
