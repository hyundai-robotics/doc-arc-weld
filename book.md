
[__SOURCE](README.md)
# ${cont_model} Robot Controller Functional Manual - Arc Welding

[__SOURCE](0-about-this-manual/README.md)
# About the Manual

[__SOURCE](0-about-this-manual/precautions.md)
# Precautions

{% include file="en/precautions.md" %}

[__SOURCE](0-about-this-manual/safety-notice.md)
# Safety Cautions

{% include file="en/safety-notice.md" %}

[__SOURCE](0-about-this-manual/structure.md)
# Book Structure

This manual consist of 8 chapters.

### Chapter 1: Arc Welding Basics
This chapter explains the settings, basic teaching methods, and convenience function required when using an Arc welding robot for the first time.
<br/><br/>

### Chapter 2: Inserting Commands
This chapter introduces various Arc welding related commands and their simple setup methods. Through this chapter, you can get a quick overview of the basic functions supported by our company Arc Welidng Robots.
<br/><br/>

### Chapter 3: Command Property
This chapter explains the property functions for detailed settings of some commands introduced in Chapter 2. It explains how to edit Arc welding conditions, which are essential settings when using an Arc welding robot, and how to edit application function commands.
<br/><br/>

### Chapter 4: Arc Welder Settings
This chapter introduces how to select the Arc Welder you want to use and the items that need to be set for each welder.
<br/><br/>

### Chapter 5: Editing Arc Welding Conditions
This chapter explains how to edit Arc welding conditions. It introduces how to set essential parameters for welding, such as current, voltage, welding mode, and gas pre/post-flow. Since welding conditions vary by welder, you can only understand the content about the welder you want to use.
<br/><br/>

### Chapter 6: Weaving Function
This chapter introduces the weaving function and its detailed settings. You can skip this chapter if you are not using the weaving operation.
<br/><br/>

### Chapter 7: Arc Welding Data Monitoring
This chapter explains functions that utilize data sent by the welder during welding process. It describes how to monitor real-time data from the welder and how to save that data to a file. It also describes features for plotting and conveniently reviewing previously saved data as graphs, as well as functions for quantifying welding quality.
<br/><br/>

### Chapter 8: Arc Welding Application Functions
This chapter introduces Arc welding application functions that can be useful in special situations.
It provides a brief overview of functions that can be applied when the welding line of the workpiece is uneven, or when errors in the workpiece position lead to issues with welding quality.
<br/><br/>

When using our Arc Welding Robots for the first time, we recommend reading Chapters 1 ~ 5. For Chapters 6 ~ 8, we suggest selectively reading about the functions you need.

<br>

[__SOURCE](1_Basic_information/README.md)
# 1. Arc Welding Basics
[__SOURCE](1_Basic_information/1_Introduction/README.md)
# 1.1 Overview

Teach the Arc welding operation as shown in the following figure.


![](../../_assets/1_1_1.png)<br>
*Figure 1.1.1. Basic Arc Weld Teaching*

</br>

(1) Turn on the power switch on the front of the Controller.

(2) Select the `[mode witch]` on the (Teach Pendant)TP in manual mode.

(3) Press the `[Program]` on the TP and enter the program number.

(4) If you proceed this far, the TP screen will be displayed as shown below.

![](../../_assets/1_1_2.png)<br>
*Figure 1.1.2. Screen with new program number selected*

</br>

(5) Press the `[Motor On]` button on the TP to power the robot's motor.

(6) Use the axis control key to move the robot's torch to the position in Step 1.

(7) Press the `[rec. cond]` key, then specify the desired interpolation type, speed, accuracy, and tool number.  

- After moving to the desired item using the direction key, set the value and press the `[ENTER]` key to save the setting
- press the `[tool]` key and enter the desired tool number.


![](../../_assets/1_1_3.png)<br>
*Figure 1.1.3. Recording Conditions*

</br>

- Press the `[rec. cond]` key to record the step as shown below.

![](../../_assets/1_1_4.png)<br>
*Figure 1.1.4. Program with recorded Step (1)*

</br>

(8)	Repeat steps 5 through 7 for steps 2 through 4.
 

![](../../_assets/1_1_5.png)<br>
*Figure 1.1.5. Program with recorded Step (2)*

(9) Since the welding area is from Step 2 to Step 3, move the cursor to Step 2.

- Enter the `[F6: cmd. Input] - arcweld - weaving`, input the condition number, and press the `[ENTER]` key.
- In the same way, enter the **[arcon]**, input the condition number, and press the `[ENTER]` key.
(For Arc Welding condition settings, refer to [5. Editing Arc Welding Conditions](../../5_Condition_editing/README.md).)


(10) Move the cursor to Step 3, which is the step where Arc Welding ends.
 
- Again, enter the **[weaving]** and set it to off.
- Also, enter the **[arcoff]**.


(11) Modify the speed of Step 3 to your desired welding speed (e.g., 20mm/s).

(12) Finally, enter the `[F6: cmd. input] - flowctrl - end` command to terminate the program.

![](../../_assets/1_1_6.png)<br>
*Figure 1.1.6. Teaching Completion Screen*
[__SOURCE](1_Basic_information/2_Function_setting/README.md)
# 1.2 Arc Welding function settings
[__SOURCE](1_Basic_information/2_Function_setting/1_usage.md)
# 1.2.1 Arc Welding application settings

(1) Depending on the Robot model, the Arc welding function might not be active. If in this the case, follow the steps below to enable. (Note: Engineer authority is required to set up the Arc welding function)

(2) In manual mode, press `[F2: System] - 5: Initialization - 3: Usage setting`. A dialog box will appear, as shown in [Figure 1.2.1.], allowing you to configure the robot's application, the welder you want to use, user keys, and I/O signal assignments.

(3) [Figure 1.2.1] shows an active Arc welding steps, where the welder number in welder information has been selected as **No.4(Fronius)**. From this screen, pressing **welder setting** will take you to a dialog box where you can configure the conditions for the desired welder.

(4) For detailed settings of the welder characteristic file, please refer to [4. Arc Welder Settings](../../4_Setting/README.md).


![](../../_assets/1_2_1.png)<br>
*Figure 1.2.1. Usage Setting Dialog*
[__SOURCE](1_Basic_information/2_Function_setting/2_signals_functions.md)
# 1.2.2 Arc Welding various signals and funtion settings

On the manual mode screen, press `[F2: System] - 4: Application parameter - 2: Arc welding` to bring up a screen where you can set various conditions for Arc welding applications, as shown below.


![](../../_assets/1_2_2.png)<br>
*Figure 1.2.2. Arc Welding Application parameter Dialog*
 

The details for each item are as follows:

#### [General]
Inching speed(%): 
|`(Low)`[1 ~ 50] %, `(High)`[10 ~ 100] %|, This refers to the wire feed speed when jogging the wire forward(`[SHIFT]+[2]` (wire inching)) or backward(`[SHIFT]+[3]` (wire retreat)).<br> You can set the feed speed for both low-speed and high-speed operation (when the key is pressed for 3 seconds or more).

`[GUN]` key status output signal:
Set the signal to output the current status of the `[GUN]` key on the TP.

`[GUN]` key control disable input: 
Assign an input signal to externally control the `[Gun]` key's on/off status. Once this signal is assigned, you won't be able to change the arc welding on/off status by pressing the `[GUN]` key on the TP. This function helps prevent issues where welding might be skipped in a welding section due to accidential presses of the `[GUN]` key.<br> (When the assigned signal is received, the LED of the `[GUN]` key turns off, and the robot enters a `Dry Run` state where no welding is performed in the arc welding section, despite the robot running.)

Coolant Error Input Signal:
For water-cooled Arc welding torches, a signal is configured to detect issues with coolant circulation. When this signal is received during welding, it is considered an error, which triggers the robot's operation and welding process to stop.


Welder Error treat: 
|[`Disable`, `Warn`, `Error`]|, Set how to handle welder errors.

Wire Empty error treat: 
|[`Disable`, `Warn`, `Error`]|, Set the error handling method when no welding wire is present.

Gas Pressure Error treat: 
|[`Disable`,`Warn`, `Error`]|, Set the error handling method in case of gas pressure abnormalities.

{% hint style="info" %}
Warn gives a warnning message, Error makes robot stop moving with error message.
{% endhint %}

Arc Welding I/V change auto saving: 
|[`Disable`, `Enable`]|, This setting determines whether to automatically save changes to current and voltage values when they are changed within the `arc change IV(Arc Welding Current/Voltage Adjustment dialog box)`. For more details, please refer to [[1.3.3 Change the Current/Voltage during Welding]](../3_Convenient_functions/3_change_current_voltage.md).

Vibration reduction for heavy torch: 
|[`Disable`, `Welding point`, `All range`]|, This setting is designed to reduce vibrations when using heavy torches. It helps to minimize vibrations that may occur when using heavy torches such as water-cooled or push-pull torches.<br> When set to `Welding Points`, a significant reduction in vibrations can be achieved in the welding point entry section without substantial changes in the robot's operating speed.<br> When set to `All range`, a filter specifically designed for heavy Arc torches is applied, virtually eliminating vibrations throughout the entire preocess. However, this may result in a decrease in the robot's operating speed.

Arc welding enable during manual mode: 
|[`Disable`, `Enable`]| This setting determines whether welding can be performed through ste-forward in manual mode.<br> When set to `Enable`, welding can be performed by stepping forward to the Arc welding section, with the execution unit set to `End`. For more details, please refer to [[1.3.4 Manual mode Arc Welding]](../3_Convenient_functions/4_manual_mode.md).

Stick check at cycle start: 
|[`Check`, `Ignore`]| This setting determines whether a wire stick check will be performed when the robot starts its first cycle.<br> When `"check"` is enabled, the robot will perform a check for approximately 0.2 seconds at the beginning before proceeding with movement.

TCP speed ratio monitoring: 
|[`Disable`, `Enable`]| This setting determines whether to monitor the rate of change in the TCP speed.

#### [Touch Sensing]
Touch Sensing Stop Setting: 
|[`Immediately`, `Normal`]|, Set whether to `immediately stop` or `normal stop` when Touch Sensing detects a work piece.<br>If wire bending increases during a normal stop, set it to `immediately stop`

#### [Arc trajectory Monitoring]
Activation: 
|[`Disable`, `Enable`]|, Sets whether to monitor the Arc trajectory.


[__SOURCE](1_Basic_information/2_Function_setting/3_crash_sensor.md)
# 1.2.3 Collision sensor signal settings

Arc welding robot systems uses a collision sensor to prevent torch deformation. The collision sensor basically uses negative logic to immediately detect issues such as a disconnected sensor cable.

The setup dialog box is as follows:

You can configure the collision sensor processing method on `[F2: System] - 1: User Environment`.


#### [Collision sensor process]
| item | Description |
|------|------|
|**Emergency Stop**|When a collision sensor signal is input, the robot turns off its motor and performs an emergency stop|
|**Stop**|When a collision sensor signal is input, the robot keeps its motors On and performs a stop|

#### [How to Change Signal Logic]
If the tool collides and the collision sensor signal turns on, the motor will not turn on. In this case, you need to change the signal logic to negative logic as follows.

- `[F2: System] - 2: Control parameter - 2: Input/Output signal setting - 1: Input signal attribute` - Adding a Signal and Checking the Negative Logic Box  


![](../../_assets/1_2_3.png)<br>
*Figure 1.2.3. How to Change Signal Logic*

{% hint style="info" %}
When you set up a collision sensor in the system's input signal settings, the system will prioritize the input from this signal. Any collision sensor signals received via welder communication will be ignored.
{% endhint %}

[__SOURCE](1_Basic_information/3_Convenient_functions/README.md)
# 1.3 Arc Welding Convenience Functions
[__SOURCE](1_Basic_information/3_Convenient_functions/1_gas_check.md)
# 1.3.1 Gas Check, Wire Inching, and Wire Retract

This describes the functionality for controlling the shield gas valve and the wire feeder motor in an arc welding system. You can check the current shield gas flow rate using the gas check function. The inching and reverse inching(retreat) functions let you adjust the length of the wire protruding from the welding torch.

Here are the functions and how to use them: 


### Gas Check

| Item      | Description                     |
| ------- | ---------------------- |
| **HotKey** | `[Shift]+[1]`          |
| **Dedicated Key** | User Key `GAS CHK`         |
| **Function**  | Open the shield gas valve to verify the gas flow rate |


### Wire Inching

| Item      | Description                          |
| ------- | --------------------------- |
| **HotKey** | `[Shift]+[2]`               |
| **Dedicated Key** | User Key `inching`              |
| **Function**  | Feed the wire forward out of the torch to adjust its length <li>Slow Inching: Press the key for less than 3 seconds</li> <li>Fast Inching: Press the key for 3 seconds or more</li> |


### Wire Retract

| Item      | Description                 |
| ------- | ------------------ |
| **HotKey** | `[Shift]+[3]`      |
| **Dedicated Key** | User Key `retract`     |
| **Function**  | Rewind the wire to adjust its length <li>Slow Inching: Press the key for less than 3 seconds</li> <li>Fast Inching: Press the key for 3 seconds or more</li> |


### Inching Speed Setting

 >- Navigate to `[F2: System] - 4: Application parameter - 2: Arc welding`
 >- Within the Arc welding settings menu, Set your values for both low and high speeds: **Inching speed(%): Low=[---]%, High=[---]%**
 >- The speed is displayed as a percentage of the maximum inching speed.
 >- Depending on your specific welder model, changes to the inching speed may not be reflected.

[__SOURCE](1_Basic_information/3_Convenient_functions/2_high_speed.md)
# 1.3.2 High-speed mobility function

When an Arc welding program runs, the robot's movement speed in welding sections is very slow. This leads to a significant amount of time being consumed during test runs to verify the robot's working position.

To address this, we offer a high-speed movement function that allows the robot to run through welding sections faster than their recorded speed.

{% hint style="info" %}
This function is limited to operating only during step forward/backward movements in manual mode.
{% endhint %}  

The robot's movement speed when the high-speed movement function is active is not limited by the **"Maximum speed during step forward/backward"** in the condition settings. Furthermore, you can enable or disable the high-speed movement function within a welding section, regardless of its current application status(e.g., you can disable it even while it's currently running within a welding section).

The operation method is as follows:


### Manual Max-speed Step FWD/BWD

| Item              | Description              |
| --------------- | --------------- |
| **Dedicated Key**         | `[Shift]+[FWD]` <br> `[Shift]+[BWD]` |
| **Function**          | Move the robot FWD/BWD at manual maximum speed. |

### Handling `[SHIFT]` Key Changes During High-speed Movement
|        | `[SHIFT]` Key Released During High-speed Movement | `[SHIFT]` Key Pressed During Teaching Speed Step FWD/BWD |
| ------ | --------------------- |--------------------- |
| **Operation** | Move the robot forward/backward at manual maximum speed. | Robot stops, then moves at manual maximum speed |

[__SOURCE](1_Basic_information/3_Convenient_functions/3_change_iv.md)
# 1.3.3 Change the Current/Voltage during Welding

This function is used when teaching Arc welding tasks and there's a need to change the welding current/voltage during welding to find the appropriate settings.

Using this function, you can change the current/voltage in real-time during welding to find optimal conditions and then immediately save the verified conditions as welding parameters.

