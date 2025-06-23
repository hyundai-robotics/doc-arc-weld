# 8.5.1 LVS Overview and Specifications

{% hint style="info" %}
This feature is available during from version 60.30-03.
{% endhint %}

This function performs real-time compensation for workpiece and jig errors by recognize the welding seam using an LVS(Laser Vision Sensor), thereby enabling seam tracking during welding.

The LVS must be directly connected to the robot's flange. The sensor detects the welding seam, and the robot's tool tracks the seam in real-time.

In other words, through seam tracking, welding can still be performed even if the position of the welding target changes and deviates from the original reference points.


<p align="center">
 <img src="../../_assets/8_5_1.png" width="90%"></img>
 <em><p align="center">Figure 8.5.1. LVS Seam Tracking Flowchart</p></em>
</p>

</br>

## 명령어 Command

LVS 용접선 검출 및 추적 기능은 ```lvs``` 명령어를 통해 수행하며 TP의 **[명령입력 > 아크 > lvs]** 를 입력하여 명령어를 입력할 수 있습니다.

The LVS Seam Finding and Tracking function is executed through the `lvs` command, which can be entered by selecting **[cmd. input > arcweld > lvs]** in the TP.

The structure of the command is as follows:

```python
lvs <function argument> cnd=<condition Number>, seam=<profile number to be sensed position>, sp=<pose variable of the sensed position>, mp=<pose variable of the master reference>, ms=<shift variable of the current sensing position relative to the master>
```

<table>
  <thead>
    <tr>
      <th>Major Category</th>
      <th>Sub Category</th>
      <th>Meaning</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="9">function argument</td>
    </tr>
    <tr>
      <td style="text-align:left">laser_on</td>
      <td style="text-align:left">Turn on the laser.</td>
    </tr>
    <tr>
      <td style="text-align:left">laser_off</td>
      <td style="text-align:left">Turn off the laser.</td>
    </tr>
    <tr>
      <td style="text-align:left">seam_find</td>
      <td style="text-align:left">
        The seam position of the laser currently being sensed by the sensor is stored in the pose variable specified by the 'sp' argument of the command (robot/base coordinate system). <br>
        Note that the orientation(RX, RY, RZ) is recorded as the tool's orientation at the time the command is executed.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">seam_find_p</td>
      <td style="text-align:left">
        The seam position of the laser currently being sensed by the sensor is stored in the pose variable specified by the 'sp' argument of the command (robot/base coordinate system). <br>
        Note that the orientation(RX, RY, RZ) remains as the original pose variable, and only the X, Y, and Z values are updated. <br>
        This is particularly useful when using functions such as 'intersection', where the intersection point is determined using three points to calculate the pose.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">auto_calib</td>
      <td style="text-align:left">
        Performs auto-calibration between TCP and LVS.(refer to <a href="https://hrbook-hrc.web.app/#/view/doc-arc-weld/english/8_Application_function/5_LVS_tracking/3_calibration">LVS Calibration</a>)
      </td>
    </tr>
    <tr>
      <td style="text-align:left">search</td>
      <td style="text-align:left">
        The starting point is found while moving in the +ToolX, -ToolX directions, and tracking preparation is performed. <br>
        The detected starting point is stored in the pose variable specified by the 'sp' argument of the command.
        (refer to <a href="https://hrbook-hrc.web.app/#/view/doc-arc-weld/english/8_Application_function/5_LVS_tracking/6_search">LVS search func.</a>)
      </td>
    </tr>
    <tr>
      <td style="text-align:left">step_search</td>
      <td style="text-align:left">
        The starting point or the start point of a multi-bead is found while moving int the +ToolX, -ToolX directions. <br>
        The detected starting point is stored in the pose variable specified by the 'sp' argument of the command.
        (refer to <a href="https://hrbook-hrc.web.app/#/view/doc-arc-weld/english/8_Application_function/5_LVS_tracking/6_search">LVS search func.</a>)
      </td>
    </tr>
    <tr>
      <td style="text-align:left">track</td>
      <td style="text-align:left">
        After the search is completed, the 'arcon' and 'weaving on' actions must be performed before executing. <br>
        Tracking continues until 'arcoff' is encountered.
      </td>
    </tr>
    <tr>
      <td colspan="2">condition Number</td>
      <td>
        This is the condition number used to apply the the settings configured in the peroperties window of the lvs command. <br>
        The properties window allows you to set search speed, search distance, queue interval, tracking limit, and sensing coordinate system(robot/base), among others.
      </td>
    </tr>
  <tr>
      <td colspan="2">profile number to be sensed position</td>
      <td>
        This refers to the number corresponding to the sensing shape and sensing conditions registered by the user in the LVS controller. 
        When the command is executed, the LVS controller loads the sensing shape and conditions associated with this number.
      </td>
    </tr>
    <tr>
      <td colspan="2">pose variable of the sensed position</td>
      <td>
        The position corresponding to the current laser location is stored as a pose variable.
      </td>
    </tr>
    <tr>
      <td colspan="2">pose variable of the master position</td>
      <td>
        This is the reference pose variable registered in master mode.
        (refer to <a href="https://hrbook-hrc.web.app/#/view/doc-arc-weld/english/8_Application_function/5_LVS_tracking/5_lvs_master_mode">8.5.5 LVS Master mode func.</a>)
      </td>
    </tr>
    <tr>
      <td colspan="2">shift variable of the current sensing position relative to the master</td>
      <td>
        The shift of the current sensed position relative to the mp(master pose) is stored.
        (refer to <a href="https://hrbook-hrc.web.app/#/view/doc-arc-weld/english/8_Application_function/5_LVS_tracking/5_lvs_master_mode">8.5.5 LVS Master mode func.</a>)
      </td>
    </tr>
  </tbody>
