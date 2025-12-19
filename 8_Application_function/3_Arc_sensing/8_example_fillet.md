# 8.3.8 Fillet Welding Example Using Touch Sensing and Arc Sensing

In general, the Arc Sensing function is used together with the touch sensing function. Touch sensing is used to accurately detect the welding start and end positions, while arc sensing is used to determine the correct welding direciton during movement after welding has started.  

The first example demonstrates a basic fillet welding operation.

The work sequence is as follows:

1) Set the weaving conditions, arc sensing conditions, and welding conditions.  
2) Use touch sensing to search for the welding start position.
3) Move to a position near the welding end area, and then use touch sensing to search for the welding end position.
4) Perform the welding operation from the welding start position using the weaving command and the arc welding command.


<p align="center">
 <img src="../../_assets/8_3_13" width="60%"></img>
 <em><p align="center">Figure 8.3.13 Fillet Touch Sensing and Arc Sensing</p></em>
</p>


The example program is shown below.

~~~~~~~Arc sensing program : 0001.JOB~~~~~~~~~~~~~~~ 
' Arc sensing program  
S1   move P,spd=60%,accu=3,tool=1              ' 1: Motion start point  
S2   move L,spd=30%,accu=3,tool=1              ' 2: Touch sensing position for welding end point  
     var p10=cpo()  
     var p1=cpo()  
     touchsen cnd=1,crd="robot", dir=["x","-z"], pose=p10   ' 3: Touch sensing for welding end point. Position stored in P10  
S3   move L,spd=30%,accu=3,tool=1              ' 4: Touch sensing position for welding start point  
     touchsen cnd=1,crd="robot",dir=["-x","-z"], pose=p1    ' 5: Touch sensing for welding start point. Position stored in P1  
S4   move L,p1,spd=20%,accu=3,tool=1            ' 6: Move to welding start point  
     weaving on, cnd=1                          ' 7: Start weaving and arc sensing  
     arcon cnd=1                                ' 8: Start welding  
S5   move L,p10,spd=60cm/min,accu=3,tool=1      ' 9: Move to welding end point  
     arcoff                                     '10: End welding  
     weaving off                                '11: End weaving and arc sensing  
S6   move P,spd=60%,accu=3,tool=1               '12: Motion end point  
     END  
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
