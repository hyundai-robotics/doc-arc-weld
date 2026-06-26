# 8.5.4 LVS 接缝查找功能

### (1) 接缝查找概述

该功能将 LVS 传感器感知到的位置存储为姿态，可以作为接触传感的替代品。

{% hint style="warning" %}
  如果在使用此功能之前未对 TCP-LVS 传感器进行校准，将保存异常的姿态。
{% endhint %}

命令格式如下：  
执行该命令后，如下所示，LVS 传感器感知到的位置将存储在 po_100 变量中。

```python
  var po_100=cpo()  # 当前姿态存储在变量 po_100 中
  lvs seam_find, cnd=1, seam=1, sp=po_100 # 如果 sp 参数中没有输入的名称，则将自动声明为局部姿态变量。
```

{% hint style="warning" %}
  如果 **sp** 参数未声明，则将声明为局部姿态。 <br>
  如果 **mp** 参数未声明，则将声明为全局姿态。 <br>
  如果 **ms** 参数未声明，则将声明为全局偏移。
{% endhint %}


![](../../_assets/8_5_9_lvs_seamfind_ex.png)<br>
*图 8.5.9. LVS 感知位置中的姿态*   
</br>

{% hint style="info" %}
  - 使用 **seam_find** 命令存储在 sp 参数中的姿态的方向将保持在感知前的工具方向 (Rx, Ry, Rz)。
  - 另一方面，使用 **seam_find_p** 命令时，仅记录存储在 sp 参数中的姿态的位置。
{% endhint %}

* 如果您想在姿态中仅存储位置，而不考虑预感知的方向，请使用以下命令格式。<br>
当您希望记录焊接姿态并使位置 (X, Y, Z) 对应于 LVS 感知到的点时，该功能非常有用。

```python
var po_100=cpo()
lvs seam_find_p, cnd=1, seam=1, sp=po_100
```

* 从感知位置向工具 Y 和工具 Z 方向偏移的姿态可以通过以下方式计算。 <br>
该命令计算出在感知期间向工具 Y 方向偏移 10mm 和向工具 Z 方向偏移 10mm 的姿态。

```python
var po_100=cpo()
lvs seam_find, cnd=1, seam=1, side=10, height=10, sp=po_100
```

---

### (2) LVS 接缝查找重试

如果在接缝查找期间无法识别接缝，则将执行重试。

重试的次数在 LVS 命令属性窗口的接缝查找选项下的 **"no of retry"** 中指定。

如果在指定次数的重试后仍然无法感知，将发生错误。

重试过程按以下顺序进行：

![](../../_assets/8_5_10_lvs_seamfind_retry.png)<br>
*图 8.5.10. LVS 接缝查找重试*   
</br>

{% hint style="warning" %}
* 使用主偏移功能时，请注意重试会导致位置前后偏移（+ToolX, -ToolX）。
{% endhint %}

---

### (3) LVS 接缝查找监控

要查看 LVS 接缝查找监控屏幕，请在 TP 中点击 `[pane layout] - 选择 - LVS 焊缝查找 ([pane layout] - select - LVS seamfind)`  


![](../../_assets/8_5_11_seamfind monitoring.png)<br>
*图 8.5.11. LVS 接缝查找监控*   
</br>
<table>
  <thead>
    <tr>
      <th style="text-align:left">项目</th>
      <th style="text-align:left">描述</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">位置 (X, Y, Z)</td>
      <td style="text-align:left">
        显示当前感知的位置（以基坐标表示）<br>
        规格：母体姿态的位置。如果未注册，将显示为 (-1, -1, -1)<br>
        感知：当前感知的位置 
      </td>
    </tr>
    <tr>
      <td style="text-align:left">间隙</td>
      <td style="text-align:left">
        规格：母间隙 [mm]<br>
        感知：当前感知的间隙 [mm]
      </td>
    </tr>
    <tr>
      <td style="text-align:left">面积</td>
      <td style="text-align:left">
        开口或对接形状的内部区域宽度 [mm^2]<br>
        规格：母区域 [mm]<br>
        感知：当前感知的面积 [mm]
      </td>
    </tr>
    <tr>
      <td style="text-align:left">不匹配</td>
      <td style="text-align:left">
        不匹配值通常指左右形状的高度差。
      </td>
    </tr>
  </tbody>
</table>

{% hint style="info" %}
  间隙、面积、不匹配等值仅对制造商的 LVS 控制器支持的接缝显示。
{% endhint %}

如果母体姿态已注册，可以按 prev 或 next 按钮查看当前作业的感知历史。

{% hint style="info" %}
  有关主模式的更多详细信息，请参阅 [8.5.5 LVS 主模式功能](./5_lvs_master_mode.md)。
{% endhint %}