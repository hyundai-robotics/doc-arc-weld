# 8.5.7 LVS 跟踪功能和监控

### (1) LVS 跟踪概述

LVS 跟踪是一个补偿教学轨迹与实际焊接线之间差异的功能。

{% hint style="warning" %}
基准工件的教学应以高精度进行。<br>
在施加移位以修正工件定位误差后，应使用 LVS 功能。<br>
有关详细信息，请参阅 [8.5.5 LVS 主模式功能]。
{% endhint %}

由于激光装置安装在 TCP 前面，必须先进行搜索以执行跟踪。

{% hint style="info" %}
请参阅上一部分，**[8.5.6 LVS 搜索功能]**，以获取有关搜索功能的详细信息。
{% endhint %}


lvs 命令的配置应设置如下：

```python
    move L, spd=60%, accu=0, tool=1
    delay 0.3
    var po_100=cpo() # 当前姿态存储在变量 po_100 中
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

执行搜索命令的过程如下面的图所示（当搜索设置为有效且方向设置为 0 时）。
一个无效点被找到并存储在 `sp` 参数中作为起始点，然后 TCP 移动到起始点，同时填充数据缓冲区。

![](../../_assets/8_5_17.png)<br>
*图 8.5.17. LVS 搜索过程*   
</br>

### (2) 如何使用带偏移值的跟踪

如果您想要在接缝上使用偏移进行跟踪（而不是严格跟随焊接线），可以在 `lvs` 命令中以毫米为单位指定侧向和高度的偏移值。该偏移在工具坐标系统方向上应用。

```python
    move L, spd=60%, accu=0, tool=1
    delay 0.3
    var po_100=cpo() # 当前姿态存储在变量 po_100 中
    lvs search, cnd=1, seam=1, sp=po_100
    weavon cnd=1  
    arcon cnd=1
    lvs track, cnd=1, seam=1, sp=po_100, side=5, height=-5 # 偏移跟踪在 ToolX 中 5mm，在 ToolZ 中 -5mm
    move L, spd=30cm/min, accu=3, tool=1
    move L, spd=36cm/min, accu=3, tool=1
    move L, spd=40cm/min, accu=3, tool=1
    weavoff
    arcof
    end
```

{% hint style="info" %}
* 使用编织时，突出长度会根据角度和振幅增加。为了补偿这一点，在搜索和跟踪操作期间将高度设置为负值。
{% endhint %}

### (3) LVS 监控

![](../../_assets/8_5_18_tracking_monitoring.png)<br>
*图 8.5.18. LVS 监控*   
</br>

LVS 监控可以通过选择 `[pane layout] - 选择 - LVS 跟踪 ([pane layout] - select - LVS tracking)` 来激活。

在监控中，可以检查以下项目：

| 项目 | 描述 |
|------|------|
| 总累计补偿<br> (X, Y, Z) | 如果未使用编织，则此项目表示相对于基准坐标系统的累计补偿。如果使用编织，则表示在编织坐标系统中的累计补偿。 |
| 传感器 | qual: 指示当前激光接缝感应是否有效或无效。<br> Y, Z: 当前感应接缝在传感器图像坐标系统中的位置（2D）。 |
| 工具尖端 | TCP 相对于基准坐标系统的当前位置。 | 
| 跟踪点 | TCP 当前正在跟踪的点，相对于基准坐标系统。 |
| 感应点 | 当前被激光感测位置的基准坐标值。 |
| 缓冲区大小 | 存储在用于跟踪的数据缓冲区中的点数。如果该值不断增加、减少或达到 0，则可能存在跟踪、通信或配置的问题。 |
| 信息 | 显示自动标定的进度和其他相关信息。 |
| 实时图像 | 显示要跟踪的点，以红色圆圈表示，存储在缓冲区中。 |