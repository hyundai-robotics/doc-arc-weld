# 8.3.7 多遍命令


### (1) 命令

感应轨迹可以使用多遍命令进行保存和加载。 
该命令可以以三种不同形式使用：
<br>

```py
    multipass save, trj=<multi-pass trajectory number>, period=<trajectory saving interval distance>
    multipass load, trj=<multi-pass trajectory number>, side=<left-right Shift distance>, height=<up-down Shift distance>, reverse=<multi-pass playback direction>, tas=<torch forward/backward angle shift>, was=<torch left/right angle shift>
    multipass off
```

### (2) 多遍参数

有关多遍命令参数的详细信息，请参考以下链接: <br>
[2.11 multipass](../../2_Command/11_multipass.md)

<br>

本节将仅解释以下两个项目：  


- 左右/上下偏移

这设置了在多遍重现过程中轨迹从原始路径偏移的距离。
由于喷嘴编织与工具垂直，因此每个偏移设置如下：
左/右方向成为编织平面，而上下方向成为与编织平面垂直的平面。

![](../../_assets/8_3_11.png)<br>
*图 8.3.11 多遍偏移方向*


- 角度偏移：TAS, WAS  

在进行多遍焊接时，喷嘴必须倾斜以进行质量控制。此设置用于定义所需的倾斜。
每个项目的角度概念在以下图中阐明：  

![](../../_assets/8_3_12.png)<br>
*图 8.3.12 多遍角度偏移概念*