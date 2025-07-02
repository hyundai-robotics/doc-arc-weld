# 8.3.1 Arc Sensing Overview

When weaving during arc welding, the distance between the torch and the base material changes.
This change in distance causes a variation in wire resistance, which in turn alters the current flowing.
In other words, by using the current change during the weaving section, the distance to be corrected in the left and right directions of the weaving area can be calculated, allowing the seam to be tracked.

The height value at the welding start position is used as the reference, and the current value in the middle of the weaving section is used to correct the vertical direction during welding.
Or, instead of using the starting position current reference value, **the user can directly input a custom current value** as the reference for correction.


<!-- - 좌우 방향 보정 : 좌우 전류차 및 용접선 추출 알고리즘에 의해 로봇이 자동으로 용접선을 추종하여 이동합니다.
- 상하 방향 보정 : 용접 시작시 높이 (CTWD)를 기준으로하여 이 값을 계속 유지합니다.
                  만약 용접 도중 높이변화가 필요할 경우 job에 다음 명령어를 이용하여 사용자가 기준 전류값을 입력할 수 있습니다.  -->


```py
    move L, spd=30cm/min,accu=3,tool=0  # Entry step
    move L, spd=30cm/min,accu=3,tool=0  # Welding start step
    weaving on, cnd=1 # Set the 'Arc Sensing' function to 'Enable' in the [Property] window
    arc on, cnd=1
    move L, spd=30cm/min,accu=3,tool=0
    _weaving.height_sensing_reference_current=300 # Set the height reference value to 300A
    move L, spd=30cm/min,accu=3,tool=0
    weaving off
    arc off
    end
```  
<br/>

<p align="center">
 <img src="../../_assets/8_3_1.png" width="70%"></img>
 <em><p align="center">Figure 8.3.1. Arc Sensing Concept</p></em>
</p>

As shown in the figure, when the torch is tilted to the left or right, the current weavform changes, and this can be used to track the seam in the left and right directions.
Additionally, the current at the middle of the weaving section can be used to correct the vertical direction.

