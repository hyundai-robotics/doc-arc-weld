# 8.6.2 STITCH Func. Command
 

<p align="center">
 <img src="../../_assets/8_6_4.png" width="60%"></img>
 <em><p align="center">Figure 8.6.4. Stitch Command Example</p></em>
</p>  


```stitch``` Command: 
After selecting `[F6: cmd.input] - arcweld - stitch` in sequence, choose on/off and press **[ENTER]**.


{% hint style="warning" %}
- ```S2 move L, spd=10mm/s, accu=3, tool=1```  
	- L : Ensure that linear interpolation is selected.  
	- 200mm/sec : Welding speed - the speed during the ON section of the stitch welding. the unit must be set to mm/sec
- ```arcon / arcoff``` Use the command together to start welding.
{% endhint %}