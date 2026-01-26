# 8.2	Touch Sensing


Welding workpieces are not always in a fixed position due to errors in the jig, positioner, or workpiece mounting.
In such cases, touch sensing can be used to detect the welding start point, intermediate points, and end points, enabling accurate welding.

The touch sensing func. helps obtain the pose by detecting the position of the workpiece and the welding start, end, or intermediate points.

By recording the reference position using touch sensing, the shift of the workpiece from the reference position can be calculated when the workpiece is loaded.
When using the master mode, a mster pose can be saved through reference teaching, and the shift amount is automatically calculated via touch sensing during actual operation.


<p align="center">
 <img src="../../_assets/8_2_1.png"></img>
 <em><p align="center">Figure 8.2.1. Example of Touch Sensing</p></em>
</p>

### (1) Touch Sensing Types

The touch sensing supports a total of 5-types, as shown in [Figure 8.2.1] (Butt, Fillet, V-groove, LR Center, and Groove Detections).

<p align="center">
 <img src="../../_assets/8_2_2.png" width="90%"></img>
 <em><p align="center">Figure 8.2.2. Touch Sensing Types</p></em>
</p>

### (2) Touch Sensing Command and Setting Parameters

The touch sensing command can be recorded by entering `[F6: cmd. input] - arcweld - touchsen` on the TP.

Assuming the condition 1 set for Fillet, condition 2 set for Butt, and condition 3 for V-groove in the command (where the workpiece type is defined in the properties), the example is as follows:

```python
    move L,spd=60%,accu=0,tool=0  # Move to the touch sensing position with acc 0
    var P10=cpo() # Save the current pose to a local variable P10 before touch sensing.
    touchsen cnd=1, crd="tool_prj", dir=["tf","td"], pose=P10       # Condition 1, tool projection direction, 2-point touch
    touchsen cnd=1, crd="robot", dir=["+x","-y","-z"], pose=P10     # Condition 1, robot coordinate direction, 3-point touch
    touchsen cnd=1, crd="tool", dir="+tz", pose=P10           # Condition 1, tool coordinate direction, 1-point touch in +TZ
    touchsen cnd=2, crd="tool", dir="+tx", lift_up=3, pose=P10, gap=var1 # Condition 2, tool coordinate direction, touch the bottom and rise 3mm
    touchsen cnd=3, crd="tool", dir="-ty", lift_up=5, pose=P10   # Condition 3, tool coordinate direction, touch the bottom and rise 5mm
```

- **Sensing Distance** : The distance in the sensing direction [mm], and an error occurs if the workpiece is not detected upon reaching this distance.

- **Retreat Distance** : The distance to retreat after the initial sensing in the case of Fillet, and **the distance to raise after touching the bottom in the DetectGroove type**.

- **Sensing Speed and Retreat Speed** : Specifies the speed during search or retreat.  

- **Detection Type** : Supports sensing during contact and release of contact. Typically, sensing during contact is used, and there is alomost no error.<br/>
  If the situation requires considering even minor errors caused by wire bending during sensing, only use sensing during retreat when absolutely necessary.


<br/>

- **참고**

<center>

| Sensing Type |	Max Search</br>Directions |	Orthogonal XYZ </br>(All types </br>Supported)	| Tool Coordinate System |	Tool Projection</br>Coordinate System | Other input parameters |
|:---:|	:---: |	:---:	| :---:|	:---: |:---:|
| Fillet |	3	|O|	O |	O	|	Retreat Distance |
| Butt	| 1 |	X	|O	|X	|  |
| VGroove |	1 |	X |	O	|X | |
| LRCen |	1	|O |	O	|X |  |	
| DetectGroove |	2 |	O |	O |	O | Proceed Distance 1</br> Retreat Distance 1 </br> criteria |

</center>


In the touch sensing command, pressing on `Property` will bring up a winow as shown in [Figure 8.2.3]  
You can set conditions such as sensing distance, retreat distance, proceed distance, sensing speed, retreat speed, and detection type (contact,  release of contact), among others.  


<p align="center">
 <img src="../../_assets/8_2_3.png" width="70%" ></img>
 <em><p align="center">Figure 8.2.3. Touch Sensing Condition Edit Screen</p></em>
</p>

{% hint style="info" %}
  For detailed instructions on using the command and parameters, please refer to [2.13 touchsen](../../2_Command/13_touchsen.md) <br>
  This section explains how to use the function.
{% endhint %}