The detailed content and setup method for this function are as follows:  <br/>
("%" refers to the unit relative to the difference between the welder's minimum and maximum values)

---  

### Entering the Arc Welding Current/Voltage Change Dialog Box

![](../../_assets/1_3_1.png)<br>
*Figure 1.3.1. Arc Weld program and Change I/V*

<br>

1. Perform arc welding in automatic mode.
2. Navigate to `[pane layout] - select - arc change IV`
3. Click the **[+/-]** button to enter the adjustment button window.

---  

### Parameter Adjustment Key during Arc Welding  

|      | [+ Current]/[- Current]                   |`[SHIFT]` + [+ Current]/[- Current] |
| ------ | --------------------- |--------------------- |
| **Function** | Welding Current 1% +/-         | Welding Current 5% +/-|  

<br/>


|      | [+ Voltage]/[- Voltage]                   |`[SHIFT]` + [+ Voltage]/[- Voltage] |
| ------ | --------------------- |--------------------- |
| **Function** | Welding Voltage 1% +/-         | Welding Voltage 5% +/-|  

<br/>


|      | [+ Weaving L]/[- Weaving L]                   |`[SHIFT]` + [+ Weaving L]/[- Weaving L] |
| ------ | --------------------- |--------------------- |
| **Function** | Weaving Width(Left) 0.1[mm] +/-         |Weaving Width(Left) 0.5[mm] +/-|  

<br/>


|      | [+ Weaving R]/[- Weaving R]                   |`[SHIFT]` + [+ Weaving R]/[- Weaving R] |
| ------ | --------------------- |--------------------- |
| **Function** | Weaving Width(Right) 0.1[mm] +/-         |Weaving Width(Right) 0.5[mm] +/-|  

<br/>


|      | [+ Frequency]/[- Frequency]                   |`[SHIFT]` + [+ Frequency]/[- Frequency] |
| ------ | --------------------- |--------------------- |
| **Function** | Weaving Frequency 0.1[Hz] +/-         | Weaving Frequency 0.5[Hz] +/-|  

<br/>


---  


### Arc welding Current/Voltage Auto saving settings

- Navigate to `[F2: System] - 4: Application parameter - 2: Arc welding`
- **[Arc welding I/V change auto saving]**
    - **Disable**  
    Not saved

    - **Enable**  
    Save to welding conditions as soon as the user changes the value

---  


### Operation

The details for each item in the dialog box are as shown in the following figure.

![](../../_assets/1_3_2.png)<br>
*Figure 1.3.2. Arc Welding Change I/V dialog box*

{% hint style="info" %}
- Current/Voltage changes are saved only to the welding Start Conditions, not to the End Conditions.

- If the ```arcon``` command specifically designates current and voltage values, then the changes will only be saved to the welding conditions.

Example: arcon cnd=1,cur=200,vol=20 # The changed current and voltage are saved to welding start condition #1.
{% endhint %}

[__SOURCE](1_Basic_information/3_Convenient_functions/4_manual_mode.md)
# 1.3.4 Manual Mode Arc Welding

Generally, Arc Welding is only possible when the robot operates in automatic or remote mode.

Manual Mode Arc Welding is a function that allows welding even when the robot is in manual mode. This is convenient for repeatedly testing various welding conditions during setup.

To use Manual Mode Arc Welding, it should be set as below.

 (1) Go to `[F2: System] - 4: Application parameter - 2: Arc welding - Arc welding enable during manual mode` and check enable.

 (2) Set the **[run to(execution unit)] to "End"** (the second menu on the left side of the TP).

 (3) Execute ```arcon``` using step forward.  <br/>
 * NOTE: If the robot stops during welding(before ```arcoff```) due to a paused step forward movement, ```arcon``` won't execute when you step forward again. In this case, the robot will move to the next teaching point without welding.

[__SOURCE](1_Basic_information/3_Convenient_functions/5_vibration_reduction.md)
# 1.3.5 High weight arc torch vibration reduction function

This function aims to reduce vibrations that can occur when using heavy torches (such as water-cooled torches or push-pull torches) on a small robot. You can configure this feature as described below.

- `[F2: System] - 4: Application parameter - 2: Arc welding - Vibration reduction for heavy torch`: Disable / Welding Point / All range

To reduce vibrations, two methods are provided, each with its own advantages and disadvantages. You can refer to the pros and cons below to choose the method that best suits your situation.


| Item | Description |
| --- | --- |
| **Disable**  |  |
| **Welding Point**  | Significantly reduces a considerable amount of vibrations. No impact on robot cycle time. |
| **All range** | Reduces most vibrations. Increases robot cycle time. |
[__SOURCE](1_Basic_information/3_Convenient_functions/6_signal_test.md)
# 1.3.6 Arc Welding signal test function


The Arc Welding Signal Test function lets you test the input/output status of key welding signals and manually release wire stick-out. This feature is useful for checking the status of welder and communication as it confirms wheter specific signals are operating correctly.

To use this feature, on TP, press `[pane layout] - select - arc welding` sequentially. In the Arc Welding panel, scroll down to see the input/output signal items.


![](../../_assets/1_3_3.png)<br>
*Figure 1.3.3. Arc Welding Monitoring*

| Item | Description |
| ------------- | ---------------------------------------------------------- |
| **Output Signal** | With the desired output signal selected, click the **[Manual Output]** button to test turnning the signal on/off. |
| **Input Signal**| You can verify whether input signals are being recieved correctly according to their operation. |
| **Command Value**| <li>**Manual Wire Stick-out Release**: Select "Stick check" and click the **[Manual Output]** button. </li> <li>**Manual Welder Error Reset**: Select "Welder Error Reset" and click the **[Manual Output]** button. </li>|

[__SOURCE](1_Basic_information/3_Convenient_functions/7_operation_info.md)
# 1.3.7 Arc Welding Operation Information

This function allows you to monitor the operational information of arc welding. With this feature, you can easily check and manage the following aspects:

To use this feature, on TP, press `[pane layout] - select - arc operation info.` sequentially. 


![](../../_assets/1_3_4.png)<br>
*Figure 1.3.4. Arc Welding Operation Information Monitoring*  

| Item | Description |
| --- | --- |
| **since init.** | Displays the welding time, as well as the number of automatic retries and automatic wire stick-out release counts **since system initialization**. |
| **since pow.** | Displays the welding time, as well as the number of automatic retries and automatic wire stick-out release counts **since the system was powered on**. |
| **last cycle** | Displays the welding time, as well as the number of automatic retries and automatic wire stick-out release counts **of the immediately previous cycle**. |
| **current cycle** | Displays the welding time, as well as the number of automatic retries and automatic wire stick-out release counts **for the current cycle**. |
| **overlap count(by cause)**  | Displays the number of overlaps that occur when the robot stops during welding, categorized by the cause of the stop. |
| **clear(on fbt)** | When the Arc welding operation info window is activated, the **[clear]** button appears. Clicking this button will display the operation info clear dialog. You can click the button for the item you wish to clear to perform the desired action. |
[__SOURCE](2_Command/README.md)
# 2. Inserting Commands


[__SOURCE](2_Command/1_arcon.md)
# 2.1 arcon


### Description

```arcon``` command is used to start the Arc Welding process. This command can be used in 4 different forms. However, commands not supported by the configured welder cannot be used.
<br/>

### Syntax
  
```python
arcon
arcon cnd=<Condition Number> 
arcon cnd=<Condition Number>,job=<Job Number of the Welder>,cur=<Current>,vol=<Voltage>, vol_offset=<Voltage Offset>
arcon cnd=<Condition Number>,job=<Job Number of the Welder>  
```  

### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **Arc Welding Condition Number** | The number of the welding condition used to starting Arc Welding and the specific condition (1~100) | Variable |
| **Job Number of the Welder** | The Job number stored in the welder to be used(only for welders supporting job mode) (0 ~ 9999) | Variable |
| **Current** | The output current value for Arc Welding (0 ~ 500)[A] | Variable |
| **Voltage** | The output voltage value for Arc Welding (20 ~ 40)[V] | Variable |
| **Voltage Offset** | The voltage offset value for the synergic voltage during Arc Welding (-200 ~ 200)[V] | Variable |


### Example

```python
   arcon  # Starts Welding using the previously set welding conditions. Retry or Restart is not executed.
   arcon cnd=1  # Starts welding according to the specified welding start condition(cnd=1)
   arcon cnd=1,cur=200,vol=22  # Starts welding with the specified current and voltage(200A, 22V), while other welding conditions follow the settings of the specified welding start condition number(cnd=1)
   arcon cnd=1,job=5 # Starts welding in Job mode, using Job number 5. Other welding conditions follow the settings of the specified welding start condition number(cnd=1)
```  

### Details  

Refer to [[5. Editing Arc Welding Conditions]](../5_Condition_editing/README.md) 
<br/>


{% hint style="warning" %}
[Caution]
 - Some welder models can store various welding settings as jobs internally. In this case, you can use 'Job number of the Welder' item.
{% endhint %}
[__SOURCE](2_Command/2_arcoff.md)
# 2.2 arcoff

### Description

```arcoff``` command is used to stop Arc Welding. This command can be used in 2 different forms. However, commands not supported by the configured welder cannot be used.

<br/>

### Syntax

```python
arcoff
arcoff welder=<Condition Number>, delay=<Delay Time>
```  


### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| Condition Number | When using two welders, set the welder number to be turned off. (1 ~ 2) | Variable |
| Delay Time | When using two welders, set the delay time to be turned off. (1 ~ 2) | Variable |


### Example

```python
    arcoff                    # Terminate the arc welding without any special shutdown process
    arcoff welder=2, delay=1  # Trun off the arc of the 2nd welder after a 1-second delay.
```  


### Details 

Refer to [[5. Editing Arc Welding Conditions]](../5_Condition_editing/README.md) 

[__SOURCE](2_Command/3_weavon.md)
# 2.3 weaving on


### Description
```weaving on``` command is used to enable the weaving condition. You can enter the properties window to set the corresponding weaving condition for the specified condition number.  
<br/>

### Syntax

```python
    weaving on, cnd=<Weaving Condition number>
```  

### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **Weaving Condition number** | Load the Weaving condition number (1 ~ 1000) | Variable |


### Example

```python  
   weaving on, cnd=1    # Load and execute weaving condition number 1
   arcon cnd=1          # Execute with arc condition number 1
   move L,spd=100cm/min,accu=0,tool=0   # Perform execution according to the above weaving conditions while moving the robot
```  


### Details  
  Refer to [[6. Weaving Function]](../6_Weaving_function/README.md)

[__SOURCE](2_Command/4_weavof.md)
# 2.4 weaving off


### Description

```weaving off``` command is used to stop the weaving motion.  
<br/>

### Syntax

```python
weaving off
```  

### Example

```python
   weaving off
```  

### Details

  Refer to [[6. Weaving Function]](../6_Weaving_function/README.md)


[__SOURCE](2_Command/5_arccond.md)
# 2.5 arccond


### Description

```arccond``` command is used to configure a job using the welding database(DB), or to continuously change welding conditions using the welding DB.  
<br/>

### Syntax

```python
arccond <Interpolation type>, cnd=<Condition Number>, gap=<Gap>, spd=<Welding Speed>, rd=<Wall Direction(right distance)>, ld=<Cross Direction(left distance)>, freq=<Weaving Frequency>, cur=<Current>, vol=<Voltage>
```  

### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **Interpolation Type** | Interpolation condition setting (D: Immediate change, L: Linear interpolation change)| Character |
| **Condition Number**| The condition number that stores the welding DB (WDB) and interpolation conditions (1 ~ 1000) | Variable  |
| **Gap** | The gap value to be input (-1 ~ 1000) [mm]| Variable  |
| **Welding Speed**| Welding speed for immediate change (1 ~ 1000) [cm/min]| Variable  |
| **Wall Direction**  | Weaving wall direction width for immediate change (1 ~ 50) [mm]| Variable  |
| **Cross Direction** | Weaving cross direction width for immediate change (1 ~ 50) [mm]  | Variable  |
| **Weaving Frequency**  | Weaving frequency for immediate change (1 ~ 10) [Hz]  | Variable  |
| **Current**| Welding current for immediate change  (The range varies depending on the welder settings)| Variable  |
| **Voltage**| Welding voltage for immediate change  (The range varies depending on the welder settings)| Variable  |


### Example

```python
  	arccond D, cur=170, vol=10 # Change immediately with a current of 170A and a voltage of 10V
  	arccond D, spd=80, rd=20, ld=20, freq=1.5 # Change immediately with a welding speed 80cm/min, weaving width of 20mm, and frequency of 1.5Hz
  	arccond D, cnd=1 # Change immediatelyto condition number 1
  
  	arccond L, cnd=1  
    ...               # welding step (move command for welding section)
    arccond L, cnd=2  # Change continuously from condition 1 to condition 2 using WDB data with linear interpolation
```  

### Details  

  Refer to [[8.1 Arccond - Arc Weld Condition]](../8_Application_function/1_Arc_cond/README.md)
[__SOURCE](2_Command/6_refp.md)
# 2.6 refp

### Description

```refp``` command is used to input reference points for the weaving motion. It inputs reference points such as weaving wall and entry direction.
<br/>

### Syntax

```python
refp <Reference Point Number>
refp <Reference Point Number>,<Pose(Num)>
```  

### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **Reference Point Number** | Set the number for the type of reference points (1 ~ 8) | Variable |
| **Pose** | Input the pose of the reference points (However, if a hidden pose is used, it will be omitted) | Variable |


### Example

```python
   refp 1,P1                   # Specify the wall direction of the weaving using P1
   refp 1                      # Specify the wall direction of the weaving hidden pose
   refp 2, (-1073.33, 739.01, 258.30, 0, 76, 23)  # Specify the position of the weaving surface
```  

### Details
  Refer to [[6. Weaving Function]](../6_Weaving_function/README.md)  


{% hint style="warning" %}
-	```refp``` command, likes ```move``` command, belongs to the step category.
- When the ```refp``` command is entered using a user key, it takes the form of a hidden pose.
- After setting the execution unit to Cmd or Step, you can move to the taught position.  
{% endhint %}
[__SOURCE](2_Command/7_lvson.md)
# 2.7 lvs

### Description 

```lvs``` command uses the LVS(Laser Vision Sensor) to perform functions such as obtaining the pose of the laser position(`seam_find`), start point detection(`search`), and seam tracking(`track`).
<br/>

### Syntax

```python
    lvs laser_on, cnd=<Condition Number>, seam=<Seam Number>, sp=<Seam Pose>
    lvs laser_off, cnd=<Condition Number>, seam=<Seam Number>, sp=<Seam Pose>
    lvs search, cnd=<Condition Number>, seam=<Seam Number>, sp=<Seam Pose>
    lvs track, cnd=<Condition Number>, seam=<Seam Number>, sp=<Seam Pose>
    lvs seam_find, cnd=<Condition Number>, seam=<Seam Number>, sp=<Seam Pose>
    lvs auto_calib, cnd=<Condition Number>, seam=<Seam Number>, sp=<Seam Pose>, opt=0
```   

### Parameter

<table>
  <thead>
    <tr>
      <th>Major Category</th>
      <th>Sub Category</th>
      <th>Meaning</th>
      <th>Remarks</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="10">lvs</td>
      <tr>
        <td>`laser_on`</td>
        <td> Turns on the laser </td>
      </tr>
      <tr>
        <td>`laser_off`</td>
        <td> Turns off the laser </td>
      </tr>
      <tr>
        <td>`search`</td>
        <td> Finds the starting point before performing the track function and prepares for tracking </td>
      </tr>
      <tr>
        <td>`step_search`</td>
        <td> Find the step difference of the base material and saves it as a pose in the `sp`. </td>
      </tr>
      <tr>
        <td>`track`</td>
        <td> Starts following the welding line when `arcon` is encountered (must have executed `search` first) </td>
      </tr>
      <tr>
        <td>`track_stationary`</td>
        <td> Performs stop tracking function. </td>
      </tr>
      <tr>
        <td>`seam_find`</td>
        <td> Reflects the current position of the laser sensing location and converts it to a pose, then saves it to the `sp`. </td>
      </tr>
      <tr>
        <td>`seam_find_p`</td>
        <td> Converts the current laser sensing location to a pose, and saves it to the `sp`. </td>
      </tr>
      <tr>
        <td>`auto_calib`</td>
        <td> Performs automatic calibration between the tool and the LVS Sensor. </td>
      </tr>
    </tr>
    <tr>
      <td colspan="2">Condition Number</td>
      <td> The condition number used when performing the LVS function (1 ~ 32). The properties window for each condition number is different, and this information is used during tracking. </td>
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">Seam Number</td>
      <td>Specifies the seam number. This number is sent to the LVS controller, and the LVS sensor senses the seam corresponding to this number</td>
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">Seam Pose</td>
      <td> Specifies the pose variable to save the pose found by `seam_find` or the pose found after `search` </td>
      <td>Pose Variable</td>
    </tr>
  </tbody>
</table>  

### Example

```python
    lvs seam_find, cnd=1, seam=10, sp=p10    
    # Perform seam finding with condition number 1 and seam number 10, saving the resulting pose in p10
    lvs track, cnd=1 ,seam=10 , sp=p10
    # Start LVS seam tracking with condition number 1 and seam number 10
```  


{% hint style="info" %}
  For use as an optional feature, please contact our company.
{% endhint %}


### Details  

  Refer to [[8.5 LVS(Laser Vision Sensor) Seam Finding and Tracking]](../8_Application_function/5_LVS_tracking/README.md)

[__SOURCE](2_Command/8_lps.md)
# 2.8 lps

### Description 

```lps``` command is used to perform functions such as obtaining the pose of the laser position using a laser distance sensor (Spot Mode), detecting step differences (Step mode), and searching for a weld seam (Scan mode).

<br/>

### Syntax

```python
    lps auto_calib, cnd=<Condition Number>, Tx=<Movement Distance in the X-dir based on the tool>, Ty=<Movement Distance in the Y-dir based on the tool>
    lps spot, cnd=<Condition Number>, sp=<Stored Pose>
    lps stepp, cnd=<Condition Number>, Tx=<Movement Distance in the X-dir based on the tool>, Ty=<Movement Distance in the Y-dir based on the tool>, spd=<Robot Speed>, sp=<Stored Pose>
    lps scan, cnd=<Condition Number>, Tx=<Movement Distance in the X-dir based on the tool>, Ty=<Movement Distance in the Y-dir based on the tool>, spd=<Robot Speed>, sp=<Stored Pose>
    # When Using Master / Production Mode
    lps scan, cnd=<Condition Number>, Tx=<Movement Distance in the X-dir based on the tool>, Ty=<Movement Distance in the Y-dir based on the tool>, spd=<Robot Speed>, sp=<Stored Pose>, mp=<Pose to save in Master Mode>, ms=<Shift Variable Calculated in Production Mode>
```  

### Parameter

<table>
  <thead>
    <tr>
      <th>Major Category</th>
      <th>Sub Category</th>
      <th>Meaning</th>
      <th>Remarks</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="5">lps</td>
      <tr>
      <td>`auto_calib`</td>
      <td>
        Performs automatic calibration between the tool and the sensor.
      </td>
      </tr>
      <tr>
      <td>`spot`</td>
      <td>
        In Spot mode, the pose of the position currently indicated by the laser is obtained.
      </td>
      </tr>
      <tr>
      <td>`stepp`</td>
      <td>
        In Step mode, the pose of the position where the output value changes abruptly while the laser is moving is obtained.
      </td>
      </tr>
      <tr>
      <td>`scan`</td>
      <td>
        In Scan mode, the pose of the position estimated to be a weld point along the laser movement path is obtained.
      </td>
      </tr>
    </tr>
    <tr>
      <td colspan="2">cnd</td>
      <td>
        Condition numbers (1 to 8) used when executing the LPS function.
        The information displayed in the command property window varies depending on the condition number.
        This information is used for sensitivity settings in Automatic Calibration and Step mode, and coordinate system configuration when storing poses.
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">`Tx / Ty`</td>
      <td>
        Sets the movement distance in the X or Y direction based on the tool.
        Except for auto_calib, only one of the two values must be entered.
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">`spd`</td>
      <td>
        Specifies the speed at which the robot moves while executing the operation.
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">`sp`</td>
      <td>
        Specifies the pose variable in which the current pose found by each command is stored.
      <td>Pose Variable</td>
    </tr>
    <tr>
      <td colspan="2">`mp`</td>
      <td>
        In Master mode, the sensing result is stored in mp (master pose).
        In Production mode, it is used to calculate ms (master shift).
      <td>Pose Variable</td>
    </tr>
    <tr>
      <td colspan="2">`ms`</td>
      <td>
        A shift variable used in Production mode.
        The difference between the master pose (mp parameter) and the currently sensed pose (sp parameter) is calculated and stored.
      <td>Shift Variable</td>
    </tr>
  </tbody>
</table>  


### Example

```python
    lps auto_calib, cnd=1, Tx=50, Ty=-100
    # Performs Automatic Calibration within the specified distance range of +50 in the X direction and -100 in the Y direction, based on the tool, using condition number 1
    lps spot, cnd=1, sp=p10
    # Using condition number 1, stores the pose of the current laser position in p10, based on the coordinate system defined in the condition settings.
    lps stepp, cnd=1, Tx=50, sp=p10
    # Using condition number 1, moves 50[mm] in the X direction based on the tool, stops immediately when a step difference is detected, and stores the pose in p10.
    lps scan, cnd=1, Tx=50, spd=10, sp=p10
    # Using condition number 1, moves 50[mm] in the X direction based on the tool at a speed of 10, detects the weld point upon completion of the movement, and stores it in p10.
    # 조건 번호 1번, 툴 기준 X 방향으로 50만큼 설정된 거리만큼 이동이 완료되면 용접점을 검출하여 p10에 저장
    
    lps scan, cnd=1, Tx=50, spd=10, sp=p10, mp=mp10, ms=ms10
    # When using Master mode: Using condition number 1, moves 50[mm] in the X direction based on the tool at a speed of 10, detects the weld point upon completion of the movement, stores it in p10, compares it with mp10, and saves the calculated shift value in ms10.
```  


{% hint style="info" %}
To use this function as an optional feature, please contact our company.
{% endhint %}


### Details

  Refer to [8.7 LPS(Laser Point Sensing)](../8_Application_function/7_LPS/README.md)

[__SOURCE](2_Command/9_hsenson.md)
# 2.9 heightsen on

### Description 

```heightsen on``` command starts the height sensing function(AVC, Arc length control).  


### Syntax
```python
    heightsen on, cnd=<Condition Number>
```  

### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **Condition Number** | The number of the welding condition used to starting Arc Welding and the specific condition (1 ~ 8) | Variable |


### Example

```python   
    heightsen on, cnd=1        # Starts height sensing with condition number 1.
```  


### Details
  Refer to [[8.4 Height Sensing]](../8_Application_function/4_Height_sensing/README.md)



[__SOURCE](2_Command/10_hsensoff.md)
# 2.10 heightsen off

### Description

```heightsen off``` command is used to stop the height sensing function (AVC, Arc Voltage Control).

<br/>


### Syntax
  
```python
heightsen off
```  


### Example

```python   
   heightsen off            # End height sensing execution
```  


### Details
  Refer to [[8.4 Height Sensing]](../8_Application_function/4_Height_sensing/README.md)
<br/>



[__SOURCE](2_Command/11_multipass.md)
# 2.11 multipass

### Description  

```multipass``` command is used for multi-pass welding to reproduce the arc sensing path.  
Using this command, you can perform welding by reproducing the original arc welding path with a specified amount of shift.  
<br/>


### Syntax

```python  
multipass save, trj=<Multi-pass trajectory Number>, period=<trajectory save interval distance>
multipass load, trj=<Multi-pass trajectory Number>, side=<lateral shift distance>, height=<vertical shift distance>, reverse=<Multi-pass run direction>, tas=<torch shift angle (front/rear)>, was=<torch shift angle(left/right)>
multipass off
```  

### Parameter
<table>
  <thead>
    <tr>
      <th>Major Category</th>
      <th>Sub Category</th>
      <th>Meaning</th>
      <th>Remarks</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="4">multipass</td>
    </tr>
    <tr>
      <td>`save`</td>
      <td>Multi-pass trajectory save</td>
    </tr>
    <tr>
      <td>`load`</td>
      <td>Multi-pass trajectory load</td>
    </tr>
    <tr>
      <td>`off`</td>
      <td>Multi-pass off</td>
    </tr>
    <tr>
      <td colspan="2">Multi-pass trajectory Number</td>
      <td> Trajectory Number to save/load the multi-pass (1 ~ 50)</td>
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">trajectory save interval distance</td>
      <td> Sampling interval distance when saving the multi-pass trajectory (5 ~ 100)[mm] </td>
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">lateral shift distance</td>
      <td> Shift distance in the left/right direction from the origin Arc sensing path (-20 ~ 20)[mm] </td>
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">vertical shift distance</td>
      <td> Shift distance in the up/down direction from the origin Arc sensing path (-20 ~ 20)[mm] </td>
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">Multi-pass run direction</td>
      <td> Whether to reproduce the path in the reverse direction (0: forward, 1: reverse) </td>
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">torch shift angle (front/rear)</td>
      <td> Torch tilt angle shift in the front/rear direction during multi-pass reproduction (-20 ~ 20)[deg] </td>
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">torch shift angle (left/right)</td>
      <td> Torch tilt angle shift in the left/right direction during multi-pass reproduction (-20 ~ 20)[deg] </td>
      <td>Variable</td>
    </tr>
  </tbody>
</table>  

### Example

```python
     weaving on, cnd=1 
     multipass save, trj=1, period=10       # Save to trajectory 1 at 10mm intervals
     arcon cnd=1
S10  move L,tg=R2,spd=LV1!cm/min,accu=3,tool=1
S11  move L,tg=R2,spd=LV1!cm/min,accu=3,tool=1
     arcoff
     weaving off
     multipass off
S12  move L,spd=50%,accu=3,tool=1
S13  move L,spd=50%,accu=3,tool=1
S14  move L,spd=50%,accu=3,tool=1
     multipass load,trj=1,side=3,height=3,reverse=0,tas=0,was=0
     # Load trajectory 1 with a 3mm shift to the left, 3mm upward, in forward direction, with no angle shift
S15  move L,R2,spd=50%,accu=0,tool=1       # Move step to the Multi-pass starting position
     weaving on, cnd=11
     arcon cnd=1 
S16  move L,tg=R2,spd=LV1!cm/min,accu=3,tool=1  
S17  move L,tg=R2,spd=LV1!cm/min,accu=3,tool=1
     arcoff
     weaving off  
     multipass off
```  

[__SOURCE](2_Command/12_posical.md)
# 2.12 posi_calib

### Description 

```posi_calib``` command is used to perform positioner calibration, which is required for the positioner to operate synchronously with the robot.
Typically, positioner calibration is carried out via a settings dialog.
However, when the positioner is changed using a servo tool changer, calibration must be updated during robot operation.
This command allows calibration to be performed directly within the robot program.


- For detailed instructions on using this command, please refer to [2.3.4 posi_calib](https://hrbook-hrc.web.app/#/view/doc-positioner-sync/en/2-system_settings/2-3-positioner-calibration/4_posi_calib?cont_model=${cont_model})


[__SOURCE](2_Command/13_touchsen.md)
# 2.13 touchsen

### Description

```touchsen``` command performs wire touch sensing. You can configure the sensing type and conditions in the properties window.
After moving to the desired sensing position using a `move` command, executing the `touchsen` command initiates touch sensing at that position automatically, based on the specified sensing type and condition.

<br/>


### Syntax

```python
touchsen cnd=<Condition number>, crd=<Coordinate System>, dir=<Direction>, pose=<Pose to save>
touchsen cnd=<Condition number>, crd=<Coordinate System>, dir=<Direction>, rotation=<Sensing Angle>, pose=<Pose to save>
touchsen cnd=<Condition number>, crd=<Coordinate System>, dir=<Direction>, lift_up=<Lifting Distance>, criteria=<Detection Threshold in Detect Groove>, pose=<Pose to save>, gap=<butt gap value>
touchsen cnd=<Condition number>, crd=<Coordinate System>, dir=<Direction>, mpose=<Pose to save in Master Mode>, mshift=<Shift Variable Calculated in Production Mode>
```  


### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **Condition number** | Touch sensing Condition number (1 ~ 1000) | Variable |
| **Coordinate System** | Coordinate system used to define sensing direction ("robot", "base", "tool", "tool_prj") | Variable |
| **Direction** | Touch sensing direction (supported directions vary by sensing type) ("+x", ["+x", "-z"], ["+ty", "+tz"]) | String Array |
| **Pose to save** | Specifies the pose variable where the sensing result will be stored. | Variable |
| **Sensing Angle** | Rotational angle applied to the sensing direction with respect to the selected coordinate system (Y+30, Y-30, X+30, X-30, TL+30, TL-30, TY+30, TY-30) | Variable |
| **Lifting Distance** | The upward distance the robot moves after bottom detection | Variable |
| **Criteria(Detection Threshold in Detect Groove)** | Reference distance for groove detection[mm] | Variable |
| **Butt Gap Value** | Variable to store the lower gap measured via touch sensing in Butt or V-groove type | Variable |
| **mpose(Pose to save in Master Mode)** | In Master mode, sensing results are stored in `mpose`. In Production mode, `mpose` is used to calculate `mshift`. | Variable |
| **mshift(Shift Variable Calculated in Production Mode)** | In Production mode, `mshift` stores the calculated shift value as a vecotr difference: (current sensing pose - master pose) | Variable |


### Example

```python
    var var1=0      # Declare a variable to store the measured gap during butt joint sensing.
    var P10=cpo()   # Declare a pose variable `P10` and save the current pose to it.
    touchsen cnd=2, crd="tool", dir=["+y"], lift_up=3, pose=P10, gap=var1  # condition 2, in tool crd system, After bottom sensing, lift by 3mm, and store the gap in var1
    touchsen cnd=1, crd="tool", dir=["tf", "td"], pose=P10, 0  # condition 1, in Tool projection crd system, 2-points
    touchsen cnd=1, crd="base", dir=["+x","-y","-z"], pose=P10, 0  # condition 1, in base crd system, 3-points
```  


### Details
  Refer to [[8.2 Touch Sensing]](../8_Application_function/2_Touch_sensing/README.md)
<br/>


[__SOURCE](2_Command/14_stitch.md)
# 2.14 stitch

### Description 

```stitch``` command performs stitch welding. You can set the stitch conditions by placing the cursor on the command and clicking the **Properties** button.
After moving to the desired stitch welding position using a `move` command, use stitch together with the `arcon` command.
When the stitch function is executed, stitch welding starts at the specified position and continues until the stitch operation is completed.  
<br/>

### Syntax

```python
stitch on, cnd=<Condition Number>
stitch off
```  


### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **Condition number** | Stitch Condition Number (1 ~ 1000) | Variable |


### Example
```python
   stitch on, cnd=2         #  execute stitch on condition 2
   stitch off               #  terminate stitch
```


### Details  
  Refer to [[8.6 STITCH Function]](../8_Application_function/6_Stitch/README.md)

[__SOURCE](2_Command/15_calcshift.md)
# 2.15 calshift

### Description  

```calshift``` command calculates the shift using two Pose variables.
It is frequently used to calculate shifts based on pose variables saved from touch sensing.  
<br/>


### Syntax

```python
<Shift Val>=calshift(<Pose Val 1>, <Pose Val 2>)
<Shift Val>=calshift(<Pose Val 1>, <Pose Val 2>,"TV")
```  


### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **Shift Variable Input** | Enter the shift variable to store the calculated shift | Shift Variable |
| **Pose Variable Input** | Enter the pose variable (1 ~ 9999) | Pose Variable |
| **TV** | Calculates the shift in the direction perpendicular to the tool (1 ~ 9999) | string |


### Example

```python
    move L, spd=30%, ...
    var pose_1 = cpo()
    move L, spd=30%, ...
    var pose_2 = cpo()
    var sft_1
    sft_1=calshift(pose_1,pose_2)   
    # calculate the vector shift between pose_1 and pose_2, and store the result in sht_1
```  
  
[__SOURCE](3_Property/README.md)
# 3. Command Property
[__SOURCE](3_Property/1_overall.md)
# 3.1 Overview

When teaching an arc welding program, not only the welding conditions such as voltage and current but also detailed settings related to weaving, retries/overlaps, and the characteristics of the welder are necessary.
Furthermore, in general robot operation, there may be cases where the position information (coordinates and orientation) of the taught steps or auxiliary points needs to be verified.  
By placing the cursor on the command and pressing the `[Property]` button located on the left side of the TP, a function is provided that allows easy and quick editing of these files.


### Example of Command [Property]

| Command | Property | 
| -----| -------| 
| `arcon `| Set the current, voltage, synergic, initial/aux/end conditions, etc. | 
| `weaving on `| Set weaving type, frequency, width, and weaving direction, etc. |
| `lvs `| Configure tracking-related informations, seam finding settings, etc. |
| `arccond `| Manage welding condition database(WDB) with settings for current, voltage, frequency, and weaving width. |
| `move `| Change the current recorded position to base coordinate system, robot coordinate system, or joint coordinate system. |



As an example of editing welding start conditions, when the cursor is placed on the `arcon` command, which turns on the arc, pressing the `[Property]` button will display the details of the condition number currently used in the welding start conditions.
In this screen, you can view or modify the detailed settings of the welding start conditions.

Similarly, after placing the cursor on a specific command and entering the `[Property]` window, you can easily and quickly check and modify the settings, such as the conditions or positions recorded in the steps.
If you wish to save the changes and exit, press `[OK]`; if you wish to exit without saving, press the `[ESC]` key on the teaching pendant.


![](../_assets/3_1_1.png)<br>
*Figure 3.1.1. Property in Robot Program Command*


{% hint style="info" %}
    For more details, please refer to [2. Inserting Commands]
{% endhint %}
[__SOURCE](4_Setting/README.md)
# 4. Arc Welder Settings
[__SOURCE](4_Setting/1_Arc_communication/README.md)
# 4.1 Arc Welder communication settings


Follow the steps below to connect the PC and controller using an Ethernet cable:

1. Run the **Sycon** program on the PC.
2. Add the cifx card, then right-click its icon and select **configuration**.
3. Configure each items as follows:
  **Driver**: Set to nexX Driver
  **Bus Parameters**: Set Baud rate to 250kBits/s
  **Device Assignment**: Select the added cifx card and click OK.
4. Right-click the cifx icon and select **download**.
4. Right-click the cifx icon and select **network scan**.


![](../../_assets/4_1_1.png)<br>
*Figure 4.1.1. Sycon Communication Status*  

After completing the below steps, the sycon screen will appear as shown above. (when connected to Hyundai PNS Welder)

6. Right-click the welder icon and select **disconnect**, then go to **configuration > General > UCM** tab and set UCMM to Group3.
7. Right-click the welder icon and select **upload**, then right-click the cifx icon and select **download**.

On the Robot TP, navigate to `[F2: System] - 2: Control parameter - 2: Input/Output signal setting - 6: fb block allocation` and assign the blocks to be used.
Once this is completed, the data transmitted from the welder to the controller will be displayed in bold within the assigned blocks.
(Verify this in `[pane layout] - select - public input - assigned fb block`)


{% hint style="info" %}
  For more information, please refer to [${cont_model} - Industrial Communication](https://hrbook-hrc.web.app/#/view/doc-industrial-communication/en-${cont_model}/README?cont_model=${cont_model}) 
{% endhint %}

[__SOURCE](4_Setting/2_Arc_setting/README.md)
# 4.2 Arc Welder Settings

User can operate various welders together with our Arc Welding Robots. To support this, a function is provided to edit welder-specific settings. The welder configuration screen can be accessed as follows: `[F2: System] - 5: Initialization - 3: Usage setting`


###	Welder Maker Number
> The currently selected welder maker number is displayed. You can check the welder numbers for each maker by clicking the **[Welder information]** button. By clicking the **[Welder setting]** button on this screen, the condition editing screen for the selected welder will appear.


![](../../_assets/1_2_1.png)<br>
*Figure 4.2.1. Usage Setting Dialog box* 

</br>

![](../../_assets/4_2_2.png)<br>
*Figure 4.2.2. Hyundai Welder Condition Settings*   

</br>

![](../../_assets/4_2_3.png)<br>
*Figure 4.2.3. Hyundai Welder I/O Signal Assignment*   


The welder condition screen provides editing functions related to welder characteristics, so the editable items differ by welder. The following items are commonly editable in the welder condition screen.

| Item | Default Value | Description |
|---|------|---|
| Name                   | Supported welder model name | Records the model name of the welder |
| Comment                | Welder Maker name | Records a description of the welder |
| Stick detection time   | [0.2] seconds <br>(Range: 0.1 ~ 10.0) | Checks wire fusion during setting time after arc welding ends |
| ARC OFF detection time | [0.3] seconds <br>(Range: 0.0 ~ 10.0) | Sets the reference time for detecting arc off during arc welding. If the arc is off longer than this time, it is recognized as arc off.<br> It set too low, arc ignition failures may occur frequently.<br> If set too high, robot movement and wire inching continue longer after arc off, increasing the robot travel distance and wire protrusion length after arc off. |


[__SOURCE](5_Condition_editing/README.md)
# 5. Editing Arc Welding Conditions
[__SOURCE](5_Condition_editing/1_Condition_config/README.md)
# 5.1 Configure Arc Welding Condition

To perform Arc Welding our controller, it is necessary to configure both the welder and the welding conditions. In addition to basic arc welding, special functions such as weaving or arc sensing require detailed settings for each respective feature.
Our company provides the ability to edit Arc welder characteristic files([[4. Arc Welder Settings]](../../4_Setting/README.md)), arc welding application functions([[1.2.2 Arc Welding various signals and funtion settings]](../../1_Basic_information/2_Function_setting/2_signals_functions.md)), and arc welding condition settings, enabling users to weld in various environments with desired configurations using a variety of welder.

Arc welding conditions are structed as follows:
- Arc welding Start Conditions: Editing settings for welding initiation and main welding parameters
  - Auxiliary Arc welding Start conditions: Editing retry and restart functions
- Arc welding End Conditions: Editing settings for welding termination
  - Auxiliary Arc welding End condiitons: Editing the automatic wire stick-out release


[__SOURCE](5_Condition_editing/2_Time_chart/README.md)
# 5.2 Arc Welding FlowChart

This is the Time Flowchart for digital Arc Welding. For each condition setting, please refer to the dialog box desciptions for each command below.
 
![](../../_assets/5_2_1.png)<br>
*Figure 5.2.1. Digital Arc Welding FlowChart*


[__SOURCE](5_Condition_editing/3_Start_condition/README.md)
# 5.3 Welding Start condition


When the arc welding settings are digital and the cursor is placed on the command line `arcon cnd=_`, pressing the [property] key will bring up the editing screen for the welding start conditions.

 
![](../../_assets/5_3_1.png)<br>
*Figure 5.3.1. Hyosung welder setting*  


![](../../_assets/5_3_2.png)<br>
*Figure 5.3.2. Fronius welder setting*  

 
![](../../_assets/5_3_3.png)<br>
*Figure 5.3.3. EWM welder setting*

 

After editing the conditions, pressing the `[ESC]` key will close the dialog box without saving the changes, while pressing `[OK]` key will save the settings and close the dialog box.

The following items apply to all welder in common. For model-specific settings, please refer to the following chapter.

The contents of common items may vary in name, unit, and range for each welder. Please refer to the respective table for model-specific differences.

</br>

### Setting Items
---
### (1)	Condition Number  
Specifies the welding start condition number to be edited.(Max: 32) 

<center>

| Item | Name | Range |
| :---: | :---: | :---: |
| Common to all welders | Condition Number | 1 ~ 32 |

</center>

</br>  

### (2)	Description  
Records the description for the specified welding start condition.

<center>

| Supported Welder | Name |
| :---: | :---: |
| Common to all welders | Comment |

</center>

</br>  
    
### (3)	Synergic Code  
Sets the synergic code to b transmitted to the welder. The code value is configured in a separate synergic selection screen. The synergic selection screen can be accessed by pressing the `[Synergic Selection]` button on the welding start condition creen.

<center>

| Supported Welder | Name | Unit | Range | Default |
| :---: | :---: | :---: |:---: | :---: |
| Hyosung | Synergic Code | - |- | 040 |
| Fronius </br>(Not supported) |-|-|-|-|
| EWM | Synergic no. | - |- | 185|

</center>
    
</br>  

### (4)	Welding Current / Welding Power / Wire Feed Speed  
Set the welding current value. This is the current used during the welding process. The current of the initial and final conditions is determined as a ratio of this value.
<center>

| Supported Welder | Name | Unit | Range | Default |
| :---: | :---: | :---: |:---: | :---: |
| Hyosung | Welding Current | A | 40.0 ~ 350.0 | 100.0 |
| EWM | Wire Feed Speed |  m/min | 0.0 ~ 25.0 | 3.1 |
| Fronius(TPS) | Welding Power | % | 0.0 ~ 100.0 | 100.0 |

</center>
    
</br>

### (5)	Welding voltage / Welding voltage Correction / Welding voltage Offset / Arc length correction  
In digital welding, the welding voltage is often not entered directly, but instead selected automatically based on welding current from the synergic data. If you wish to modify the welding voltage automatically selected by the synergic data, set the offset value for the voltage to be adjusted based on the selected welding voltage.
<center>

| Supported Welder | Name | Unit | Range | Default |
| :---: | :---: | :---: |:---: | :---: |
| Hyosung(Indiv.) | Welding voltage | V | 10.0 ~ 38.0 | 10.0 |
| Hyosung(Synergic) | Welding voltage Correction | % | 50.0 ~ 150.0 | 50.0 |
| EWM | Welding voltage Offset | VP | -10.0 ~ 10.0 | 2.0 |
| Fronius(TPS) | arc length correction | % | -30.0 ~ 30.0 | 0 |
</center>
    
</br>

### (6)	Gas preflow
Set the time to preflow shileld gas before starting the arc welding to isolate and prepare the welding area.

<center>  

| Supported Welder | Name | Unit | Range | Default |
| :---: | :---: | :---: |:---: | :---: |
| Common to all welders | gas preflow | sec | 0.0 ~ 10.0 | 0.5 |  

</center>

</br>  

### (7)	WCR Wait Time  
Indicates the time waiting for the WCR input. If the WCR signal is not received within this time, a retry will be performed. However, if the retry count is set to 0, an error will be displayed, and the robot will stop. Retry methods and retry counts can be configured in the welding auxiliary conditions. (Refer to [5.5 Welding Auxiliary condition](../5_Aux_condition/README.md))

<center>

| Supported Welder | Name | Unit | Range | Default |
| :---: | :---: | :---: |:---: | :---: |
| Common to all welders | WCR Wait Time | sec | 1.0 ~ 10.0 | 2 |


</center>
    
</br>

### (8)	Robot delay time  
After the arc welding has started normally, sets the time the robot will wait before moving along the welding line to perform the welding. This is independent of the initial conditions, and the robot can move even while processing initial conditions.
<center>

| Supported Welder | Name | Unit | Range | Default |
| :---: | :---: | :---: |:---: | :---: |
| Common to all welders | Robot delay time | sec | 0.0 ~ 10.0 | 0 |

</center>
    
</br>

### (9) Initial condition maintain time  
Sets the time for maintaining the initial current value at the start of arc welding.
<center>

| Supported Welder | Name | Unit | Range | 
| :---: | :---: | :---: |:---: |
| Common to all welders | Initial condition maintain time | sec | 0.0 ~ 10.0 | 

</center>
    
</br>

### (10) Initial Welding Current / Welding Power / Wire Feed Speed  
Sets the welding current to be output during the initial condition hold time at the start of arc welding.
This is set as a percent(%) relative to the welding current of the main condition.
<center>

| Supported Welder | Name | Unit | Range | Default |
| :---: | :---: | :---: |:---: | :---: |
| Hyosung | Initial Welding Current | A | 40.0 ~ 350.0 | 120 |
| Fronius | Initial Welding Power | % | 20 ~ 200 | 120 |
| EWM | Initial Wire Feed Speed | m/min | 0.0 ~ 25.0 | 3.72 |

</center>
    
</br>

### (11) Initial Welding voltage / Welding voltage Correction / Arc length correction  
Sets the welding voltage to be output during the initial condition hold time at the start of arc welding.
This is set as a correction value relative to the synergic voltage.  
<center>

| Supported Welder | Name | Unit | Range | Default |
| :---: | :---: | :---: |:---: | :---: |
| Hyosung(Indiv.) | Initial Welding voltage | V | 10.0 ~ 38.0 | 10.0 |
| Hyosung(Synergic) | Initial Welding voltage Correction | % | 50.0 ~ 150.0 | 50.0 |
| EWM | Initial Welding voltage Offset | VP | -10.0 ~ 10.0 | 2 |
| Fronius | Initial Arc Length Correction | %| -30.0 ~ 30.0 | 0 |
</center>
    
</br>

### (12) Slope Time  
Sets the time to process the current change between the initial condition and this condition as a slope.
<center>

| Supported Welder | Name | Unit | Range | 
| :---: | :---: | :---: |:---: |
| Common to all welders | Slope Time | sec | 0.0 ~ 10.0 | 


</center>
    
</br>

### (13) Excess Allowed Time  
Sets the allowable time for exceeding the welding voltage/current and feed motor current limits. If the welding voltage/current or feed motor current exceeds the limits for longer than this time, a restart will be performed. However, If the restart count is set to 0, an error will be displayed, and the robot will stop. The restart method and restart count, as well as other restart-related features, can be configured in the welding auxiliary conditions. If this time is set to 0 seconds, the arc limits monitoring function will not be used.
<center>

| Supported Welder | Name | Unit | Range | Default | 
| :---: | :---: | :---: |:---: |:---: |
| Common to all welders | Excess Allowed Time | sec | 0.0 ~ 10.0 | 0 | 


</center>
    
</br>

### (14) Welding Voltage upper/lower limit  
Sets the upper and lower voltage limits during welding. If the limits are exceeded for longer than the allowed time, an error will occur.
<center>

| Supported Welder | Name | Unit | Range | 
| :---: | :---: | :---: |:---: |
| Common to all welders | Welding Voltage upper/lower limit | V | 0.0 ~ 100.0 | 


</center>
    
</br>

### (15) Welding Current upper/lower limit  
Sets the upper and lower current limits during welding. If the limits are exceeded for longer than the allowed time, an error will occur.
<center>

| Supported Welder | Name | Unit | Range | 
| :---: | :---: | :---: |:---: |
| Common to all welders | Welding Current upper/lower limit | A | 0.0 ~ 1000 | 


</center>
    
</br>
    
### Convenience Features
---
Convenience features are provided via the F buttons at the bottom of the settings screen when configuring welding conditions.

- `[F1: Select]`  
When multiple conditions exist, you can select a specific condition to edit by entering its number.

- `[F2: Initialize]`  
Resets the welding condition parameters to their default values.

- `[F3: Weld Seq.]`  
Displays the welding sequence chart while the button is being held down. 
Pressing this under the 'Start Condition' tab displays the welding start sequence, and pressing it under the 'End Condition' tab displays the welding end sequence.

- `[F4: Conv. Ratio]`  
This button is activated when a specific item under the initial sequence or end conditions is selected. When you enter a conversion ratio (%), the system automatically calculates and enters the converted value relative to the main condition.

|Reference Value (Main Condition)|Initial Conditions|End Conditions|
|-|-|-|
|Welding Current / Welding Power / Wire Feed Speed|Initial Welding Current / Welding Power / Wire Feed Speed|End Welding Current / Welding Power / Wire Feed Speed |
|Welding Voltage / Welding Voltage Calibration / Arc Length Calibration|Initial Welding Voltage / Welding Voltage Calibration / Arc Length Calibration|End Welding Voltage / Welding Voltage Calibration / Arc Length Calibration|

- `[F5: Synergic Sel.]`  
This button is displayed if the welding machine supports synergic settings. Clicking this button opens the screen for configuring synergic codes.

</br>
[__SOURCE](5_Condition_editing/3_Start_condition/1_hyosung.md)
# 5.3.1 Welding Start condition - Hyosung-only settings

### (1) Welding Mode: `Normal, Pulse`  
Set the Arc Welding method.

### (2)	Slowdown Adjuctment: [ 100 ] % (range: 0 ~ 255)  
Adjust the offset for the wire feed speed before the arc is initiated.

### (3)	Inductor Effect: [  100] % (range: 0 ~ 255)  
Set the inductor effect.

[__SOURCE](5_Condition_editing/3_Start_condition/2_fronius.md)
# 5.3.2 Welding Start condition - Fronius-only settings

### (1)	Operation Mode: `Prog-Std, Prog-Pulse, CMT, JOB, TIG`  
Set the welding mode supported by the Fronius welder. The descriptions for each mode as follows:

- **Prog-Std**: Use the standard welding program stored in the welder.
- **Prog-Pulse**: Use the pulse welding program stored in the welder.
- **CMT**: Use the Cool Metal Transfer functions.
- **JOB**: Use the job stored in the welder.
- **TIG**: Use of TIG(Tungsten Insert Gas) welding functionality.

### (2)	Prog/Job Number  
Set the program or job number to be used from the ones stored in the welder.
If the operation mode is set to Job, the job number will be used.

### (3)	Dynamic correction: [ 0 ]% (range: -5.0 ~ 5.0)  

Set the dynamic correction value. A smaller value results in a strong and stable arc, but increases the amount of spatter. A larger value generates a smoother arc and reduces the amount of spatter.


[__SOURCE](5_Condition_editing/3_Start_condition/3_ewm.md)
# 5.3.3 Welding Start condition - EWM-only settings

### (1)	JOB mode: `Disable, Enable` 
Set the Job mode supported by the EWM AlphaQ welder. The descriptions for each mode are as follows:
- disable: Welding is performed with wire feed speed and voltage offset based on the synergy data stored in the welder.
- enable: Welding is pserfored with the job stored in welder.

### (2)	Welding mode  
Set whether pulse welding is used.

### (3)	Super pulse function  
When pulse weling is enabled, it configures the use oft the Super Pulse(2-stage pulse) function.

### (4)	Job Number (synergic)  
Enter the synergy number or job number to be used for welding. Press the [Synergy selection] button at the bottom of the TP to open a dialog box where you can set the job number that corresponds to the welding method, material, gas type, and wire diameter.

### (5)	Dynamic correction: [ 0 ] (range: -40.0 ~ 40.0)  
Set the dynamic correction. A smaller value results in a strong and stable arc, but increases the amount of spatter. A larger value generates a smoother arc and reduces the amount of spatter.

### (6)	Lift arc start: `Not use, Use`  
Set whether to use the lift arc function at the start of welding. Using the lift arc function can reduce the occurrence of excessive spatter during the start of welding.

[__SOURCE](5_Condition_editing/4_End_condition/README.md)
# 5.4 Welding End condition

When the arc welding settings are digital and [End condition] tab is pressed in the welding start condition dialog box, the following welding end condition editing screen appears.


![](../../_assets/5_4_1.png)<br>
*Figure 5.4.1. Welding End Condition Setting (e.g. EWM)* 


After editing the welding end conditions, pressing the `[ESC]` key will close the dialog box without saving the changes, while pressing `[OK]` key will save the settings and close the dialog box.

</br>

The descriptions for each item are as follows:

</br>

### (1)	Condition Number: [1] (Range: changes not allowed)  
Displays the welding start condition number. In digital arc welding, the end condition number and start condition number are managed as one. Therefore, to change the end condition number, the start condition number must also be changed.  

### (2)	End Welding Current / Welding Power / Wire Feed Speed  
Set the current value to be output during crater treatment. This is set as a percentage(%) relative to the current welding conditions (welding current, welding power, and wire feed speed). However, for EWM welders, this is set in m/min, the same as the welding conditions.

<center>

| supported Welder | Name | Unit | Range | Default |
| :---: | :---: | :---: |:---: | :---: |
| Hyosung | End Welding Current | A |28.0 ~ 350.0 | 28.0 |
| EWM | End Wire Feed Speed | m/min | 0.0 ~ 25.0 | 2.17 |
| Fronius | End Welding Power | % | 10 ~ 100 | 70 |
</center>

### (3)	End Welding voltage/ Welding voltage corrction / Arc length correction  
Set the voltage value to be output during crater treatment. The voltage is specified and output according to the set value.
<center>

| supported Welder | Name | Unit | Range | Default |
| :---: | :---: | :---: |:---: | :---: |
| Hyosung(Indiv.) | End welding voltage | V | 10.0 ~ 38.0 | 10.0 |
| Hyosung(Synergic) | End welding voltage correction | % | 50.0 ~ 150.0 | 50.0 |
| EWM | End Welding voltage offset | VP | -10.0 ~ 10.0 | 2 |
| Fronius(TPS) | End Arc length correction |  % | -30.0 ~ 30.0 | 0 |

</center>

### (4)	Downslope Time(Crate Time): [0] sec (Range: 0.0 ~ 10.0)  
Sets the time for processing the current change between the main condition and the end condition as a slope.

![](../../_assets/5_4_2.png)<br>
*Figure 5.4.2. DownSlope Time and Crate Time Chart*

### (5)	Condition Hold time: [1] sec (Range: 0.1 ~ 10.0)   
Set the time to maintain the output value specified in the 'current ratio' item under the welding end condition.

### (6)	Wire Burnback: [ 0 ] ms (Range: 0.0 ~ 200.0)  
Configures burnback processing. May vary depending on the welder.

### (7)	Gas Post Flow: [ 0 ] sec (Range: 0.0 ~ 10.0)  
Set the time to continue the shielding gas output even after the arc is turned off.

### (8)	Crater move time: [ 0 ] sec (Range: 0.0 ~ 10.0) / Crater move distance : [0] mm (Range: 0.0 ~ 100.0)
During crater treatment, sets the distance the robot will move backward during the DownSlope time and condition hold time. The speed is automatically determined based on the distance and time.

### (9) Auto Stick Release Count : [0] times (Range: 0 to 9) / Condition : [0] (Range: 0 to 32) / Time: [0] sec (Range: 0.0 to 10.0)  
During arc welding, the welding wire may stick to the base material at the end of welding. To prevent this, the welding power source temporarily increases the voltage at the end of welding as an anti-sticking process.
However, sticking may still occur even after this process. Therefore, the robot controller sends a post-weld sticking detection signal to the welding power source to check whether sticking has occurred.
The auto stick release function automaticllay performs a burnback release when sticking is detected after welding, allowing the robot to continue operation without stopping.
This process is repeated for the configured number of times. If the sticking is not released after the specified number of attempts is exceeded, the robot will stop.

* Count : [0] times (Range: 0 to 9)
    This parameter specifies the maximum number of burnback release attempts. If the sticking is not released within the configured number of attempts, an error will occur. 
    Exceptionally, when set to 0, the sticking check is skipped and the system proceeds directly to the next step.

* Condition : [0] (Range: 0 to 32)
    This parameter specifies the welding condition number used for the burnback release process. When set to 0, the burnback release is performed using the current welding start condition.

* Time: [0] sec (Range: 0.0 to 10.0)
    This parameter specifies the duration for which the burnback release condition output is maintained.
[__SOURCE](5_Condition_editing/5_Aux_condition/README.md)
# 5.5 Welding Auxiliary condition


When the arc welding settings are digital and [Auxiliary condition] tab is pressed in the welding start condition dialog box, the following welding auxiliary condition editing screen appears.


[__SOURCE](5_Condition_editing/5_Aux_condition/1_retry.md)
# 5.5.1 Welding Auxiliary condition - Retry


There may be cases where the arc does not ignite due to foreign materials attached near the weld start point of the base material when starting arc welding. The retry function automatically attempts to reignite the arc in such cases of arc ignition failure, enabling continuous operation without robot stoppage.

  
![](../../_assets/5_5_1.png)<br>
*Figure 5.5.1. Welding Auxiliary condition (Retry) Setting(e.g. EWM)*

{% hint style="info" %}
[Note]   
The retry function is activated when arc ignition fails after an attempt, while the restart function is activated when welding is interrupted during arc welding and needs to be resumed.
{% endhint %}


The left section of [Figure 5.5.1] represents the retry conditions in the welding auxiliary conditions. The descriptions for each item of the retry conditions are as follows:  

### (1)	Retract Time: [0] sec (Range: 0.00 ~ 10.00)  
  The retry function is performed after attempting to weld by feeding the wire and failing to ignite the arc. As a result, the wire may be excessively fed during the retry process. In this case, the wire might contact the base material and cause fusion or get too close to the base material, resulting in unstable arc ignition. To address this, the function supports retracting the wire before the retry to create an optimal environment for welding. This setting specifies the time for retracting the wire. If this value is not 0, the wire will be retracted, the torch will move, and then the arc ignition will be attempted.  

### (2)	Retract speed: [10] % (Range: 0.0 ~ 100.0)  
  Specifies the speed at which the wire is retracted during the retry process. This feature may not be supported depending on the welder model. (e.g. Saprom welders)  

### (3)	Repetition: [5] times (Range: 0 ~ 9)  
  Specifies the number of times the arc ignition will be retried after failure. If the arc fails to ignite within the specified number of retries, the system will return to the origin(the initial arc ignition attempt point, or the weld start point) and stop.  

### (4)	Retry condition: [0] (Range: 0 ~ 32)  
  Specifies the welding condition number to be used for retrying the arc ignition. During the retry, welding will be performed according to the conditions (current, voltage, etc.) of the welding start condition that was entered.
  However, if the entered condition number is "0" or if the operation mode is set to reentry, the welding will be perfomed based on the main condition of the currently active welding start condition.  

### (5)	Operation mode: ReEnter / Shift / Multi-direc.  
  Sets the method for moving the torch during a retry. Three different methods are supported, and the torch movement for each setting is as follows: (Please refer to [Figure 5.5.2])  

- A. ReEnter  
  When arc ignition fails, the torch steps backward to the previous step and attempts to ignitie the arc again. The distance of this backward movement is set in the welding auxiliary condition retry settings menu under the "Retreat/Weld line dist". After stepping back a certain distance, the torch will step forward again, so the voltage/current conditions follow the welding start conditions.  

- B. Shift  
  After moving by the shift distance set in the retry conditions of the welding auxiliary condition, the torch returns to the arc ignition step. The shift distance can be set in the forward/backward, left/right, and up/down direction relative to the welding line. During the retry, the welding conditions follow the welding start conditions in the retry settings. If arc ignition is successful, the arc is maintained, and the torch moves to the welding start point at the set speed, where welding proceeds.  

- C. Multi-direc.  
  In the retry conditions of the welding auxiliary settings, the "shift Distance" is devided into forward/backward, left/right, and up/down movements. The 1st retry attempts to move along the welding line by the forward/backward distance. The 2nd retry attempts the left/right and up/down movements, considering the distances set for those directions. The 3rd retry moves in the opposite direction of the left/right position from the second retry. For retries 4-6, the same operation is performed at twice the distance compared to retries 1-3, and for retries 7-9, the same operation is performed at three times the distance. Welding starts according to the welding start conditions in the retry settings, and if arc ignition is successful, the arc is maintained, and the torch moves to the welding start point at the set speed, where welding proceeds.  

### (6)	Speed: [100]cm/min (Range: 1.0 ~ 999.0)  
  Specifies the speed at which the torch moves to the retry position or returns to the welding start point during the retry.  

### (7)	Retreat/Weld line dist.: [3] mm (Range: 0.00 ~ 99.99)   
  When the operation mode is set to ReEnter, this is the distance the torch moves during the retry.  

### (8)	Shift distance: FWD/BWD = [ 2 ], L/R = [ 2 ], Up/Down = [ 1 ] mm (Range: -99.99 ~ 99.99)  
  When the operation mode is set to Shift, this is the distance the torch moves during the retry.  
    

![](../../_assets/5_5_2.png)<br>
*Figure 5.5.2 Retry Function Sequence*


[__SOURCE](5_Condition_editing/5_Aux_condition/2_restart.md)
# 5.5.2 Welding Auxiliary condition - Restart  

During arc welding, the process may be interrupted due to factors such as arc failure, exceeding the limits of welding current and voltage, gas pressure drop, wire shortage, cooling water errors, etc.
When welding is restarted from the point where the process was interrupted, there is a risk of leaving un-welded areas.
In such cases, the restart function compensates for the un-welded sections by performing overlap welding.

After welding is interrupted, the system automatically restarts or, after eliminating the cause of the interruption, resumes operation.
It moves backward along the weld line for a certain distance and then resumes welding. This results in an overlap region near the point where welding was stopped, preventing un-welded areas from being created.

This section describes the restart conditions and overlap settings.

 
![](../../_assets/5_5_3.png)<br>
*Figure 5.5.3. Welding Auxiliary condition (Restart) Setting(e.g. EWM)*


### (1)	Restart Repetition: [ 3 ] times (Range: 0 ~ 9)   
Specifies the maximum number of restart attempts within the same welding section. If this count is exceeded, the error "**E1274 Re-startup count exceeded within the same welding section**" will occur.  

### (2)	Restart Condition: [ 0 ] (Range: 0 ~ 32)   
Specifies the welding condition number to be used during the overlap region when restarting the welding. The welding will be performed with the specified initial welding conditions(current, voltage, etc.)  
If the input condition number is "0", welding will proceed with the current welding start conditions from the point of overlap.

### (3)	Overlap distance: [ 5 ] mm (Range: 0.0 ~ 99.9)  
Specifies the length of the overlap (overlap distance) when restarting the welidng. The robot will move back by the specified distance and then resume welding.  

### (4)	Moving Speed: [ 50 ] mm/sec (Range: 1.0~150.0)  
Specifies the speed at which the torch is moved to the overlap start position.
This corresponds to the movement speed in the section from ③ to ④ in [figure 5.5.4]  

### (5)	Welding Speed: [ 50 ] cm/min (Range: 10.0~999.0)  
Specifies the robot's speed while performing overlap welding from the start to the end position. This is the speed during the overlap region in section ④ of [Figure 5.5.4].

When an error occurs during welding from the start point to the end point (⑤), and if the overlap condition is semi-automatic, the user must identify the cause of the welding stop and address the error (①).
After resolving the issue (②), pressing the `Start` button (③) will resume welding.
The robot will automatically move to the overlap start position at the speed set by the `Moving speed` (④).
Once at the position, it will perform overlap welding at the `Welding speed` for the specified distance, and then continue welding at the normal speed.
However, if an error occurs during the overlap welding, the robot will not repeat the overlap but will directly start welding from that point onward.

---

![](../../_assets/5_5_4.png)<br>
*Figure 5.5.4. Restart Function Sequence*


### (6)	Overlap Condition Settings  
The lower section of [Figure 5.5.3] defines how to perform overlap welding when the welding process is interrupted due to reasons such as Arc Off (arc failure), exceeding limits, Gas Off (gas pressure drop), Wire Off (wire shortage), or Coolant Off (coolant error) during arc welding.
    
-  A. Auto  
    This setting performs overlap automatically. It can only be configured if welding has been interrupted due to arc stoppage.
    In the event of an arc stoppage during welding, the process does not stop. Instead, overlap welding is carried out based on the method set in the restart section of the welding auxiliary conditions, after which the main process resumes.
    However, if the arc stops again during the overlap welding section, welding will resume from that position immediately.  

- B. Semi-Auto  
    This setting allows the user to perform overlap manually. If issues such as Arc Off, exceeding limits, gas pressure drop, wire shortage, or coolant error occur, welding is interrupted, ant the robot is also halted.
    After addressing the cause, the user must press `Start`, upon which overlap welding will be performed based on the method set in the restart section of the welding auxiliary conditions, and then main process resumes.
    At this point, if the robot is moved to a different location using the jog function and `Start` is pressed, it will move directly to the overlap welding position and resume welding.

- C. Ignore  
    This setting ignores errors. When this setting is enabled, the robot continues the process without stopping even if welding is interrupted. In other words, the process will proceed regardless of arc stoppage or exceeding the set limits.
    This method can only be applied when welding has been interrupted due to arc stoppage or exceeding limits, and the process is being restarted.

- D. Disable  
    This setting prohibits overlap welding. If issus such as arc stoppage, exceeding limits, gas pressure drop, wire shortage, or coolant error occur, welding is interrupted and the robot is halted.
    After addressing the cause, the user must press `Start`, overlap welding will not be performed, and welding will begin from the position where the robot was stopped.


{% hint style="warning" %}
  When moving the robot, pressing the step forward/backward keys will reset the restart information, prventing overlap overlap from being performed. Only jog movements should be used to move the robot.
{% endhint %}



[__SOURCE](6_Weaving_function/README.md)
# 6. Weaving Function

[__SOURCE](6_Weaving_function/1_Weaving_function/README.md)
# 6.1 Weaving Functions

The weaving function is used in arc welding to widen the weld bead width. The details of the weaving function are determined by the weaving conditions and reference points. The following settings can be configured in the weaving conditions.  

[__SOURCE](6_Weaving_function/1_Weaving_function/1_condition_.md)
# 6.1.1 Weaving Condition

When the cursor is placed above the `weaving ...` command, pressing the `[Property]` key will display the weaving condition editing screen as shown below.  


![](../../_assets/6_1_1.png)<br>
*Figure 6.1.1. Weaving Condition Settings*

---

The details for each field in the weaving conditions are as follows:  

### (1)	Condition Number: [1] (Range: 1 ~ 1000)  

This is the condition number where the weaving operation settings are stored.
Conditions can be added or removed by pressing the [+] or [-] buttons.
You can navigate to the previous or next condition number to edit the corresponding condition.

### (2)	Weaving Type: <Single, Triangle, L type, Circle, DownCurve>  

This field specifies the type of weaving motion. (please refer to [[6.1.2 Weaving Type]](../1_Weaving_function/2_configuration_.md))

### (3)	Frequency: [2] Hz (Range: 0.0 ~ 10.0)  

This field sets the weaving frequency, with a range of `0.0 to 10.0 Hz`. When the frequency is set to '0', the movement time will be applied instead.  
(please refer to [[6.1.3 Frequency]](../1_Weaving_function/3_frequency.md))  

### (4)	Default Pattern  

This field sets the pattern for the weaving motion.
(please refer to [[6.1.4 Default Pattern]](../1_Weaving_function/4_pattern.md))  

- **Left Distance(Wall Direction Distance)** : [2.5] mm (Range: 1.0 ~ 25.0)
- **Right Distance(Other Direction Distance)** : [2.5] mm (Range: 1.0 ~ 25.0)
- **Angle** : [90] degrees (Range: 0.1 ~ 180.0)
- **Offset Angle** : When the torch orientation reference is used, the field specifies the angle at which the tilts to the left or right from its position.
- **Wall Direaction** : <**Vertical**, **Horizon**, **Base on Torch**>

### (5) Forward Angle: [0] degrees (Range : -90.0 ~ 90.0)  

This field indicates the weaving angle relative to the forward direction.
When set to 0 degrees, the forward and weaving directions form a right angle.  
(please refer to [[6.1.4 Default Pattern]](../1_Weaving_function/4_pattern.md))  

### (6)	Boundary Limitation: <Enable, Disable>  

This option determines whether the weaving trajectory is restricted by the boundaries at the start and end of the welding section. When this function is enabled, the weaving trajectory is confined within the welding area.  
(please refer to [[6.1.4 Default Pattern]](../1_Weaving_function/4_pattern.md))  

### (7)	Robot Behavior when Weaving Stops: <Moving, Stop>

When a timer is set in the weaving pattern, the weaving motion will stop at both the left and right ends of the weaving.
In this case, this setting determines whether the robot continues to move or stops during the weaving stop period.  

### (8) Move Time: [1] sec (Range: 0.0 ~ 10.0), Timer(Weaving Stop): [0] (Range : 0.00 ~ 2.00)  

If the weaving frequency is set to '0', the weaving motion will be performed based on the move time.
In this case, the move time for each section and the weaving stop time between sections are configured.  
(please refer to [[6.1.5 Weaving Section Setting]](../1_Weaving_function/5_weaving_section.md))  

When the 'Weaving Frequency' is set, only the 'Timer (Weaving Stop)' setting can be adjusted.
Druing the total time set for the specified frequency, the robot performs weaving for the duration excluding the time set in the 'Timer (Weaving Stop)'. During the weaving stop time, weaving stops.
Whether the robot continues to move during the weaving stop time is determined by the setting of 'Robot Behavior when Weaving Stops'.

### (9) Weaving Axis Number: [1]  

This setting determines whether the part perfoming the weaving motion is the robot or an auxiliary axis.
When set to an auxiliary axis, the robot will move as recorded, and only the auxiliary axis will move according to the set distance and frequency to implement weaving.
If an auxiliary axis is selected, the auxiliary axis specified in the 'Auxiliary Axis Number' field will perform the weaving motion.

[__SOURCE](6_Weaving_function/1_Weaving_function/2_configuration_.md)
# 6.1.2 Weaving Type    


Set the pattern shape of the weaving as shown in the following figure.
 
![](../../_assets/6_1_2_1.png)<br>
*Figure 6.1.2. Weaving Pattern Type*

![](../../_assets/6_1_2_2.png)<br>
*Figure 6.1.2. Weaving Pattern Type - Down curve*


[__SOURCE](6_Weaving_function/1_Weaving_function/3_frequency.md)
# 6.1.3 Frequency


"**Frequency**" refers to the repetition cycle of the weaving. When the "Frequency" is set to '0', the repetition cycle is defined by the move time method instead of the frequency method.
To specify the repetition cycle using the frequency method, a value other than '0' must be set.  

The frequency is releated to both the leteral and longitudinal distances.
As the frequency increases, the available lateral and longitudinal distances decrease, resulting in a smaller amplitude. Conversely, as the frequency decreases, the amplitude can be increased.
In the case of a triangular weaving pattern, the sum of the lateral and longitudinal move times equals the diagonal move time. 
 

[__SOURCE](6_Weaving_function/1_Weaving_function/4_pattern.md)
# 6.1.4 Default Pattern

Configure each parameter shown in the following figure. 
  
<p align="center">
  <img src="../../_assets/6_1_3.png" width="60%"></img>
  <img src="../../_assets/6_1_3_1.png" width="45%"></img>
  <em><p align="center">Figure 6.1.3 Weaving Parameters according to Wall Direction</p></em>
</p>

- **Left Distance(Wall Direction Distance)** : [2.5] mm (Range: 1.0 ~ 25.0)
- **Right Distance(Other Direction Distance)** : [2.5] mm (Range: 1.0 ~ 25.0)

### (1) Left Distance(Wall Direction Distance)

Set the distance in the left (wall) direction.  


### (2) Right Distance(Other Direction Distance)

Set the distance in the right direction.  


### (3)	Angle

As shown in Figure 6.3, set the angle between the left (wall) direction and the right direction.
The angle is measured from the left (wall) direction to the right direction.
However, when using **REFP 4**, this angle will be ignored.


### (4)	Offset Angle (refer to [Figure 6.1.3])

When the wall direction is set based on the torch posture, this setting defines the angle at which the weaving surface rotates relative to the direction of weaving progression (the dirction in Figure (3) marked with ⊙).
When set to 0°, the angle between the left (wall) direction and the right direction is bisected.


### (5) Wal Direction (refer to [Figure 6.1.3])

Set the left (wall) direction to one of the following options: vertical (Figure (1)), horizontal (Figure (2)), or torch posture-based (Figure (3))
Generally, the left (wall) direction is set to vertical, while the horizontal direction is typically used for weaving with a 180-degree angle on the plane.  

For torch posture-based weaving, the left (wall) direction is set counterclockwise from the direction of weaving progression (the dirction in Figure (3) marked with ⊙).
Torch posture-based weaving can accommodate all left (wall directions), and it can also adapt when the left (wall) direction changes during the weaving process.


### (6) Forward Angle

This refers to the angle of the weaving vibration direction relative to the welding line. The adjustable range is -90.0 to 90.0 degrees.
When set to 0°, the weaving will move perpendicular to the welding line.


![](../../_assets/6_1_4.png)<br>
*Figure 6.1.4. Weaving Forward Angle*

    
### (7)	Boundary Limitation

For weaving with a forward angle other than 0°, the weaving may exceed the boundary of the section at the start and end of the weaving area.  
The boundary limitation setting allows you to choose whether the weaving should be confined within the section boundaries or if it can proceed without any restrictions beyond the section boundaries.

 
![](../../_assets/6_1_5.png)<br>
*Figure 6.1.5 Weaving Boundary Limitation* 

[__SOURCE](6_Weaving_function/1_Weaving_function/5_weaving_section.md)
# 6.1.5 Weaving Section Setting

### (1)	Robot Behavior when Weaving Stops  

When the Timer (Weaving Stop) is set to a value other than 0, the weaving pattern will stop at the end of the weaving section for the specified duration.
In this state, you can configure whether the robot will continue to move or stop.

If set to **Move**, the robot behaves as shown on the left in the figure; if set to **Stop**, the behavior is as shown on the right.  


![](../../_assets/6_1_6.png)<br>
*Figure 6.1.6. Robot Behavior when Weaving Stops* 

### (2)	Move Time

This setting defines the move time for each section when "Frequency" is set to '0'.
The move time for unused sections (e.g., sections 3 and 4 in simple oscillation) will be ignored.

![](../../_assets/6_1_7.png)<br>
*Figure 6.1.7. Movement Section by Weaving Pattern* 


### (3)	Timer (Weaving Stop)

Set the weaving stop time at the endpoint of each section as shown in the figure below.
This setting also applies when the weaving frequency is configured.
When the weaving frequency is set, the robot's move time during the weaving cycle is calculated as follows:  
* Robot Move Time = (1 / Weaving Frequency) - Total Timer Time

{% hint style="warning" %}
  if "Robot Behavior when Weaving Stops" is set to **Move**, the movement trajectory does not stop, and it will follow a straight path, as shown in the figure below.
{% endhint %}
 
 
![](../../_assets/6_1_8.png)<br>
*Figure 6.1.8. Trajectory Example When Timer is Set*   

{% hint style="warning" %}
  if "Robot Behavior when Weaving Stops" is set to **Stop**, the movement trajectory also stops, but the robot's speed remains the same.
{% endhint %}
[__SOURCE](6_Weaving_function/2_Reference_point/README.md)
# 6.2 Reference Point(refp) Features


To perform weaving, a weaving coordinate system is required to determine the location where the weaving pattern will be created, as explained in [[6.1 Weaving Functions]](../1_Weaving_function/README.md).
The configured weaving coordinate system is usde to set the detailed parameters for the weaving function.
By default, when the weaving motion begins, the Z-axis of the robot's coordinate system is set to the wall direction.
The weaving coordinate system (rectangular coordinate system) is automatically created using the position of the pose approaching the welding start point and the direction of the torch during the welding process.  

However, in some cases, such as when the welding start pose, the shape of the base material, or its position prevent the creation of the weaving coordinate system, or when modifications to the default weaving coordinate system are needed (e.g., when the angle between the wall direction and the other direction is not 90 degrees), the reference point function can be used to create a desired weaving coordinate system and align the weaving pattern with the base material.


{% hint style="info" %}
  When the **[Wall Direction]** setting is configured as Torch Posture-Based, no other `refp` commands except `refp3` are used.
{% endhint %}
[__SOURCE](6_Weaving_function/2_Reference_point/1_sorts.md)
# 6.2.1 Reference Point Type


![](../../_assets/6_2_1.png)<br>
*Figure 6.2.1. Weaving Coordinate System* 


### (1)	refp 1  

The `refp1` command specifies the wall direction of the weaving coordinate system.
If the wall direction is not specifically defined, the robot will use the vertical direction as the wall direction to perform the weaving opeartion.
Therefore, if the wall direction is not vertical, this command should be used to set the wall direction.  

* **Usage**: Record a point on the surface of the workpiece in the wall direction as `refp 1`. <br> This point and the welding seam(straight line ⓢⓔ) can be used to determine the wall direction. <br> If only the `refp1` command is used, the other direction will be set by rotating the wall direction by the default pattern angle relative to the direction of movement.


### (2)	refp 2  

The `refp2` command sets the side of the space when the weaving trajectory will be created, based on the plane that defines the wall direction.

* **Usage**: Record any point in the space on the side where weaving will be performed as `refp 2`. <br> [Figure 6.2.2] shows an example of the weaving coordinate system when `refp 2` is recorded between two base materials. <br> When only the `refp 2` command is used, the Z-axis of the robot's coordinate system is set to the wall direction, and the other direction is determined accordingly.


### (3)	refp 3  

The `refp3` command specifies the direction of weaving in a stationary weaving operation, where the robot remains stationary and only the positioner rotates.  

* **Usage**: Record any point along a straight line that indicates the direction of movement, starting from the robot's stationary position, as `refp 3`. <br> The robot will weave along a direction perpendicular to the line formed by the welding start point and `refp 3`. 

* Example: After setting refp3, specify the same positions for the welding start and end steps. The travel speed is set by time. <br> (Note: If `refp 3` is not specified, no weaving will occur, and an error will be triggered.)


### (4)	refp 4  

The `refp 4` command sets the angle between the wall direction and the other direction.
[Figure 6.2.3.] shows an example when the angle is set to 90 degrees.
When using this command to specify the angle, the value set in `Angle` will be ignored.

    
![](../../_assets/6_2_2.png)<br>
*Figure 6.2.2. Weaving Direction and Reference Point* 
    

<p align="center">
  <img src="../../_assets/6_2_3.png" width="65%"></img>
  <img src="../../_assets/6_2_3_1.png" width="65%"></img>
  <em><p align="center">Figure 6.2.3. Usage of Different Reference Points</p></em>
</p>   


{% hint style="info" %}
  - refp 1: Ensure the distance from the welding seam is at least 5mm.
  - refp 2: Ensure the distance from the wall direction plane is at least 5mm.
  - refp 3: Ensure the distance from the start point is at least 5mm.
  - refp 4: Set the angle when it is difficult to measure the angle of the weaving pattern.
{% endhint %}
[__SOURCE](6_Weaving_function/2_Reference_point/2_editing.md)
# 6.2.2 Reference Point Edit

### (1) Recording Reference Points : Similar to the Move Command

- ① **Move the Cursor**: Move the cursor to the location where the reference point will be recorded (typically just above the `weaving on` command step).
- ② **Record the Reference Point Command**: Press `[F6: cmd. Input] - arcweld - refp` to record the reference point command.
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


[__SOURCE](6_Weaving_function/3_Weav_sync_out/README.md)
# 6.3 Weaving Sync Out


This feature allows for smooth control of heat input (weld deposit) by adjusting the current and voltage on the left and right sides during weaving.  

{% hint style="info" %}
  The functionality is supported from version 60.30-00.
{% endhint %}  

![](../../_assets/6_3_1_weav_sync_out.png)<br>
*그림 6.3.1. Example of Weaving Sync Output Function*   

As shown in the figure above, this feature is used when it is necessary to control the heat input and weld deposit during left and right weaving, or when the bead shape needs to be adjusted.

To use this feature, enter the `[Property]` window of the `weaving` command and configure the following settings.


![](../../_assets/6_3_2_weav_sync_out_setting.png)<br>
*Figure 6.3.2. Weaving Sync Output Function Settings*   

<table>
  <thead>
    <tr>
      <th style="text-align:left">Item</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Enable</td>
      <td style="text-align:left">
        When enabled, it adjusts the current/voltage output during weaving according to the user's settings.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Output(left/right)</td>
      <td style="text-align:left">
        The percentage of curren/voltage output change relative to the baseline condition within the left and right weaving settings
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Range</td>
      <td style="text-align:left">
        Set the percentage range of output change during the left and right weaving.
      </td>
    </tr>
  </tbody>
</table>
[__SOURCE](7_Monitoring/README.md)
# 7. Arc Welding Data Monitoring

During arc welding, there are instances where the current/voltage command values sent form the robot controller to the welder are compared with the actual current/voltage values output from the welder to the robot controller. In such cases, the arc welding data graph monitoring function can be used to check the welding-related data in real time.

</br>

Our controller offers 2-type of monitoring functions for welding data monitoring:

(1) **Detailed Information Monitoring**: Allows you to check all available data.

(2) **Arc Welding Data Graph**: Enalbes viewing of the command and actual current/voltage data in waveform.

(3) **Arc Trajectory Monitoring**: You can view the trajectory of the tool tip and the torch in detail while welding.

[__SOURCE](7_Monitoring/1_detail_mon.md)
# 7.1 Detailed Information Monitoring

This function allows you to check detailed data related to arc welding. The information provided may vary depending on the set welder, so the monitoring window may differ based on the configured welder. If a communication error occurs with the welder or if there is no communication connection, the "Welder Error Code" or "Welder Communication Status" items will be displayed with a red background. The following data can be monitored in the detailed information monitoring.

![](../_assets/7_1_1.png)<br>
*Figure 7.1.1. Arc Welding Detailed Information Monitoring*

1. Current Input: The commanded welding current sent from the robot to the welder (A)

2. Current Output: The actual welding current currently being output by the welder (A)

3. Voltage Iutput: The commanded welding voltage sent from the robot to the welder (V)

4. Voltage Output: The actual welding voltage currently being output by the welder (V)

5. Welding Process

6. Feeding Speed: The wire feeding speed (m/min)

7. Operation Mode: Arc welding mode

8. Prog/Job Number

9. Feed Motor Current: The current driving the actual fedding motor (A)

10. Welder Error Number

11. Pulse Dynamic Compensation

12. Additional Information Window: This section displays useful additional information such as the upper and lower limits of current/voltage and their units. 

13. Input Signals: Signals sent from the welder to the robot controller.(Can be checked under `[F2: System] - 5: Initialization - 3: Usage Setting - Welder Setting - Input signal assign`)

14. Output Signals: Signals sent from the robot controller to the welder.(Can be checked under `[F2: System] - 5: Initialization - 3: Usage Setting - Welder Setting - Output signal assign`)

15. Command Values: Frequently used commands that can be manually output.


[__SOURCE](7_Monitoring/2_data_graph.md)
# 7.2 Arc welding data graph

Arc welding data graph displays information related to the welding data's waveform, allowing you to view not only the real-time data but also past data at a glance.

To use this feature, on TP, press `[pane layout] - select - arc data graph` sequentially. 

 
![](../_assets/7_2_1.png)<br>
*Figure 7.2.1. Arc Welding data graph*

The following items can be checked in the monitoring window:

1. Welding Status(initial conditions, gas pre-flow, end conditions, gas post-flow, crater movement, main welding, etc.)

2. Job/Prog no, Synergic settings

3. Input Current / Command current graph

4. Input voltage / Command voltage graph

5. Moving average filtered graph of input current and voltage

6. Upper and lower limits of welding current and voltage

Arc Welding data graph offers left/right and up/down movement functions. You can also add rows and columns to view more data. By toggling the `[Auto scroll]` button, you can review the past welding screens even during the current welding process.

You can increase the number of rows in the graph by pressing the **[Row]** or **[Col]** button at the bottom of the arc welding data graph screen. If you want to zoom in on the data graph further, you can press **[SHIFT] + [Row]** or **[SHIFT] + [Col]** to enlarge the display.
[__SOURCE](7_Monitoring/3_arc_trj_mgr.md)
# 7.3 Arc Trajectory Manager

This features displays the trajectory, current, voltage, and torch position (welding angle, push-pull angle) in real-time during arc welding.

Through this, you can monitor the welding angle, current, and voltage in real time during arc welding, making it easier to modify the welding teaching later.

To enable this feature, follow these steps:

Set "Arc trajectory monitoring" to 'activation on' under `[F2: System] - 4: Application parameter - 2: Arc welding`.


{% hint style="info" %}
This feature is available during from version 60.30-00.
{% endhint %}

![](../_assets/7_3_1_arc_trj_mgr.png)<br>
*Figure 7.3.1. Real-time Arc trajectory monitoring*

You can monitor the trajectory and welding information in real-time from the `arcon` to the `arcoff` section.

Use the arrow keys to move the plane, or press **[Shift] + [+/-]** keys to zomm in or out.

The welding angle and push/pull angle are calculated base on the welding direction relative to the welding plane.

{% hint style="info" %}
The welding plane automatically rotates according to the welding trajectory.
{% endhint %}



[__SOURCE](7_Monitoring/4_arc_monitoring/README.md)
# 7.4 Arc Monitoring

{% hint style="info" %}
This feature is supported in version 70.00-00 and later.  
{% endhint %}

This function allows you to view monitoring features related to arc welding on a single screen.
It integrates the following features: Arc Welding, Real-time change welding data, Arc sensing and multi-pass, Arc operation information, Arc trajectory monitoring  


To access this function, navigate to `[(right panel) pane layout] - select - arc monitoring`.
The following sections describe each screen and the available monitoring functions.  


[__SOURCE](7_Monitoring/4_arc_monitoring/1_arc_welding.md)
# 7.4.1 Arc Welding


When entering the "Arc Monitoring" screen for the first time, this screen is displayed by default.
To switch to this screen from another screen, click `[F1: Arc Welding]` on the bottom panel.
This screen displays the analog and digital signals exchanged with the welder.

![](../../_assets/7_4_1_1.png)<br>
*Figure 7.4.1.1. Arc Welding Monitoring*  

On the "Arc Welding" screen, click the `[F7: Select]` button on the bottom panel to change the panel contents and access the following functions:  


### (1) Welder set.

![](../../_assets/7_4_1_2.png)<br>
*Figure 7.4.1.2. Manual Welder Setup*  

Click the `[F1: welder set.]` button on the bottom panel to open the following window.
In this window, you can manually configure the welding machine.


### (2) Manual Output

![](../../_assets/7_4_1_3.png)<br>
*Figure 7.4.1.3. Manual Output*  

Select the desired signal from either the analog output singals or digital output signals(e.g. "Stick Check" or "OFF (fb1.12)" as shown in the figure), and then click the `[F2: Manual Output]` button on the bottom panel.
A window will appear where you can configure the selected signal to be output.  


### (3) I/O Setup

A wide variety of data is exchanged between the robot controller and the welder in the form of analog and digital signals(refer to `[F2: System] - 5: Initialization - 3: Usage setting - [F2: Welder setting]`).
However, the signals that operators need to monitor are typically limited.
Click the `[F3: Set I/O]` button on the bottom panel to open the following window.  

![](../../_assets/7_4_1_4.png)<br>
*Figure 7.4.1.4. I/O Output Setup*  

This window displays all signals exchanged between the robot controller and the welder.
Select only the required data and click to `OK` to monitor the selected signals only.
You can also use the `Select All` or `Clear All` buttons at the top to enable or disable all items at once.  

[__SOURCE](7_Monitoring/4_arc_monitoring/2_arc_sensing.md)
# 7.4.2 Arc Sensing


This screen is displayed when the `[F2: Arc Sensing]` button on the bottom panel is clicked from the "Arc Monitoring" screen.
For details on the information available on this screen, refer to the following link: [[8.3.5 Arc Sensing Monitoring]](../../8_Application_function/3_Arc_sensing/5_arcsen_monitoring.md)  

 
[__SOURCE](7_Monitoring/4_arc_monitoring/3_arc_operinfo.md)
# 7.4.3 Arc Operation Information


This screen is displayed when the `[F3: Arc OperInfo]` button on the bottom panel is clicked from the "Arc Monitoring" screen.
For details on the information available on this screen, refert to the following link: [[1.3.7 Arc Welding Operation Information]](../../1_Basic_information/3_Convenient_functions/7_operation_info.md)  



[__SOURCE](7_Monitoring/4_arc_monitoring/4_arc_trj_monitor.md)
# 7.4.4 Arc Trajectory Monitoring


To use this function, first navigate to `[F2: System] - 4: Application parameter - 2: Arc welding` and set the **"Arc Trajectory monitoring"** to **"Enable"**.
On the left side, the table data selected from the bottom panel is displayed, and on the right side, the "Arc Trajectory Monitoring" screen is shown.
This screen provides real-time visualization of the welding trajectory and the torch posture (work angle and push/pull angle) during arc welding.  
(You can monitor the trajectory and welding information in real time from `arcon` to `arcoff`)


![](../../_assets/7_4_4_1.png)<br>
*Figure 7.4.4.1. Arc Trajectory Monitoring*  

You can adjust the size of the table and canvas by clicking and dragging the center divider.
(However, one view cannot completely cover the other. If the screen is minimized and then restored to full-screen, the layout will be reset)
Use the `+/-` key along with the `[shift]` key to zoom in or out.  
Within the canvas, you can drag to adjust the view position.  


[__SOURCE](8_Application_function/README.md)
# 8. Arc Welding Application Functions

We provide various application features to enhance the quality and stability of arc welding. This section briefly introduces these features. Detailed explanations and applications can be found in separate feature manuals, so please refer to the respective manuals for more in-depth information.

[__SOURCE](8_Application_function/1_Arc_cond/README.md)
# 8.1 Arccond - Arc Welding Condition DB & interpolation


Welding conditions can be stored in a database (DB) for use or interpolated during the welding process.
The usage of this function is as follows:

`[F6: cmd. input] - arcweld - arccond` to enter the command in the JOB file.

The command format is as follows:
```arccond <interpolation type>, cnd=<condition number>, gap=<gap>, spd=<welding speed>, rd=<wall direction>, ld=<sie direction>, freq=<weaving frequency>, cur=<crruent>, vol=<voltage>```


<br>

- **interpolation type**: D(stepped, immediate application) / L(Linear interpolation)
- **cnd**: condition number (WDB-welding database- and interpolation conditions can be edited via the properties window)
[__SOURCE](8_Application_function/1_Arc_cond/1_cmd_para.md)
# 8.1.1 Step Change using Command Factors

The stepped change function can be used in the command arguments as follows:

| Method | Example |
| :--- | :--- |
| Changing IV(Current, Voltage) |move L, spd=60%, ...<br/>move L, spd=10%, ...   <span style="color: green"> # Weld point(seam) Entry Step </span> <br>    arcon cnd=1  <br>    move L, spd=40cm/min, ... <br>   <b>  arccond D, cur=175, vol=20 </b>  <span style="color: green"> # Change current to 175A, voltage to 20V </span> <br>   move L, spd=30cm/min, ...  <br>    arcof <br>   end |
| Changing Welding Speed and Weaving Parameter | move L, spd=60%, ...  <br>   move L, spd=10%, ...    <span style="color: green"> # Weld point(seam) Entry Step  </span> <br> weaving on, cnd=1 <br>   arcon cnd=1   move L, spd=40cm/min, ... <br> <b>  arccond D, spd=80, rd=20, ld=10, freq=1.5, cur=175, vol=20 </b> <br> <span style="color: green">  # Change welding speed to 80cm/min, weaving width to 20/10mm, frequency to 1.5HZ, current to 175A, and voltage ot 20V </span> <br>  move L, spd=30cm/min, ...  <br>   weaving off <br>   arcof  <br> end |
[__SOURCE](8_Application_function/1_Arc_cond/2_wdb_step.md)
# 8.1.2 Step Change using WDB(Welding DataBase)

```python
    arccond D, cnd=1
```

In the command above, by entering the properties window, you can view the following configuration window.

 
![](../../_assets/8_1_1.png)<br>
*Figure 8.1.1. Arc Welding Condition Dialog* 

<br>

You can add or delete **cnd**(welding conditions), allowing you to store and use welding conditions in the database as follows:
    Conditions that can be stored in the DB: welding speed, current, voltage, weaving frequency, weaving width

Using this, the following JOB configuration can be created:

```python
    move L, spd=60%, ...
    move L, spd=10%, ...	    # Weld point(seam) Entry Step
    arcon cnd=1
    move L, spd=40cm/min, ...
    arccond D, cnd=1  	    # Immediately change to Welding DB Condition 1
    move L, spd=30cm/min, ...
    arcof
    end
```
[__SOURCE](8_Application_function/1_Arc_cond/3_wdb_continuous.md)
# 8.1.3 Continuous Interpolation Change using WDB(Welding DataBase)


For example, this function allows for linear interpolation of welding condition(such as current, voltage, welding speed, weaving width, and weaving frequency) while welding a workpiece where the butt gap is 5mm at the start and 25mm at the end.
In this case, the continuous change of welding conditions (L interpolation) is performed in a linear fashion as shown below.

 
![](../../_assets/8_1_2.png)<br>
*Figure 8.1.2. Linear Interpolation of Welding Conditions* 

<br>

Using the above items from DB 1 and DB 2, a JOB utilizing continuous interpolation change is as follows: 

```python
move L, spd=60%, ...
move L, spd=10%, ...	    # Weld point(seam) Entry Step
arcon cnd=1
move L, spd=40cm/min, ...
arccond L, cnd=1  	    # Continuous interpolation change from Welding DB 1 -> 2
move L, spd=30cm/min, ...    # In this step, the conditions linearly change from cnd(DB) 1 -> 2
arccond L, cnd=2  	    # The next step requires arcof
arcoff
move L, spd=10%, ...	    # Weld point(seam) Exit Step
end
```
[__SOURCE](8_Application_function/1_Arc_cond/4_interpolation.md)
# 8.1.4 Changing the welding Speed and Weaving Width Using Interpolation Condition


This feature is separate from the previously mentioned functionalities. It allows welding conditions to be set based on the reference gap, and then automatically calculates the welding speed and weaving width by measuring the gap at the start and end points through actual touch sensing.  
By entering the "Gap correction" tab in the properties window of the `arccond` command, you can set speed and width accroding to the gap for each condition.
In the split window, clicking on "Arc interpolation" will display this setting as a graph.


![](../../_assets/8_1_3.png)<br>
*Figure 8.1.3. Arc Welding Condition(Gap correction) Dialog box* 

![](../../_assets/8_1_4.png)<br>
*Figure 8.1.4. Arc Interpolation Monitoring* 

<br>

The operation of this function is as follows:

![](../../_assets/8_1_5.png)<br>
*Figure 8.1.5. Welding Condition Interpolation Operation* 

<br>
 

The gap-speed graph can be illustrated as follows:  

The gap-spd graph entered in the Gap correction tab of the properties window of the `arccond` command is created.
At the welding start point, the difference in speed between WDB welding speed and the WDB reference speed (the spd value at the reference gap on the graph) is assumed to be bSpd. The starting speed is then calculated by applying dSpd to the Spd value of the original graph at the current gap.

Similarly, at the welding end point, the difference in speed between the WDB welding speed and the WDB reference speed (the spd value at the reference gap on the graph) is assumed to dSpd2. The ending speed is calculated by applying dSpd2 to the Spd value of the original graph at the current gap.

As shown in the figure above, the welding speed increases linearly between the two `arccond` commands.


An example of the JOB configuration is as follows:

```python
    move L, spd=60%, ...
    move L, spd=10%, ...	    # Weld point(seam) Entry Step
    arcon cnd=1
    move L, spd=40cm/min, ...
    arccond L, cnd=1, gap=20  
    move L, spd=30cm/min, ...    # In this step, welding speed and weaving width change linearly
    arccond L, cnd=2, gap=10   
    arcoff
    move L, spd=10%, ...	    # Weld point(seam) Exit Step
    end
```
[__SOURCE](8_Application_function/2_Touch_sensing/README.md)
# 8.2	Touch Sensing


Welding workpieces are not always in a fixed position due to errors in the jig, positioner, or workpiece mounting.
In such cases, touch sensing can be used to detect the welding start point, intermediate points, and end points, enabling accurate welding.

The touch sensing func. helps obtain the pose by detecting the position of the workpiece and the welding start, end, or intermediate points.

By recording the reference position using touch sensing, the shift of the workpiece from the reference position can be calculated when the workpiece is loaded.
When using the master mode, a mster pose can be saved through reference teaching, and the shift amount is automatically calculated via touch sensing during actual operation.


![](../../_assets/8_2_1.png)<br>
*Figure 8.2.1. Example of Touch Sensing*

### (1) Touch Sensing Types

The touch sensing supports a total of 6-types, as shown in [Figure 8.2.1] (Butt, Fillet, V-groove, LR Center, Groove Detections, and Single point).

![](../../_assets/8_2_2.png)<br>
*Figure 8.2.2. Touch Sensing Types*

### (2) Touch Sensing Command and Setting Parameters

The touch sensing command can be recorded by entering `[F6: cmd. input] - arcweld - touchsen` on the TP.

Assuming the condition 1 set for Fillet, condition 2 set for Butt, and condition 3 for V-groove in the command (where the workpiece type is defined in the properties), the example is as follows:

```python
    move L,spd=60%,accu=0,tool=0  # Move to the touch sensing position with acc 0
    var P10=cpo() # Save the current pose to a local variable P10 before touch sensing.
    touchsen cnd=1, crd="tool_prj", dir=["tf","td"], pose=P10       # Condition 1, tool projection direction, 2-point touch
    touchsen cnd=1, crd="robot", dir=["+x","-y","-z"], pose=P10     # Condition 1, robot coordinate direction, 3-point touch
    touchsen cnd=1, crd="tool", dir="+z", pose=P10           # Condition 1, tool coordinate direction, 1-point touch in +Z
    touchsen cnd=2, crd="tool", dir="+x", lift_up=3, pose=P10, gap=var1 # Condition 2, tool coordinate direction, touch the bottom and rise 3mm
    touchsen cnd=3, crd="tool", dir="-y", lift_up=5, pose=P10   # Condition 3, tool coordinate direction, touch the bottom and rise 5mm
```

- **Sensing Distance** : The distance in the sensing direction [mm], and an error occurs if the workpiece is not detected upon reaching this distance.

- **Retreat Distance** : The distance to retreat after the initial sensing in the case of Fillet, and **the distance to raise after touching the bottom in the DetectGroove type**.

- **Sensing Speed and Retreat Speed** : Specifies the speed during search or retreat.  

- **Detection Type** : Supports sensing during contact and release of contact. Typically, sensing during contact is used, and there is alomost no error.<br/>
  If the situation requires considering even minor errors caused by wire bending during sensing, only use sensing during retreat when absolutely necessary.


<br/>

- **참고**

<center>

| Sensing Type |	Max Search</br>Directions |	Orthogonal XYZ </br>(All types </br>Supported)	| Tool Coordinate System |	Tool Projection</br>Coordinate System | Other input parameters |
|:---:|	:---: |	:---:	| :---:|	:---: |:---:|
| Fillet |	3	|O|	O |	O	|	Retreat Distance |
| Butt	| 1 |	X	|O	|X	|  |
| VGroove |	1 |	X |	O	|X | |
| LRCen |	1	|O |	O	|X |  |	
| DetectGroove |	2 |	O |	O |	O | Proceed Distance 1</br> Retreat Distance 1 </br> criteria |
|Single Point|    1 |    O |    O |    O | |
</center>


In the touch sensing command, pressing on `Property` will bring up a winow as shown in [Figure 8.2.3]  
You can set conditions such as sensing distance, retreat distance, proceed distance, sensing speed, retreat speed, and detection type (contact,  release of contact), among others.  


![](../../_assets/8_2_3.png)<br>
*Figure 8.2.3. Touch Sensing Condition Edit Screen*

{% hint style="info" %}
  For detailed instructions on using the command and parameters, please refer to [2.13 touchsen](../../2_Command/13_touchsen.md) <br>
  This section explains how to use the function.
{% endhint %}

<!-- - **명령어 사용 예시**
```python
    - touchsen cnd=<조건번호>, crd=<좌표계>, dir=[센싱 방향1, 센싱 방향2, 센싱 방향3], pose=<결과포즈 저장변수>, gap=<butt gap 변수>
    - touchsen cnd=<조건번호>, crd=<좌표계>, dir=[센싱 방향1, 센싱 방향2, 센싱 방향3], rotation=<센싱 방향 각도>, pose=<결과포즈 저장변수>, gap=<butt gap 변수>
    - touchsen cnd=<조건번호>, crd=<좌표계>, dir=[센싱 방향1, 센싱 방향2, 센싱 방향3], rotation=<센싱 방향 각도>, mpose=<결과포즈 저장변수>, mshift=<계산된 시프트 변수, gap=butt gap 변수>
```   -->

<!-- - **파라미터**
  - 터치센싱 조건번호 (cnd) : cnd=1	
  - 터치센싱 좌표계 (crd) : "robot", "base", "tool", "tool_prj" 
  - 센싱 방향 파라미터 (dir) : "+x", ["+x","-z"], [+tx, +tz], ["tf","td"],  
  - butt, groove 바닥 탐색 후 상승량 [mm] : lift_up=3		
  - detect groove 탐지 기준 거리 [mm] : criteria=5
  - 센싱 결과 포즈변수 : pose=var_po10
  - butt 하단 갭 변수 (소숫점 첫째 자리에서 반올림) : gap=var_gap 

- **참고**  
  센싱방향(dir)은 작업물 타입에 따라 다음과 같이 지정할 수 있습니다.

  - Fillet	: 최소 1개 ~ 3개 지정
              +x, -x, +y, -y, +z, -z (crd="robot" 또는 "base")
              tf, td, tl, tr (crd="tool_prj")
              +tx, -tx, +ty, -ty, +tz, -tz (crd="tool")
  - Butt 	: 1개 지정, 하강방향은 +tz 방향
            +tx, -tx, +ty, -ty, +tz, -tz (crd="tool")
  - V Groove 	: 1개 지정, 하강방향은 +tz 방향
                +tx, -tx, +ty, -ty, +tz, -tz (crd="tool")
  - LRCen 	: 1개 지정
              +x, -x, +y, -y, +z, -z (crd="robot" 또는 "base")
              +tx, -tx, +ty, -ty, +tz, -tz (crd="tool")
  - DetectGroove: 2개 지정 (하강방향, 전진방향 순서)
                  tf, td, tl, tr (crd="tool_prj")
                  +tx, -tx, +ty, -ty, +tz, -tz (crd="tool") -->


### (3) Detailed Description of Touch Sensing by Sensing Type

---

#### [1] Fillet

![](../../_assets/8_2_4.png)<br>
*Figure 8.2.4. Example of Touch Sensing - Fillet*

- Examples of Command
```python
  touchsen cnd=1, crd="robot", dir=["+x","-y", "-z"], pose=P10
  touchsen cnd=1, crd="tool_prj", dir=["tf", "td"], pose=P10
  touchsen cnd=1, crd="tool", dir=["+z"], pose=P10
```  
  - 1-Point sensing : Only one sensing direction is specified.
  - 2-Point sensing : Two sensing directions are specified sequentially.
  - 3-Point sensing : Three sensing directions are specified sequentially.
- Tool Projection Method (crd="tool_prj") : For convenience, the forward, downward, left, and right directions are determined based on the torch posture.  <br> The directioon can be specified as tf(forward), td(downward), tl(left), tr(right). (tl = RotZ(90) * tf, tr = RotZ(-90) * tf)
- For workpieces with rotational amounts (RX, RY, RZ), such as tilted Fillets, the sensing direction can be changed using the angle specification option. Please refer to the bottom of the manual for usage.

---

#### [2] V Groove

![](../../_assets/8_2_5.png)<br>
*Figure 8.2.5. Example of Touch Sensing - V Groove*   

- Examples of Command
```python
  touchsen cnd=3, crd="tool", dir=[-ty], lift_up=3, pose=P10    # Condition 3, tool coordinate direction
```  
  - V-Groove Type can be used for sensing workpieces with a Groove shape. However, it is recommended to teach the tool posture so that it is positioned along the bisector of the angle, similar to the figure above, before starting the sensing.  
  - The direction parameter corresponds to one direction for the left-right sequence. The downward sequence direction is fixed in the `+z` direction relative to the tool.  
  - For stable sensing, it is recommended to set the lift-up amount to at least 3mm.  

- Sensing Sequence  
  - The sensing sequence proceeds as follows: upper left-right → middle return → bottom → bottom left-right → middle  

![](../../_assets/8_2_6.png)<br>
*Figure 8.2.6. Touch Sensing Sequence - V-Groove*   

---
 
#### [3] BUTT

![](../../_assets/8_2_7.png)<br>
*Figure 8.2.7. Example of Touch Sensing - Butt*   


- Examples of Command
```python
    touchsen cnd=2, crd="tool", dir="+x", lift_up=3, pose=P10, gap=var_gap   
    # Condition 2, tool coordinate direction, touch the bottom and rise 3mm
```  
  - Butt Type is recommended to teach the tool posture vertically to the floor surface before starting the sensing, as shown in the figure above.
  - The direction parameter corresponds to one direction for the left-right sequence. The downward sequence direction is fixed in the `+z` direction relative to the tool.  
  - After bottom sensing, it is recommended to set the lift-up amount to at least 3mm for stable sensing. The size of the sensed gap may change depending on the lift-up amount.  

- Sensing Sequence
  - The sensing sequence proceeds as follows: upper left-right → middle return → bottom → bottom left-right → middle  

![](../../_assets/8_2_8.png)<br>
*Figure 8.2.8. Touch Sensing Sequence - Butt*   

#### [4] Single point

- Examples of Command
```python
  touchsen cnd=1, crd="tool", dir="+z", pose=P10
```  
  - Senses only in the specified single direction.
---

### (4) Sensing Direction Angle Transformation

Angle transformation of the sensing direction is supported in Fillet and Groove Detection types.
By specifying an angle for the sensing direction, you can change the direction of the search process.
In the command, the rotation parameter is entered as "X30", "Y-30", "TL20", etc.  

Angle specification rotates the entire search direction by the specified angle along one of the selected axes, either the TL axis or the orthogonal XYZ axes.
[FIgure 8.2.9] shows an example where the Fillet and Groove detection workpieces are rotated by 30 degrees along the Y-axis or TL axis.


![](../../_assets/8_2_9.png)<br>
*Figure 8.2.9. Example of Touch Sensing - Angle setting*       

- Examples of Command

```python
   touchsen cnd=1, crd="robot", dir=["+x","-z"], rotation="Y30", pose=P100
   touchsen cnd=1, crd="robot", dir=["+x","-z"], rotation="TL30", pose=P100
   touchsen cnd=2, crd="tool_prj", dir=["td","tf"], lift_up=5, rotation="Y-30", pose=P100
   touchsen cnd=2, crd="tool_prj", dir=["td","tf"], rotation="TL-30", pose=P100   # Detect Groove 
```

- The angle rotation axes that can be specified depending on the workpiece type and the sensing direction coordinate system designated in the command are as shown in the table below.

<center>

| Sensing Type	| Sensing Direction </br> Coordinate System	| Angle Specification Axis |
|:---:|:---:|:---:|
|Fillet	| All	| Orthogonal XYZ axes </br> TL axis |
|Detect Groove |	Tool (crd="tool") </br> Tool Projection (crd="tool_prj") |	Orthogonal XYZ axes </br> TL axis |

</center>


### (5) Master/Execution Mode in Touch Sensing

The master mode can be turned On/Off using the user key.
When touch sensing is performed with the master mode On, the master pose can be saved and used as a reference for teaching.  
During actual operation, the master mode is turned Off, and touch sensing is performed. In this case, the system automatically calculates the shift amount of the workpiece relative to the master pose based on the current sensing pose.  

In master mode, the sensed pose is saved in the variable specified by the `mpose` input parameter of the touch sensing command.
In execution mode (when master mode is OFF), the current sensed pose is compared with the pose sensed in master mode, and the shift amount is calculated.
The shift amount is then recorded in the variable specified by the `mshift` input parameter.


- Examples of Command
```python
   var P10=cpo()
   var sft_var1=Shift(0,0,0,0,0,0,"base")
   ....
   touchsen cnd=1, crd="robot", dir=["+x","-z"], mpose=P10, mshift=sft_var1
```  

- For example, in master mode, the sensed pose is saved in the `P10` pose variable, and in execution mode, when sensing is performed, the shift amount between the master mode pose and the current sensed pose is automatically calculated and stored in the sft_var1 variable.

[__SOURCE](8_Application_function/3_Arc_sensing/README.md)
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


[__SOURCE](8_Application_function/3_Arc_sensing/1_arcsen_concept.md)
# 8.3.1 Arc Sensing Overview

When weaving during arc welding, the distance between the torch and the base material changes.
This change in distance causes a variation in wire resistance, which in turn alters the current flowing.
In other words, by using the current change during the weaving section, the distance to be corrected in the left and right directions of the weaving plane can be calculated, allowing the seam to be tracked.

The height value at the welding start position is used as the reference, and the current value in the middle of the weaving section is used to correct the vertical direction during welding.
Or, instead of using the starting position current reference value, **the user can directly input a custom current value** as the reference for correction.


<!-- - 좌우 방향 보정 : 좌우 전류차 및 용접선 추출 알고리즘에 의해 로봇이 자동으로 용접선을 추종하여 이동합니다.
- 상하 방향 보정 : 용접 시작시 높이 (CTWD)를 기준으로하여 이 값을 계속 유지합니다.
                  만약 용접 도중 높이변화가 필요할 경우 job에 다음 명령어를 이용하여 사용자가 기준 전류값을 입력할 수 있습니다.  -->


```py
    move L, spd=30cm/min,accu=3,tool=0  # Entry step
    move L, spd=30cm/min,accu=3,tool=0  # Welding start step
    weaving on, cnd=1 # Set the 'Arc Sensing' function to 'Enable' in the [Property] window
    arc on, cnd=1
    move L, spd=30cm/min,accu=3,tool=0
    _weaving.height_sensing_reference_current=300 # Set the height reference value to 300A
    move L, spd=30cm/min,accu=3,tool=0
    weaving off
    arc off
    end
```  

![](../../_assets/8_3_1.png)<br>
*Figure 8.3.1. Arc Sensing Concept*

As shown in the figure, when the torch is tilted to the left or right, the current weavform changes, and this can be used to track the seam in the left and right directions.
Additionally, the current at the middle of the weaving section can be used to correct the vertical direction.


[__SOURCE](8_Application_function/3_Arc_sensing/2_arcsen_spec.md)
# 8.3.2 Arc Sensing Support Specifications


The Arc Sensing Seam Tracking does not support all welding applications.
For any issues beyond the ones listed below, please contact us for technical support.  

The specifications below are based on data obtained from extensive testing conducted by our company. 
(For conditions outside of the specified parameters, please contact us for verification tests based on the workpiece and usage conditions.)  


### (1) Welding Conditions
  - Welding Methods: CO2, MAG, MIG, FCAW  
  - Wire Diameter: 1.0 ~ 1.6 mm (Solid wire, Flux-cored wire)  
  - Maximum Welding Speed: Depending on the welder chaeracteristics (10 cm/min ~ 70 cm/min)
  - Welding Current: 160[A] ~ 600[A]  


### (2) Workpiece Conditions
  - Minimum Thickness: 2t or greater  
  - Maximum Tracking Performance: Determined by sensitivity settings and maximum correction distance per second  
     - When improving tracking performance, welding path vibrations may occur, so verification tests are required.  

### (3) Weaving Conditions  
  - Weaving Type: Single oscillation, L-type, Triangular
  - Frequency Range: 0.5 ~ 4.0 Hz(Single oscillation), 0.1 ~ 3.0 Hz(L-type, Triangular)
  - Amplitude Range: 1.0 X 1.0 mm or more(Single oscillation), 1.5 X 1.5 mm or more(L-type), 3.0 X 3.0 mm or more(Triangular)
  - Dwell Time: 0.0 ~ 2.0[sec]

{% hint style="info" %}
  Please check the communication specifications of the welding power source.
  The communication cycle for welding current and seam tracking data must be 10ms or less(e.g. EWM, Fronius).
  Arc Sensing guarantees weld seam tracking under stable welding conditions(when the current waveform is stable).
{% endhint %}

### (4) Interpolation Type
  - Linear Interpolation: Available
  - Circular Interpolation: Available
  - Positioner Synchronization (Linear): Available
  - Positioner Synchronization (Circular): Available

### (5) Joint Type
   - Fillet, V-groove  
   - Maximum Allowable Gap: Depends on weaving width

### (6) Other Functions
  - Sensing Trajectory Deviation Limiting Function
  - Torch Height Setting Function during Sensing

[__SOURCE](8_Application_function/3_Arc_sensing/3_1_arcsen_condition_general.md)
# 8.3.3.1 Arc Sensing Condition(General)


In the `Weaving` command, clickin on [Properties] opens the Weaving Condition Edit Screen.
The second tab of this window is where settings related to arc sensing during weaving can be configured, as shown below.  


![](../../_assets/8_3_2.png)<br>
*Figure 8.3.2. Arc Sensing Condition(General) Dialog Box*

The settings and operation methods for each item are as follows:  

### (1) Arc Sensing Activation: <Disable, Enable> 

This option allows you to set whether the arc sensing function is enabled or disabled.
When set to "Enabled", arc sensing tracking will be applied starting from the move command after "arc on" and "weaving" have been executed.


### (2) Sensing Type Selection: <Welding Seam, Current Difference, Current Difference + Gap, Welding Seam Estimation & Current Difference>  

<br/>

```For ${cont_model}, it is recommended to use "Welding Seam Estimation & Current Difference."```<br/>
The options for Welding Seam, Current Difference, and Current Difference + Gap are the same as for Hi5a, so please refer to the Hi5a controller manual.


### (3) Left/Right Sensing Sensitivity: [0 ~ 10]

This setting adjusts the sensitivity for left and right sensing on the weaving plane.<br>
The default value is 5, which changes the strength of the left/right sensing.<br>
```When performing delay time calibration, set this to -1.```

{% hint style="info" %}
  During arc sensing, executing the system variable `weavings_.side_sensing_sensitivity=0` will disable tracking. To enable tracking agian, set this value to a positive number.
{% endhint %}


### (4) Left/Right Sensing Start Cycle: [0 ~ 9]

This setting determines the cycle at which left/right sensing will begin on the weaving plane.<br>
```For stable operation, set it to 4 or higher.```


### (5) Height (Up/Down) Sensing Sensitivity: [0 ~ 10]

This setting adjusts the sensitivity for up and down sensing on the weaving plane.<br>
The default value is 5, which changes the strength of the up/down sensing.<br>
```When performing delay time calibration, set this to -1.```

{% hint style="info" %}
  During arc sensing, executing the system variable `weavings_.height_sensing_sensitivity=0` will disable tracking. To enable tracking agian, set this value to a positive number.
{% endhint %}


### (6) Height (Up/Down) Sensing Start Cycle: [Left/Right Start Cycle +1 ~ 10]

This setting determines the cycle at which up/down sensing will begin on the weaving plane.<br>
```For stable operation, set it to 4 or higher.```


### (7) Hight (Up/Down) Sensing Reference Current: [0 ~ 1000]

This setting determines the reference current for up/down sensing. <br>
The torch height during arc sensing welding wire tracking is based on this setting.<br>
```When set to 0, the average value of the initial section current will be used as the reference. (If there is a tack weld at the start of the weld, be cautious as an unintended high initial current may be used as the reference.) ```

{% hint style="info" %}
  When `weavings_.height_sensing_reference_current=200` is executed immediately after `weaving on` and `arc on`, tracking will be maintained while keeping a height of 200A.
{% endhint %}


### (8) Real-Time Gap Sensing Sensitivity: [0(disabled) ~ 10]

<!-- This function automatically adjusts welding speed and weaving based on the gap. When not in use, set it to 0. <br>
When enabled, this setting adjusts the sensitivity of the width variation. The value should be set according to bead quality and the degree of width variation. -->

Set to 0. (Not Supported)


### (9) Real-Time Gap Sensing Resolution: [ ]  

### (10) Real-Time Sensing Gap: [ ]  

### (11) Real-Time Gap Sensing Speed: [ ]  


[__SOURCE](8_Application_function/3_Arc_sensing/3_2_arcsen_condition_advanced.md)
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

[__SOURCE](8_Application_function/3_Arc_sensing/3_3_arcsen_calibration.md)
# 8.3.3.3 Arc Sensing Calibration

To use the arc sensing function, a calibration process must be completed first.  
This process calculates the delay time to synchronize the weaving cycle and the current data cycle.

{% hint style="info" %}
  Arc sensing is dependent on welder settings, including welding mdoe, operation mode, Job/Prog number, and synergic code, and thus has a corresponding delay time.<br>
  Up to 3 calibration data sets can be stored.<br>
  Example: When the settings are Pulse, Synergic 185, Job 0 (disabled), the corresponding calibration information will be loaded and used during arc sensing.
{% endhint %}

### Calibration Process

<br>

#### Preparation: Prepare a flat specimen for bead-on-plate welding.

#### Step 1.  

Enter the `[Property]` window of the weaving command and set the wall direction to vertical.

#### Step 2.  

Enter the Arc Sensing (General) in the property window of the weaving command, set the type to "Welding Seam Estimation & Current Difference", and set both the left/right and up/down sensitivities to -1.  


![](../../_assets/8_3_5.png)<br>
*Figure 8.3.5. Arc Sensing Calibration*
<br>


#### Step 3. 

Create an entry step to approach from the opposite direction of the virtual wall as shown in the figure above, and teach the starting and ending points with a 60 cm gap between them.  
In this case, keep the torch working angle (Roll angle) consistent within the range of 30 to 45 degrees.

#### Step 4.  

Perform the actual arc welding in automatic mode.  

#### Step 5.  

Navigate to the delay time table tab in the property window of the weaving command. <br>
Click on the "Auto Calib" option at the bottom left to check the currently calibrated delay time.

#### Step 6.  

Enter the corresponding value into the field for the current weaving frequency (the frequency applied during calibrations).

#### Step 7.  

Repeat Steps 2 through 5 for frequencies ranging from 0.5 Hz ~ 3.0 Hz.  

<br>

After completing this process, you can check the arc sensing (delay table tracking gain) results on the forth tab of the weaving condition editing screen.


![](../../_assets/8_3_6.png)<br>
*Figure 8.3.6. Arc Sensing Condition Tab(Tracking gain) Dialog Box*
<br>


At this time, the delay time value represents the degree of current lead or lag.

![](../../_assets/8_3_6-2.png)<br>
*Figure 8.3.6-2. Meaning of Arc Sensing Delay Time*
<br>


{% hint style="info" %}
  The delay time must be within the range of **-40 ~ +40**. The vertical and horizontal tracking gains (mm/A) are recommended to be set within the range of **0.2 ~ 0.5**.
{% endhint %}

{% hint style="info" %}
  Once all weaving operations from from 0.5 Hz to 3.0 Hz have been performed, navigate to the "Auto Calib" option at the bottom left of the delay time table tab in the weaving command property window, and click "Apply" to apply all settings in bulk.
{% endhint %}

Once the calibration process is completed, change the sensing sensitivity for both vertical/horizontal directions to 5 to enable the arc sensing function.


[__SOURCE](8_Application_function/3_Arc_sensing/4_arcsen_command.md)
# 8.3.4 Setting Weaving and Arc Sensing Conditions Using Commands

### (1) Necessity of Functionality

Weaving and arc sensing conditions cannot be automatically adjusted during operation. <br>
Therefore, the conditions can be modified using commands, and the changes will only be effective within the specific weaving section.  


### (2) Method of Using Commands  

To insert the command, enter `[F6: cmd input] - var_io - assignment` while in manual mode. Then, move the cursor to the left variable and select `[F3: System Variables] - arcweld - _weaving.{parameter}`, where you can input the desired value.  <br>

The entered command will appear in the following format:  
```e.g. _weaving.frequency=2.0```  


- Example)
```py
    weaving on, cnd=1	                # Weaving Command (cmd)
    arcon cnd=1
    move L,S=5mm/s,accu=1,tool=2
    _weaving.right_distance = 4	        # Set the wall direction dist using a cmd
    _weaving.left_distance = 3	        # Set the wall direction dist using a cmd
    MOVE L,S=5mm/s,A=1,T=2	            # parameter will be modified starting from this section
```

The input values for each command are restricted within the range of condition settings defined in the condition file.  
For parameters that are not explicitly specified by the command, the conditions set in the weaving command will be used.  

The applicability of the settings for each element of _weaving to the functionality is as follows:  

<br>

| Variable Name | Immediately after Weaving Cmd | Weaving without Arc sensing | Weaving with Arc sensing | Continuous Change of Welding Conditions |
|-------|-------|-------|-------|-------|
| weave | O | O | O | O |
| frequency | O | O | O | O |
| left_distance | O | O | O | O |
| right_distance | O | O | O | O |
| angle | O | O | O | O |
| wall_direction | O | O | O | O |
| offset_angle | O | O | O | O |
| forward_angle | O | O | O | O |
| boundary_limit | O | O | O | O |
| segment_time_1 | O | O | O | O |
| segment_delay_1 | O | O | O | O |
| height_sensing_mode | O | - | O | O |
| side_sensing_sensitivity | O | - | O | O |
| height_sensing_sensitivity | O | - | O | O |
| BaseCur | O | - | O | O |
| StickOut | O | - | O | O |
| asymetric_sensing_ratio | O | - | O | O |


<!-- ### (3) 위빙 파라미터 명령어 종류 및 내용은 다음 링크를 참고해주세요.

[로봇언어 HRScript_weaving문](https://hrbook-hrc.web.app/#/view/doc-hrscript/ko/10-etc/3-sysvar/_weaving)   -->



<!-- 
(2)에서 설명한 각 파라미터 종류와 설명은 

weave: 위빙 패턴

frequency: 위빙 주파수

left_distance: 벽방향 거리

right_distance: 타방향 거리

angle: 기본패턴의 각도

wall_direction: 기본패턴의 벽방향

forward_angle: 진행각도

boundary_limit: 경계제한 사용 여부

segment_time_1: 이동시간 사용 시 각 구간의 시간

Dwesegment_delay_1: 이동시간 사용 시 위빙만 정지하는 시간

height_sensing_mode: 아크 센싱 중 상하센싱 실행방법

side_sensing_sensitivity: 좌우방향 아크 센싱 민감도

height_sensing_sensitivity: 상하방향 아크 센싱 민감도

BaseCur: 상하센싱 기준전류

이 값을 설정하여 토치와 모재간 거리를 설정할 수 있습니다. 
토치와 모재의 거리를 더 멀리 하려면 이 값을 낮추십시오. 
반대로 토치와 모재를 가까이 하려면 이 값을 높이십시오.

StickOut: 아크 센싱 중 상하방향으로 토치를 이동시키기 위한 값. 입력된 mm만큼 토치 높이가 변경됩니다. +값 입력 시 토치와 모재간 거리가 멀어지고 -값 입력 시 토치가 모재와 가까워 집니다.

asymetric_sensing_ratio: 좌우 비대칭 센싱 비율

 -->

[__SOURCE](8_Application_function/3_Arc_sensing/5_arcsen_monitoring.md)
# 8.3.5 Arc Sensing Monitoring

### (1) Monitoring Execution

By accessing `[pane layout] - select - arc sensing`, the Arc Sensing Monitoring window will be activated.
This feature is only available when the Arc Sensing license is valid.


### (2)	Explanation of Monitoring Items

![](../../_assets/8_3_7.png)<br>
*Figure 8.3.7 Arc Sensing Monitoring*

- Left/Right Tracking: Displays the left and right distance to be corrected, calculated based on the tracking speed, distance, and current diffrential in the left-right direction by sensing.

- Up/Down Tracking: Displays the up and down distance to be corrected, calculated based on the tracking speed, distance, and welding seam in the up-down direction by sensing.

- XYZ Tracking: Displays the distance tracked so far compared to the original trajectory, in terms of the Base coordinate system's X, Y, and Z directions.


<!-- 센싱 데이터

- BC: 상하방향 센싱 기준 전류
- CC: 상하방향 센싱 용 현재 구간의 중앙 부분 전류.
- LR: 현재 구간의 위빙 끝 영역 전류
- WC: 용접기의 용접 전류
- Mode: 현재 적용 중인 지연시간, 모드 번호

상하방향 기준전류는 사용자가 입력하거나 용접 시작 영역에서 중앙 부분 전류를 일정 구간 동안 평균한 값으로 설정합니다.
상하방향의 센싱은 기준전류와 현재 측정 전류를 차이를 이용하여 보정할 상하방향 거리를 계산합니다. 따라서 기준 전류를 높이면 토치와 모재가 가까워지고 기준 전류를 낮추면 토치와 모재가 멀어집니다.

위빙 데이터: 현재 위빙폭, 위빙 주파수, 지연시간, 모드 번호를 표시합니다.

멀티패스: 저장된 멀티패스 데이터의 현재/전체 카운트, 시프트 거리, 각도를 표시합니다. -->


[__SOURCE](8_Application_function/3_Arc_sensing/6_multipass_overview.md)
# 8.3.6 Multi-pass Overview

The multi-pass welding feature is used when the required weld length in thick plate arc welding is too wide to be completed in a single pass, or when the volume to be filled by welding is too large, requiring multiple welding passes.  

Due to the inherent characteristics of arc sensing, the sensing may be unstable except for the root pass, which is the first layer.
Therefore, only the root pass is tracked using arc sensing.
The trajectory of this pass is tehn saved, and the stored trajectory is shifted to create passes for the second layer and beyond.  

Since the position of the multi-pass work program is the same as that of the root pass trajectory, it is easy to perform multi-pass welding by simply copying the root pass work program and inserting the multi-pass command.


![](../../_assets/8_3_8.png)<br>
*Figure 8.3.8 Root Pass Arc sensing (left) and Multi-pass welding for 2-3 layers*

![](../../_assets/8_3_9.png)<br>
*Figure 8.3.9 Actual Multi-Pass Welding*

When creating multi-pass beads in a stacked, inclined configuration as shown in Figure 2 above, welding can be performed by modifying only the start and end points of the weld and slightly shifting them.  
This will result in a stacked configuration as shown below.


![](../../_assets/8_3_10.png)<br>
*Figure 8.3.10 Multi-pass Stacked Shape with Inclination*
[__SOURCE](8_Application_function/3_Arc_sensing/7_multipass_command.md)
# 8.3.7 Multi-pass Command


### (1) Command

The sensing trajectory can be saved and loaded using the multipass command. 
This command can be used in three different forms:
<br>

```py
    multipass save, trj=<multi-pass trajectory number>, period=<trajectory saving interval distance>
    multipass load, trj=<multi-pass trajectory number>, side=<left-right Shift distance>, height=<up-down Shift distance>, reverse=<multi-pass playback direction>, tas=<torch forward/backward angle shift>, was=<torch left/right angle shift>
    multipass off
```

### (2) Multi-pass Parameters

For detailed information on the multi-pass command parameters, please refer to the following link: <br>
[2.11 multipass](../../2_Command/11_multipass.md)

<br>

This section will explain only the following two items:  


- Left-Right/Up-Down Shift

This sets the distance by which the trajectory is shifted from the original path during multipass reproduction.
Since the torch weaving is perpendicular to the tool, each shift is set as follows:
the left/right direction becomes the weaving plane, and the up/down direction becomes the plane perpendicular to the weaving plane.

![](../../_assets/8_3_11.png)<br>
*Figure 8.3.11 Multipass Shift Direction*


- Angle Shift: TAS, WAS  

When performing multi-pass welding, the torch must be tilted for quality control. This setting is used to define the required tilt.
The concept of angles for each item is illusatrated in the following figures:  

![](../../_assets/8_3_12.png)<br>
*Figure 8.3.12 Multipass Angle Shift Concept*

[__SOURCE](8_Application_function/3_Arc_sensing/8_example_fillet.md)
# 8.3.8 Fillet Welding Example Using Touch Sensing and Arc Sensing

In general, the Arc Sensing function is used together with the touch sensing function. Touch sensing is used to accurately detect the welding start and end positions, while arc sensing is used to determine the correct welding direciton during movement after welding has started.  

The first example demonstrates a basic fillet welding operation.

The work sequence is as follows:

1) Set the weaving conditions, arc sensing conditions, and welding conditions.  
2) Use touch sensing to search for the welding start position.
3) Move to a position near the welding end area, and then use touch sensing to search for the welding end position.
4) Perform the welding operation from the welding start position using the weaving command and the arc welding command.


