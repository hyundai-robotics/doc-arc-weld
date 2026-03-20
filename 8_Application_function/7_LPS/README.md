# 8.7 LPS(Laser Point Sensing)  

{% hint style="info" %}
This function is supported in versions 70.00-00 and later.
{% endhint %}

This function is used to achieve effects similar to touch sensing, such as detecting the weld start point, intermediate points, and end point.
Since touch sensing requires the welding wire to make direct contact with the base material, it takes a longer execution time and may cause interference due to the welding torch.  

To overcome these limitations, the Laser Point Sensing (LPS) function using a 1D-type laser distance sensor is provided.
By utilizing a laser, sensing time is reduced and interference constraints are minimized, allowing weld points to be detected more easily and quickly under simple conditions.  

Once the laser sensor is installed on the tool flange equipped with the welding torch using a bracket, and tool-to-sensor calibration is performed once, the pose of the position indicated by the laser can be obtained easily.
In addition to step detection, the pose of a weld point can be obtained easily regardless of the base material shape, without requiring complex condition settings.
Similar to touch sensing, Master mode can be used, and when a workpiece is introduced, the amount of shift from the reference position can be calculated automatically.  


In the following sections, you will complete the sensor setup and begin using the LPS function.


