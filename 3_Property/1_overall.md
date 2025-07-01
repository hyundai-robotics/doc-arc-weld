# 3.1 Overview

When teaching an arc welding program, not only the welding conditions such as voltage and current but also detailed settings related to weaving, retries/overlaps, and the characteristics of the welder are necessary.
Furthermore, in general robot operation, there may be cases where the position information (coordinates and orientation) of the taught steps or auxiliary points needs to be verified.  
By placing the cursor on the command and pressing the [**Property**] button located on the left side of the TP, a function is provided that allows easy and quick editing of these files.


### Example of Command [Property]

| Command | Property | 
| -----| -------| 
| `arcon `| Set the current, voltage, synergic, initial/aux/end conditions, etc. | 
| `weaving on `| Set weaving type, frequency, width, and weaving direction, etc. |
| `lvs `| Configure tracking-related informations, seam finding settings, etc. |
| `arccond `| Manage welding condition database(WDB) with settings for current, voltage, frequency, and weaving width. |
| `move `| Change the current recorded position to base coordinate system, robot coordinate system, or joint coordinate system. |



As an example of editing welding start conditions, when the cursor is placed on the `arcon` command, which turns on the arc, pressing the [**Property**] button will display the details of the condition number currently used in the welding start conditions.
In this screen, you can view or modify the detailed settings of the welding start conditions.

Similarly, after placing the cursor on a specific command and entering the [**Property**] window, you can easily and quickly check and modify the settings, such as the conditions or positions recorded in the steps.
If you wish to save the changes and exit, press [**OK**]; if you wish to exit without saving, press the [**ESC**] key on the teaching pendant.


<p align="center">
 <img src="../_assets/3_1_1.png" width="65%"></img>
 <em><p align="center">Figure 3.1.1. Property in Robot Program Command</p></em>
</p>


{% hint style="info" %}
    For more details, please refer to [2. Inserting Commands]
{% endhint %}