![](../../_assets/8_3_13.png)<br>
*Figure 8.3.13 Fillet Touch Sensing and Arc Sensing*


The example program is shown below.

~~~~~~~Arc sensing program : 0001.JOB~~~~~~~~~~~~~~~ 
' Arc sensing program  
S1   move P,spd=60%,accu=3,tool=1              ' 1: Motion start point  
S2   move L,spd=30%,accu=3,tool=1              ' 2: Touch sensing position for welding end point  
     var p10=cpo()  
     var p1=cpo()  
     touchsen cnd=1,crd="robot", dir=["x","-z"], pose=p10   ' 3: Touch sensing for welding end point. Position stored in P10  
S3   move L,spd=30%,accu=3,tool=1              ' 4: Touch sensing position for welding start point  
     touchsen cnd=1,crd="robot",dir=["-x","-z"], pose=p1    ' 5: Touch sensing for welding start point. Position stored in P1  
S4   move L,p1,spd=20%,accu=3,tool=1            ' 6: Move to welding start point  
     weaving on, cnd=1                          ' 7: Start weaving and arc sensing  
     arcon cnd=1                                ' 8: Start welding  
S5   move L,p10,spd=60cm/min,accu=3,tool=1      ' 9: Move to welding end point  
     arcoff                                     '10: End welding  
     weaving off                                '11: End weaving and arc sensing  
