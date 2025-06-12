# 1.3.3 Change the Current/Voltage during Welding

This function is used when teaching Arc welding tasks and there's a need to change the welding current/voltage during welding to find the appropriate settings.

Using this function, you can change the current/voltage in real-time during welding to find optimal conditions and then immediately save the verified conditions as welding parameters.

The detailed content and setup method for this function are as follows:  <br/>
("%" refers to the unit relative to the difference between the welder's minimum and maximum values)

---  

### Entering the Arc Welding Current/Voltage Change Dialog Box

<p align="center">
 <img src="../../_assets/1_3_1.png" width="70%"></img>
 <em><p align="center">Figure 1.3.1. Arc Weld program and Change I/V</p></em>
</p>

<br>

1. Perform arc welding in automatic mode.
2. Navigate to **[pane layout > select > arc change IV]**
3. Click the **[+/-]** button to enter the adjustment button window.

---  

### Parameter Adjustment Key during Arc Welding  

|      | [+ Current]/[- Current]                   |`[SHIFT]` + [+ Current]/[- Current] |
| ------ | --------------------- |--------------------- |
| **Function** | Welding Current 1% +/-         | Welding Current 5% +/-|

|      | [+ Voltage]/[- Voltage]                   |`[SHIFT]` + [+ Voltage]/[- Voltage] |
| ------ | --------------------- |--------------------- |
| **Function** | Welding Voltage 1% +/-         | Welding Voltage 5% +/-|

|      | [+ Weaving L]/[- Weaving L]                   |`[SHIFT]` + [+ Weaving L]/[- Weaving L] |
| ------ | --------------------- |--------------------- |
| **Function** | Weaving Width(Left) 0.1[mm] +/-         |Weaving Width(Left) 0.5[mm] +/-|

|      | [+ Weaving R]/[- Weaving R]                   |`[SHIFT]` + [+ Weaving R]/[- Weaving R] |
| ------ | --------------------- |--------------------- |
| **Function** | Weaving Width(Right) 0.1[mm] +/-         |Weaving Width(Right) 0.5[mm] +/-|

|      | [+ Frequency]/[- Frequency]                   |`[SHIFT]` + [+ Frequency]/[- Frequency] |
| ------ | --------------------- |--------------------- |
| **Function** | Weaving Frequency 0.1[Hz] +/-         | Weaving Frequency 0.5[Hz] +/-|



---  


### Arc welding Current/Voltage Auto saving settings

- Navigate to **[System > 4: Application parameter > 2: Arc welding]**
- **[Arc welding I/V change auto saving]**
    - **Disable**  
    Not saved

    - **Enable**  
    Save to welding conditions as soon as the user changes the value

---  


### Operation

The details for each item in the dialog box are as shown in the following figure.

<p align="center">
 <img src="../../_assets/1_3_2.png" width="70%"></img>
 <em><p align="center">Figure 1.3.2. Arc Welding Change I/V dialog box</p></em>
</p>

{% hint style="info" %}
- Current/Voltage changes are saved only to the welding Start Conditions, not to the End Conditions.

- If the ```arcon``` command specifically designates current and voltage values, then the changes will only be saved to the welding conditions.

Example: arcon cnd=1,cur=200,vol=20 # The changed current and voltage are saved to welding start condition #1.
{% endhint %}
