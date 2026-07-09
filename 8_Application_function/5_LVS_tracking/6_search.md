# 8.5.6 LVS Search Func.

### (1) How to Use the Search Function
LVS provides a search function, and searching must precede tracking.

- `search`: Searches for the starting point end, while the TCP (Tool Center Point) moves to the starting position, stores, the points to be tracked in a buffer at set intervals, preparing for tracking.
- `step_search`: Used for multi-pass bead detection and step detection

When search is performed, search is executed, and depending on the option, it operates as follows:

(1) Above Laser
The TCP moves to the position of the laser, stores tracking points in the buffer, and completes the tracking preparation.

(2) Detect
It moves by the search distance in the search direction, detects the point where sensing is impossible, and the TCP moves to the position immediately preceding that point, stores tracking points in the buffer, and completes the tracking preparation.

By performing the search function, the system becomes ready to perform "seam tracking". 

Search is used as follows.

```python
  move L, spd=60%, accu=0, tool=1
  delay 0.1 #If the accu at the search start position is not 0, insertion is required.
  var po_100=cpo() #Stores the current pose in the declared variable po_100.
  lvs search, cnd=1, seam=1, sp=po_100 #Tracking ready
```

To configure the search function, enter **[property]** in the `lvs` command, where the search settings can be adjusted as follows:


![](../../_assets/8_5_14_lvs_search_setting.png)<br>
*Figure 8.5.14. lvs search settings*   
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
      <td style="text-align:left">function</td>
      <td style="text-align:left">
        Sets the use of the search function.<br>
        'Laser Above' : Moves to the laser position of lvs and saves target positions in the buffer.<br>
        'Detect': After detecting unsensable points in the search direction, move to the position immediately prior to detection and save the target positions in the buffer.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">distance</td>
      <td style="text-align:left">
       Enter the maximum seek distance [mm].
      </td>
    </tr>
    <tr>
      <td style="text-align:left">direction</td>
      <td style="text-align:left">
       0 : Navigates in the +ToolX direction.<br>
       1 : Navigates in the -ToolX direction.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">speed</td>
      <td style="text-align:left">
        Set the search speed in mm/sec units.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">offset</td>
      <td style="text-align:left">
        You can shift the point found in the direction of the weld line from the search point by a set amount of mm.
      </td>
    </tr>
  </tbody>
</table>

![](../../_assets/8_5_15_lvs_search_example.png)<br>
*Figure 8.5.15. lvs search Example*   
</br>

If a variable is assigned to find_flag, 1 is stored on a successful search and 0 on a failed search. Please note that the lvs command is marked as completed if the search fails.

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