S6   move P,spd=60%,accu=3,tool=1               '12: Motion end point  
     END  
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

[__SOURCE](8_Application_function/3_Arc_sensing/9_example_butt_gap.md)
# 8.3.9 Arc Sensing Example : Automatic Weaving Width Setting Using Touch Sensing


Create a single job program that can be applied to both workpieces shown below.

![](../../_assets/8_3_14.png)<br>
*Figure 8.3.14 Butt Joint Workpieces for Touch Sensing and Arc Sensing*

Assumed Operating Conditions  

- A process that welds the joint between two workpieces, 180° planar weaving, 
- Welding travel direction: X+. Touch sensing is performed left and right along the Y direction.
- Arc Sensing parameter settings are assumed to have been completed in advance.
- When the gap is 4.0 mm, the welding speed is 7.0mm/sec
- When the gap is 8.0 mm, the welding speed is 3.5mm/sec

The work sequence is as follows:

1) Using the touch sensing command, measure the weld center position and the gap distance at **the end point** of the butt joint.
2) Using the touch sensing command, measure the weld center position and the gap distance at **the start point** of the butt joint.
3) Check whether the gap_var value is within the allowable range. Stop the robot if the gap is outside 2.0 mm to 10.0 mm.
4) Set half of the measured gap distance as the weaving offset for each side: left (wall side) and right (opposite side).
5) Calculate the welding speed by interpolation using the speeds at 4.0 mm and 8.0 mm gap. If the gap is less than 4.0 mm, apply a fixed speed of 7.0 mm/s. If the gap exceeds 8.0 mm, apply a fixed speed of 4.0 mm/s.
6) Automatically apply the calculated weaving width and welding travel speed, and then perform the welding operation.
7) After completing the operation, return to the original start position.


