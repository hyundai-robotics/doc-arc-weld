# 8.3.3.2 Arc Sensing Condition(Advanced)


In the third tab of the Weaving Condition Edit Screen, advanced settings can be configured.<br>

```It is recommended to use the default values in this tab whenver possible.```


![](../../_assets/8_3_3.png)<br>
*Figure 8.3.3. Arc Sensing Condition(Advanced) Dialog Box*


The settings and operation methods for each item are as follows:

### (1) Maximum Tracking Speed: [0.1~ 20.0] mm/s

This setting defines the maximum left/rgiht/up/down distance (or speed) that can be tracked in 1 second.


### (2) Tracking Limit Distance: [0 ~ 200] mm (0: Disabled)

This setting defines the limit for the left/right/up/down arc sensing tracking distance.
If tracking exceeds the limit set by the arc sensing, an error will occur and stop the operation.


### (3) Calculation Range: [1 ~ 100] % (default: 50%)

This setting defines the range for calculating the left/right current. <br>
```As the weaving amplitude decreases, it is advantageous to set this value smaller. (e.g. for 1mm amplitude, set to 50%; for 0.5 mm amplitude, 40% is recommended.)```


### (4) Asymmetric Sensing Ratio: [-50 ~ 50] %

This setting defines the asymmetric sensing ratio when the left and right bead widths are different.<br>
A positive value indicates the right direction when viewed from the back of the torch in the welding direction, and a negative value indicates the left direction.

{% hint style="info" %}
  During arc sensing, if `weavings_.asymetric_sensing_ratio=10` is executed, asymmetric tracking will occur towards the right, maintaining the right-side current 10A higher.
  If this value is set to a negative number, asymmetric tracking will occur towards the left.
{% endhint %}


---

### (5) Abnormal Data Handling Method: <Error, Warning, Disable>

This setting defines how to handle data when the normal current range, calculated using the "detection margin," exceeds the limit for the "detection time."

- Error: The robot diplays an error and stops.
- Warning: The robot displays a warning and continues the operation.
- Disable: The robot continues the operation without any interruption.


### (6) Detection Margin: [100 ~ 200] %

This setting defines the margin for determining abnormal current values from the current data. The default value is 150 %.<br>
As shown in the figure below, the range is based on 'Q1 - 1.5 * IQR' for the lower bound and 'Q3 + 1.5 * IQR' for the upper bound.


![](../../_assets/8_3_4.png)<br>
*Figure 8.3.4. Abnormal Detection Margin*
<br>

### (7) Detection Time: [10 ~ 1000] ms

This setting defines the amount of time allowed for current input that exceeds the abnormal detection margin.<br>
If the margin is exceeded for a period longer than this time, the robot will operate based on the selected handling method (error, warning, or disable).

---

### (8) Hybrid Mode ```(Welding Seam Estimation + Current Difference)``` <br>

This setting determines whether the current will be regressed at the end of each weaving half-cycle or at the end of each full weaving cycle.


### (9) Current Regression Error Tolerance ```(Welding Seam Estimation + Current Difference)``` <br>

This setting defines the acceptable current error during regression. For smaller weaving widths or minor improvement angles, a smaller value should be selected. The default value is 1A.


### (10) Data Sampling Option during Regression ```(Welding Seam Estimation + Current Difference)``` <br>

This setting defines the method for processing sampled data during regression: Raw, Median, or Average.

</br>
