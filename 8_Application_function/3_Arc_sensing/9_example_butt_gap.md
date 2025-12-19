# 8.3.9 Arc Sensing Example : Automatic Weaving Width Setting Using Touch Sensing


Create a single job program that can be applied to both workpieces shown below.

<p align="center">
 <img src="../../_assets/8_3_14.png" width="60%"></img>
 <em><p align="center">Figure 8.3.14 Butt Joint Workpieces for Touch Sensing and Arc Sensing</p></em>
</p>

Assumed Operating Conditions  

- A process that welds the joint between two workpieces, 180° planar weaving, 
- Welding travel direction: X+. Touch sensing is performed left and right along the Y direction.
- Arc Sensing parameter settings are assumed to have been completed in advance.
- When the gap is 4.0 mm, the welding speed is 7.0mm/sec
- When the gap is 8.0 mm, the welding speed is 3.5mm/sec

The work sequence is as follows:

1) Using the touch sensing command, measure the weld center position and the gap distance at **the end point** of the butt joint.
2) Using the touch sensing command, measure the weld center position and the gap distance at **the start point** of the butt joint.
3) Check whether the gap_var value is within the allowable range. Stop the robot if the gap is outside 2.0 mm to 10.0 mm.
4) Set half of the measured gap distance as the weaving offset for each side: left (wall side) and right (opposite side).
5) Calculate the welding speed by interpolation using the speeds at 4.0 mm and 8.0 mm gap. If the gap is less than 4.0 mm, apply a fixed speed of 7.0 mm/s. If the gap exceeds 8.0 mm, apply a fixed speed of 4.0 mm/s.
6) Automatically apply the calculated weaving width and welding travel speed, and then perform the welding operation.
7) After completing the operation, return to the original start position.


<p align="center">
 <img src="../../_assets/8_3_15.png" width="60%"></img>
 <em><p align="center">Figure 8.3.15 Butt Joint Touch Sensing and Arc Sensing</p></em>
</p>

The example program is shown below.

~~~~~~~Arc sensing program: 0002.JOB~~~~~~~~~~~~~~~ 
     ' Butt joint arc sensing program 
     ' Condition No. 1: start condition, Condition No. 10: end condition
S1   move P,spd=60%,accu=3,tool=1              ' 1: Motion start point  
S2   move L,spd=30%,accu=3,tool=1              ' 2: Touch sensing position for welding end point  
     var p10=cpo()  
     var p1=cpo()  
     var gap_var1=0  
     var gap_var11=0  
     touchsen cnd=2,crd="tool",dir="+ty",lift_up=5,pose=p10,gap=gap_var11  
                                                ' 3: Touch sensing for welding end point. Position stored in P10  
S3   move L,spd=30%,accu=3,tool=1              ' 4: Touch sensing position for welding start point  
     touchsen cnd=3,crd="+ty",lift_up=5,pose=p1,gap=gap_var1  
                                                ' 5: Touch sensing for welding start point. Position stored in P1  

     ' Calculate welding speed and weaving width according to gap at the start point  
     var V3=0  
     IF gap_var1<2.0 OR gap_var1>10.0 THEN      ' Gap out of allowable range  
     GOTO *Error  
     ELSEIF gap_var1<4.0 THEN                   ' If gap ≤ 4 mm, fix speed to 7 mm/s  
     V3=7.0                                     ' Welding speed at start  
     ELSEIF gap_var1>8.0 THEN                   ' If gap ≥ 8 mm, fix speed to 4 mm/s  
     V3=4.0                                     ' Welding speed at start  
     ELSE                                       ' Linear interpolation for gap range 4–8 mm  
     V3=(7-3.5)/(4-8)*gap_var1+10.5             ' Linearly interpolated welding speed at start  
     ENDIF  

     var V4=gap_var1/2.0                        ' Left-side weaving width (half of gap)  
     var V5=gap_var1/2.0                        ' Right-side weaving width (half of gap)  

     '--------------------------------------------------------  
     ' Calculate welding speed and weaving width according to gap at the end point  
     var V13=0  
     IF gap_var11<2.0 OR gap_var11>10.0 THEN    ' Gap out of allowable range  
     GOTO *Error  
     ELSEIF gap_var11<4.0 THEN                  ' If gap ≤ 4 mm, fix speed to 7 mm/s  
     V13=7.0                                    ' Welding speed at end  
     ELSEIF gap_var11>8.0 THEN                  ' If gap ≥ 8 mm, fix speed to 4 mm/s  
     V13=4.0                                    ' Welding speed at end  
     ELSE                                       ' Linear interpolation for gap range 4–8 mm  
     V13=(7-3.5)/(4-8)*gap_var11+10.5           ' Linearly interpolated welding speed at end  
     ENDIF  

     var V14=gap_var11/2.0                      ' Left-side weaving width  
     var V15=gap_var11/2.0                      ' Right-side weaving width  

     '---------------------------------------------------------  
S4   move L,1,S=20%,A=3,T=1                     ' 6: Move to welding start point  
     weaving on, cnd=2                          ' 7: Start weaving and arc sensing  
     arcon cnd=2                                ' 8: Start welding  
     arc_cond L,spd=V3,ld=V4,rd=V5,freq=2       ' 9: Continuous change of welding parameters (start)  

S5   move L,p10,spd=60cm/min,accu=3,tool=1      '10: Move to welding end point  
     arc_cond L,spd=V13,ld=V14,rd=V15,freq=2    '11: Continuous change of welding parameters (end)  
     arcoff                                     '12: End welding  
     weaving off                                '13: End weaving and arc sensing  

S6   move P,spd=60%,accu=3,tool=1               '14: Motion end point  
     END  

     *Error                                     '15: Escape routine when gap is out of range  
     DO200=1                                   '16: Output signal to indicate error  
     STOP                                      '17: Stop robot  
     END  
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
