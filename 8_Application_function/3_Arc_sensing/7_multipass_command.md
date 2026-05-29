# 8.3.7 Multi-pass Command


### (1) Command

The sensing trajectory can be saved and loaded using the multipass command. 
This command can be used in three different forms:
<br>

```py
    multipass save, trj=<multi-pass trajectory number>, period=<trajectory saving interval distance>
    multipass load, trj=<multi-pass trajectory number>, side=<left-right Shift distance>, height=<up-down Shift distance>, reverse=<multi-pass playback direction>, tas=<torch forward/backward angle shift>, was=<torch left/right angle shift>
    multipass off
```

### (2) Multi-pass Parameters

For detailed information on the multi-pass command parameters, please refer to the following link: <br>
[2.11 multipass](../../2_Command/11_multipass.md)

<br>

This section will explain only the following two items:  


- Left-Right/Up-Down Shift

This sets the distance by which the trajectory is shifted from the original path during multipass reproduction.
Since the torch weaving is perpendicular to the tool, each shift is set as follows:
the left/right direction becomes the weaving plane, and the up/down direction becomes the plane perpendicular to the weaving plane.

![](../../_assets/8_3_11.png)<br>
*Figure 8.3.11 Multipass Shift Direction*


- Angle Shift: TAS, WAS  

When performing multi-pass welding, the torch must be tilted for quality control. This setting is used to define the required tilt.
The concept of angles for each item is illusatrated in the following figures:  

![](../../_assets/8_3_12.png)<br>
*Figure 8.3.12 Multipass Angle Shift Concept*
