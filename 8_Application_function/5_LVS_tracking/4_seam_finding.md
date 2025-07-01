# 8.5.4 LVS Seam Finding Func.

### (1) Seam Finding Overview

This function stores the position sensed by the LVS as a pose, and can be used as a substitute for touch sensing.

{% hint style="warning" %}
  If the TCP-LVS sensor calibration has not been performed before using this function, an abnormal pose will be saved.
{% endhint %}

The command format is as follows:  
After executing this, as shown below, the position sensed by the LVS will be stored in the po_100 variable.

```python
  var po_100=cpo()  # The current pose is stored in the variable po_100
  lvs seam_find, cnd=1, seam=1, sp=po_100 # If there is no variable with the name entered in the sp parameter, it will be automatically declared as a local pose variable.
```

{% hint style="warning" %}
  If the **sp** parameter is not declared, it will be declared as a local pose. <br>
  If the **mp** parameter is not declared, it will be declared as a global pose. <br>
  If the **ms** parameter is not declared, it will be declared as a global shift.
{% endhint %}


<p align="center">
 <img src="../../_assets/8_5_9_lvs_seamfind_ex.png" width="80%"></img>
 <em><p align="center">Figure 8.5.9. Pose in the LVS sensing position</p></em>
</p>   
</br>

{% hint style="info" %}
  - The orientation of the pose stored in the sp parameter with the **seam_find** command will maintain the tool's orientation (Rx, Ry, Rz) before sensing.
  - On the other hand, with the **seam_find_p** command, only the position is recorded in the pose stored in the sp parameter.
{% endhint %}

* If you want to store only the position in the pose regardless of the pre-sensing orientation, use the following command format.<br>
This function is useful when you want to record the welding posture in the pose and then make the position (X, Y, Z) correspond to the point sensed by the LVS.

```python
var po_100=cpo()
lvs seam_find_p, cnd=1, seam=1, sp=po_100
```

* The pose shifted in the direction of Tool Y and Tool Z from the sensed position can be calculated as follows. <br>
This command calculates a pose that has shifted by 10mm in the Tool Y direction and 10mm in the Tool Z direction, based on the tool orientation during sensing.

```python
var po_100=cpo()
lvs seam_find, cnd=1, seam=1, side=10, height=10, sp=po_100
```

---

### (2) LVS Seam Finding Retry

If the seam cannot be recognized during seam finding, a retry will be performed. 

The number of retries is specified in the **"no of retry"** under the Seam finding option in the LVS command's properties window.

If sensing is still impossible after the specified number of retries, an error will occur.

The retry process is performed in the following sequence:

<p align="center">
 <img src="../../_assets/8_5_10_lvs_seamfind_retry.png" width="60%"></img>
 <em><p align="center">Figure 8.5.10. LVS Seam Finding Retry</p></em>
</p>   
</br>

{% hint style="warning" %}
* When using the master-shift function, be aware that retries will cause the position to shift forward and backward(by +ToolX, -ToolX).
{% endhint %}

---

### (3) LVS Seam Finding Monitoring

To view the LVS seam finding monitoring screen, click **[pane layout > select > LVS seamfind]** in the TP  


<p align="center">
 <img src="../../_assets/8_5_11_seamfind monitoring.png" width="60%"></img>
 <em><p align="center">Figure 8.5.11. LVS Seam Finding Monitoring</p></em>
</p>   
</br>
<table>
  <thead>
    <tr>
      <th style="text-align:left">Item</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Position (X, Y, Z)</td>
      <td style="text-align:left">
        Displays the current sensed position (in base coordinates)<br>
        Spec : The position of the master pose. If not registered, it will display as (-1, -1, -1)<br>
        Sensing : Current sensed position 
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Gap</td>
      <td style="text-align:left">
        Spec : Master gap [mm]<br>
        Sensing : Current sensed gap [mm]
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Area</td>
      <td style="text-align:left">
        Internal area width of groove or butt shape [mm^2]<br>
        Spec : Master area [mm]<br>
        Sensing : Current sensed area [mm]
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Mismatch</td>
      <td style="text-align:left">
        Mismatch value typically refers to the height difference of the left-right shape.
      </td>
    </tr>
  </tbody>
</table>

{% hint style="info" %}
  Gap, area, mismatch, and similar values are displayed only for seams supported by the manufacturer's LVS controller.
{% endhint %}

If the master pose is registered, you can check the sensing history for the current job by pressing prev or next button.

{% hint style="info" %}
  For more details on the master mode, please refer to [8.5.5 LVS Master mode func.](./5_lvs_master_mode.md).
{% endhint %}