![](../../_assets/8_3_15.png)<br>
*Figure 8.3.15 Butt Joint Touch Sensing and Arc Sensing*

The example program is shown below.

~~~~~~~Arc sensing program: 0002.JOB~~~~~~~~~~~~~~~ 
     ' Butt joint arc sensing program 
     ' Condition No. 1: start condition, Condition No. 10: end condition
S1   move P,spd=60%,accu=3,tool=1              ' 1: Motion start point  
S2   move L,spd=30%,accu=3,tool=1              ' 2: Touch sensing position for welding end point  
     var p10=cpo()  
     var p1=cpo()  
     var gap_var1=0  
     var gap_var11=0  
     touchsen cnd=2,crd="tool",dir="+ty",lift_up=5,pose=p10,gap=gap_var11  
                                                ' 3: Touch sensing for welding end point. Position stored in P10  
S3   move L,spd=30%,accu=3,tool=1              ' 4: Touch sensing position for welding start point  
     touchsen cnd=3,crd="+ty",lift_up=5,pose=p1,gap=gap_var1  
                                                ' 5: Touch sensing for welding start point. Position stored in P1  

     ' Calculate welding speed and weaving width according to gap at the start point  
     var V3=0  
     IF gap_var1<2.0 OR gap_var1>10.0 THEN      ' Gap out of allowable range  
     GOTO *Error  
     ELSEIF gap_var1<4.0 THEN                   ' If gap ≤ 4 mm, fix speed to 7 mm/s  
     V3=7.0                                     ' Welding speed at start  
     ELSEIF gap_var1>8.0 THEN                   ' If gap ≥ 8 mm, fix speed to 4 mm/s  
     V3=4.0                                     ' Welding speed at start  
     ELSE                                       ' Linear interpolation for gap range 4-8 mm  
     V3=(7-3.5)/(4-8)*gap_var1+10.5             ' Linearly interpolated welding speed at start  
     ENDIF  

     var V4=gap_var1/2.0                        ' Left-side weaving width (half of gap)  
     var V5=gap_var1/2.0                        ' Right-side weaving width (half of gap)  

     '--------------------------------------------------------  
     ' Calculate welding speed and weaving width according to gap at the end point  
     var V13=0  
     IF gap_var11<2.0 OR gap_var11>10.0 THEN    ' Gap out of allowable range  
     GOTO *Error  
     ELSEIF gap_var11<4.0 THEN                  ' If gap ≤ 4 mm, fix speed to 7 mm/s  
     V13=7.0                                    ' Welding speed at end  
     ELSEIF gap_var11>8.0 THEN                  ' If gap ≥ 8 mm, fix speed to 4 mm/s  
     V13=4.0                                    ' Welding speed at end  
     ELSE                                       ' Linear interpolation for gap range 4-8 mm  
     V13=(7-3.5)/(4-8)*gap_var11+10.5           ' Linearly interpolated welding speed at end  
     ENDIF  

     var V14=gap_var11/2.0                      ' Left-side weaving width  
     var V15=gap_var11/2.0                      ' Right-side weaving width  

     '---------------------------------------------------------  
