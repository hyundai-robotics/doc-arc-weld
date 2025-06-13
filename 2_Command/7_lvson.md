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
<br/>

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
<br/>

### Example

```python
   lvs seam_find, cnd=1, seam=10, sp=p10    
   # 조건번호 1번, seam번호 10번으로 seam 파인딩 기능 수행, 결과포즈는 p10에 저장
   lvs track, cnd=1 ,seam=10 , sp=p10           
   # 조건번호 1번, seam번호 10번으로 LVS 용접선 추종 시작
```  
<br/><br/>


{% hint style="info" %}
옵션 기능으로 사용을 위해서는 당사에 문의하시기 바랍니다.
{% endhint %}
