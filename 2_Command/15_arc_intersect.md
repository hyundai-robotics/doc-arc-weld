# 2.15 arc_intersect


{% hint style="info" %}
This feature is supported in versions 70.04-00 and later.
{% endhint %}


### Description  

The ```arc_intersect``` command is used to apply Master Mode and Production Mode in arc applications. Its usage is identical to that of the existing intersection function. Parameter values are processed according to whether Master Mode is enabled or disabled.
<br/>  


### Syntax  

```py
  arc_intersect sp=<Pose to save>,crd=<Coordinate System>,mp=<Master Pose to save in Master Mode>,ms=<Shift Variable Calculated in Production Mode>,p1=<Line Reference Pose1>,p2=<Line Reference Pose2>,p3=<Line Reference Pose3>
  arc_intersect sp=<Pose to save>,crd=<Coordinate System>,mp=<Master Pose to save in Master Mode>,ms=<Shift Variable Calculated in Production Mode>,p1=<Line Reference Pose1>,p2=<Line Reference Pose2>,p3=<Line Reference Pose3>,p4=<Line Reference Pose4>
```  


### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| sp | Pose variable used to store the result of the command execution. | Pose Variable |
| crd | Coordinate system used to calculate the shift variable ("base", "robot", "tool") | String |
| mp | Stores the same value as sp in Master Mode. Used to calculate ms in Production Mode. | Pose Variable |
| ms | Shift variable used in Production Mode. Represents the difference between mp and sp, calculated in the specified coordinate system. | Shift Variable |
| p1 ~ p4 | Reference poses used to define a line. Refer to the link below for details on defining a line using three or four points. [HRScript intersection](https://hrbook-hrc.web.app/#/view/doc-hrscript/en/10-etc/2-func/3-intersection?cont_model=${cont_model}) | Pose Variable |  


### Example
```python
  lvs seam_find, cnd=1, seam=10, sp=p1  # Store the detected point in p1
  lvs seam_find, cnd=1, seam=10, sp=p2  # Store the detected point in p2
  lvs seam_find, cnd=1, seam=10, sp=p3  # Store the detected point in p3

  arc_intersect sp=p10,crd="robot",mp=mp10,ms=ms10,p1=p1,p2=p2,p3=p3
  # Store the point calculated from p1 to p3 in p10, and update mp10 and ms10 according to the Master Mode status.
```  
  