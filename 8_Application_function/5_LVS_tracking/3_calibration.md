# 8.5.3 LVS Calibration


In order to use the LVS funtionality, calibration between the TCP and sensor coordinate system must be performed first.

${cont_model} controller supports automatic calibration.

Let's now look at how to perform automatic calibration between TCP and LVS sensor.

### (1) Preparation of Calibration Specimen

Prepare a 15 cm long lap joint specimen with a 3 mm step.


{% hint style="info" %}
If you wish to use it for testing purpose, please contact us to prepare the calibration specimen.
{% endhint %}

---

### (2) Automatic Calibration Teaching

![](../../_assets/8_5_7_lvs_autocalib.png)<br>
*Figure 8.5.7. LVS Auto Calibration*   
</br>

As shown in the figure above, move the TCP to the reference point of the specimen using the jog function.

The torch orientation should be perpendicular to the specimen (both Roll and Pitch direction should be vertical).

Position the laser line perpendicular to the edge of the specimen using jog (typically controlled by Tool Z).

In this state(where the torch is positioned perpendicular to the specimen and the laser line is perpendicular to the edge of the specimen), press **[Record]** to insert the `move` command.

{% hint style="warning" %}
- Use a level to precisely align the torch's orientation perpendicular to the calibration specimen.
- The vertical accuracy of the torch and the accuracy with which the laser line is perpendicular to the edge of the specimen will affect the calibration accuracy.
{% endhint %}


After inserting `delay 0.5`, input the `lvs` command.

The seam parameter of the `lvs` command is the number corresponding to the shape and conditions registered in the LVS controller.

{% hint style="info" %}
For calibration, register the seam as a lap joint in the LVS controller's software.<br>
Set the registered number in the seam parameter of the lvs command.
{% endhint %}


The program written as described is shown below:

```python
    move L,spd=60%,accu=0,tool=0  # Calibration specimen reference point
    delay 0.5
    lvs auto_calib, cnd=1, seam=1, sp=p1, opt=0
    end
```

---

### (3) Preparations

Automatic Calibration involves motions such as front/back, left/right, roll direction rotation, and height adjustments, so ensure safety precautions are followed.

{% hint style="warning" %}
* Adjust the LVS settings (exposure time, laser intensity, shape settings) so that the LVS can recognize the seam of the specimen even at higher positions.
* When the laser is pointing to the flat surface outside the reference point of the specimen, the LVS controller should not be able to recognize the seam.
{% endhint %}


---

### (4) Execution

Once calibration is complete, the "comp!" indicator will appear in the 'info' section of the 'LVS tracking' monitoring table.

---

### (5) Tool and LVS Calibration Information

Each tool number has its own LVS calibration, which is useful when using tool changing.

If you perform automatic calibration for tool 0 and want to use tool 1 or tool 2, you will need to perform automatic calibration for those tools as well.

If you want to use the same tool information but with different numbers, you can enter the following window to copy and apply the calibration information.

- Navigate to `[F2: System] - 4: Application parameter - 5: LVS tracking - 2: LVS Calibration`.<br>

![](../../_assets/8_5_8_lvs_tool_calibmat.png)<br>
*Figure 8.5.8. LVS Calibration Information*   
</br>