# 2.7 lvs

### Description 

```lvs``` 命令使用 LVS(激光视觉传感器) 执行功能，例如获取激光位置的姿态(`seam_find`)、起始点检测(`搜索 (search)`)和缝线跟踪(`track`)。
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
        <td>`laser_on`</td>
        <td> 打开激光 </td>
      </tr>
      <tr>
        <td>`laser_off`</td>
        <td> 关闭激光 </td>
      </tr>
      <tr>
        <td>`搜索 (search)`</td>
        <td> 在执行跟踪功能之前找到起始点并为跟踪做准备 </td>
      </tr>
      <tr>
        <td>`step_search`</td>
        <td> 找到基材的步骤差，并将其保存为姿态在 `sp` 中。 </td>
      </tr>
      <tr>
        <td>`track`</td>
        <td> 当遇到 `arcon` 时开始跟随焊接线（必须先执行 `搜索 (search)`） </td>
      </tr>
      <tr>
        <td>`track_stationary`</td>
        <td> 执行停止跟踪功能。 </td>
      </tr>
      <tr>
        <td>`seam_find`</td>
        <td> 反映激光感应位置的当前位置并转换为姿态，然后保存到 `sp` 中。 </td>
      </tr>
      <tr>
        <td>`seam_find_p`</td>
        <td> 将当前激光感应位置转换为姿态，并保存到 `sp` 中。 </td>
      </tr>
      <tr>
        <td>`auto_calib`</td>
        <td> 执行工具与 LVS 传感器之间的自动校准。 </td>
      </tr>
    </tr>
    <tr>
      <td colspan="2">Condition Number</td>
      <td> 执行 LVS 功能时使用的条件编号 (1 ~ 32)。每个条件编号的属性窗口不同，这些信息在跟踪期间使用。 </td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">Seam Number</td>
      <td>指定缝线编号。该编号发送到 LVS 控制器，LVS 传感器感应与该编号对应的缝线</td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">Seam Pose</td>
      <td> 指定用于保存 `seam_find` 找到的姿态或 `搜索 (search)` 后找到的姿态的姿态变量 </td>
      <td>姿态变量</td>
    </tr>
  </tbody>
</table>  

### Example

```python
    lvs seam_find, cnd=1, seam=10, sp=p10    
    # 使用条件编号 1 和缝线编号 10 执行缝线查找，将结果姿态保存到 p10
    lvs track, cnd=1 ,seam=10 , sp=p10
    # 使用条件编号 1 和缝线编号 10 启动 LVS 缝线跟踪
```  


{% hint style="info" %}
  作为可选功能使用，请联系我们的公司。
{% endhint %}


### Details  

  参考 [[8.5 LVS(激光视觉传感器) 缝线查找和跟踪]](../8_Application_function/5_LVS_tracking/README.md)