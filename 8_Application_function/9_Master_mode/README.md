# 8.9 Master Mode/Production Mode

### (1) Overview  

The Master/Production mode feature saves the pose obtained from a reference workpiece and compares it with the pose obtained from a production workpiece to calculate the positional difference as a shift amount.  

* **Master Mode (On)**: Senses the reference workpiece and registers the master pose.
* **Production Mode (Master Mode Off)**: Senses the production workpiece and calculates the shift amount relative to the master pose.  

Master mode can be turned On/Off through **[User Key] - [Master Mode]**.  

| Category | Master Mode (On) | Production Mode (Master Mode Off) |
| :--- | :--- | :--- |
| Sensed pose `sp` | Stores the current sensing or calculation result | Stores the current sensing or calculation result |
| Master pose `mp` | Stores the same result as `sp` to update the reference position | References the registered reference position without updating it |
| Master shift `ms` | Initializes the shift amount to `0` | Stores the positional difference between the current result and the master pose |

The shift amount is calculated in the direction of **current sensed position - master position** in the specified calculation coordinate system.
Only the position components X, Y, and Z are calculated, while the rotation components Rx, Ry, and Rz are set to 0. Therefore, this function alone does not compensate for rotational errors of the workpiece.  


### (2) Applicable Commands  

| Command | Applicable Function | Result |
| :--- | :--- | :--- |
| `touchsen` | Touch sensing | Registers the sensed pose as the master pose or calculates the shift amount |
| `lvs` | `seam_find`, `seam_find_p`, `intersection`, `step_search` | Registers the detected or calculated pose as the master pose or calculates the shift amount |
| `lps` | `spot`, `stepp`, `scan` | Registers the detected pose as the master pose or calculates the shift amount |
| `arc_intersect` | Intersection calculation using three or four reference poses | Registers the calculated pose as the master pose or calculates the shift amount |

* Note  
`lvs search` and `lvs check_seam` require the `sp` parameter, but do not support the `mp`/`ms` processing described above. The `sp` parameter is optional for `lvs track`.  

For detailed usage of each command, refer to [2.7 lvs](../../2_Command/7_lvson.md), [2.8 lps](../../2_Command/8_lps.md), [2.13 touchsen](../../2_Command/13_touchsen.md), and [2.15 arc_intersect](../../2_Command/15_arc_intersect.md).  


### (3) Common Parameters and Variable Creation

| Parameter | Variable Type | Description | If the Specified Variable is Not Defined |
| :--- | :--- | :--- | :--- |
| `sp` | Pose | Stores the current sensing or calculation result | Automatically created as a local pose variable |
| `mp` | Pose | Stores and references the master pose | Automatically created as a global pose variable only in master mode |
| `ms` | Shift | Stores the shift amount relative to the master pose | Automatically created as a global shift variable only in master mode |

Automatic variable creation is performed **only when a valid variable name is specified in the parameter but the variable has not yet been defined**. Omitting the parameter does not automatically assign a variable name or create a variable.
If the specified variable is already defined, the existing variable is used. Therefore, make sure that the variable type is appropriate (pose or shift).  

In production mode, the variables specified by the `mp` and `ms` parameters must already be defined. Also, verify that the master pose has been properly registered. Simply declaring the variables does not replace master teaching.  


{% hint style="warning" %}
In general, only the `sp` parameter is used. However, in master mode, both `mp` and `ms` parameters must be specified. For `arc_intersect`, all parameters must always be specified.
{% endhint %}


### (4) Operating Procedure

#### 1. Master Teaching

1. Install the reference workpiece and check the sensor settings, sensing conditions, and calculation coordinate system.
2. Teach each sensing start position and verify the sensing path.
3. Set **[User Key] - [Master Mode]** to On.
4. Execute the sensing commands with the `sp`, `mp`, and `ms` parameters specified.
5. Verify that the reference pose is stored in `mp` for each sensing point and that `ms` is initialized to 0.
6. After completing master registration, set master mode to Off.  

#### 2. Production Operation

1. Install the production workpiece and verify that master mode is Off.
2. Execute the sensing commands using the `mp` and `ms` variables corresponding to the same sensing points used during master teaching.
3. The current sensing result is stored in `sp`, and the shift amount relative to the master pose is calculated and stored in `ms`.
4. Verify the calculated shift amount and coordinate system before applying the shift to correct the work path.  

{% hint style="warning" %}
* If master mode is turned On during production, the master pose will be updated with the sensing result of the current workpiece. Keep master mode Off unless you intend to register a new reference position.
* Use separate master pose and shift variables for different sensing points. Reusing the same variable will overwrite the results from previous sensing points.
* If the sensing conditions, tool, or coordinate system have changed, verify the reference position and calculated shift amount before using the existing master pose.
{% endhint %}


### (5) Examples

The following examples demonstrate how to specify the command parameters. Each command assumes that the corresponding sensor and sensing conditions have been configured and that the robot has reached the sensing start position. Before executing the commands, set the conditions, direction, travel distance, and speed appropriate for the actual workpiece.  

```python
    # Touch sensing
    touchsen cnd=1,crd="robot",dir="+y",sp=p10,mp=mp10,ms=ms10

    # Master registration/shift calculation using LVS sensing results
    lvs seam_find,cnd=1,seam=10,sp=p10,mp=mp10,ms=ms10

    # Master registration/shift calculation using LPS sensing results
    lps scan,cnd=1,Tx=50,spd=10,sp=p20,mp=mp20,ms=ms20
```  

* To obtain only the sensing pose with Master Mode Off, **omit both `mp` and `ms`**.  


### (6) Related Information

* [8.2 Touch Sensing](../2_Touch_sensing/README.md)
* [8.5.5 LVS Master Mode Func.](../5_LVS_tracking/5_lvs_master_mode.md)
* [8.7.3 Using the LPS Function](../7_LPS/3_function.md)
