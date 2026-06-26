# 2.13 touchsen

### 描述

```touchsen``` 命令执行线触摸感应。您可以在属性窗口中配置感应类型和条件。
在使用 `移动 (move)` 命令移动到所需的感应位置后，执行 `touchsen` 命令会根据指定的感应类型和条件自动在该位置启动触摸感应。

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
| **Condition number** | 触摸感应条件编号 (1 ~ 1000) | 可变 |
| **Coordinate System** | 用于定义感应方向的坐标系统 ("robot", "base", "tool", "tool_prj") | 可变 |
| **Direction** | 触摸感应方向 (受支持方向因感应类型而异) ("+x", ["+x", "-z"], ["+ty", "+tz"]) | 字符串数组 |
| **Pose to save** | 指定将存储感应结果的姿态变量。 | 可变 |
| **Sensing Angle** | 应用于根据所选坐标系统的感应方向的旋转角度 (Y+30, Y-30, X+30, X-30, TL+30, TL-30, TY+30, TY-30) | 可变 |
| **Lifting Distance** | 机器人在底部检测后向上移动的距离 | 可变 |
| **Criteria(Detection Threshold in Detect Groove)** | 瓦沟检测的参考距离[mm] | 可变 |
| **Butt Gap Value** | 通过触摸感应测量的下缝隙，存储为变量的 Butt 或 V-groove 类型 | 可变 |
| **mpose(Pose to save in Master Mode)** | 在主模式下，感应结果存储在 `mpose` 中。在生产模式下，`mpose` 用于计算 `mshift`。 | 可变 |
| **mshift(Shift Variable Calculated in Production Mode)** | 在生产模式下，`mshift` 存储计算出的位移值作为向量差异: (当前感应姿态 - 主姿态) | 可变 |

### 示例

```python
    var var1=0      # 声明一个变量以存储在 Butt joint 感应过程中测量的缝隙。
    var P10=cpo()   # 声明一个姿态变量 `P10` 并将当前姿态保存到它。
    touchsen cnd=2, crd="tool", dir=["+y"], lift_up=3, pose=P10, gap=var1  # 条件 2，在工具坐标系统中，底部感应后抬升3mm，并将缝隙存储在 var1 中
    touchsen cnd=1, crd="tool", dir=["tf", "td"], pose=P10, 0  # 条件 1，在工具投影坐标系统中，2点
    touchsen cnd=1, crd="base", dir=["+x","-y","-z"], pose=P10, 0  # 条件 1，在基座坐标系统中，3点
```  

### 细节
  参考 [[8.2 Touch Sensing]](../8_Application_function/2_Touch_sensing/README.md)
<br/>