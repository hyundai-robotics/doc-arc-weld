# 6.2 Reference Point(refp) Features


To perform weaving, a weaving coordinate system is required to determine the location where the weaving pattern will be created, as explained in [[6.1 Weaving Functions]](../1_Weaving_function/README.md).
The configured weaving coordinate system is usde to set the detailed parameters for the weaving function.
By default, when the weaving motion begins, the Z-axis of the robot's coordinate system is set to the wall direction.
The weaving coordinate system (rectangular coordinate system) is automatically created using the position of the pose approaching the welding start point and the direction of the torch during the welding process.  

However, in some cases, such as when the welding start pose, the shape of the base material, or its position prevent the creation of the weaving coordinate system, or when modifications to the default weaving coordinate system are needed (e.g., when the angle between the wall direction and the other direction is not 90 degrees), the reference point function can be used to create a desired weaving coordinate system and align the weaving pattern with the base material.


{% hint style="info" %}
  When the **[Wall Direction]** setting is configured as Torch Posture-Based, no other `refp` commands except `refp3` are used.
{% endhint %}