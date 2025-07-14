# 6.2.2 Reference Point Edit

### (1) Recording Reference Points : Similar to the Move Command

- ① **Move the Cursor**: Move the cursor to the location where the reference point will be recorded (typically just above the `weaving on` command step).
- ② **Record the Reference Point Command**: Press [**Command Input > arcweld > refp**] to record the reference point command.
- ③ **Enter the Reference Point Number**
- ④ Pose Method:
  - The *Hidden Pose Method* records the current robot position.
  - When using the *Pose Variable Input Method*, enter the pose variable after the reference point number.


### (2) Moving to the Reference Point

Reference points determine the weaving pattern, so typically, the robot does not move to the reference point during playback.
However, when checking or modifying the reference point location, follow these steps.  

- ① Move the cursor to the reference point command.
- ② Press the step forward key to move to the reference point.  

When moving, the interpolation type is set to linear, and the movement speed, tool, and acceleration settings will be based on the conditions set in the weaving section's start step.


### (3)	Modifying the Reference Point (for Hidden Pose Method)

- ① Move the Cursor to the reference point command.
- ② Use the Jog key to move to the new location for the reference point.
- ③ Press **[SHIFT] + [위치수정]** key to change the reference point's location.


### (4) Deleting the Reference Point Command

- ① Move the cursor to the reference point command.
- ② Press **[SHIFT] + [DEL]** to delete the reference point command.


### (5)	Modifying the Reference Point Number

- ① Move the cursor to the reference point command.
- ② Press **[ENTER]** key.
- ③ Input the new reference point number and press **[ENTER]**.
- ④ Press **[ENTER]** again to confirm the change of the reference point number.

