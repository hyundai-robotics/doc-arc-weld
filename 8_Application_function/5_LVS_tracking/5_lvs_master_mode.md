# 8.5.5 LVS Master Mode Func.

### (1) Master Mode Overview

The Master Mode function stores a reference position (Master pose) and calculates the shift between the current sensed position and the reference position during actual production.

To enable this functionality, **[user key > Master Mode]** must be activated to register the reference position(Master pose) in advance.


<p align="center">
 <img src="../../_assets/8_5_12_lvs_seamfind_mastermode.png" width="90%"></img>
 <em><p align="center">Figure 8.5.12. Example of Master Mode and Actual Motion</p></em>
</p>   
</br>

As shown in the left part of the figure, after activating Master Mode, the Master Pose is saved to the pose variable assigned to the `mp` parameter in the `lvs` command.

Typically, the sensing points are pre-taught, and once Master Mode is activated, the system automatically plays back to the complete the master teaching.

In thick welding application, several tens of welding waypoints will typically be registered as Master Poses.

Once the Master Teaching is completed, the Master Mode is turned off. There is no need to turn Master Mode back on after completing the Master Teaching.

During production, the robot operates in automatic or remote mode and senses each welding point to calculate the shift.

At this point, the shift relative to the Master Pose is automatically calculated and stored in the shift variable designated by the `ms` parameter in the `lvs` command.

This shift value is then applied to the `tg` parameter in the `move` command to compensate for the shift in the welding position, allowing the welding operation to be carried out accurately.


{% hint style="warning" %}
Important notes when registering master pose.

* During the registeration of the Master Pose, ensure that the side and height of the seam sensed by the LVS S/W at the sensing position are both close to 0.
* By teaching as described above, sensing can be performed stably, and Master Pose management, as well as the detection of any misalignment in the LVS or tool, can be easily recognized.

{% endhint %}


<p align="center">
 <img src="../../_assets/8_5_13_lvs_seamfind_mastermode_warn.png" width="90%"></img>
 <em><p align="center">Figure 8.5.13. Important Considerations When Registering Master Pose</p></em>
</p>   
</br>

---

### (2) Shift Quantity Check Function Relaive to Master Mode

The shift quantity(in mm) between the current sensed pose and the Master Pose can be checked to verify if it falls within the user-defined range.

To set the range, access the **[property]** window in the lvs command, and enter the desired distance from the reference position in the "distance from reference position" field under the "Seam finding option"(in mm). 

If the shift value exceeds the user-defined range during seam finding, an error will occur.

{% hint style="warning" %}
If the `sp` parameter is not declared, it will be treated as a local pose.<br>
If the `mp` parameter is not declared, it will be treated as a global pose.<br>
If the `ms` parameter is not declared, it will be treated as a global pose.
{% endhint %}