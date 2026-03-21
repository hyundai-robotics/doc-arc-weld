# 8.5.7 LVS 跟踪功能及监控

### (1) LVS 跟踪概述

LVS 跟踪是一种功能，可补偿教导轨迹与实际焊接线之间的差异。

{% hint style="warning" %}
基准工件的参考教学应以高精度进行。<br>
在应用偏移以纠正工件的定位误差后，应使用 LVS 功能。<br>
有关更多详细信息，请参见 [8.5.5 LVS 主模式功能]。
{% endhint %}

由于激光器安装在 TCP 前面，因此必须先进行搜索以进行跟踪。

{% hint style="info" %}
  有关搜索功能的详细信息，请参见前一部分，**[8.5.6 LVS 搜索功能]**。
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

执行搜索命令的过程在以下图中说明（当搜索设置为有效且方向设置为 0 时）。
找到一个无效点并将其存储在 `sp` 参数中作为起点，然后 TCP 在填充数据缓冲区的同时移动到起点。

![](../../_assets/8_5_17.png)<br>
*图 8.5.17. LVS 搜索过程*   
</br>

### (2) 如何使用带有偏移值的跟踪

如果您想以偏移量跟踪缝隙（而不是准确跟随焊接线），可以在 `lvs` 命令中以毫米单位指定侧面和高度的偏移值。此偏移量在工具坐标系方向上应用。

```python
    move L, spd=60%, accu=0, tool=1
    delay 0.3
    var po_100=cpo() # 当前姿态存储在变量 po_100 中
    lvs search, cnd=1, seam=1, sp=po_100
    weavon cnd=1  
    arcon cnd=1
    lvs track, cnd=1, seam=1, sp=po_100, side=5, height=-5 # 偏移跟踪，ToolX 方向 5mm，ToolZ 方向 -5mm
    move L, spd=30cm/min, accu=3, tool=1
    move L, spd=36cm/min, accu=3, tool=1
    move L, spd=40cm/min, accu=3, tool=1
    weavoff
    arcof
    end
```

{% hint style="info" %}
* 使用铺网时，伸出长度会根据角度和幅度增加。为补偿这一点，在搜索和跟踪操作期间将高度设置为负值。
{% endhint %}

### (3) LVS 监控

![](../../_assets/8_5_18_tracking_monitoring.png)<br>
*图 8.5.18. LVS 监控*   
</br>

可以通过选择 `[pane layout] - 选择 - LVS 追踪 ([pane layout] - select - LVS tracking)` 来激活 LVS 监控。

在监控中，可以检查以下项目：

| 项目 | 描述 |
|------|------|
| 总累计补偿<br> (X, Y, Z) | 如果未使用铺网，这代表相对于基础坐标系统的累计补偿。如果使用铺网，则指的是在铺网坐标系统中的累计补偿。 |
| 传感器 | qual: 表示当前激光缝合传感是否合法。<br> Y, Z: 当前在传感器图像坐标系统（2D）中感知到的缝合位置。 |
| 工具尖端 | TCP 相对于基础坐标系统的当前位置。 | 
| 跟踪点 | TCP 目前跟踪的点，相对于基础坐标系统。 |
| 感应点 | 当前被激光感应的位置的基础坐标值。 |
| 缓冲区大小 | 存储在跟踪缓冲区中的点数。如果此值持续增加、减少或达到 0，则可能存在跟踪、通信或配置问题。 |
| 信息 | 显示自动校准的进度及其他相关信息。 |
| 实时图像 | 显示要跟踪的点，由红色圆圈表示，存储在缓冲区中。 |