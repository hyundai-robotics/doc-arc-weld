# 2.7 lvs

### 描述 

```lvs``` 命令使用 LVS（激光视觉传感器）执行如获取激光位置的姿态（`seam_find`）、起始点检测（`搜索 (search)`）和缝迹跟踪（`track`）等功能。
<br/>

### 语法

```python
    lvs laser_on, cnd=<条件编号>, seam=<缝编号>, sp=<缝姿态>
    lvs laser_off, cnd=<条件编号>, seam=<缝编号>, sp=<缝姿态>
    lvs search, cnd=<条件编号>, seam=<缝编号>, sp=<缝姿态>
    lvs track, cnd=<条件编号>, seam=<缝编号>, sp=<缝姿态>
    lvs seam_find, cnd=<条件编号>, seam=<缝编号>, sp=<缝姿态>
    lvs auto_calib, cnd=<条件编号>, seam=<缝编号>, sp=<缝姿态>, opt=0
```   

### 参数

<table>
  <thead>
    <tr>
      <th>主要类别</th>
      <th>子类别</th>
      <th>含义</th>
      <th>备注</th>
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
        <td> 在执行追踪功能之前找到起始点并准备进行追踪 </td>
      </tr>
      <tr>
        <td>`step_search`</td>
        <td> 找到基础材料的步长差并将其作为姿态保存在 `sp` 中。 </td>
      </tr>
      <tr>
        <td>`track`</td>
        <td> 当遇到 `arcon` 时开始跟随焊接线（必须先执行 `搜索 (search)`） </td>
      </tr>
      <tr>
        <td>`track_stationary`</td>
        <td> 执行停止追踪功能。 </td>
      </tr>
      <tr>
        <td>`seam_find`</td>
        <td> 反映激光感应位置的当前姿态并将其转换为姿态，然后保存到 `sp` 。 </td>
      </tr>
      <tr>
        <td>`seam_find_p`</td>
        <td> 将当前激光感应位置转换为姿态，并保存到 `sp` 。 </td>
      </tr>
      <tr>
        <td>`auto_calib`</td>
        <td> 在工具和 LVS 传感器之间执行自动校准。 </td>
      </tr>
    </tr>
    <tr>
      <td colspan="2">条件编号</td>
      <td> 执行 LVS 功能时使用的条件编号（1 ~ 32）。每个条件编号的属性窗口不同，此信息在追踪时使用。 </td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">缝编号</td>
      <td>指定缝编号。此编号发送给 LVS 控制器，LVS 传感器感应与此编号对应的缝</td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">缝姿态</td>
      <td> 指定保存 `seam_find` 发现的姿态或 `搜索 (search)` 后发现的姿态的姿态变量 </td>
      <td>姿态变量</td>
    </tr>
  </tbody>
</table>  

### 示例

```python
    lvs seam_find, cnd=1, seam=10, sp=p10    
    # 使用条件编号 1 和缝编号 10 执行缝发现，将结果姿态保存在 p10 中
    lvs track, cnd=1 ,seam=10 , sp=p10
    # 使用条件编号 1 和缝编号 10 开始 LVS 缝追踪
```  


{% hint style="info" %}
  作为可选功能使用，请联系我们公司。
{% endhint %}
### 细节  

  请参阅 [[8.5 LVS(激光视觉传感器) 接缝查找和跟踪]](../8_Application_function/5_LVS_tracking/README.md)