</table>  
<br/>


The tracking function using the ```lvs``` command can be used as follows:


<p align="center">
 <img src="../../_assets/8_5_2.png" width="60%"></img>
 <em><p align="center">Figure 8.5.2. Teaching Method for LVS Seam Tracking</p></em>
</p>


---

## LVS 기능 사양 LVS Function Specifications

* General motion tracking functionality supported (Linear L interpolation, Circular C interpolation, and composite linear and circular segments)
* Weaving tracking functionality supported (0.5Hz ~ 3Hz)
* Positioner synchronized tracking functionality supported (SMOV segment)
* Positioner synchronized + Weaving tracking functionality supported (0.5Hz ~ 3Hz)


<table>
  <thead>
    <tr>
      <th style="text-align:left">Item</th>
      <th style="text-align:left">LVS Manufacturer</th>
      <th style="text-align:left">Repetition Accuracy</th>
      <th style="text-align:left">Repetition Precision</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">seam_find / seam_find_p</td>
      <td style="text-align:left">SCANSONIC (350, 150, 150 advanced)</td>
      <td style="text-align:left">Left/Right : 0.1 mm (Reference +- 30mm height),  0.4mm<br>Height : 0.4mm (Reference +- 30mm height), 2mm<br>Front/Back : 0.4mm (Reference +- 30mm height), 1.5mm</td>
      <td style="text-align:left">0.05 mm</td>
    </tr>
    <tr>
      <td style="text-align:left">seam_find / seam_find_p</td>
      <td style="text-align:left">OXFORD (OSL-50)</td>
      <td style="text-align:left">Left/Right : 0.4 mm (Reference +- 30mm height),  0.7mm<br>Height : 0.6mm (Reference +- 30mm height), 3mm<br>Front/Back : 0.6mm (Reference +- 30mm height), 2.5mm</td>
      <td style="text-align:left">0.2 mm</td>
    </tr>
    <tr>
      <td style="text-align:left">seam_find / seam_find_p</td>
      <td style="text-align:left">Full-v</td>
      <td style="text-align:left">Left/Right : 0.6 mm (Reference +- 30mm height),  2mm<br>Height : 0.8mm (Reference +- 30mm height), 4.5mm<br>Front/Back : 0.6mm (Reference +- 30mm height), 4mm</td>
      <td style="text-align:left">0.35 mm</td>
    </tr>
    <tr>
      <td style="text-align:left">track</td>
      <td style="text-align:left">SCANSONIC (350, 150, 150 advanced)</td>
      <td style="text-align:left">0.2mm (Linear)<br>0.4mm (weaving)<br>0.25mm (positioner synchronized)<br>0.5mm (weaving + positioner synchronized)</td>
      <td style="text-align:left">0.05 mm</td>
    </tr>
    <tr>
      <td style="text-align:left">track</td>
      <td style="text-align:left">OXFORD (OSL-50)</td>
      <td style="text-align:left">0.3mm (Linear)<br>0.5mm (weaving)<br>0.4mm (positioner synchronized)<br>0.6mm (weaving + positioner synchronized)</td>
      <td style="text-align:left">0.2 mm</td>
    </tr>
    <tr>
      <td style="text-align:left">track</td>
      <td style="text-align:left">Full-v</td>
      <td style="text-align:left">0.3mm (Linear)<br>0.6mm (weaving)<br>0.4mm (positioner synchronized)<br>0.7mm (weaving + positioner synchronized)</td>
      <td style="text-align:left">0.35 mm</td>
    </tr>
  </tbody>
</table>