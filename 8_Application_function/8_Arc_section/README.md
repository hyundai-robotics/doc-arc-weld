# 8.8 Arcsection

{% hint style="info" %}
This feature is supported in versions 70.04-00 and later.
{% endhint %}

This function is used to specify a particular length [mm] between arcon and arcoff, and to linearly interpolate (start value ~ end value) the current, voltage, welding speed, weaving width, and weaving frequency over that length starting from the time the command is executed.

The operation is as shown in the following figure.

![](../../_assets/8_8_1.png)<br>
*그림 8.8.1 Arcsection 기능 사양*<br/>

When arcsection is finished, the element retains the value of e until arcoff is executed.

If you run arcsection on the same element again before arcsection finishes, the value changes to the new element's s value and is linearly interpolated.
