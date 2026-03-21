# 2.13 touchsen

### 描述

```touchsen``` 命令执行线触摸传感。您可以在属性窗口中配置传感类型和条件。
在使用 `move` 命令移动到所需的传感位置后，执行 `touchsen` 命令会根据指定的传感类型和条件自动在该位置启动触摸传感。

<br/>

### 语法

```python
touchsen cnd=<Condition number>, crd=<Coordinate System>, dir=<Direction>, pose=<Pose to save>
touchsen cnd=<Condition number>, crd=<Coordinate System>, dir=<Direction>, rotation=<Sensing Angle>, pose=<Pose to save>
touchsen cnd=<Condition number>, crd=<Coordinate System>, dir=<Direction>, lift_up=<Lifting Distance>, criteria=<Detection Threshold in Detect Groove>, pose=<Pose to save>, gap=<butt gap value>
touchsen cnd=<Condition number>, crd=<Coordinate System>, dir=<Direction>, mpose=<Pose to save in Master Mode>, mshift=<Shift Variable Calculated in Production Mode>
```  

### 参数

| 项目 | 含义 | 备注 |
| --- | --- | --- |
| **条件编号** | 触摸传感条件编号 (1 ~ 1000) | 可变 |
| **坐标系统** | 用于定义传感方向的坐标系统 ("robot", "base", "tool", "tool_prj") | 可变 |
| **方向** | 触摸传感方向 (支持方向因传感类型而异) ("+x", ["+x", "-z"], ["+ty", "+tz"]) | 字符串数组 |
| **保存的姿态** | 指定传感结果将存储的姿态变量。 | 可变 |
| **传感角度** | 对所选坐标系统参考的传感方向应用的旋转角度 (Y+30, Y-30, X+30, X-30, TL+30, TL-30, TY+30, TY-30) | 可变 |
| **提升距离** | 机器人在底部检测后向上移动的距离 | 可变 |
| **标准（检测槽中的阈值）** | 槽检测的参考距离[mm] | 可变 |
| **搭接间隙值** | 用于存储通过触摸传感在搭接或V型槽类型中测量的较低间隙的变量 | 可变 |
| **mpose（主模式下保存的姿态）** | 在主模式下，传感结果存储在 `mpose` 中。在生产模式下，`mpose` 用于计算 `mshift`。 | 可变 |
| **mshift（在生产模式中计算的移位变量）** | 在生产模式中，`mshift` 存储计算出的位移值作为向量差：(当前传感姿态 - 主姿态) | 可变 |

### 示例

```python
    var var1=0      # 声明一个变量以存储在搭接连接传感过程中测量的间隙。
    var P10=cpo()   # 声明一个姿态变量 `P10` 并将当前姿态保存到其中。
    touchsen cnd=2, crd="tool", dir=["+y"], lift_up=3, pose=P10, gap=var1  # 条件2，使用工具坐标系统，底部传感后抬起3mm，并将间隙存储在var1中
    touchsen cnd=1, crd="tool", dir=["tf", "td"], pose=P10, 0  # 条件1，使用工具投影坐标系统，2点
    touchsen cnd=1, crd="base", dir=["+x","-y","-z"], pose=P10, 0  # 条件1，使用基座坐标系统，3点
```  

### 详细信息
  请参见 [[8.2 触摸传感]](../8_Application_function/2_Touch_sensing/README.md)
<br/>