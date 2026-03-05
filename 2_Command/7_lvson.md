# 2.7 lvs

### Description 

```lvs``` command uses the LVS(Laser Vision Sensor) to perform functions such as obtaining the pose of the laser position(`seam_find`), start point detection(`search`), and seam tracking(`track`).
<br/>

### Syntax

```python
    lvs laser_on, cnd=<Condition Number>, seam=<Seam Number>, sp=<Seam Pose>
    lvs laser_off, cnd=<Condition Number>, seam=<Seam Number>, sp=<Seam Pose>
    lvs search, cnd=<Condition Number>, seam=<Seam Number>, sp=<Seam Pose>
    lvs track, cnd=<Condition Number>, seam=<Seam Number>, sp=<Seam Pose>
    lvs seam_find, cnd=<Condition Number>, seam=<Seam Number>, sp=<Seam Pose>
    lvs auto_calib, cnd=<Condition Number>, seam=<Seam Number>, sp=<Seam Pose>, opt=0
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
      <td rowspan="10">lvs</td>
      <tr>
        <td>laser_on</td>
        <td> Turns on the laser </td>
      </tr>
      <tr>
        <td>laser_off</td>
        <td> Turns off the laser </td>
      </tr>
      <tr>
        <td>search</td>
        <td> Finds the starting point before performing the track function and prepares for tracking </td>
      </tr>
      <tr>
        <td>step_search</td>
        <td> Find the step difference of the base material and saves it as a pose in the `sp`. </td>
      </tr>
      <tr>
        <td>track</td>
        <td> Starts following the welding line when `arcon` is encountered (must have executed `search` first) </td>
      </tr>
      <tr>
        <td>track_stationary</td>
        <td> Performs stop tracking function. </td>
      </tr>
      <tr>
        <td>seam_find</td>
        <td> Reflects the current position of the laser sensing location and converts it to a pose, then saves it to the `sp`. </td>
      </tr>
      <tr>
        <td>seam_find_p</td>
        <td> Converts the current laser sensing location to a pose, and saves it to the `sp`. </td>
      </tr>
      <tr>
        <td>auto_calib</td>
        <td> Performs automatic calibration between the tool and the LVS Sensor. </td>
      </tr>
    </tr>
    <tr>
      <td colspan="2">Condition Number</td>
      <td> The condition number used when performing the LVS function (1 ~ 32). The properties window for each condition number is different, and this information is used during tracking. </td>
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">Seam Number</td>
      <td>Specifies the seam number. This number is sent to the LVS controller, and the LVS sensor senses the seam corresponding to this number</td>
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">Seam Pose</td>
      <td> Specifies the pose variable to save the pose found by `seam_find` or the pose found after `search` </td>
      <td>Pose Variable</td>
    </tr>
  </tbody>
</table>  

### Example

```python
    lvs seam_find, cnd=1, seam=10, sp=p10    
    # Perform seam finding with condition number 1 and seam number 10, saving the resulting pose in p10
    lvs track, cnd=1 ,seam=10 , sp=p10
    # Start LVS seam tracking with condition number 1 and seam number 10
```  


{% hint style="info" %}
  For use as an optional feature, please contact our company.
{% endhint %}


### Details  

  Refer to [[8.5 LVS(Laser Vision Sensor) Seam Finding and Tracking]](../8_Application_function/5_LVS_tracking/README.md)