<!-- - **명령어 사용 예시**
```python
    - touchsen cnd=<조건번호>, crd=<좌표계>, dir=[센싱 방향1, 센싱 방향2, 센싱 방향3], pose=<결과포즈 저장변수>, gap=<butt gap 변수>
    - touchsen cnd=<조건번호>, crd=<좌표계>, dir=[센싱 방향1, 센싱 방향2, 센싱 방향3], rotation=<센싱 방향 각도>, pose=<결과포즈 저장변수>, gap=<butt gap 변수>
    - touchsen cnd=<조건번호>, crd=<좌표계>, dir=[센싱 방향1, 센싱 방향2, 센싱 방향3], rotation=<센싱 방향 각도>, mpose=<결과포즈 저장변수>, mshift=<계산된 시프트 변수, gap=butt gap 변수>
```   -->

<!-- - **파라미터**
  - 터치센싱 조건번호 (cnd) : cnd=1	
  - 터치센싱 좌표계 (crd) : "robot", "base", "tool", "tool_prj" 
  - 센싱 방향 파라미터 (dir) : "+x", ["+x","-z"], [+tx, +tz], ["tf","td"],  
  - butt, groove 바닥 탐색 후 상승량 [mm] : lift_up=3		
  - detect groove 탐지 기준 거리 [mm] : criteria=5
  - 센싱 결과 포즈변수 : pose=var_po10
  - butt 하단 갭 변수 (소숫점 첫째 자리에서 반올림) : gap=var_gap 

- **참고**  
  센싱방향(dir)은 작업물 타입에 따라 다음과 같이 지정할 수 있습니다.

  - Fillet	: 최소 1개 ~ 3개 지정
              +x, -x, +y, -y, +z, -z (crd="robot" 또는 "base")
              tf, td, tl, tr (crd="tool_prj")
              +tx, -tx, +ty, -ty, +tz, -tz (crd="tool")
  - Butt 	: 1개 지정, 하강방향은 +tz 방향
            +tx, -tx, +ty, -ty, +tz, -tz (crd="tool")
  - V Groove 	: 1개 지정, 하강방향은 +tz 방향
                +tx, -tx, +ty, -ty, +tz, -tz (crd="tool")
  - LRCen 	: 1개 지정
              +x, -x, +y, -y, +z, -z (crd="robot" 또는 "base")
              +tx, -tx, +ty, -ty, +tz, -tz (crd="tool")
  - DetectGroove: 2개 지정 (하강방향, 전진방향 순서)
                  tf, td, tl, tr (crd="tool_prj")
                  +tx, -tx, +ty, -ty, +tz, -tz (crd="tool") -->


### (3) Detailed Description of Touch Sensing by Sensing Type

---

#### [1] Fillet

<p align="center">
 <img src="../../_assets/8_2_4.png" width="60%"></img>
 <em><p align="center">Figure 8.2.4. Example of Touch Sensing - Fillet</p></em>
</p>

- Examples of Command
```python
  touchsen cnd=1, crd="robot", dir=["+x","-y", "-z"], pose=P10
  touchsen cnd=1, crd="tool_prj", dir=["tf", "td"], pose=P10
  touchsen cnd=1, crd="tool", dir=["+tz"], pose=P10
```  
  - 1-Point sensing : Only one sensing direction is specified.
  - 2-Point sensing : Two sensing directions are specified sequentially.
  - 3-Point sensing : Three sensing directions are specified sequentially.
- Tool Projection Method (crd="tool_prj") : For convenience, the forward, downward, left, and right directions are determined based on the torch posture.  <br> The directioon can be specified as tf(forward), td(downward), tl(left), tr(right). (tl = RotZ(90) * tf, tr = RotZ(-90) * tf)
- For workpieces with rotational amounts (RX, RY, RZ), such as tilted Fillets, the sensing direction can be changed using the angle specification option. Please refer to the bottom of the manual for usage.

---

#### [2] V Groove

<p align="center">
 <img src="../../_assets/8_2_5.png" width="70%"></img>
 <em><p align="center">Figure 8.2.5. Example of Touch Sensing - V Groove</p></em>
</p>   

- Examples of Command
```python
  touchsen cnd=3, crd="tool", dir=[-ty], lift_up=3, pose=P10    # Condition 3, tool coordinate direction
```  
  - V-Groove Type can be used for sensing workpieces with a Groove shape. However, it is recommended to teach the tool posture so that it is positioned along the bisector of the angle, similar to the figure above, before starting the sensing.  
  - The direction parameter corresponds to one direction for the left-right sequence. The downward sequence direction is fixed in the `+Tz` direction.  
  - For stable sensing, it is recommended to set the lift-up amount to at least 3mm.  