S4   move L,1,S=20%,A=3,T=1                     ' 6: Move to welding start point  
     weaving on, cnd=2                          ' 7: Start weaving and arc sensing  
     arcon cnd=2                                ' 8: Start welding  
     arc_cond L,spd=V3,ld=V4,rd=V5,freq=2       ' 9: Continuous change of welding parameters (start)  

S5   move L,p10,spd=60cm/min,accu=3,tool=1      '10: Move to welding end point  
     arc_cond L,spd=V13,ld=V14,rd=V15,freq=2    '11: Continuous change of welding parameters (end)  
     arcoff                                     '12: End welding  
     weaving off                                '13: End weaving and arc sensing  

S6   move P,spd=60%,accu=3,tool=1               '14: Motion end point  
     END  

     *Error                                     '15: Escape routine when gap is out of range  
     DO200=1                                   '16: Output signal to indicate error  
     STOP                                      '17: Stop robot  
     END  
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

[__SOURCE](8_Application_function/4_Height_sensing/README.md)
# 8.4 Height Sensing


This function is used in cases where the robot tool needs to maintain a constant distance from the workpiece, such as TIG welding. In TIG welding, the height is proportional to the arc length, which is why this function is called Arc Voltage Control(AVC). The distance from the workpiece is adjusted by the analog voltage input from the sensor, a correction parameter for the Arc length detected by the welder, and the welding current or voltage values.

<!-- 본 기능의 사용을 위해서는 센싱 기능을 위한 데이터 입력 설정을 '유효'로 선택해야 합니다.
센싱 기능을 위한 데이터 입력 설정의 세부 내용은 '1.3 Arc 용접 응용 조건 설정'을 참고하여 주십시오.  -- ???? -->

Once the setup for the sensing function input data is complete, the height sensing function can be used through the following procedure.

### (1) Command

To start height sensing, use the command `height on, cnd=1`.
The command is followed by the condition number. There are a total of 8 height sensing conditions.
To stop height sensing, use the command `height off`.
The stop command does not require any additional arguments.

An example of a job program with height sensing commands is as follows:

```python
    S1   move L,spd=100%,accu=1,tool=0
    S2   move L,spd=20%,accu=1,tool=0
    S3   move L,spd=100mm/s,accu=1,tool=0
         heightsen on, cnd=1		  # Start height sensing
         arcon cnd=2		       # Start Arc welding
    S4   move L,spd=10mm/s,accu=1,tool=0
         arcoff			       # End Arc welding
         heigghtsen off			  # End height sensing
    S5   move L,spd=20%,accu=1,tool=0
         END 
```

### (2) Height Sensing Function Operation Sequence

Height sensing begins after the ```arcon``` command is executed. Since the current and voltage are typically unstable at the start of welding, the input data is ignored until they stabilize.
Once the input data stabilizes, the average is calculated based on the method of setting the reference data. If the user manually enters the reference data, height sensing is performed immediately.  

The opration sequence of height sensing is as follows:

<p align="center">
  <img src="../../_assets/8_4_1.png" width="50%"></img>
  <em><p align="center">Figure 8.4.1. Height Sensing Function Operation Sequence</p></em>
</p>


[__SOURCE](8_Application_function/4_Height_sensing/1_hsen_condition.md)
# 8.4.1 Height Sensing Condition


Press the **[Property]** key in the `heightsen` command to access the "Heigth Sensing Condition" settings screen. The condition settings screen is shown below.
 
![](../../_assets/8_4_2.png)<br>
*Figure 8.4.2. Height Sensing Condition Dialog Box*

---

Each item's settings and operations are as follows:

### (1) Condition Number: [1 ~ 8]

Set the height sensing condition number.


### (2) Type of Input Data

Displays the type of input data. For GMAW, welding current is used, while for TIG welding, welding voltage is used.


### (3) Reference Data Setting: <Average Input Data, User Input Data>

Choose the method for setting the reference data.
- Average Input Data : Set the reference data based on the average value of the sensing initial reference data.
- User Input Data : Allow the user to directly enter the reference data.


### (4) Input Data Ignore Time: [0.0 ~ 5.0]

The time to ignore signals during the unstable initial welding state.
If setting reference data with "Average Input Data", this time is used to calculate the reference value using the average over the specified time.
If using "User Input data", height sensing begins immediately.


### (5) Input Data Average Time: [0.5 ~ 10.0]

Set the time to average the input data to calculate the sensing reference data.
This item appears when "Average Input Data" is selected for the reference data setting method.
(if the accurate reference height is not yet determined)


### (6) Reference Data Setting: [-500.0 ~ 500.0]

This is the item where the user directly enters the height sensing reference value. This item appears when "User Input Data" is selected for setting the reference data.


### (7) Sensing Coefficient: [-100.0 ~ 100.0]

This is the distance coefficient corresponding to the difference in the input data. A smaller value results in smoother tracking with less responsiveness to input data, while a larger value increases tracking speed but may cause oscillations along the trajectory.


### (8) Tracking Speed Limit: [0.1 ~ 10.0]

This sets the maximum tracking value per second based on sensing. A smaller value results in smoother tracking, while a larger value speeds up tracking.


<!-- ### (10) 노이즈 민감도  
    입력 데이터의 노이즈에 대한 민감도를 설정합니다. 비활성화 되어 있는 경우 지원하지 않는 버전입니다. -->

### (9) Tracking Limit Distance: [-300.0 ~ 0.0] ~ [0.0 ~ 200.0]

This sets the total tracking distance limit for height sensing.


