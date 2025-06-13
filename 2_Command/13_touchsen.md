# 2.13 touchsen

### Description

```touchsen``` command performs wire touch sensing. You can configure the sensing type and conditions in the properties window.
After moving to the desired sensing position using a `move` command, executing the `touchsen` command initiates touch sensing at that position automatically, based on the specified sensing type and condition.

<br/>


### Syntax

```python
touchsen cnd=<Condition number>, crd=<Coordinate System>, dir=<Direction>, pose=<Pose to save>
touchsen cnd=<Condition number>, crd=<Coordinate System>, dir=<Direction>, rotation=<Sensing Angle>, pose=<Pose to save>
touchsen cnd=<Condition number>, crd=<Coordinate System>, dir=<Direction>, lift_up=<Lifting Distance>, criteria=<Detection Threshold in Detect Groove>, pose=<Pose to save>, gap=<butt gap value>
touchsen cnd=<Condition number>, crd=<Coordinate System>, dir=<Direction>, mpose=<Pose to save in Master Mode>, mshift=<Shift Variable Calculated in Production Mode>
```  
<br/>


### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **Condition number** | Touch sensing Condition number (1 ~ 1000) | Variable |
| **Coordinate System** | Coordinate system used to define sensing direction ("robot", "base", "tool", "tool_prj") | Variable |
| **Direction** | Touch sensing direction (supported directions vary by sensing type) ("+x", ["+x", "-z"], ["+ty", "+tz"]) | String Array |
| **Pose to save** | Specifies the pose variable where the sensing result will be stored. | Variable |
| **Sensing Angle** | Rotational angle applied to the sensing direction with respect to the selected coordinate system (Y+30, Y-30, X+30, X-30, TL+30, TL-30, TY+30, TY-30) | Variable |
| **Lifting Distance** | The upward distance the robot moves after bottom detection | Variable |
| **Criteria(Detection Threshold in Detect Groove)** | Reference distance for groove detection[mm] | Variable |
| **Butt Gap Value** | Variable to store the lower gap measured via touch sensing in Butt or V-groove type | Variable |
| **mpose(Pose to save in Master Mode)** | In Master mode, sensing results are stored in `mpose`. In Production mode, `mpose` is used to calculate `mshift`. | Variable |
| **mshift(Shift Variable Calculated in Production Mode)** | In Production mode, `mshift` stores the calculated shift value as a vecotr difference: (current sensing pose - master pose) | Variable |


### Example

```python
    var var1=0      # Declare a variable to store the measured gap during butt joint sensing.
    var P10=cpo()   # Declare a pose variable `P10` and save the current pose to it.
    touchsen cnd=2, crd="tool", dir=["+y"], lift_up=3, pose=P10, gap=var1  # condition 2, in tool crd system, After bottom sensing, lift by 3mm, and store the gap in var1
    touchsen cnd=1, crd="tool", dir=["tf", "td"], pose=P10, 0  # condition 1, in Tool projection crd system, 2-points
    touchsen cnd=1, crd="base", dir=["+x","-y","-z"], pose=P10, 0  # condition 1, in base crd system, 3-points
```  
<br/>


### Details
  Refer to [[8.2 Touch Sensing]](../8_Application_function/2_Touch_sensing/README.md)
<br/>