- Sensing Sequence  
  - The sensing sequence proceeds as follows: upper left-right → middle return → bottom → bottom left-right → middle  

<p align="center">
 <img src="../../_assets/8_2_6.png" width="60%"></img>
 <em><p align="center">Figure 8.2.6. Touch Sensing Sequence - V-Groove</p></em>
</p>   

---
 
#### [3] BUTT

<p align="center">
 <img src="../../_assets/8_2_7.png" width="30%"></img>
 <em><p align="center">Figure 8.2.7. Example of Touch Sensing - Butt</p></em>
</p>   


- Examples of Command
```python
    touchsen cnd=2, crd="tool", dir="+tx", lift_up=3, pose=P10, gap=var_gap   
    # Condition 2, tool coordinate direction, touch the bottom and rise 3mm
```  
  - Butt Type is recommended to teach the tool posture vertically to the floor surface before starting the sensing, as shown in the figure above.
  - The direction parameter corresponds to one direction for the left-right sequence. The downward sequence direction is fixed in the `+Tz` direction.  
  - After bottom sensing, it is recommended to set the lift-up amount to at least 3mm for stable sensing. The size of the sensed gap may change depending on the lift-up amount.  

- Sensing Sequence
  - The sensing sequence proceeds as follows: upper left-right → middle return → bottom → bottom left-right → middle  

<p align="center">
 <img src="../../_assets/8_2_8.png" width="60%"></img>
 <em><p align="center">Figure 8.2.8. Touch Sensing Sequence - Butt</p></em>
</p>   



### (4) Sensing Direction Angle Transformation

Angle transformation of the sensing direction is supported in Fillet and Groove Detection types.
By specifying an angle for the sensing direction, you can change the direction of the search process.
In the command, the rotation parameter is entered as "X30", "Y-30", "TL20", etc.  

Angle specification rotates the entire search direction by the specified angle along one of the selected axes, either the TL axis or the orthogonal XYZ axes.
[FIgure 8.2.9] shows an example where the Fillet and Groove detection workpieces are rotated by 30 degrees along the Y-axis or TL axis.


<p align="center">
 <img src="../../_assets/8_2_9.png" width="300"></img>
 <em><p align="center">Figure 8.2.9. Example of Touch Sensing - Angle setting</p></em>
</p>       

- Examples of Command

```python
   touchsen cnd=1, crd="robot", dir=["+x","-z"], rotation="Y30", pose=P100
   touchsen cnd=1, crd="robot", dir=["+x","-z"], rotation="TL30", pose=P100
   touchsen cnd=2, crd="tool_prj", dir=["td","tf"], lift_up=5, rotation="Y-30", pose=P100
   touchsen cnd=2, crd="tool_prj", dir=["td","tf"], rotation="TL-30", pose=P100   # Detect Groove 
```

- The angle rotation axes that can be specified depending on the workpiece type and the sensing direction coordinate system designated in the command are as shown in the table below.

<center>

| Sensing Type	| Sensing Direction </br> Coordinate System	| Angle Specification Axis |
|:---:|:---:|:---:|
|Fillet	| All	| Orthogonal XYZ axes </br> TL axis |
|Detect Groove |	Tool (crd="tool") </br> Tool Projection (crd="tool_prj") |	Orthogonal XYZ axes </br> TL axis |

</center>


### (5) Master/Execution Mode in Touch Sensing

The master mode can be turned On/Off using the user key.
When touch sensing is performed with the master mode On, the master pose can be saved and used as a reference for teaching.  
During actual operation, the master mode is turned Off, and touch sensing is performed. In this case, the system automatically calculates the shift amount of the workpiece relative to the master pose based on the current sensing pose.  

In master mode, the sensed pose is saved in the variable specified by the `mpose` input parameter of the touch sensing command.
In execution mode (when master mode is OFF), the current sensed pose is compared with the pose sensed in master mode, and the shift amount is calculated.
The shift amount is then recorded in the variable specified by the `mshift` input parameter.


- Examples of Command
```python
   var P10=cpo()
   var sft_var1=Shift(0,0,0,0,0,0,"base")
   ....
   touchsen cnd=1, crd="robot", dir=["+x","-z"], mpose=P10, mshift=sft_var1
```  

- For example, in master mode, the sensed pose is saved in the `P10` pose variable, and in execution mode, when sensing is performed, the shift amount between the master mode pose and the current sensed pose is automatically calculated and stored in the sft_var1 variable.