### (10) Integral Coefficient for Error: [0.00 ~ 10.00]

This sets the correction amount for continuous error values in height sensing performance.
Setting a value greater than 0 improves tracking performance, but if the value is too large, oscillations in the trajectory may occur.
Start with a very small value and gradually adjust it to an appropriate setting for the field.


<!-- 
### (12) 초기 기준 데이터: [-500.0 ~ 500.0]
    용접 초반에 별도의 기준 데이터를 적용하려고 할 때 설정합니다. 입력 데이터 무시 시간이 지난 후 '초기설정된 시기준 데이터 적용 시간'에서 설정된 시간동안 이 기준 데이터를 이용하여 높이 센싱이 수행됩니다.

### (13) 초기 기준 데이터 적용 시간: [0.0 ~ 10.0]  
    초기 기준 데이터로 높이 센싱을 수행할 시간을 설정합니다. 이 시간이 지난 후에는 '기준 데이터 설정' 항목에서 입력한 데이터로 높이센싱이 수행됩니다.

### (14) 입력 데이터 평균 시간: [0.5 ~ 10.0]  
    기준데이터 설정방법이 Average input data(입력데이터 평균)인 경우 표시되는 항목입니다. 입력 무시시간이 지난 후 기준데이터 계산을 위해 입력데이터를 평균하는 시간입니다.

### (15) 기준 데이터 설정: [-500 ~ 500]  
    기준데이터 설정방법이 User input data(사용자 입력데이터)인 경우 표시되는 항목입니다. 입력 무시시간이 지난 후 기준데이터 계산을 위해 입력데이터를 평균하는 시간입니다.

### (16) 높이 센싱 계수: [-100.0 ~ 100.0]  
    데이터 추종량을 계산하는데 사용하는 센싱 계수를 설정합니다. 이 값이 크면 보정할 거리가 증가하므로 추종 속도가 증가하고 진동이 발생할 수 있습니다. 이 값이 작으면 추종 속도가 감소하지만 진동이 작아집니다. 
    이 값이 0으로 설정되면 높이센싱기능이 동작하지만 위치추종은 수행하지 않고 데이터만 입력 받습니다. 센싱을 위한 기준데이터를 얻기 위한 경우 사용하십시오.

### (17) 센싱에 의한 추종속도 제한치: [0.001 ~ 5.0]  
    초당 추종 거리 제한치를 설정합니다. 이 값은 로봇의 급격한 추종을 제한하기 위하여 설정합니다. 이 값이 크면 추종 속도가 증가하고 진동이 발생할 수 있습니다. 이 값이 작으면 로봇의 추종가능 거리가 감소하지만 진동이 작아집니다. 

### (18) 높이 센싱 범위: [-300.0 ~ 0.0], [0.0 ~ 200.0]  
    높이센싱의 총 추종거리 제한치를 설정합니다. -->

[__SOURCE](8_Application_function/5_LVS_tracking/README.md)
# 8.5 LVS(Laser Vision Sensor) Seam Finding and Tracking

[__SOURCE](8_Application_function/5_LVS_tracking/1_overall.md)
# 8.5.1 LVS Overview and Specifications

{% hint style="info" %}
This feature is available during from version 60.30-03.
{% endhint %}

This function performs real-time compensation for workpiece and jig errors by recognize the welding seam using an LVS(Laser Vision Sensor), thereby enabling seam tracking during welding.

The LVS must be directly connected to the robot's flange. The sensor detects the welding seam, and the robot's tool tracks the seam in real-time.

In other words, through seam tracking, welding can still be performed even if the position of the welding target changes and deviates from the original reference points.


![](../../_assets/8_5_1.png)<br>
*Figure 8.5.1. LVS Seam Tracking Flowchart*

</br>

#### Command

The LVS Seam Finding and Tracking function is executed through the `lvs` command, which can be entered by selecting `[F6: cmd. input] - arcweld - lvs` in the TP.

The structure of the command is as follows:

```python
lvs <function argument> cnd=<condition Number>, seam=<profile number to be sensed position>, sp=<pose variable of the sensed position>, mp=<pose variable of the master reference>, ms=<shift variable of the current sensing position relative to the master>, find_flag=<flag variable>
```

<table>
  <thead>
    <tr>
      <th>Major Category</th>
      <th>Sub Category</th>
      <th>Meaning</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="9">function argument</td>
    </tr>
    <tr>
      <td style="text-align:left">laser_on</td>
      <td style="text-align:left">Turn on the laser.</td>
    </tr>
    <tr>
      <td style="text-align:left">laser_off</td>
      <td style="text-align:left">Turn off the laser.</td>
    </tr>
    <tr>
      <td style="text-align:left">seam_find</td>
      <td style="text-align:left">
        The seam position of the laser currently being sensed by the sensor is stored in the pose variable specified by the 'sp' argument of the command (robot/base coordinate system). <br>
        Note that the orientation(RX, RY, RZ) is recorded as the tool's orientation at the time the command is executed.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">seam_find_p</td>
      <td style="text-align:left">
        The seam position of the laser currently being sensed by the sensor is stored in the pose variable specified by the 'sp' argument of the command (robot/base coordinate system). <br>
        Note that the orientation(RX, RY, RZ) remains as the original pose variable, and only the X, Y, and Z values are updated. <br>
        This is particularly useful when using functions such as 'intersection', where the intersection point is determined using three points to calculate the pose.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">auto_calib</td>
      <td style="text-align:left">
        Performs auto-calibration between TCP and LVS.(refer to <a href="https://hrbook-hrc.web.app/#/view/doc-arc-weld/en/8_Application_function/5_LVS_tracking/3_calibration?cont_model=${cont_model}">LVS Calibration</a>)
      </td>
    </tr>
    <tr>
      <td style="text-align:left">search</td>
      <td style="text-align:left">
        The starting point is found while moving in the +ToolX, -ToolX directions, and tracking preparation is performed. <br>
        The detected starting point is stored in the pose variable specified by the 'sp' argument of the command.
        (refer to <a href="https://hrbook-hrc.web.app/#/view/doc-arc-weld/en/8_Application_function/5_LVS_tracking/6_search?cont_model=${cont_model}">LVS search func.</a>)
      </td>
    </tr>
    <tr>
      <td style="text-align:left">step_search</td>
      <td style="text-align:left">
        The starting point or the start point of a multi-bead is found while moving int the +ToolX, -ToolX directions. <br>
        The detected starting point is stored in the pose variable specified by the 'sp' argument of the command.
        (refer to <a href="https://hrbook-hrc.web.app/#/view/doc-arc-weld/en/8_Application_function/5_LVS_tracking/6_search?cont_model=${cont_model}">LVS search func.</a>)
      </td>
    </tr>
    <tr>
      <td style="text-align:left">check_seam</td>
      <td style="text-align:left">Saves the pose recognized for the distance [mm] set in opt while moving in the +ToolX and -ToolX directions to sp.(<a href="https://hrbook-hrc.web.app/#/view/doc-arc-weld/ko/8_Application_function/5_LVS_tracking/7_tracking_monitoring?cont_model=${cont_model}">8.5.6 LVS tracking func.</a>)</td>
    </tr>
    <tr>
      <td style="text-align:left">track</td>
      <td style="text-align:left">
        After the search is completed, the 'arcon' and 'weaving on' actions must be performed before executing. <br>
        Tracking continues until 'arcoff' is encountered.
      </td>
    </tr>
    <tr>
      <td colspan="2">condition Number</td>
      <td>
        This is the condition number used to apply the the settings configured in the peroperties window of the lvs command. <br>
        The properties window allows you to set search speed, search distance, queue interval, tracking limit, and sensing coordinate system(robot/base), among others.
      </td>
    </tr>
  <tr>
      <td colspan="2">profile number to be sensed position</td>
      <td>
        This refers to the number corresponding to the sensing shape and sensing conditions registered by the user in the LVS controller. 
        When the command is executed, the LVS controller loads the sensing shape and conditions associated with this number.
      </td>
    </tr>
    <tr>
      <td colspan="2">pose variable of the sensed position</td>
      <td>
        The position corresponding to the current laser location is stored as a pose variable.
        During the execution of the track command, the position where the laser reaches the final welding location is stored as a pose variable.
      </td>
    </tr>
    <tr>
      <td colspan="2">pose variable of the master position</td>
      <td>
        This is the reference pose variable registered in master mode.
        (refer to <a href="https://hrbook-hrc.web.app/#/view/doc-arc-weld/en/8_Application_function/5_LVS_tracking/5_lvs_master_mode?cont_model=${cont_model}">8.5.5 LVS Master mode func.</a>)
      </td>
    </tr>
    <tr>
      <td colspan="2">shift variable of the current sensing position relative to the master</td>
      <td>
        The shift of the current sensed position relative to the mp(master pose) is stored.
        (refer to <a href="https://hrbook-hrc.web.app/#/view/doc-arc-weld/en/8_Application_function/5_LVS_tracking/5_lvs_master_mode?cont_model=${cont_model}">8.5.5 LVS Master mode func.</a>)
      </td>
    </tr>
    <tr>
      <td colspan="2">opt</td>
      <td>
        When using the auto_calib command, this value should be set to 0.
        For Scansonic Full-V LVS, specifying 20 performs precise automatic calibration.
      </td>
    </tr>
    <tr>
      <td colspan="2">find_flag</td>
      <td>
        Specifying a variable for this parameter means the following:
        1. Search
         1 on success, 0 on failure; a warning is generated upon failure, and the lvs step is marked as completed.
        2. Seam Finding
         1 on success, 0 on failure; the lvs step is marked as completed upon failure.
        3. Check seam
         It is set to 1 when tracking starts and progresses by 5mm or more. It is set to 0 if error E32702 occurs, which happens when the LVS fails to recognize a seam beyond a certain section during tracking. (Available upon restart by Job)
        4. Tracking
         The currently tracked step number is saved. This is useful when configuring a restart as a Job.
      </td>
    </tr>
  </tbody>
</table>  


The tracking function using the ```lvs``` command can be used as follows:


![](../../_assets/8_5_2.png)<br>
*Figure 8.5.2. Teaching Method for LVS Seam Tracking*


---

#### LVS Function Specifications

* General motion tracking functionality supported (Linear L interpolation, Circular C interpolation, and composite linear and circular segments)
* Weaving tracking functionality supported (0.5Hz ~ 3Hz)
* Positioner synchronized tracking functionality supported (SMOV segment)
* Positioner synchronized + Weaving tracking functionality supported (0.5Hz ~ 3Hz)


<table>
  <thead>
    <tr>
      <th style="text-align:left">Item</th>
      <th style="text-align:left">LVS Manufacturer</th>
      <th style="text-align:left">Repetition Accuracy</th>
      <th style="text-align:left">Repetition Precision</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left" rowspan="3">seam_find / seam_find_p</td>
      <td style="text-align:left">SCANSONIC (350, 150, 150 advanced)</td>
      <td style="text-align:left">Left/Right : 0.1 mm (Reference +- 30mm height),  0.4mm<br>Height : 0.4mm (Reference +- 30mm height), 2mm<br>Front/Back : 0.4mm (Reference +- 30mm height), 1.5mm</td>
      <td style="text-align:left">0.05 mm</td>
    </tr>
    <tr>
      <td style="text-align:left">OXFORD (OSL-50)</td>
      <td style="text-align:left">Left/Right : 0.4 mm (Reference +- 30mm height),  0.7mm<br>Height : 0.6mm (Reference +- 30mm height), 3mm<br>Front/Back : 0.6mm (Reference +- 30mm height), 2.5mm</td>
      <td style="text-align:left">0.2 mm</td>
    </tr>
    <tr>
      <td style="text-align:left">Full-v</td>
      <td style="text-align:left">Left/Right : 0.6 mm (Reference +- 30mm height),  2mm<br>Height : 0.8mm (Reference +- 30mm height), 4.5mm<br>Front/Back : 0.6mm (Reference +- 30mm height), 4mm</td>
      <td style="text-align:left">0.35 mm</td>
    </tr>
    <tr>
      <td style="text-align:left" rowspan="3">track</td>
      <td style="text-align:left">SCANSONIC (350, 150, 150 advanced)</td>
      <td style="text-align:left">0.2mm (Linear)<br>0.4mm (weaving)<br>0.25mm (positioner synchronized)<br>0.5mm (weaving + positioner synchronized)</td>
      <td style="text-align:left">0.05 mm</td>
    </tr>
    <tr>
      <td style="text-align:left">OXFORD (OSL-50)</td>
      <td style="text-align:left">0.3mm (Linear)<br>0.5mm (weaving)<br>0.4mm (positioner synchronized)<br>0.6mm (weaving + positioner synchronized)</td>
      <td style="text-align:left">0.2 mm</td>
    </tr>
    <tr>
      <td style="text-align:left">Full-v</td>
      <td style="text-align:left">0.3mm (Linear)<br>0.6mm (weaving)<br>0.4mm (positioner synchronized)<br>0.7mm (weaving + positioner synchronized)</td>
      <td style="text-align:left">0.35 mm</td>
    </tr>
  </tbody>
</table>
[__SOURCE](8_Application_function/5_LVS_tracking/2_settings.md)
# 8.5.2 LVS Settings


To use LVS functionality, sensor installation and communication settings are required.

Let's now look at the process involved.

### (1) Mounting the LVS Sensor using the connection bracket

The connection bracket can either be designed and used by yourself, or you may receive one from HD Hyundai Robotics or the LVS manufacturer. <br>

![](../../_assets/8_5_3_lvs_mount_setup.png)<br>
*Figure 8.5.3. LVS Mounting Precautions*

{% hint style="warning" %}
  - To achieve repetition accruacy and precision, directly mount the LVS bracket to the robot flange<br>
  - In other words, install the mechanical assembly as follows: flange - LVS mount, LVS sensor - shock sensor(if used) - torch.
{% endhint %}

The tool coordinate system should be set as follows: the welding direction opposite to the progress direction should be set as the +Tool X direction, and the wire direction should be set as the +Tool Z direction, as shown in the diagram below.

The LVS sensor must be installed so that the laser is positioned perpendicular to the welding seam, which is straight (see figure)


![](../../_assets/8_5_4.png)<br>
*Figure 8.5.4. TCP and Sensor Installation, Tool Coordinate System Setup*

{% hint style="info" %}
  For instructions on setting the tool coordinate system, refer to the Tool Calibration and Angle Correction Manual(Angle Calibration) section.
{% endhint %}

{% hint style="warning" %}
  In order to use LVS, the laser should be positioned ahead of the welding direction, and the tool coordinate system must be set as shown in the diagram above.
{% endhint %}

---

### (2) Communication Settings

Connect the LVS sensor controller and the robot controller using an Ethernet cable.<br>
Navigate to `[F2: System] - 4: Application parameter - 5: LVS tracking - 1: Envrionment setting`.<br>

In the **[Communication]** tab, configure the following items:

- LVS brand : Scansonic, Oxford (or Meta), Full-v<br>
- IP Address : Enter the IP address of the sensor controller.
- Local Port : The port for the robot controller. (For Oxford, 8000)
- Remote Port : The port for the sensor controller. (For Oxford, 8002)

After entering the above information, click **[connect]**. If the status shows "connected," the connection is successfully established.


{% hint style="info" %}
- [IP Address] : The IP address used for sending data from the LVS controller to the robot controller is set in the LVS controller.
  - If the settings are incorrect, the connection may fial. In such cases, refer to the LVS manufacturer's manual.
- [Port] : When selecting a brand, the default values will automatically be applied, so there is no need for the user to modify them.
  - If the port is incorrect, the connection may fial. In such cases, refer to the LVS manufacturer's manual.
{% endhint %}

---

### (3) Basic Settings

In the **[Tracking]** tab, configure the following items: 
- P gain : Specifies the intensity with which the TCP tracks to the converted position and orientation.
- D gain : Specifies the speed at which the TCP responds to the converted position and orientation.
- Max tracking Distance : Specifies the maximum tracking amount per second in [mm/sec].


<table>
  <thead>
    <tr>
      <th style="text-align:left">Item</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Recommended Settings</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">P, D gain</td>
      <td style="text-align:left">Specifies the intensity with which the TCP tracks to the converted position and orientation.</td>
      <td style="text-align:left">
        General tracking (without weaving) : Set within the range 1 ~ 10. <br>
        Weaving tracking (with weaving) : Use the default value of 10. <br>
        The default values are P gain: 10 and D gain: 10. Adjust these values to suit the actual workpiece.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Max tracking distance/sec [mm/sec]</td>
      <td style="text-align:left">Specifies the maximum tracking amount per second in [mm/sec].</td>
      <td style="text-align:left">
        Set within the range of 1 to 5. The default value is 10.<br>
        LVS seam tracking is designed to correct small deviations from the taught trajectory, so setting a larger value is not necessary.
      </td>
    </tr>
  </tbody>
</table>


Preferences have been completed through the above process.

---

#### Full-V Sensor Configuration Example

![](../../_assets/8_5_5_lvs_setting_fullv_1.png)<br>
*Figure 8.5.5. Full-V Sensor Connection Settings*

As shown in the figure above, select the LVS brand as FULL, then check the IP address of the LVS sensor in the Full-V softeware.  <br>
Enter the IP in the `[F2: System] - 4: Application parameter - 5: LVS tracking - 1: Envrionment setting` window.  <br> Afterward, click the "connect" button at the bottom and verify that the connection status shows.  <br>
If "disconnected" appears, check the hardware connection and IP address.<br>

Refer to the manual provided by Full-V and the figure below to register the seam you wish to use in the Full-V software.  


![](../../_assets/8_5_6_lvs_setting_fullv_2.png)<br>
*Figure 8.5.6. Example of Seam Setting in Full-V Software*
[__SOURCE](8_Application_function/5_LVS_tracking/3_calibration.md)
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
Please refer to the following when teaching.

```python
move L,spd=60%,accu=0,tool=0  # Calibration specimen reference point location
delay 0.5
lvs auto_calib, cnd=1, seam=1, sp=p1, opt=0
end
```

{% hint style="info" %}
For Scansonic Full-V sensors, using opt=20 allows for precise calibration.
{% endhint %}

Move the TCP to the reference point of the specimen using the jog tool as shown in the figure below. It is recommended to use the Tool coordinate system jog tool during calibration.

As shown in Figures 1 and 2, half of the wire must be positioned so that it reaches the corner of the specimen from each direction.

The torch must be positioned perpendicular to the specimen. (Perpendicular in both roll and pitch directions)

Position the laser line with the jog so that it is perpendicular to the edge of the specimen.

In this state (where the torch is positioned perpendicular to the specimen and the laser line is perpendicular to the edge of the specimen), press **[Record]** to insert the `move` command.

{% hint style="warning" %}
* Use a spirit level to align the calibration specimen perpendicularly from all directions.
* The verticality of the torch and the degree to which the laser line is perpendicular to the edge of the specimen affect the calibration accuracy.
{% endhint %}

Insert `delay 0.5`, then insert the `lvs` command.

The `seam` argument of the `lvs` command is the number for the geometry and condition registered in the LVS controller.

{% hint style="info" %}
For calibration, register the seam as a Lap joint in the LVS controller software.<br>
Set the registered number in the seam argument of the lvs command.
{% endhint %}

![](../../_assets/8_5_7_lvs_autocalib.png)  
*Figure 8.5.7. LVS Auto Calibration*  

---

### (3) Preparations

Automatic Calibration involves motions such as front/back, left/right, roll direction rotation, and height adjustments, so ensure safety precautions are followed.

{% hint style="warning" %}
* Adjust the LVS settings (exposure time, laser intensity, shape settings) so that the LVS can recognize the seam of the specimen even at higher positions.
* When the laser is pointing to the flat surface outside the reference point of the specimen, the LVS controller should not be able to recognize the seam.
{% endhint %}

![](../../_assets/8_5_7_lvs_autocalib_2.png)<br>

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
[__SOURCE](8_Application_function/5_LVS_tracking/4_seam_finding.md)
# 8.5.4 LVS Seam Finding Func.

### (1) Seam Finding Overview

This function stores the position sensed by the LVS as a pose, and can be used as a substitute for touch sensing.

{% hint style="warning" %}
  If the TCP-LVS sensor calibration has not been performed before using this function, an abnormal pose will be saved.
{% endhint %}

The command format is as follows:  
After executing this, as shown below, the position sensed by the LVS will be stored in the po_100 variable.

```python
  var po_100=cpo()  # The current pose is stored in the variable po_100
  lvs seam_find, cnd=1, seam=1, sp=po_100 # If there is no variable with the name entered in the sp parameter, it will be automatically declared as a local pose variable.
```

{% hint style="warning" %}
  If the **sp** parameter is not declared, it will be declared as a local pose. <br>
  If the **mp** parameter is not declared, it will be declared as a global pose. <br>
  If the **ms** parameter is not declared, it will be declared as a global shift.
{% endhint %}


![](../../_assets/8_5_9_lvs_seamfind_ex.png)<br>
*Figure 8.5.9. Pose in the LVS sensing position*   
</br>

{% hint style="info" %}
  - The orientation of the pose stored in the sp parameter with the **seam_find** command will maintain the tool's orientation (Rx, Ry, Rz) before sensing.
  - On the other hand, with the **seam_find_p** command, only the position is recorded in the pose stored in the sp parameter.
{% endhint %}

* If you want to store only the position in the pose regardless of the pre-sensing orientation, use the following command format.<br>
This function is useful when you want to record the welding posture in the pose and then make the position (X, Y, Z) correspond to the point sensed by the LVS.

```python
var po_100=cpo()
lvs seam_find_p, cnd=1, seam=1, sp=po_100
```

* The pose shifted in the direction of Tool Y and Tool Z from the sensed position can be calculated as follows. <br>
This command calculates a pose that has shifted by 10mm in the Tool Y direction and 10mm in the Tool Z direction, based on the tool orientation during sensing.

```python
var po_100=cpo()
lvs seam_find, cnd=1, seam=1, side=10, height=10, sp=po_100
```

* When assigning a variable to `find_flag` of the `lvs` command during seam finding, 1 is stored on success and 0 on failure. Please note that the command is treated as completed upon failure. If `find_flag` is not assigned, an error occurs upon failure.

```python
var f1=0
lvs seam_find, cnd=1, seam=1, sp=po_100, find_flag=f1
```
---

### (2) LVS Seam Finding Retry

If the seam cannot be recognized during seam finding, a retry will be performed. 

The number of retries is specified in the **"no of retry"** under the Seam finding option in the LVS command's properties window.

If sensing is still impossible after the specified number of retries, an error will occur.

The retry process is performed in the following sequence:

![](../../_assets/8_5_10_lvs_seamfind_retry.png)<br>
*Figure 8.5.10. LVS Seam Finding Retry*   
</br>

{% hint style="warning" %}
* When using the master-shift function, be aware that retries will cause the position to shift forward and backward(by +ToolX, -ToolX).
{% endhint %}

---

### (3) LVS Seam Finding Monitoring

To view the LVS seam finding monitoring screen, click `[pane layout] - select - LVS seamfind` in the TP  


![](../../_assets/8_5_11_seamfind monitoring.png)<br>
*Figure 8.5.11. LVS Seam Finding Monitoring*   
</br>
<table>
  <thead>
    <tr>
      <th style="text-align:left">Item</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Position (X, Y, Z)</td>
      <td style="text-align:left">
        Displays the current sensed position (in base coordinates)<br>
        Spec : The position of the master pose. If not registered, it will display as (-1, -1, -1)<br>
        Sensing : Current sensed position 
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Gap</td>
      <td style="text-align:left">
        Spec : Master gap [mm]<br>
        Sensing : Current sensed gap [mm]
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Area</td>
      <td style="text-align:left">
        Internal area width of groove or butt shape [mm^2]<br>
        Spec : Master area [mm]<br>
        Sensing : Current sensed area [mm]
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Mismatch</td>
      <td style="text-align:left">
        Mismatch value typically refers to the height difference of the left-right shape.
      </td>
    </tr>
  </tbody>
</table>

{% hint style="info" %}
  Gap, area, mismatch, and similar values are displayed only for seams supported by the manufacturer's LVS controller.
{% endhint %}

If the master pose is registered, you can check the sensing history for the current job by pressing prev or next button.

{% hint style="info" %}
  For more details on the master mode, please refer to [8.5.5 LVS Master mode func.](./5_lvs_master_mode.md).
{% endhint %}


[__SOURCE](8_Application_function/5_LVS_tracking/5_lvs_master_mode.md)
# 8.5.5 LVS Master Mode Func.

### (1) Master Mode Overview

The Master Mode function stores a reference position (Master pose) and calculates the shift between the current sensed position and the reference position during actual production.

To enable this functionality, `user key - Master Mode` must be activated to register the reference position(Master pose) in advance.


![](../../_assets/8_5_12_lvs_seamfind_mastermode.png)<br>
*Figure 8.5.12. Example of Master Mode and Actual Motion*   
</br>

As shown in the left part of the figure, after activating Master Mode, the Master Pose is saved to the pose variable assigned to the `mp` parameter in the `lvs` command.

Typically, the sensing points are pre-taught, and once Master Mode is activated, the system automatically plays back to the complete the master teaching.

In thick welding application, several tens of welding waypoints will typically be registered as Master Poses.

Once the Master Teaching is completed, the Master Mode is turned off. There is no need to turn Master Mode back on after completing the Master Teaching.

During production, the robot operates in automatic or remote mode and senses each welding point to calculate the shift.

At this point, the shift relative to the Master Pose is automatically calculated and stored in the shift variable designated by the `ms` parameter in the `lvs` command.

This shift value is then applied to the `tg` parameter in the `move` command to compensate for the shift in the welding position, allowing the welding operation to be carried out accurately.


{% hint style="warning" %}
Important notes when registering master pose.

