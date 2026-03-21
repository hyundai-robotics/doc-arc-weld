# 8.3.7 多次命令

### (1) 命令

传感轨迹可以使用多次命令进行保存和加载。  
此命令可以以三种不同的形式使用：
<br>

```py
    multipass save, trj=<multi-pass trajectory number>, period=<trajectory saving interval distance>
    multipass load, trj=<multi-pass trajectory number>, side=<left-right Shift distance>, height=<up-down Shift distance>, reverse=<multi-pass playback direction>, tas=<torch forward/backward angle shift>, was=<torch left/right angle shift>
    multipass off
```

### (2) 多次参数

有关多次命令参数的详细信息，请参阅以下链接： <br>
[2.11 multipass](../../2_Command/11_multipass.md)

<br>

本节将仅解释以下两个项目：  

- 左右/上下位移

此设置轨迹在多次再现过程中与原始路径的偏移距离。  
由于焊枪的编织与工具垂直，每个偏移设置如下：左右方向成为编织面，上下方向成为与编织面垂直的面。

![](../../_assets/8_3_11.png)<br>
*图 8.3.11 多次位移方向*

- 角度偏移：TAS, WAS  

在进行多次焊接时，焊枪必须倾斜以控制质量。此设置用于定义所需的倾斜。  
每个项目的角度概念在以下图中说明：  

![](../../_assets/8_3_12.png)<br>
*图 8.3.12 多次角度偏移概念*