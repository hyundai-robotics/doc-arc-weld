# 2.8 lps

### Description 

```lps``` 命令用于执行一些功能，例如使用激光距离传感器获取激光位置的姿态（点模式）、检测高度差（步进模式）以及搜索焊缝（扫描模式）。

<br/>

### Syntax

```python
    lps auto_calib, cnd=<条件编号>, Tx=<基于工具的X方向移动距离>, Ty=<基于工具的Y方向移动距离>
    lps spot, cnd=<条件编号>, sp=<存储姿态>
    lps stepp, cnd=<条件编号>, Tx=<基于工具的X方向移动距离>, Ty=<基于工具的Y方向移动距离>, spd=<机器人速度>, sp=<存储姿态>
    lps scan, cnd=<条件编号>, Tx=<基于工具的X方向移动距离>, Ty=<基于工具的Y方向移动距离>, spd=<机器人速度>, sp=<存储姿态>
    # 使用主控/生产模式时
    lps scan, cnd=<条件编号>, Tx=<基于工具的X方向移动距离>, Ty=<基于工具的Y方向移动距离>, spd=<机器人速度>, sp=<存储姿态>, mp=<在主控模式下保存的姿态>, ms=<在生产模式下计算的移位变量>
```  

### Parameter

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
      <td rowspan="5">lps</td>
      <tr>
      <td>`auto_calib`</td>
      <td>
        执行工具和传感器之间的自动校准。
      </td>
      </tr>
      <tr>
      <td>`spot`</td>
      <td>
        在点模式下，获取激光当前指示的位置的姿态。
      </td>
      </tr>
      <tr>
      <td>`stepp`</td>
      <td>
        在步进模式下，获取激光移动时输出值骤然变化的位置的姿态。
      </td>
      </tr>
      <tr>
      <td>`scan`</td>
      <td>
        在扫描模式下，获取估计为激光移动路径上的焊接点的位置的姿态。
      </td>
      </tr>
    </tr>
    <tr>
      <td colspan="2">cnd</td>
      <td>
        执行 LPS 功能时使用的条件编号（1 到 8）。
        命令属性窗口中显示的信息根据条件编号而异。
        此信息用于自动校准和步进模式中的灵敏度设置，以及存储姿态时的坐标系配置。
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">`Tx / Ty`</td>
      <td>
        设置基于工具的X或Y方向的移动距离。
        除了auto_calib，两个值中只能输入一个。
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">`spd`</td>
      <td>
        指定机器人在执行操作时的移动速度。
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">`sp`</td>
      <td>
        指定用于存储每个命令找到的当前姿态的姿态变量。
      <td>姿态变量</td>
    </tr>
    <tr>
      <td colspan="2">`mp`</td>
      <td>
        在主控模式下，感应结果存储在mp（主姿态）中。
        在生产模式下，用于计算ms（主移位）。
      <td>姿态变量</td>
    </tr>
    <tr>
      <td colspan="2">` (ms)`</td>
      <td>
        在生产模式下使用的移位变量。
        计算并存储主姿态（mp参数）与当前感应姿态（sp参数）之间的差异。
      <td>移位变量</td>
    </tr>
  </tbody>
</table>  
### 示例

```python
    lps auto_calib, cnd=1, Tx=50, Ty=-100
    # 在指定的距离范围内执行自动校准，X方向为+50，Y方向为-100，基于工具，使用条件编号1
    lps spot, cnd=1, sp=p10
    # 使用条件编号1，将当前激光位置的姿态存储在p10中，基于条件设置中定义的坐标系。
    lps stepp, cnd=1, Tx=50, sp=p10
    # 使用条件编号1，基于工具在X方向上移动50[mm]，在检测到步进差异时立即停止，并将姿态存储在p10中。
    lps scan, cnd=1, Tx=50, spd=10, sp=p10
    # 使用条件编号1，基于工具以10的速度在X方向上移动50[mm]，在移动完成后检测焊接点，并将其存储在p10中。
    # 条件编号1，工具基准X方向移动50时，完成后检测焊接点并存储于p10
    
    lps scan, cnd=1, Tx=50, spd=10, sp=p10, mp=mp10, ms=ms10
    # 当使用主模式时：使用条件编号1，基于工具以10的速度在X方向上移动50[mm]，在移动完成后检测焊接点，存储在p10中，与mp10进行比较，并将计算的位移值保存到ms10中。
```  


{% hint style="info" %}
要将此功能用作可选功能，请联系我公司。
{% endhint %}


### 细节

  参见 [8.8 LPS(激光点传感)](../8_Application_function/8_LPS/README.md)