* During the registeration of the Master Pose, ensure that the side and height of the seam sensed by the LVS S/W at the sensing position are both close to 0.
* By teaching as described above, sensing can be performed stably, and Master Pose management, as well as the detection of any misalignment in the LVS or tool, can be easily recognized.

{% endhint %}


![](../../_assets/8_5_13_lvs_seamfind_mastermode_warn.png)<br>
*Figure 8.5.13. Important Considerations When Registering Master Pose*   
</br>

---

### (2) Shift Quantity Check Function Relaive to Master Mode

The shift quantity(in mm) between the current sensed pose and the Master Pose can be checked to verify if it falls within the user-defined range.

To set the range, access the **[property]** window in the lvs command, and enter the desired distance from the reference position in the "distance from reference position" field under the "Seam finding option"(in mm). 

If the shift value exceeds the user-defined range during seam finding, an error will occur.

{% hint style="warning" %}
If the `sp` parameter is not declared, it will be treated as a local pose.<br>
If the `mp` parameter is not declared, it will be treated as a global pose.<br>
If the `ms` parameter is not declared, it will be treated as a global pose.
{% endhint %}
[__SOURCE](8_Application_function/5_LVS_tracking/6_search.md)
# 8.5.6 LVS Search Func.

### (1) How to Use the Search Function
LVS provides a search function, and searching must precede tracking.

- `search`: Searches for the starting point end, while the TCP (Tool Center Point) moves to the starting position, stores, the points to be tracked in a buffer at set intervals, preparing for tracking.
- `step_search`: Used for multi-pass bead detection and step detection

When search is performed, search is executed, and depending on the option, it operates as follows:

(1) Above Laser
The TCP moves to the position of the laser, stores tracking points in the buffer, and completes the tracking preparation.

(2) Detect
It moves by the search distance in the search direction, detects the point where sensing is impossible, and the TCP moves to the position immediately preceding that point, stores tracking points in the buffer, and completes the tracking preparation.

By performing the search function, the system becomes ready to perform "seam tracking". 

Search is used as follows.

```python
  move L, spd=60%, accu=0, tool=1
  delay 0.1 #If the accu at the search start position is not 0, insertion is required.
  var po_100=cpo() #Stores the current pose in the declared variable po_100.
  lvs search, cnd=1, seam=1, sp=po_100 #Tracking ready
```

To configure the search function, enter **[property]** in the `lvs` command, where the search settings can be adjusted as follows:


![](../../_assets/8_5_14_lvs_search_setting.png)<br>
*Figure 8.5.14. lvs search settings*   
</br>

<table>
  <thead>
    <tr>
      <th style="text-align:left">Item</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">function</td>
      <td style="text-align:left">
        Sets the use of the search function.<br>
        'Laser Above' : Moves to the laser position of lvs and saves target positions in the buffer.<br>
        'Detect': After detecting unsensable points in the search direction, move to the position immediately prior to detection and save the target positions in the buffer.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">distance</td>
      <td style="text-align:left">
       Enter the maximum seek distance [mm].
      </td>
    </tr>
    <tr>
      <td style="text-align:left">direction</td>
      <td style="text-align:left">
       0 : Navigates in the +ToolX direction.<br>
       1 : Navigates in the -ToolX direction.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">speed</td>
      <td style="text-align:left">
        Set the search speed in mm/sec units.
      </td>
    </tr>
    <tr>
      <td style="text-align:left">offset</td>
      <td style="text-align:left">
        You can shift the point found in the direction of the weld line from the search point by a set amount of mm.
      </td>
    </tr>
  </tbody>
</table>

![](../../_assets/8_5_15_lvs_search_example.png)<br>
*Figure 8.5.15. lvs search Example*   
</br>

If a variable is assigned to find_flag, 1 is stored on a successful search and 0 on a failed search. Please note that the lvs command is marked as completed if the search fails.

The **search** and **seam tracking** functions can be taught as shown below.

```python
    move L, spd=60%, accu=0, tool=1
    delay 0.3
    var po_100=cpo() # The current pose is stored in the variable po_100
    lvs search, cnd=1, seam=1, sp=po_100
    weavon cnd=1
    arcon cnd=1
    lvs track, cnd=1, seam=1, sp=po_100
    move L, spd=30cm/min, accu=3, tool=1
    move L, spd=36cm/min, accu=3, tool=1
    move L, spd=40cm/min, accu=3, tool=1
    weavoff
    arcof
    end
```

---

### (2) How to Use the Multi-pass Bead Detection Function (step_search) 


This function is used to detect the starting point of a multi-pass bead, and its usage is identical to the `search` function.

In the **[property]** window of the `lvs` command, set the function to "Enable" and configure the scan distance in the "distance" field.

It can be used as follows:

```python
    move L, spd=60%, accu=0, tool=1 # Set the starting point for the multi-pass bead detection scan.
    delay 0.3
    var po_100=cpo() # The current pose is stored in the variable po_100
    lvs step_search, cnd=1, seam=1, sp=po_100
    move L, tg=po_100, spd=40cm/min, accu=3, tool=1 # Move to the found location.
    end
```
[__SOURCE](8_Application_function/5_LVS_tracking/7_tracking_monitoring.md)
# 8.5.7 LVS Tracking Func. and Monitoring

### (1) LVS Tracking Overview

LVS Tracking is a function that compensates for the different between the taught trajectory and the actual welding line.

{% hint style="warning" %}
The reference teaching for the base workpiece should be performed with high precision.<br>
After applying the shift to correct the positioning error of the workpiece, the LVS function should be used.<br>
For further details, please refer to [8.5.5 LVS Master Mode Func.].
{% endhint %}

Since the laser is mounted in front of the TCP, a search must be performed first to carry out tracking.

{% hint style="info" %}
  Please refer to the previous section, **[8.5.6 LVS Search Func.]**, for detailed information about the search function.
{% endhint %}


The configuration of the lvs command should be set as follows:

```python
    move L, spd=60%, accu=0, tool=1
    delay 0.3
    var po_100=cpo() # The current pose is stored in the variable po_100
    lvs search, cnd=1, seam=1, sp=po_100
    weavon cnd=1  
    arcon cnd=1
    lvs track, cnd=1, seam=1, sp=po_100
    move L, spd=30cm/min, accu=3, tool=1
    move L, spd=36cm/min, accu=3, tool=1
    move L, spd=40cm/min, accu=3, tool=1
    weavoff
    arcof
    end
```

When the search command is executed, it operates as follows depending on the option:

(1) Detect: Finds an invalid point as a starting point, saves it to sp, and then fills the data buffer while moving to the starting point.

(2) Above Laser: Fills the data buffer while the TCP moves to the laser position.

After the search, arc welding is performed while tracking the weld line in real time.

![](../../_assets/8_5_17.png)<br>
*그림 8.5.17. lvs search and tracking process*   
</br>

### (2) Teaching method for cases where tracking is interrupted due to an error in a section where the LVS is continuously unable to recognize during welding

The sp of the lvs track command stores the TCP position where the laser can be located at the last welding position.

If an error occurs because the LVS fails to recognize the weld line multiple times, it can be made to restart as follows.

The _lvs.last_tracking_sno system variable stores the step number being tracked.

![](../../_assets/8_5_18.png)<br>
*Figure 8.5.18. Manual restart method for unrecognized seam error*   
</br>

You can use the check_seam function to find a section that is recognized more efficiently than the method above.

This function finds a recognized point within the distance set in opt and saves it as a pose in sp.

![](../../_assets/8_5_20_check_seam_function.png)<br>
*Figure 8.5.19. Description of check_seam function*   
</br>


### (3) How to use tracking with specified offset amount

```python
    move L, spd=60%, accu=0, tool=1
    delay 0.3
    var po_100=cpo() # The current pose is stored in the variable po_100
    lvs search, cnd=1, seam=1, sp=po_100
    weavon cnd=1  
    arcon cnd=1
    lvs track, cnd=1, seam=1, sp=po_100, side=5, height=-5 # offset tracking with 5mm in the ToolX, and -5mm in the ToolZ
    move L, spd=30cm/min, accu=3, tool=1
    move L, spd=36cm/min, accu=3, tool=1
    move L, spd=40cm/min, accu=3, tool=1
    weavoff
    arcof
    end
```

{% hint style="info" %}
* When using weaving, the stickout length increases depending on the angle and amplitude. To compensate for this, set the height with a negative value during both search and track operations.
{% endhint %}

### (4) LVS Monitoring

You can switch screens for LVS monitoring by following the sequence `[(Right Panel) Creative Adjustments] - Select - LVS Follow`.

In monitoring, you can check the following items.

![](../../_assets/8_5_19_tracking_monitoring.png)<br>
*Figure 8.5.19. LVS Monitoring*   
</br>


LVS Monitoring can be activated by selecting `[pane layout] - select - LVS tracking`.

In the monitoring, the follwing items can be checked:


| Item | Description |
|------|------|
| Total Cumulative Compensation<br> (X, Y, Z) | If weaving is not used, this represents the cumulative compensation relative to the base coordinate system. If weaving is used, it refers to the cumulative compensation in the weaving corrdinate syste. |
| Sensor | qual: Indicates whether the current laser seam sensing is valid or invalid.<br> Y, Z: The position of the currently sensed seam in the sensor image coordinate system(2D). |
| Tool Tip | The current position of the TCP relative to the base coordinate system. | 
| Tracking Point | The point that the TCP is currently tracking, relative to the base coordinate system. |
| Sensing Point | The base coordinate value of the location currently being sensed by the laser. |
| Buffer Size | The number of points stored in the buffer for tracking. If this value keeps increasing, decreasing, or reaches 0, there may be a problem with tracking, communication, or configuration. |
| Information | Displays the progress of the auto-calibration and other relevant information. |
| Real-time Image | Displays the points to be tracked, represented by red circles, that are stored in the buffer. |


[__SOURCE](8_Application_function/6_Stitch/README.md)
# 8.6 STITCH Function
[__SOURCE](8_Application_function/6_Stitch/1_overall_.md)
# 8.6.1  STITCH Func. Overview

Stitch welding is a function where welding is performed intermittently, similar to stitching. In [Figure 8.6.2], stitch welding is performed by setting start and end points on the specimen. In stitch welding, parameters `a` and `b` are set as shown in [Figure 8.6.1] to determine the length of the welding section and the non-welding section, thus forming the stitch pattern.

[Figure 8.6.3] provides a simple explanation of the stitch welding process. Positions from P[1] to P[4] are recorded. In this diagram, stitch welding is performed at the P[2] and P[3] sections, using the commands ```stitch on/off``` and ```arcon/arcoff```.

</br>

![](../../_assets/8_6_1.png)<br>
*Figure 8.6.1. Stitch Func. basic parameter* 

</br>



![](../../_assets/8_6_2.png)<br>
*Figure 8.6.2. Stitch Welding specimen* 
 
</br>


![](../../_assets/8_6_3.png)<br>
*Figure 8.6.3. Stitch Welding Process* 










 






[__SOURCE](8_Application_function/6_Stitch/2_command.md)
# 8.6.2 STITCH Func. Command
 

![](../../_assets/8_6_4.png)<br>
*Figure 8.6.4. Stitch Command Example*  


```stitch``` Command: 
After selecting `[F6: cmd.input] - arcweld - stitch` in sequence, choose on/off and press **[ENTER]**.


{% hint style="warning" %}
- ```S2 move L, spd=10mm/s, accu=3, tool=1```  
	- L : Ensure that linear interpolation is selected.  
	- 200mm/sec : Welding speed - the speed during the ON section of the stitch welding. the unit must be set to mm/sec
- ```arcon / arcoff``` Use the command together to start welding.
{% endhint %}
[__SOURCE](8_Application_function/6_Stitch/3_parameter.md)
# 8.6.3 STITCH Func. Parameter setting


![](../../_assets/8_6_5.png)<br>
*Figure 8.6.5. Stitch Welding Process Profile*


[Figure 8.6.5] illustrates the stitch welding process. Based on this chart, you can configure the options for the `stitch` command.

![](../../_assets/8_6_6.png)<br>
*Figure 8.6.6. Stitch Welding Condition Dialog Box1 (General)*

![](../../_assets/8_6_7.png)<br>
*Figure 8.6.7. Stitch Welding Condition Dialog Box2 (Section)*


[Figure 8.6.6] shows the screen accessed by placing the cursor on the `stitch` command and pressing the `[Property]` button on the left side of the TP screen. [Figure 8.6.7] is accessed by selecting the `[Section]` tab from the previous screen.
The descriptions of the parameters for each figure are as follows:

- Condition Number: Select from the list of conditions on the right
- Description: Input using the soft keyboard
- General
  - (1) On delay Time: The time period during which the welding signal is turned on in advance
  - (2) Off delay Time: The time period during which the welding signal is turned off in advance
  - (3) Distance to Start: The length of the speed entry section before the stitch welding starts(On section)
  - (4) Off Speed: Welding Speed during the non-overlapping (Off) section

- Section
  - (5) Section: Stitch welding condition  <br/>
    Example. When stitch welding under the conditions of section 1 is performed for the specified count, stitch welding proceeds under the conditions of section 2
  - (6) On Distance: Length of the welding section
  - (7) Off Distance: Length of the non-overlapping (Off) section
  - (8) Count: Number of stitch welding repetitions
  - (9) On speed: Welding speed during the welding section

{% hint style="warning" %}
- `(9) on speed`: The speed for the welding (ON) section in the stitch section is set as the step speed.
{% endhint %}


[__SOURCE](8_Application_function/6_Stitch/4_aux_spec.md)
# 8.6.4 STITCH Func. Additional Specifications

- **Emergency Stop, Restart**  

During stitch welding, the process can resume after an emergency stop or playback stop. However, if the controller power is turned off and rebooted, the stitch welding cannot be restarted.
[__SOURCE](8_Application_function/7_LPS/README.md)
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



[__SOURCE](8_Application_function/7_LPS/1_settings.md)
<script id="page-config" type="application/json">
{
	"permittedStrs": ["Hi6", "Hi7"]
}
</script>

# 8.7.1 Laser Sensor Setup  


To use the LPS function, it is necessary to first install the laser sensor and configure communication specifications and related settings.
<br/>

### (1) Mounting the Laser Sensor Using a Connection Bracket

The connection bracket may be designed and fabricated by the user, or provided by our company or the sensor manufacturer.

![](../../_assets/8_7_1.png)<br>
*Figure 8.7.1. Installation of the laser sensor using a bracket*

A laser distance sensor consists of a transmitter and a receiver.
When the robot is aligned with the arc torch, ensure that the transmitter/receiver of the laser sensor is aligned with the tool-based X direction (refer to the laser manufacturer's specifications).
In addition, it is recommended to install the sensor on the right side of the tool Y direction (right side when facing the torch).  

When the laser is installed and powered on, keeping the distance between the tool tip and the laser point as short as possible is advantageous in terms of interference prevention and CT (Cycle Time).
Finally, the sensor installation position relative to the tool tip must be suitable for the specifications of the laser sensor being used (measurement range), and should be installed higher than the minimum specified distance.



{% hint style="warning" %}
  It is recommended to mount the sensor bracket directly to the robot flange. In other words, install the mechanical structure in the following order: **Flange - Laser sensor and bracket - Shock sensor - Torch.**
{% endhint %}


### (2) Communication Setup

The laser sensor can be connected according to its specifications by referring to the following link.
(Refer to [${cont_model} - Industrial Communication](https://hrbook-hrc.web.app/#/view/doc-industrial-communication/en-${cont_model}/README?cont_model=${cont_model}))

This page describes examples for selected sensors only.

* Before proceeding with the setup, connect the sensor head, controller, communication unit (if applicable), and SMPS, and then supply power.
(If the connection order is incorrect, sensing values may not be received. Therefore, ensure that the sensor is connected first during subsequent setups as well.)


#### Serial - Example: Keyence LK-G400

First, configure the sensor controller settings.

* Communication Speed Setting (Required)  
1. Press and hold the `SET` key, then press the `[UP]` key to select `Enu`.
2. Press the `ENT` key and use the `[RIGHT]` key to select function `A` (RS-232C).
3. Press the `ENT` key to check the current value (A-b0 to b4; 9600 / 19200 / 38400 / 57600 / 115200).

* Display Unit Setting (Optional)  
1. Press and hold the `SET` key, then press the `[UP]` key to select `oUt-1`.
2. Press the `ENT` key and use the `[RIGHT]` key to select function `G`.
3. Press the `ENT` key and use the `[UP]` key to set the desired number of decimal places (G-0 to ; 0.01, 0.001, ...).

Navigate to `[F2: System] - 4: Application Parameters - 6: Laser Point Sensing - 1: Environment Setting`.

![](../../_assets/8_7_2.png)<br>
*Figure 8.7.2. Laser Communication Setup (Keyence LK-G)*
</br>

Select Keyence as the LPS brand to configure the settings.
Once the setup is complete, verify that the value displayed in the **Sensing Distance (mm)** field matches the output value from the controller.

<br/>


#### EtherNet/IP - Example: Baumer OM-70

Connect the sensor to a PC and access the web interface.
(The default fixed IP address is 192.168.0.250.)

![](../../_assets/8_7_3.png)<br>
*Figure 8.7.3. Baumer Sensor Web Configuration*
</br>  

Navigate to `Device Configuration` tab and set the communication method according to the intended purpose.
At this time, enable only the method that matches the currently used communication protocol in the Process Interface section.

If **Ethernet/IP** is used, complete the network settings accordingly. In the ${cont_model}, network ranges 0, 1, and 2 are used by default, so a different range must be assigned. (e.g. 192.168.10.250.)

![](../../_assets/8_7_4.png)<br>
*Figure 8.7.4. Baumer Sensor Network Settings*
</br>   

Afterward, proceed step by step by following the link below.
Note that Hi6 does not support built-in Ethernet, so a communication card must be used ([Hi6 - Industrial Communication](https://hrbook-hrc.web.app/#/view/doc-industrial-communication/en-Hi6/1-cifx-pci-communication/3-cifx-pci-settings-industrial-communication/3-EtherNet-IP/README?cont_model=Hi6)).
From Hi7 and later, built-in Ethernet is supported, allowing communication to be established using the controller alone ([Hi7 - Industrial Communication](https://hrbook-hrc.web.app/#/view/doc-industrial-communication/en-Hi7/2-ethernet-ip/4-scanner/README?cont_model=Hi7)).



![](../../_assets/8_7_5.png)<br>
*Figure 8.7.5. Baumer Sensor Signal Assignment*
</br>

Once the above steps are completed, navigate to `[F2: System] - 4: Application Parameters - 6: Laser Point Sensing - 1: Environment Setting - Signal tab`.
Configure the input signals for the assigned blocks.
You can then confirm that the distance (current value) is output as the sensor value. (Additional settings are required if sensor-to-distance mapping is needed.)


#### EtherNet/IP - Example: Keyence IL-300

* Refer to the manufacturer's manual and our manual to connect the sensor in the same manner as the Baumer sensor.
As described above, the Ethernet connection method differs depending on whether an Hi6 or Hi7 controller is used.

[__SOURCE](8_Application_function/7_LPS/2_calibration.md)
# 8.7.2 TCP-Sensor Calibration  


Before using the LPS function, calibration between the TCP and the sensor must be performed.
The following section describes how to perform TCP-to-sensor calibration.

<br/>

### (1) Preparation of the Calibration Specimen

When a license is purchased through our company, a calibration specimen for automatic calibration is provided.

<br/>


### (2) Preparation  

Before performing calibration, the tool must be perfectly aligned with the calibration plane.
Teach the tool manually in the X and Y directions based on the tool coordinate system, and check that the laser output remains constant (with the error kept within 0.5 or less). Adjust the RX and RY values as necessary.  

Once the tool is aligned, position the wire tip at the edge of the calibration plane.
When teaching in the tool-based X-Y directions, adjust the RZ value so that the laser point moves along the edge corner.  

<br/>

![](../../_assets/8_7_2_1.png)<br>
*Figure 8.7.2.1 Preparation before calibration*<br/>  

After completing the above steps, all preparations required for performing calibration are complete.


### (3) Performing Automatic Calibration

Position the wire tip at one vertex of the calibration plane.
In addition, ensure that the laser point is located inside the calibration plane.  

<br/>

![](../../_assets/8_7_2_2.png)<br>
*Figure 8.7.2.2 Start of calibration*<br/>  

From the lower panel, select `[F6: cmd. input] - arcweld - lps` and insert the following command.

```py
  lps auto_calib, cnd=<Condition Number>, Tx=<Movement Distance in the X-dir based on the tool>, Ty=<Movement Distance in the Y-dir based on the tool
```

At this time, the movement distance must be set greater than the distance the laser is required to travel.
If detection fails within the specified parameters, a calibration error will occur.  

When executed in automatic method, calibration is performed through the following sequence of operations:  

1. The laser point moves in the Tx and Ty directions, initially moving toward the tool tip direction.
2. The robot is lifted in the +Z direction based on the robot coordinate system, and the same process as in Step 1 is performed.
3. The robot moves downward in the -Z direction based on the robot coordinate system, while interpolation is performed toward the transmitter/receiver direction of the sensor (current bracket specification Tx).  

Once calibration is fully completed, an execution mark appears on the left side of the step, and all motion stops.  


### (4) Calbration Information

Navigate to `[F2: System] - 4: Application Parameters - 6: Laser Point Sensing - 2: Calibration` to check the calibration results.
When the value in the **Calibration done** field changes to "2", it indicates that all calibration processes, including interpolation, have been completed.  
Calibration information is stored per tool number, which is useful when using tool change functions.
If the tool information is the same but a different tool number is to be used, the calibration data can be copied and reused.

<br/>

![](../../_assets/8_7_2_3.png)<br>
*Figure 8.7.2.3 Calibration Result*<br/>  



[__SOURCE](8_Application_function/7_LPS/3_function.md)
# 8.7.3 Using the LPS Function  


{% hint style="warning" %}
If tool-to-sensor calibration (ref. 8.7.2) has not been performed before using this function, invalid poses may be stored.
{% endhint %}

### Property Window

The properties of the LPS command are as follows.  
<br/>

![](../../_assets/8_7_3_0.png)<br>
*Figure 8.7.3.0 LPS Property*<br/>  

#### Gap Coefficient

  This parameter is used to detect step differences in **Step mode (stepp)** and allows the user to specify the detected height difference.
  However, this parameter is not used during the calibration process, as a separate calibration specimen is used.

#### Step Sensitivity

  This parameter sets the data processing sensitivity based on repeatability.
  In most cases, users can use the default value, and no additional adjustment is required.

#### Slope Threshold (Slope Degree)

  This parameter is used to detect edges.
  In addition to the step coefficient, it can be configured during tool-to-sensor calibration operations and step detection.
  Since edges are not always vertical, this parameter allows the system to respond to sloped surfaces.

#### Pose Coordinates / Shift Coordinates

  This setting specifies the coordinate system in which data is stored when each mode is executed.
  In particular, Shift Coordinates are used when Master mode is enabled.

<br/>

### (1) Spot Mode  

**Spot mode** is used to verify calibration results or to obtain the pose of the position currently indicated by the laser.  

<br/>

![](../../_assets/8_7_3_1.png)<br>
*Figure 8.7.3.1 Spot Mode*<br/>  

```py
  var p10=cpo()
  lps spot,cnd=1,pose=p10
  move L,tg=p10,spd=10%,acc=0,tool=0
```

{% hint style="warning" %}
  In this case, only the position is recorded in the pose specified by the sp parameter.
  The tool orientation (Rx, Ry, Rz) prior to sensing is not preserved.
{% endhint %}

<br/>


### (2) Step Mode

**Step Mode** is used to detect positions where a height difference occurs on the base material.
Depending on whether the height difference is lower or higher, the scan direction should be reserved accordingly.  

<br/>

![](../../_assets/8_7_3_2.png)<br>
*Figure 8.7.3.2 Step Mode*<br/>  

```py
  var p10=cpo()
  lps stepp,cnd=1,Tx=50,spd=5,pose=p10
  move L,tg=p10,spd=10%,acc=0,tool=0
```


The system moves by the specified distance in the X or Y direction based on the tool while searching for a step difference.
If no step is detected within the specified distance, a detection error occurs.  

<br/>


### (3) Scan Mode

![](../../_assets/8_7_3_3.png)<br>
*Figure 8.7.3.3 Scan Mode on various geometries*<br/>  

```py
  var p10=cpo()
  lps scan,cnd=1,Ty=50,spd=5,pose=p10
  move L,tg=p10,spd=10%,acc=0,tool=0
```

Scan mode detects weld points while moving by the specified distance in the X or Y direction based on the tool.
It can be executed with a single command regardless of the joint geometry, such as fillet, V-groove, or butt joints.
Detection results can be retrieved via the REST API, or verified by registering and using the application provided by our company.  

For instructions on how to register and use the application, please refer to the following link: [Software Development Kit (SDK)](https://hrbook-hrc.web.app/#/view/doc-hi6-sdk/en/README?cont_model=${cont_model})  


{% hint style="warning" %}
  Set the movement distance sufficiently to include the weld seam, and ensure that the tool motion is not parallel to the scanned surface.
{% endhint %}  


#### (3-1) Monitoring Screen  

![](../../_assets/8_7_3_4.png)<br>
*Figure 8.7.3.4 LPS Graph*<br/>  

After registering the application, the monitoring screen can be accessed through the following method: `[Pane layout] - select - LPS Graph` 

<br/>

![](../../_assets/8_7_3_5.png)<br>
*Figure 8.7.3.5 Example screen - V-groove*<br/>  

![](../../_assets/8_7_3_6.png)<br>
*Figure 8.7.3.6 Example screen - Butt joint*<br/>  


When the function is executed, results can be viewed as shown in the figure above.
The currently provided screen offers the following features:  

1. The screen can be refreshed by clicking the Refresh button in the upper-left corner.
2. The numeric value displayed in the upper-right corner represents the real-time output value of the laser sensor.
3. The calculated weld point is indicated by a red dot.

