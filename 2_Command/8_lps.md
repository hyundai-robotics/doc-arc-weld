# 2.8 lps

### Description 

```lps``` 命令用于执行一些功能，例如使用激光测距传感器获取激光位置的姿态（点模式）、检测阶梯差（步进模式）和寻找焊缝（扫描模式）。

<br/>

### Syntax

```python
    lps auto_calib, cnd=<Condition Number>, Tx=<工具基准的X方向移动距离>, Ty=<工具基准的Y方向移动距离>
    lps spot, cnd=<Condition Number>, sp=<存储姿态>
    lps stepp, cnd=<Condition Number>, Tx=<工具基准的X方向移动距离>, Ty=<工具基准的Y方向移动距离>, spd=<机器人速度>, sp=<存储姿态>
    lps scan, cnd=<Condition Number>, Tx=<工具基准的X方向移动距离>, Ty=<工具基准的Y方向移动距离>, spd=<机器人速度>, sp=<存储姿态>
    # 当使用主模式/生产模式时
    lps scan, cnd=<Condition Number>, Tx=<工具基准的X方向移动距离>, Ty=<工具基准的Y方向移动距离>, spd=<机器人速度>, sp=<存储姿态>, mp=<主模式下保存的姿态>, ms=<生产模式下计算的移位变量>
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
      <td>`auto_calib`</td>
      <td>
        在工具和传感器之间执行自动校准。
      </td>
      </tr>
      <tr>
      <td>`点 (spot)`</td>
      <td>
        在点模式中，获取激光指示的位置的姿态。
      </td>
      </tr>
      <tr>
      <td>`stepp`</td>
      <td>
        在步进模式中，获取激光移动时输出值突然变化位置的姿态。
      </td>
      </tr>
      <tr>
      <td>`scan`</td>
      <td>
        在扫描模式中，获取沿激光移动路径估计为焊点的位置的姿态。
      </td>
      </tr>
    </tr>
    <tr>
      <td colspan="2">cnd</td>
      <td>
        执行 LPS 功能时使用的条件编号（1 到 8）。
        命令属性窗口中显示的信息根据条件编号而异。
        此信息用于自动校准和步进模式中的灵敏度设置，以及存储姿态时的坐标系配置。
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">`Tx / Ty`</td>
      <td>
        设置基于工具的X或Y方向的移动距离。
        除了auto_calib，两个值中只能输入一个。
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">`spd`</td>
      <td>
        指定在执行操作时机器人移动的速度。
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">`sp`</td>
      <td>
        指定当前通过每个命令找到的姿态存储的姿态变量。
      <td>Pose Variable</td>
    </tr>
    <tr>
      <td colspan="2">`mp`</td>
      <td>
        在主模式下，感测结果存储在 mp（主姿态）中。
        在生产模式下，用于计算 ms（主移位）。
      <td>Pose Variable</td>
    </tr>
    <tr>
      <td colspan="2">` (ms)`</td>
      <td>
        在生产模式下使用的移位变量。
        计算并存储主姿态（mp参数）与当前感测姿态（sp参数）之间的差。
      <td>Shift Variable</td>
    </tr>
  </tbody>
</table>  


### Example

```python
    lps auto_calib, cnd=1, Tx=50, Ty=-100
    # 在指定的 +50 的 X 方向和 -100 的 Y 方向的距离范围内，根据工具，使用条件编号 1 执行自动校准
    lps spot, cnd=1, sp=p10
    # 使用条件编号 1，将当前激光位置的姿态存储在 p10 中，基于条件设置中定义的坐标系统。
    lps stepp, cnd=1, Tx=50, sp=p10
    # 使用条件编号 1，基于工具在 X 方向移动 50[mm]，在检测到阶梯差时立即停止，并将姿态存储在 p10 中。
    lps scan, cnd=1, Tx=50, spd=10, sp=p10
    # 使用条件编号 1，基于工具在 X 方向以 10 的速度移动 50[mm]，在完成移动后检测焊点，并将其存储在 p10 中。
    # 条件编号 1番，工具基准X方向上移动50[mm]并检测焊点，将其存储在 p10 中
    
    lps scan, cnd=1, Tx=50, spd=10, sp=p10, mp=mp10, ms=ms10
    # 当使用主模式时：使用条件编号 1，基于工具在 X 方向以 10 的速度移动 50[mm]，在完成移动后检测焊点，将其存储在 p10，中与 mp10 进行比较，并将计算的移位值保存到 ms10 中。
```  


{% hint style="info" %}
要将此功能用作可选功能，请联系我们的公司。
{% endhint %}


### Details

  请参见 [8.7 LPS(Laser Point Sensing)](../8_Application_function/7_LPS/README.md)