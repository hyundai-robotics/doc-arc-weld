# 8.5.6 LVS Search Func.

### (1) How to Use the Search Function

LVS provides a search function, which is used for the following purposes:

- `search`: Searches for the starting point end, while the TCP (Tool Center Point) moves to the starting position, stores, the points to be tracked in a buffer at set intervals, preparing for tracking.
- `step_search`: Used for multi-pass bead detection and step detection

When a search is performed, the system searches for the target, and if an invalid point is detected, the most recent valid point is stored as the pose in the `sp` parameter.

Subsequently, in order to prepare for tracking, the system stores the points to be followed in a buffer as the TCP moves to the found point.

By performing the search function, the system becomes ready to perform "seam tracking". 

{% hint style="info" %}
  The search process detects invalid seams (when the LVS controller cannot detect a seam) and searches for the starting point.
  The **search** function finds the start(or end), then moves to that location, storing the points to be tracked in a buffer.
{% endhint %}


```search``` function is used as follows:

```python
    move L, spd=60%, accu=0, tool=1
    delay 0.1 # if the accuracy of the starting position is not 0, it must be inserted.
    var po_100=cpo() # The current pose is stored in the variable po_100
    lvs search, cnd=1, seam=1, sp=po_100
```

To configure the search function, enter **[property]** in the `lvs` command, where the search settings can be adjusted as follows:


<p align="center">
 <img src="../../_assets/8_5_14_lvs_search_setting.png" width="80%"></img>
 <em><p align="center">Figure 8.5.14. lvs search settings</p></em>
</p>   
</br>

| Item | Description |
|------|------|
| function | Set the usage of the search function. <br> 'Disable': The system moves to the laser position of the LVS and stores the target positions in a buffer. <br> 'Enable': The system detects both the starting and ending points in the search direction, then moves to the detected location while storing the target positions in the buffer. |
| distance | If the search function is set to **enable**, the maximum distance for searching the starting point should be entered [mm]. |
| direction | 0: Search in the +ToolX direction. <br> 1: Search in the -ToolX direction. |
| speed | The search speed can be set in mm/sec. |
| offset | Points found in the direction of the welding line can be shifted by the specified number of mm from the detected position. |

<br>

<p align="center">
 <img src="../../_assets/8_5_15_lvs_search_example.png" width="80%"></img>
 <em><p align="center">Figure 8.5.15. lvs search Example</p></em>
</p>   
</br>

The **search** and **seam tracking** functions can be taught as shown below.

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

---

### (2) How to Use the Multi-pass Bead Detection Function (step_search) 


This function is used to detect the starting point of a multi-pass bead, and its usage is identical to the `search` function.

In the **[property]** window of the `lvs` command, set the function to "Enable" and configure the scan distance in the "distance" field.

It can be used as follows:

```python
    move L, spd=60%, accu=0, tool=1 # Set the starting point for the multi-pass bead detection scan.
    delay 0.3
    var po_100=cpo() # The current pose is stored in the variable po_100
    lvs step_search, cnd=1, seam=1, sp=po_100
    move L, tg=po_100, spd=40cm/min, accu=3, tool=1 # Move to the found location.
    end
```