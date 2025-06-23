# 8.5.7 LVS Tracking Func. and Monitoring

### (1) LVS Tracking Overview

LVS Tracking is a function that compensates for the different between the taught trajectory and the actual welding line.

{% hint style="warning" %}
The reference teaching for the base workpiece should be performed with high precision.<br>
After applying the shift to correct the positioning error of the workpiece, the LVS function should be used.<br>
For further details, please refer to [8.5.5 LVS Master Mode Func.].
{% endhint %}

Since the laser is mounted in front of the TCP, a search must be performed first to carry out tracking.

{% hint style="info" %}
  Please refer to the previous section, **[8.5.6 LVS Search Func.]**, for detailed information about the search function.
{% endhint %}


The configuration of the lvs command should be set as follows:

```python
    move L, spd=60%, accu=0, tool=1
    delay 0.3
    var po_100=cpo() # The current pose is stored in the variable po_100
    lvs search, cnd=1, seam=1, sp=po_100
    weavon cnd=1  
    arcon cnd=1
    lvs track, cnd=1, seam=1, sp=po_100
    move L, spd=30cm/min, accu=3, tool=1
    move L, spd=36cm/min, accu=3, tool=1
    move L, spd=40cm/min, accu=3, tool=1
    weavoff
    arcof
    end
```

The processs of executing the search command is illustrated in the following figure (when search is set to valid and direction is set to 0).
An invalid point is found and stored in the `sp` parameter as the starting point, then the TCP moves to the starting point while filling the data buffer. 

<p align="center">
 <img src="../../_assets/8_5_17.png" width="80%"></img>
 <em><p align="center">Figure 8.5.17. LVS search process</p></em>
</p>   
</br>

### (2) How to Use Tracking with an Offset Value

If you want to track with an offset from the seam (instead of exactly following the welding line), you can specify the offset values for side and height in the `lvs` command in mm units. The offset is applied in the tool coordinate system direction.


```python
    move L, spd=60%, accu=0, tool=1
    delay 0.3
    var po_100=cpo() # The current pose is stored in the variable po_100
    lvs search, cnd=1, seam=1, sp=po_100
    weavon cnd=1  
    arcon cnd=1
    lvs track, cnd=1, seam=1, sp=po_100, side=5, height=-5 # offset tracking with 5mm in the ToolX, and -5mm in the ToolZ
    move L, spd=30cm/min, accu=3, tool=1
    move L, spd=36cm/min, accu=3, tool=1
    move L, spd=40cm/min, accu=3, tool=1
    weavoff
    arcof
    end
```

{% hint style="info" %}
* When using weaving, the stickout length increases depending on the angle and amplitude. To compensate for this, set the height with a negative value during both search and track operations.
{% endhint %}

### (3) LVS Monitoring

<p align="center">
 <img src="../../_assets/8_5_18_tracking_monitoring.png" width="80%"></img>
 <em><p align="center">Figure 8.5.18. LVS Monitoring</p></em>
</p>   
</br>


LVS Monitoring can be activated by selecting **[pane layout > select > LVS tracking]**.

In the monitoring, the follwing items can be checked:


| Item | Description |
|------|------|
| Total Cumulative Compensation<br> (X, Y, Z) | If weaving is not used, this represents the cumulative compensation relative to the base coordinate system. If weaving is used, it refers to the cumulative compensation in the weaving corrdinate syste. |
| Sensor | qual: Indicates whether the current laser seam sensing is valid or invalid.<br> Y, Z: The position of the currently sensed seam in the sensor image coordinate system(2D). |
| Tool Tip | The current position of the TCP relative to the base coordinate system. | 
| Tracking Point | The point that the TCP is currently tracking, relative to the base coordinate system. |
| Sensing Point | The base coordinate value of the location currently being sensed by the laser. |
| Buffer Size | The number of points stored in the buffer for tracking. If this value keeps increasing, decreasing, or reaches 0, there may be a problem with tracking, communication, or configuration. |
| Information | Displays the progress of the auto-calibration and other relevant information. |
| Real-time Image | Displays the points to be tracked, represented by red circles, that are stored in the buffer. |

