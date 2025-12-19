# 8.3 Arc Sensing and Multi Pass

{% hint style="info" %}
  - To use this feature, an Arc sensing license is required.<br> Please contact us to purchase and obtain the license.
  - Additionally, this feature requires **the weaving funtion** to be enabled.<br> Please refer to the weaving section before starting. **[6. Weaving Function](../../6_Weaving_function/README.md)**
{% endhint %}

Arc Sensing is a seam tracking feature that can be used for arc welding on thick materials(such as thick plates).
When using this feature, even if there are seam deviations due to workpiece tolerance or deformation, the welding can be performed accurately.
<br>

The typical usage method is as follows: <br>
1. Teach the reference points (starting point, intermediate points, and endpoint) for the welding area by sensing the seam on the reference workpiece (register the master pose)
2. Perform seam sensing at the same locations on the actual workpiece (calculate the shift relative to the master pose)
3. Apply the calculated shift to each point
4. Use arc sensing for real-time seam tracking during welding


{% hint style="info" %}
  - Before using this function, it is necessary to first perform Arc Sensing delay time calibration.
  - Seam sensing refers to the process of finding the starting point, intermediate points, and endpoint of the welding area.
  - Seam sensing can be performed using touch sensing, LVS seamfinding, LPS(Laser Point Sensing) features.
{% endhint %}

This manual explains the newly added Arc Sensing feature in ${cont_model}.  
The newly added Arc Sensing feature in ${cont_model} is activated by entering the properties window of the `weaving` command and setting the **'type' in the Arc Sensing (General) tab to 'seam & cur_diff'**.

---

**Multi-Pass** is a feature used when welding needs to be repeated over multiple passes rather than in a single pass.
Using this, the first layer (root pass) is welded, and since sensing may be unstable, the tracking trajectory is saved.
Then, the saved trajectory is shifted to generate two or more passes for welding.  

Typically, Arc Sensing is used to perform multi-pass welding, and multi-pass welding is conducted using Arc Sensing.

