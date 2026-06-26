
[__SOURCE](README.md)
# ${cont_model} Robot Controller Functional Manual - 弧焊
[__SOURCE](0-about-this-manual/README.md)
# 关于手册
[__SOURCE](0-about-this-manual/precautions.md)
# 注意事项

{% include file="zh/precautions.md" %}
[__SOURCE](0-about-this-manual/safety-notice.md)
# 安全警告

{% include file="zh/safety-notice.md" %}
[__SOURCE](0-about-this-manual/structure.md)
# Book Structure

本手册由 8 个章节组成。

### Chapter 1: Arc Welding Basics
本章解释了首次使用弧焊机器人时所需的设置、基本教学方法和便利功能。
<br/><br/>

### Chapter 2: Inserting Commands
本章介绍了各种与弧焊相关的命令及其简单设置方法。通过本章，您可以快速了解我们公司弧焊机器人的基本功能。
<br/><br/>

### Chapter 3: Command Property
本章解释了第 2 章中介绍的一些命令的属性功能。它解释了如何编辑弧焊条件，这是使用弧焊机器人时的必要设置，以及如何编辑应用功能命令。
<br/><br/>

### Chapter 4: Arc Welder Settings
本章介绍了如何选择要使用的弧焊机及每台焊机需要设置的项目。
<br/><br/>

### Chapter 5: Editing Arc Welding Conditions
本章解释了如何编辑弧焊条件。介绍了如何设置焊接的基本参数，如电流、电压、焊接模式以及气体前/后流。由于焊接条件因焊机而异，因此您只能了解与您想要使用的焊机相关的内容。
<br/><br/>

### Chapter 6: Weaving Function
本章介绍了编织功能及其详细设置。如果您不使用编织操作，可以跳过本章。
<br/><br/>

### Chapter 7: Arc Welding Data Monitoring
本章解释了在焊接过程中利用焊机发送的数据的功能。描述了如何实时监控焊机数据以及如何将这些数据保存到文件中。还描述了绘图和方便查看以前保存的数据作为图形的功能，以及量化焊接质量的功能。
<br/><br/>

### Chapter 8: Arc Welding Application Functions
本章介绍了在特殊情况下可能有用的弧焊应用功能。它提供了在工件焊接线不均匀时，或工件位置错误导致焊接质量问题时可以应用的功能的简要概述。
<br/><br/>

首次使用我们的弧焊机器人时，我们建议您阅读第 1 至第 5 章。对于第 6 至第 8 章，我们建议您选择性地阅读您需要的功能。 

<br>
[__SOURCE](1_Basic_information/README.md)
# 1. 弧焊基础
[__SOURCE](1_Basic_information/1_Introduction/README.md)
# 1.1 概述

按照下图进行弧焊操作的教学。

![](../../_assets/1_1_1.png)<br>
*图 1.1.1. 基本弧焊教学*

</br>

(1) 打开控制器前面的电源开关。

(2) 在手动模式下选择 `[mode witch]` 的 (Teach Pendant)TP。

(3) 按下 TP 上的 `[Program]` 并输入程序编号。

(4) 如果你进行到这里，TP 屏幕会显示如下。

![](../../_assets/1_1_2.png)<br>
*图 1.1.2. 选择新程序编号的屏幕*

</br>

(5) 按下 TP 上的 `[Motor On]` 按钮以给机器人的电机供电。

(6) 使用轴控制键将机器人的焊枪移动到步骤 1 中的位置。

(7) 按下 `[rec. cond]` 键，然后指定所需的插补类型、速度、精度和工具编号。

- 使用方向键移动到所需项后，设置值并按下 `[ENTER]` 键以保存设置
- 按下 `[tool]` 键并输入所需的工具编号。

![](../../_assets/1_1_3.png)<br>
*图 1.1.3. 记录条件*

</br>

- 按下 `[rec. cond]` 键以记录步骤，如下所示。

![](../../_assets/1_1_4.png)<br>
*图 1.1.4. 记录步骤 (1) 的程序*

</br>

(8)	重复步骤 5 到 7，进行步骤 2 到 4。
 
![](../../_assets/1_1_5.png)<br>
*图 1.1.5. 记录步骤 (2) 的程序*

(9) 由于焊接区域从步骤 2 到步骤 3，将光标移动到步骤 2。

- 输入 `[F6: cmd. Input] - arcweld - weaving`，输入条件编号，然后按下 `[ENTER]` 键。
- 以相同方式，输入 **[arcon]**，输入条件编号，然后按下 `[ENTER]` 键。
(有关弧焊条件设置，请参考 [5. 编辑弧焊条件](../../5_Condition_editing/README.md)。)

(10) 将光标移动到步骤 3，这是弧焊结束的步骤。
 
- 再次输入 **[weaving]** 并将其关闭。
- 还要输入 **[arcoff]**。

(11) 将步骤 3 的速度修改为您所需的焊接速度（例如，20mm/s）。

(12) 最后，输入 `[F6: cmd. input] - flowctrl - end` 命令以终止程序。

![](../../_assets/1_1_6.png)<br>
*图 1.1.6. 教学完成屏幕*
[__SOURCE](1_Basic_information/2_Function_setting/README.md)
# 1.2 弧焊功能设置
[__SOURCE](1_Basic_information/2_Function_setting/1_usage.md)
# 1.2.1 弧焊应用设置

(1) 根据机器人型号，弧焊功能可能未激活。如果是这种情况，请按照以下步骤启用。(注：设置弧焊功能需要工程师权限)

(2) 在手动模式下，按`[F2: 系统] - 5: 初始化 - 3: 用途设置 ([F2: System] - 5: Initialization - 3: Usage setting)`。对话框将出现，如[图 1.2.1.]所示，允许您配置机器人的应用、您想使用的焊机、用户键和 I/O 信号分配。

(3) [图 1.2.1] 显示了激活的弧焊步骤，其中焊机信息中的焊机编号已选择为 **No.4(Fronius)**。在此屏幕上，按 **焊机设置** 将带您到一个对话框，在该对话框中可以配置所需焊机的条件。

(4) 有关焊机特性文件的详细设置，请参阅 [4. 弧焊机设置](../../4_Setting/README.md)。

![](../../_assets/1_2_1.png)<br>
*图 1.2.1. 用途设置对话框*
[__SOURCE](1_Basic_information/2_Function_setting/2_signals_functions.md)
# 1.2.2 弧焊各种信号和功能设置

在手动模式屏幕上，按 `[F2: 系统] - 4: 应用参数 - 2: 弧焊 ([F2: System] - 4: Application parameter - 2: Arc welding)` 调出可以设置弧焊应用的各种条件的屏幕，如下所示。

![](../../_assets/1_2_2.png)<br>
*图 1.2.2. 弧焊应用参数对话框*

每个项目的详细信息如下：

#### [一般]
进给速度(%): 
|`(低) ((Low))`[1 ~ 50] %, `(高) ((High))`[10 ~ 100] %|, 这指的是在前进(`[SHIFT]+[2]` (线材进给))或后退(`[SHIFT]+[3]` (线材退回))时的线材进给速度。<br> 您可以设置低速和高速操作的进给速度（当按键按下3秒或更长时间时）。

`[GUN]` 键状态输出信号:
设置信号以输出 TP 上 `[GUN]` 键的当前状态。

`[GUN]` 键控制禁用输入: 
分配一个输入信号以外部控制 `[Gun]` 键的开/关状态。一旦分配了此信号，您将无法通过按下 TP 上的 `[GUN]` 键更改弧焊的开/关状态。此功能有助于防止由于意外按下 `[GUN]` 键而导致焊接部分焊接可能被跳过的问题。<br> (当接收到分配的信号时，`[GUN]` 键的 LED 关闭，机器人进入 `Dry Run` 状态，即使机器人在运行中也不会在弧焊部分进行焊接。)

冷却液错误输入信号:
对于水冷弧焊炬，配置信号以检测冷却液循环的问题。当在焊接过程中收到此信号时，视为错误，触发机器人的操作和焊接过程停止。

焊接机错误处理: 
|[`不执行 (Disable)`, `警告 (Warn)`, `错误 (Error)`]|, 设置如何处理焊接机错误。

线材空缺错误处理: 
|[`不执行 (Disable)`, `警告 (Warn)`, `错误 (Error)`]|, 设置当没有焊接线材时的错误处理方式。

气体压力错误处理: 
|[`不执行 (Disable)`,`警告 (Warn)`, `错误 (Error)`]|, 设置气体压力异常时的错误处理方式。

{% hint style="info" %}
警告会发出警告信息，错误会使机器人停止移动并显示错误信息。
{% endhint %}

弧焊 I/V 变化自动保存: 
|[`不执行 (Disable)`, `启用 (Enable)`]|, 此设置决定在 `弧变化 IV(弧焊电流/电压调整对话框)` 中更改当前和电压值时是否自动保存更改。有关更多详细信息，请参见 [[1.3.3 焊接过程中更改电流/电压]](../3_Convenient_functions/3_change_current_voltage.md)。

重型炬的振动减少: 
|[`不执行 (Disable)`, `焊接点 (Welding point)`, `全范围 (All range)`]|, 此设置旨在减少使用重型炬时的振动。它有助于最小化在使用水冷或推拉式炬时可能发生的振动。<br> 当设置为 `焊接点` 时，可以在焊接点入口部分实现显著减少振动，而对机器人的操作速度没有实质性改变。<br> 当设置为 `全范围 (All range)` 时，应用专为重型弧焊炬设计的滤波器，几乎消除了整个过程中的振动。然而，这可能会导致机器人的操作速度降低。

手动模式下的弧焊启用: 
|[`不执行 (Disable)`, `启用 (Enable)`]| 此设置决定是否可以通过在手动模式下向前移动来执行焊接。<br> 当设置为 `启用 (Enable)` 时，可以通过向前踏入弧焊部分来执行焊接，执行单元设置为 `结束 (End)`。有关更多详细信息，请参见 [[1.3.4 手动模式下的弧焊]](../3_Convenient_functions/4_manual_mode.md)。

循环开始时的电缆检查: 
|[`检查 (Check)`, `忽略 (Ignore)`]| 此设置决定在机器人启动其第一个循环时是否执行线材粘连检查。<br> 当 `"检查"` 被启用时，机器人将在开始前约0.2秒内进行检查，然后继续移动。

TCP 速度比监控: 
|[`不执行 (Disable)`, `启用 (Enable)`]| 此设置决定是否监控 TCP 速度的变化率。

#### [触摸感应]
触摸感应停止设置: 
|[`立即 (Immediately)`, `正常 (Normal)`]|, 设置当触摸感应检测到工件时是 `立即停止` 还是 `正常停止`。<br> 如果正常停止期间线材弯曲增大，设置为 `立即停止`。

#### [弧轨迹监控]
激活: 
|[`不执行 (Disable)`, `启用 (Enable)`]|, 设置是否监控弧轨迹。
[__SOURCE](1_Basic_information/2_Function_setting/3_crash_sensor.md)
# 1.2.3 碰撞传感器信号设置

弧焊机器人系统使用碰撞传感器来防止焊枪变形。碰撞传感器基本上使用负逻辑来立即检测诸如传感器电缆断开等问题。

设置对话框如下：

您可以在`[F2: 系统] - 1: 用户环境 ([F2: System] - 1: User Environment)`中配置碰撞传感器处理方法。


#### [碰撞传感器处理]
| item | Description |
|------|------|
|**紧急停止**|当输入碰撞传感器信号时，机器人将关闭电机并执行紧急停止|
|**停止**|当输入碰撞传感器信号时，机器人保持电机开启并执行停止|

#### [如何更改信号逻辑]
如果工具发生碰撞且碰撞传感器信号打开，电机将不会启动。在这种情况下，您需要将信号逻辑更改为负逻辑，如下所示。

- `[F2: 系统] - 2: 控制参数 - 2: 输入/输出信号设置 - 1: 输入信号属性 ([F2: System] - 2: Control parameter - 2: Input/Output signal setting - 1: Input signal attribute)` - 添加信号并勾选负逻辑框  


![](../../_assets/1_2_3.png)<br>
*图 1.2.3. 如何更改信号逻辑*

{% hint style="info" %}
当您在系统的输入信号设置中设置碰撞传感器时，系统将优先考虑来自此信号的输入。通过焊接机通信接收到的任何碰撞传感器信号将被忽略。
{% endhint %}
[__SOURCE](1_Basic_information/3_Convenient_functions/README.md)
# 1.3 弧焊便利功能
[__SOURCE](1_Basic_information/3_Convenient_functions/1_gas_check.md)
# 1.3.1 气体检查、线材微进和线材回收

这描述了在弧焊系统中控制保护气体阀门和送丝电机的功能。您可以使用气体检查功能检查当前的保护气体流量。微进和反向微进（回撤）功能让您调整从焊接喷嘴突出线材的长度。

以下是功能及其使用方法： 

### 气体检查

| Item      | Description                     |
| ------- | ---------------------- |
| **HotKey** | `[Shift]+[1]`          |
| **Dedicated Key** | 用户键 `GAS CHK`         |
| **Function**  | 打开保护气体阀门以验证气体流量 |


### 线材微进

| Item      | Description                          |
| ------- | --------------------------- |
| **HotKey** | `[Shift]+[2]`               |
| **Dedicated Key** | 用户键 `inching`              |
| **Function**  | 将线材前送出焊枪以调整其长度 <li>慢速微进: 按键少于 3 秒</li> <li>快速微进: 按键 3 秒或更长时间</li> |


### 线材回收

| Item      | Description                 |
| ------- | ------------------ |
| **HotKey** | `[Shift]+[3]`      |
| **Dedicated Key** | 用户键 `retract`     |
| **Function**  | 将线材回绕以调整其长度 <li>慢速微进: 按键少于 3 秒</li> <li>快速微进: 按键 3 秒或更长时间</li> |


### 微进速度设置

 >- 导航到 `[F2: 系统] - 4: 应用参数 - 2: 弧焊 ([F2: System] - 4: Application parameter - 2: Arc welding)`
 >- 在弧焊设置菜单中，设置您的低速和快速速度值: **微进速度(%): 低=[---]%, 高=[---]%**
 >- 速度以最大微进速度的百分比显示。
 >- 根据您的具体焊机型号，对微进速度的更改可能不会反映出来。
[__SOURCE](1_Basic_information/3_Convenient_functions/2_high_speed.md)
# 1.3.2 高速移动功能

当弧焊程序运行时，机器人在焊接部分的移动速度非常慢。这导致在测试运行时验证机器人的工作位置消耗了大量时间。

为了解决这个问题，我们提供了一种高速移动功能，使机器人能够以比其记录速度更快的速度通过焊接部分。

{% hint style="info" %}
该功能仅限于在手动模式下的前进/后退移动时操作。
{% endhint %}  

当高速移动功能启用时，机器人的移动速度不受条件设置中**“前进/后退时的最大速度”**的限制。此外，您可以在焊接部分启用或禁用高速移动功能，无论其当前的应用状态如何（例如，您可以在其当前在焊接部分运行时禁用它）。

操作方法如下：

### 手动最大速度前进/后退

| 项目              | 描述              |
| --------------- | --------------- |
| **专用按键**         | `[Shift]+[FWD]` <br> `[Shift]+[BWD]` |
| **功能**          | 以手动最大速度前进/后退机器人。 |

### 在高速移动期间处理 `[SHIFT]` 键的变化
|        | 在高速移动期间释放 `[SHIFT]` 键 | 在教学速度前进/后退期间按下 `[SHIFT]` 键 |
| ------ | --------------------- |--------------------- |
| **操作** | 以手动最大速度前进/后退机器人。 | 机器人停止，然后以手动最大速度移动 |

[__SOURCE](1_Basic_information/3_Convenient_functions/3_change_iv.md)
# 1.3.3 焊接过程中改变电流/电压

此功能在教授弧焊任务时使用，当需要在焊接过程中改变焊接电流/电压以找到合适的设置时。

使用此功能，可以在焊接过程中实时改变电流/电压，以寻找最佳条件，然后立即将验证后的条件保存为焊接参数。

此功能的详细内容和设置方法如下：  <br/>
("%"指的是相对焊机最低值和最高值之间的单位)

---

### 进入弧焊电流/电压变化对话框

![](../../_assets/1_3_1.png)<br>
*图 1.3.1. 弧焊程序及电流/电压变化*

<br>

1. 在自动模式下进行弧焊。
2. 导航至`[pane layout] - 选择 - 电弧变更 IV ([pane layout] - select - arc change IV)`
3. 点击**[+/-]**按钮以进入调整按钮窗口。

---

### 弧焊过程中的参数调整键  

|      | [+ 电流]/[- 电流]                   |`[SHIFT]` + [+ 电流]/[- 电流] |
| ------ | --------------------- |--------------------- |
| **功能** | 焊接电流 1% +/-         | 焊接电流 5% +/-|  

<br/>


|      | [+ 电压]/[- 电压]                   |`[SHIFT]` + [+ 电压]/[- 电压] |
| ------ | --------------------- |--------------------- |
| **功能** | 焊接电压 1% +/-         | 焊接电压 5% +/-|  

<br/>


|      | [+ 编织 L]/[- 编织 L]                   |`[SHIFT]` + [+ 编织 L]/[- 编织 L] |
| ------ | --------------------- |--------------------- |
| **功能** | 编织宽度(左) 0.1[mm] +/-         |编织宽度(左) 0.5[mm] +/-|  

<br/>


|      | [+ 编织 R]/[- 编织 R]                   |`[SHIFT]` + [+ 编织 R]/[- 编织 R] |
| ------ | --------------------- |--------------------- |
| **功能** | 编织宽度(右) 0.1[mm] +/-         |编织宽度(右) 0.5[mm] +/-|  

<br/>


|      | [+ 频率]/[- 频率]                   |`[SHIFT]` + [+ 频率]/[- 频率] |
| ------ | --------------------- |--------------------- |
| **功能** | 编织频率 0.1[Hz] +/-         | 编织频率 0.5[Hz] +/-|  

<br/>


---

### 弧焊电流/电压自动保存设置

- 导航至`[F2: 系统] - 4: 应用参数 - 2: 弧焊 ([F2: System] - 4: Application parameter - 2: Arc welding)`
- **[弧焊 I/V 变化自动保存]**
    - **禁用**  
    不保存

    - **启用**  
    用户更改值后立即保存至焊接条件

---

### 操作

对话框中每个项目的详细信息如以下图所示。

![](../../_assets/1_3_2.png)<br>
*图 1.3.2. 弧焊变化 I/V 对话框*

{% hint style="info" %}
- 电流/电压的变化仅保存到焊接开始条件，而不保存到结束条件。

- 如果```arcon```命令特别指定电流和电压值，则更改将仅保存到焊接条件中。

例如：arcon cnd=1,cur=200,vol=20 # 改变的电流和电压保存到焊接开始条件 #1.
{% endhint %}
[__SOURCE](1_Basic_information/3_Convenient_functions/4_manual_mode.md)
# 1.3.4 手动模式弧焊

一般来说，弧焊只有在机器人运行于自动或远程模式时才可能。

手动模式弧焊是一种允许在机器人处于手动模式时进行焊接的功能。这对于在设置期间反复测试各种焊接条件非常方便。

要使用手动模式弧焊，应按如下设置。

 (1) 转到 `[F2: 系统] - 4: 应用参数 - 2: 弧焊 - 手动模式下启用弧焊 ([F2: System] - 4: Application parameter - 2: Arc welding - Arc welding enable during manual mode)` 并检查启用。

 (2) 将 **[运行到（执行单元）] 设置为 "结束"**（TP左侧的第二个菜单）。

 (3) 使用前进步骤执行 ```arcon```。 <br/>
 * 注意：如果在焊接期间（在 ```arcoff``` 之前）由于暂停的前进运动而导致机器人停止，```arcon``` 在您再次前进时将不会执行。在这种情况下，机器人将移动到下一个教学点而不进行焊接。
[__SOURCE](1_Basic_information/3_Convenient_functions/5_vibration_reduction.md)
# 1.3.5 高重量弧焊枪振动减震功能

此功能旨在减少在小型机器人上使用重型焊枪（例如水冷焊枪或推拉焊枪）时可能发生的振动。您可以按照以下描述配置此功能。

- `[F2: 系统] - 4: 应用参数 - 2: 弧焊 - 高重量焊枪用减震功能设置 ([F2: System] - 4: Application parameter - 2: Arc welding - Vibration reduction for heavy torch)`: 禁用 / 焊接点 / 全范围

为了减少振动，提供两种方法，每种方法都有其优缺点。您可以参考下面的优缺点，以选择最适合您情况的方法。


| Item | Description |
| --- | --- |
| **禁用**  |  |
| **焊接点**  | 显著减少大量振动。对机器人循环时间没有影响。 |
| **全范围** | 减少大部分振动。增加机器人循环时间。 |
[__SOURCE](1_Basic_information/3_Convenient_functions/6_signal_test.md)
# 1.3.6 弧焊信号测试功能

弧焊信号测试功能允许您测试关键焊接信号的输入/输出状态并手动释放电线突出。此功能对于检查焊机和通信的状态非常有用，因为它确认特定信号是否正常工作。

要使用此功能，请在TP上依次按`[pane layout] - 选择 - 弧焊 ([pane layout] - select - arc welding)`。在弧焊面板中，向下滚动以查看输入/输出信号项目。

![](../../_assets/1_3_3.png)<br>
*图 1.3.3. 弧焊监控*

| 项目 | 描述 |
| ------------- | ---------------------------------------------------------- |
| **输出信号** | 选择所需的输出信号后，单击**[手动输出]**按钮以测试打开/关闭信号。 |
| **输入信号**| 您可以验证输入信号是否根据其操作正确接收。 |
| **命令值**| <li>**手动电线突出释放**: 选择“突出检查”，然后单击**[手动输出]**按钮。</li> <li>**手动焊机错误重置**: 选择“焊机错误重置”，然后单击**[手动输出]**按钮。</li>|
[__SOURCE](1_Basic_information/3_Convenient_functions/7_operation_info.md)
# 1.3.7 电弧焊操作信息

此功能允许您监控电弧焊的操作信息。利用此功能，您可以轻松检查和管理以下方面：

要使用此功能，在 TP 上，依次按下 `[pane layout] - 选择 - 电弧操作信息 ([pane layout] - select - arc operation info.)`。 

![](../../_assets/1_3_4.png)<br>
*图 1.3.4. 电弧焊操作信息监控*  

| 项目 | 描述 |
| --- | --- |
| **自初始化以来** | 显示焊接时间，以及**自系统初始化以来**的自动重试次数和自动焊丝伸出释放计数。 |
| **自开机以来** | 显示焊接时间，以及**自系统开机以来**的自动重试次数和自动焊丝伸出释放计数。 |
| **上一个循环** | 显示焊接时间，以及**上一个循环的**自动重试次数和自动焊丝伸出释放计数。 |
| **当前循环** | 显示焊接时间，以及**当前循环的**自动重试次数和自动焊丝伸出释放计数。 |
| **重叠计数（按原因）** | 显示机器人在焊接过程中停止时发生的重叠次数，并按停止原因分类。 |
| **清除（在 fbt 上）** | 当电弧焊操作信息窗口激活时，**[清除]** 按钮会出现。点击此按钮将显示操作信息清除对话框。您可以点击希望清除的项目按钮以执行所需的操作。 |
[__SOURCE](2_Command/README.md)
# 2. 插入命令
[__SOURCE](2_Command/1_arcon.md)
# 2.1 arcon


### Description

```arcon``` 命令用于启动弧焊过程。此命令可以以4种不同的形式使用。然而，未被配置焊机支持的命令不能被使用。
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
| **Arc Welding Condition Number** | 用于启动弧焊的焊接条件编号以及特定条件（1~100） | Variable |
| **Job Number of the Welder** | 存储在焊机中的作业编号（仅适用于支持作业模式的焊机）（0 ~ 9999） | Variable |
| **Current** | 弧焊的输出电流值（0 ~ 500）[A] | Variable |
| **Voltage** | 弧焊的输出电压值（20 ~ 40）[V] | Variable |
| **Voltage Offset** | 弧焊过程中协同电压的电压偏移值（-200 ~ 200）[V] | Variable |


### Example

```python
   arcon  # 使用先前设置的焊接条件启动焊接。不会执行重试或重启。
   arcon cnd=1  # 根据指定的焊接启动条件启动焊接（cnd=1）
   arcon cnd=1,cur=200,vol=22  # 使用指定的电流和电压（200A, 22V）启动焊接，同时其他焊接条件遵循指定焊接启动条件编号（cnd=1）的设置
   arcon cnd=1,job=5 # 在作业模式下启动焊接，使用作业编号5。其他焊接条件遵循指定焊接启动条件编号（cnd=1）的设置
```  

### Details  

请参阅 [[5. Editing Arc Welding Conditions]](../5_Condition_editing/README.md) 
<br/>


{% hint style="warning" %}
[Caution]
 - 某些焊机型号可以将各种焊接设置作为作业内部存储。在这种情况下，您可以使用“焊机的作业编号”项目。
{% endhint %}
[__SOURCE](2_Command/2_arcoff.md)
# 2.2 arcoff

### 描述

```arcoff``` 命令用于停止弧焊。此命令可以使用两种不同形式。然而，配置的焊机不支持的命令无法使用。

<br/>

### 语法

```python
arcoff
arcoff welder=<Condition Number>, delay=<Delay Time>
```  


### 参数

| 项目 | 意义 | 备注 |
| --- | --- | --- |
| Condition Number | 使用两个焊机时，设置要关闭的焊机编号。（1 ~ 2） | 变量 |
| Delay Time | 使用两个焊机时，设置关闭的延迟时间。（1 ~ 2） | 变量 |


### 示例

```python
    arcoff                    # 在没有任何特殊关闭过程的情况下终止弧焊
    arcoff welder=2, delay=1  # 在1秒延迟后关闭第二台焊机的弧。
```  


### 详细信息 

请参阅 [[5. 编辑弧焊条件]](../5_Condition_editing/README.md) 
[__SOURCE](2_Command/3_weavon.md)
# 2.3 编织开启

### 描述
```weaving on``` 命令用于启用编织条件。您可以进入属性窗口，为指定的条件编号设置相应的编织条件。  
<br/>

### 语法

```python
    weaving on, cnd=<Weaving Condition number>
```  

### 参数

| 项目 | 含义 | 备注 |
| --- | --- | --- |
| **编织条件编号** | 加载编织条件编号 (1 ~ 1000) | 变量 |


### 示例

```python  
   weaving on, cnd=1    # 加载并执行编织条件编号 1
   arcon cnd=1          # 用弧形条件编号 1 执行
   move L,spd=100cm/min,accu=0,tool=0   # 在移动机器人时，根据以上编织条件执行
```  


### 详情  
  请参阅 [[6. 编织功能]](../6_Weaving_function/README.md)
[__SOURCE](2_Command/4_weavof.md)
# 2.4 停止织造


### 描述

```weaving off``` 命令用于停止织造运动。  
<br/>

### 语法

```python
weaving off
```  

### 示例

```python
   weaving off
```  

### 详情

  请参阅 [[6. Weaving Function]](../6_Weaving_function/README.md)
[__SOURCE](2_Command/5_arccond.md)
# 2.5 arccond


### Description

```arccond``` 命令用于使用焊接数据库 (DB) 配置作业，或使用焊接数据库持续更改焊接条件。  
<br/>

### Syntax

```python
arccond <Interpolation type>, cnd=<Condition Number>, gap=<Gap>, spd=<Welding Speed>, rd=<Wall Direction(right distance)>, ld=<Cross Direction(left distance)>, freq=<Weaving Frequency>, cur=<Current>, vol=<Voltage>
```  

### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **Interpolation Type** | 插值条件设置 (D: 立即更改, L: 线性插值更改)| Character |
| **Condition Number**| 存储焊接数据库 (WDB) 和插值条件的条件编号 (1 ~ 1000) | Variable  |
| **Gap** | 输入的间隙值 (-1 ~ 1000) [mm]| Variable  |
| **Welding Speed**| 立即更改的焊接速度 (1 ~ 1000) [cm/min]| Variable  |
| **Wall Direction**  | 立即更改的编织墙面方向宽度 (1 ~ 50) [mm]| Variable  |
| **Cross Direction** | 立即更改的编织交叉方向宽度 (1 ~ 50) [mm]  | Variable  |
| **Weaving Frequency**  | 立即更改的编织频率 (1 ~ 10) [Hz]  | Variable  |
| **Current**| 立即更改的焊接电流  (范围因焊机设置而异)| Variable  |
| **Voltage**| 立即更改的焊接电压  (范围因焊机设置而异)| Variable  |


### Example

```python
  	arccond D, cur=170, vol=10 # 用170A电流和10V电压立即更改
  	arccond D, spd=80, rd=20, ld=20, freq=1.5 # 用80cm/min的焊接速度、20mm的编织宽度和1.5Hz的频率立即更改
  	arccond D, cnd=1 # 立即更改到条件编号1
  
  	arccond L, cnd=1  
    ...               # 焊接步骤 (焊接区域的移动命令)
    arccond L, cnd=2  # 使用WDB数据通过线性插值从条件1连续更改到条件2
```  

### Details  

  Refer to [[8.1 Arccond - Arc Weld Condition]](../8_Application_function/1_Arc_cond/README.md)
[__SOURCE](2_Command/6_refp.md)
# 2.6 refp

### Description

```refp``` 命令用于输入编织运动的参考点。它输入编织墙和进入方向等参考点。
<br/>

### Syntax

```python
refp <参考点编号>
refp <参考点编号>,<姿态(数量)>
```  

### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **参考点编号** | 设置参考点类型的编号 (1 ~ 8) | Variable |
| **姿态** | 输入参考点的姿态 (但是，如果使用了隐藏姿态，它将被省略) | Variable |


### Example

```python
   refp 1,P1                   # 使用 P1 指定编织的墙面方向
   refp 1                      # 指定编织隐藏姿态的墙面方向
   refp 2, (-1073.33, 739.01, 258.30, 0, 76, 23)  # 指定编织表面的位置信息
```  

### Details
  参见 [[6. Weaving Function]](../6_Weaving_function/README.md)  


{% hint style="warning" %}
-	```refp``` 命令与 ```move``` 命令一样，属于步骤类别。
- 当使用用户键输入 ```refp``` 命令时，它将采用隐藏姿态的形式。
- 在将执行单元设置为 Cmd 或 Step 之后，您可以移动到教导的位置。  
{% endhint %}
[__SOURCE](2_Command/7_lvson.md)
# 2.7 lvs

### Description 

```lvs``` 命令使用 LVS(激光视觉传感器) 执行功能，例如获取激光位置的姿态(`seam_find`)、起始点检测(`搜索 (search)`)和缝线跟踪(`track`)。
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
        <td> 打开激光 </td>
      </tr>
      <tr>
        <td>`laser_off`</td>
        <td> 关闭激光 </td>
      </tr>
      <tr>
        <td>`搜索 (search)`</td>
        <td> 在执行跟踪功能之前找到起始点并为跟踪做准备 </td>
      </tr>
      <tr>
        <td>`step_search`</td>
        <td> 找到基材的步骤差，并将其保存为姿态在 `sp` 中。 </td>
      </tr>
      <tr>
        <td>`track`</td>
        <td> 当遇到 `arcon` 时开始跟随焊接线（必须先执行 `搜索 (search)`） </td>
      </tr>
      <tr>
        <td>`track_stationary`</td>
        <td> 执行停止跟踪功能。 </td>
      </tr>
      <tr>
        <td>`seam_find`</td>
        <td> 反映激光感应位置的当前位置并转换为姿态，然后保存到 `sp` 中。 </td>
      </tr>
      <tr>
        <td>`seam_find_p`</td>
        <td> 将当前激光感应位置转换为姿态，并保存到 `sp` 中。 </td>
      </tr>
      <tr>
        <td>`auto_calib`</td>
        <td> 执行工具与 LVS 传感器之间的自动校准。 </td>
      </tr>
    </tr>
    <tr>
      <td colspan="2">Condition Number</td>
      <td> 执行 LVS 功能时使用的条件编号 (1 ~ 32)。每个条件编号的属性窗口不同，这些信息在跟踪期间使用。 </td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">Seam Number</td>
      <td>指定缝线编号。该编号发送到 LVS 控制器，LVS 传感器感应与该编号对应的缝线</td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">Seam Pose</td>
      <td> 指定用于保存 `seam_find` 找到的姿态或 `搜索 (search)` 后找到的姿态的姿态变量 </td>
      <td>姿态变量</td>
    </tr>
  </tbody>
</table>  

### Example

```python
    lvs seam_find, cnd=1, seam=10, sp=p10    
    # 使用条件编号 1 和缝线编号 10 执行缝线查找，将结果姿态保存到 p10
    lvs track, cnd=1 ,seam=10 , sp=p10
    # 使用条件编号 1 和缝线编号 10 启动 LVS 缝线跟踪
```  


{% hint style="info" %}
  作为可选功能使用，请联系我们的公司。
{% endhint %}


### Details  

  参考 [[8.5 LVS(激光视觉传感器) 缝线查找和跟踪]](../8_Application_function/5_LVS_tracking/README.md)
[__SOURCE](2_Command/8_lps.md)
# 2.8 lps

### Description 

```lps``` 命令用于执行一些功能，例如使用激光测距传感器获取激光位置的姿态（点模式）、检测阶梯差（步进模式）和寻找焊缝（扫描模式）。

<br/>

### Syntax

```python
    lps auto_calib, cnd=<Condition Number>, Tx=<工具基准的X方向移动距离>, Ty=<工具基准的Y方向移动距离>
    lps spot, cnd=<Condition Number>, sp=<存储姿态>
    lps stepp, cnd=<Condition Number>, Tx=<工具基准的X方向移动距离>, Ty=<工具基准的Y方向移动距离>, spd=<机器人速度>, sp=<存储姿态>
    lps scan, cnd=<Condition Number>, Tx=<工具基准的X方向移动距离>, Ty=<工具基准的Y方向移动距离>, spd=<机器人速度>, sp=<存储姿态>
    # 当使用主模式/生产模式时
    lps scan, cnd=<Condition Number>, Tx=<工具基准的X方向移动距离>, Ty=<工具基准的Y方向移动距离>, spd=<机器人速度>, sp=<存储姿态>, mp=<主模式下保存的姿态>, ms=<生产模式下计算的移位变量>
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
        在工具和传感器之间执行自动校准。
      </td>
      </tr>
      <tr>
      <td>`点 (spot)`</td>
      <td>
        在点模式中，获取激光指示的位置的姿态。
      </td>
      </tr>
      <tr>
      <td>`stepp`</td>
      <td>
        在步进模式中，获取激光移动时输出值突然变化位置的姿态。
      </td>
      </tr>
      <tr>
      <td>`scan`</td>
      <td>
        在扫描模式中，获取沿激光移动路径估计为焊点的位置的姿态。
      </td>
      </tr>
    </tr>
    <tr>
      <td colspan="2">cnd</td>
      <td>
        执行 LPS 功能时使用的条件编号（1 到 8）。
        命令属性窗口中显示的信息根据条件编号而异。
        此信息用于自动校准和步进模式中的灵敏度设置，以及存储姿态时的坐标系配置。
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">`Tx / Ty`</td>
      <td>
        设置基于工具的X或Y方向的移动距离。
        除了auto_calib，两个值中只能输入一个。
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">`spd`</td>
      <td>
        指定在执行操作时机器人移动的速度。
      <td>Variable</td>
    </tr>
    <tr>
      <td colspan="2">`sp`</td>
      <td>
        指定当前通过每个命令找到的姿态存储的姿态变量。
      <td>Pose Variable</td>
    </tr>
    <tr>
      <td colspan="2">`mp`</td>
      <td>
        在主模式下，感测结果存储在 mp（主姿态）中。
        在生产模式下，用于计算 ms（主移位）。
      <td>Pose Variable</td>
    </tr>
    <tr>
      <td colspan="2">` (ms)`</td>
      <td>
        在生产模式下使用的移位变量。
        计算并存储主姿态（mp参数）与当前感测姿态（sp参数）之间的差。
      <td>Shift Variable</td>
    </tr>
  </tbody>
</table>  


### Example

```python
    lps auto_calib, cnd=1, Tx=50, Ty=-100
    # 在指定的 +50 的 X 方向和 -100 的 Y 方向的距离范围内，根据工具，使用条件编号 1 执行自动校准
    lps spot, cnd=1, sp=p10
    # 使用条件编号 1，将当前激光位置的姿态存储在 p10 中，基于条件设置中定义的坐标系统。
    lps stepp, cnd=1, Tx=50, sp=p10
    # 使用条件编号 1，基于工具在 X 方向移动 50[mm]，在检测到阶梯差时立即停止，并将姿态存储在 p10 中。
    lps scan, cnd=1, Tx=50, spd=10, sp=p10
    # 使用条件编号 1，基于工具在 X 方向以 10 的速度移动 50[mm]，在完成移动后检测焊点，并将其存储在 p10 中。
    # 条件编号 1番，工具基准X方向上移动50[mm]并检测焊点，将其存储在 p10 中
    
    lps scan, cnd=1, Tx=50, spd=10, sp=p10, mp=mp10, ms=ms10
    # 当使用主模式时：使用条件编号 1，基于工具在 X 方向以 10 的速度移动 50[mm]，在完成移动后检测焊点，将其存储在 p10，中与 mp10 进行比较，并将计算的移位值保存到 ms10 中。
```  


{% hint style="info" %}
要将此功能用作可选功能，请联系我们的公司。
{% endhint %}


### Details

  请参见 [8.7 LPS(Laser Point Sensing)](../8_Application_function/7_LPS/README.md)
[__SOURCE](2_Command/9_hsenson.md)
# 2.9 heightsen on

### Description 

```heightsen on``` 命令启动高度感应功能（AVC，弧长控制）。  


### Syntax
```python
    heightsen on, cnd=<Condition Number>
```  

### Parameter

| Item | Meaning | Remarks |
| --- | --- | --- |
| **Condition Number** | 用于开始弧焊的焊接条件的编号和特定条件 (1 ~ 8) | Variable |


### Example

```python   
    heightsen on, cnd=1        # 使用条件编号 1 启动高度感应。
```  


### Details
  请参阅 [[8.4 Height Sensing]](../8_Application_function/4_Height_sensing/README.md)
[__SOURCE](2_Command/10_hsensoff.md)
# 2.10 heightsen off

### Description

```heightsen off``` 命令用于停止高度感应功能 (AVC, Arc Voltage Control)。

<br/>

### Syntax
  
```python
heightsen off
```  

### Example

```python   
   heightsen off            # 结束高度感应执行
```  

### Details
  Refer to [[8.4 Height Sensing]](../8_Application_function/4_Height_sensing/README.md)
<br/>
[__SOURCE](2_Command/11_multipass.md)
# 2.11 multipass

### Description  

```multipass``` 命令用于多次焊接，以重现弧感应路径。  
使用此命令时，您可以通过指定的偏移量重现原始弧焊路径来进行焊接。  
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
      <td>`保存 (save)`</td>
      <td>多次轨迹保存</td>
    </tr>
    <tr>
      <td>`load`</td>
      <td>多次轨迹加载</td>
    </tr>
    <tr>
      <td>` (off)`</td>
      <td>多次关闭</td>
    </tr>
    <tr>
      <td colspan="2">多次轨迹编号</td>
      <td> 用于保存/加载多次的轨迹编号 (1 ~ 50)</td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">轨迹保存间隔距离</td>
      <td> 保存多次轨迹时的采样间隔距离 (5 ~ 100)[mm] </td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">横向偏移距离</td>
      <td> 从原始弧感应路径向左/右方向的偏移距离 (-20 ~ 20)[mm] </td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">纵向偏移距离</td>
      <td> 从原始弧感应路径向上/下方向的偏移距离 (-20 ~ 20)[mm] </td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">多次运行方向</td>
      <td> 是否在反向重新生成路径 (0: 向前, 1: 反向) </td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">焊枪偏移角度 (前/后)</td>
      <td> 在多次重现过程中，焊枪在前/后方向的倾斜角度偏移 (-20 ~ 20)[度] </td>
      <td>变量</td>
    </tr>
    <tr>
      <td colspan="2">焊枪偏移角度 (左/右)</td>
      <td> 在多次重现过程中，焊枪在左/右方向的倾斜角度偏移 (-20 ~ 20)[度] </td>
      <td>变量</td>
    </tr>
  </tbody>
</table>  

### Example

```python
     weaving on, cnd=1 
     multipass save, trj=1, period=10       # 保存在轨迹1中，每10mm间隔
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
     # 加载轨迹1，左偏移3mm，向上3mm，前进方向，无角度偏移
S15  move L,R2,spd=50%,accu=0,tool=1       # 移动到多次开始位置
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

### 描述

```posi_calib``` 命令用于执行定位器校准，这是定位器与机器人同步操作所必需的。通常，通过设置对话框进行定位器校准。然而，当使用伺服工具更换器更换定位器时，必须在机器人操作期间更新校准。此命令允许在机器人程序中直接执行校准。

- 有关使用此命令的详细说明，请参阅 [2.3.4 posi_calib](https://hrbook-hrc.web.app/#/view/doc-positioner-sync/zh/2-system_settings/2-3-positioner-calibration/4_posi_calib?cont_model=${cont_model})
[__SOURCE](2_Command/13_touchsen.md)
# 2.13 touchsen

### 描述

```touchsen``` 命令执行线触摸感应。您可以在属性窗口中配置感应类型和条件。
在使用 `移动 (move)` 命令移动到所需的感应位置后，执行 `touchsen` 命令会根据指定的感应类型和条件自动在该位置启动触摸感应。

<br/>

### 语法

```python
touchsen cnd=<Condition number>, crd=<Coordinate System>, dir=<Direction>, pose=<Pose to save>
touchsen cnd=<Condition number>, crd=<Coordinate System>, dir=<Direction>, rotation=<Sensing Angle>, pose=<Pose to save>
touchsen cnd=<Condition number>, crd=<Coordinate System>, dir=<Direction>, lift_up=<Lifting Distance>, criteria=<Detection Threshold in Detect Groove>, pose=<Pose to save>, gap=<butt gap value>
touchsen cnd=<Condition number>, crd=<Coordinate System>, dir=<Direction>, mpose=<Pose to save in Master Mode>, mshift=<Shift Variable Calculated in Production Mode>
```  

### 参数

| 项目 | 含义 | 备注 |
| --- | --- | --- |
| **Condition number** | 触摸感应条件编号 (1 ~ 1000) | 可变 |
| **Coordinate System** | 用于定义感应方向的坐标系统 ("robot", "base", "tool", "tool_prj") | 可变 |
| **Direction** | 触摸感应方向 (受支持方向因感应类型而异) ("+x", ["+x", "-z"], ["+ty", "+tz"]) | 字符串数组 |
| **Pose to save** | 指定将存储感应结果的姿态变量。 | 可变 |
| **Sensing Angle** | 应用于根据所选坐标系统的感应方向的旋转角度 (Y+30, Y-30, X+30, X-30, TL+30, TL-30, TY+30, TY-30) | 可变 |
| **Lifting Distance** | 机器人在底部检测后向上移动的距离 | 可变 |
| **Criteria(Detection Threshold in Detect Groove)** | 瓦沟检测的参考距离[mm] | 可变 |
| **Butt Gap Value** | 通过触摸感应测量的下缝隙，存储为变量的 Butt 或 V-groove 类型 | 可变 |
| **mpose(Pose to save in Master Mode)** | 在主模式下，感应结果存储在 `mpose` 中。在生产模式下，`mpose` 用于计算 `mshift`。 | 可变 |
| **mshift(Shift Variable Calculated in Production Mode)** | 在生产模式下，`mshift` 存储计算出的位移值作为向量差异: (当前感应姿态 - 主姿态) | 可变 |

### 示例

```python
    var var1=0      # 声明一个变量以存储在 Butt joint 感应过程中测量的缝隙。
    var P10=cpo()   # 声明一个姿态变量 `P10` 并将当前姿态保存到它。
    touchsen cnd=2, crd="tool", dir=["+y"], lift_up=3, pose=P10, gap=var1  # 条件 2，在工具坐标系统中，底部感应后抬升3mm，并将缝隙存储在 var1 中
    touchsen cnd=1, crd="tool", dir=["tf", "td"], pose=P10, 0  # 条件 1，在工具投影坐标系统中，2点
    touchsen cnd=1, crd="base", dir=["+x","-y","-z"], pose=P10, 0  # 条件 1，在基座坐标系统中，3点
```  

### 细节
  参考 [[8.2 Touch Sensing]](../8_Application_function/2_Touch_sensing/README.md)
<br/>
[__SOURCE](2_Command/14_stitch.md)
# 2.14 缝合

### 描述

```stitch``` 命令执行缝合焊接。您可以通过将光标放在命令上并单击 **属性** 按钮来设置缝合条件。
在使用 `移动 (move)` 命令移动到所需的缝合焊接位置后，使用 `arcon` 命令一起进行缝合。
当缝合功能被执行时，缝合焊接从指定位置开始，并持续到缝合操作完成。  
<br/>

### 语法

```python
stitch on, cnd=<Condition Number>
stitch off
```  


### 参数

| 项目 | 说明 | 备注 |
| --- | --- | --- |
| **条件编号** | 缝合条件编号 (1 ~ 1000) | 可变 |


### 示例
```python
   stitch on, cnd=2         #  执行缝合在条件 2
   stitch off               #  终止缝合
```


### 详细信息  
  请参阅 [[8.6 STITCH Function]](../8_Application_function/6_Stitch/README.md)
[__SOURCE](2_Command/15_calcshift.md)
# 2.15 calshift

### 描述  

```calshift``` 命令使用两个姿态变量计算位移。  
它通常用于根据触觉传感器保存的姿态变量计算位移。  
<br/>

### 语法

```python
<Shift Val>=calshift(<Pose Val 1>, <Pose Val 2>)
<Shift Val>=calshift(<Pose Val 1>, <Pose Val 2>,"TV")
```  

### 参数

| 项目 | 含义 | 备注 |
| --- | --- | --- |
| **位移变量输入** | 输入要存储计算位移的位移变量 | 位移变量 |
| **姿态变量输入** | 输入姿态变量 (1 ~ 9999) | 姿态变量 |
| **TV** | 计算与工具垂直的方向上的位移 (1 ~ 9999) | 字符串 |

### 示例

```python
    move L, spd=30%, ...
    var pose_1 = cpo()
    move L, spd=30%, ...
    var pose_2 = cpo()
    var sft_1
    sft_1=calshift(pose_1,pose_2)   
    # 计算 pose_1 和 pose_2 之间的矢量位移，并将结果存储在 sht_1 中
```  
[__SOURCE](3_Property/README.md)
# 3. 命令属性
[__SOURCE](3_Property/1_overall.md)
# 3.1 概述

在教授弧焊程序时，不仅需要焊接条件，如电压和电流，还需要与编织、重试/重叠以及焊接机特性相关的详细设置。此外，在一般机器人操作中，可能需要验证所教步骤或辅助点的位置信息（坐标和方向）。  
通过将光标放在命令上并按下位于 TP 左侧的 `[Property]` 按钮，提供了一个便捷快速编辑这些文件的功能。


### 命令 [Property] 示例

| 命令 | 属性 | 
| -----| -------| 
| `arcon (arcon )`| 设置电流、电压、协同、初始/辅助/结束条件等。 | 
| `weaving on (weaving on )`| 设置编织类型、频率、宽度和编织方向等。 |
| `lvs (lvs )`| 配置跟踪相关信息、接缝查找设置等。 |
| `arccond (arccond )`| 管理焊接条件数据库（WDB），并设置电流、电压、频率和编织宽度。 |
| `移动 (move )`| 将当前记录的位置更改为基坐标系、机器人坐标系或关节坐标系。 |



作为编辑焊接开始条件的示例，当光标放在 `arcon` 命令上时，按下 `[Property]` 按钮将显示当前用于焊接开始条件的条件编号的详细信息。在此界面中，您可以查看或修改焊接开始条件的详细设置。

同样，在特定命令上放置光标并进入 `[Property]` 窗口后，您可以轻松快速地检查和修改设置，例如步骤中记录的条件或位置。如果您希望保存更改并退出，请按 `[OK]`；如果您希望在不保存的情况下退出，请按教师挂件上的 `[ESC]` 键。


![](../_assets/3_1_1.png)<br>
*图 3.1.1. 机器人程序命令中的属性*


{% hint style="info" %}
    有关更多详细信息，请参阅 [2. 插入命令]
{% endhint %}
[__SOURCE](4_Setting/README.md)
# 4. 弧焊机设置
[__SOURCE](4_Setting/1_Arc_communication/README.md)
# 4.1 弧焊机通信设置

按照以下步骤使用以太网电缆连接PC和控制器：

1. 在PC上运行**Sycon**程序。
2. 添加cifx卡，然后右键单击其图标并选择**配置**。
3. 按照以下方式配置每个项目：
  **驱动程序**：设置为nexX驱动程序  
  **总线参数**：将波特率设置为250kBits/s  
  **设备分配**：选择添加的cifx卡并点击确定。
4. 右键单击cifx图标并选择**下载**。  
4. 右键单击cifx图标并选择**网络扫描**。

![](../../_assets/4_1_1.png)<br>
*图 4.1.1. Sycon通信状态*  

完成以下步骤后，sycon屏幕将显示如上所示的内容。（当连接到现代PNS焊机时）

6. 右键单击焊机图标并选择**断开连接**，然后转到**配置 > 一般 > UCM**选项卡并设置UCMM为Group3。
7. 右键单击焊机图标并选择**上传**，然后右键单击cifx图标并选择**下载**。

在机器人TP上，导航至`[F2: 系统] - 2: 控制参数 - 2: 输入/输出信号设置 - 6: fb 块分配 ([F2: System] - 2: Control parameter - 2: Input/Output signal setting - 6: fb block allocation)`并分配要使用的块。  
完成后，从焊机传输到控制器的数据将在分配的块中以粗体显示。  
（在`[窗格布局] - 选择 - 公共输入 - 已分配fb块 ([pane layout] - select - public input - assigned fb block)`中验证这一点）

{% hint style="info" %}
  如需更多信息，请参阅[${cont_model} - 工业通信](https://hrbook-hrc.web.app/#/view/doc-industrial-communication/zh-${cont_model}/README?cont_model=${cont_model}) 
{% endhint %}
[__SOURCE](4_Setting/2_Arc_setting/README.md)
# 4.2 电弧焊机设置

用户可以与我们的电弧焊接机器人一起操作各种焊机。为此，提供了编辑焊机特定设置的功能。焊机配置屏幕可以通过以下方式访问: `[F2: 系统] - 5: 初始化 - 3: 用途设置 ([F2: System] - 5: Initialization - 3: Usage setting)`

### 焊机制造商编号
> 当前选择的焊机制造商编号会显示。您可以通过点击 **[焊机信息]** 按钮检查每个制造商的焊机编号。通过点击该屏幕上的 **[焊机设置]** 按钮，将出现所选焊机的条件编辑屏幕。

![](../../_assets/1_2_1.png)<br>
*图 4.2.1. 用途设置对话框* 

</br>

![](../../_assets/4_2_2.png)<br>
*图 4.2.2. 现代焊机条件设置*   

</br>

![](../../_assets/4_2_3.png)<br>
*图 4.2.3. 现代焊机 I/O 信号分配*   

焊机条件屏幕提供与焊机特性相关的编辑功能，因此可编辑的项目因焊机而异。以下项目在焊机条件屏幕中通常可编辑。

| 项目 | 默认值 | 描述 |
|---|------|---|
| 名称                   | 支持的焊机型号名称 | 记录焊机的型号名称 |
| 注释                   | 焊机制造商名称 | 记录焊机的描述 |
| 电弧检出时间          | [0.2] 秒 <br>(范围: 0.1 ~ 10.0) | 在电弧焊接结束后的设置时间内检查焊丝融合 |
| 电弧关闭检测时间     | [0.3] 秒 <br>(范围: 0.0 ~ 10.0) | 设置在电弧焊接期间检测电弧关闭的参考时间。如果电弧关闭时间超过此时间，将被识别为电弧关闭。<br> 如果设置得太低，可能会频繁发生电弧点火故障。<br> 如果设置得太高，机器人移动和焊丝进给将在电弧关闭后持续更长时间，从而增加机器人行驶距离和电弧关闭后的焊丝突出长度。 |
[__SOURCE](5_Condition_editing/README.md)
# 5. 编辑弧焊条件
[__SOURCE](5_Condition_editing/1_Condition_config/README.md)
# 5.1 配置弧焊条件

要执行我们的控制器的弧焊，必须配置焊接机和焊接条件。除了基本的弧焊外，诸如编织或弧感应等特殊功能需要为各自的特性进行详细设置。  
我们公司提供编辑弧焊机特性文件([[4. Arc Welder Settings]](../../4_Setting/README.md))、弧焊应用功能([[1.2.2 Arc Welding various signals and funtion settings]](../../1_Basic_information/2_Function_setting/2_signals_functions.md))和弧焊条件设置的能力，使用户能够在各种环境中使用所需的配置进行焊接，采用多种焊接机。

弧焊条件的结构如下：
- 弧焊开始条件：编辑焊接启动和主要焊接参数的设置
  - 辅助弧焊开始条件：编辑重试和重新启动功能
- 弧焊结束条件：编辑焊接终止的设置
  - 辅助弧焊结束条件：编辑自动焊丝伸出释放
[__SOURCE](5_Condition_editing/2_Time_chart/README.md)
# 5.2 弧焊流程图

这是数字弧焊的时间流程图。有关每个条件设置，请参阅下面每个命令的对话框描述。
 
![](../../_assets/5_2_1.png)<br>
*图 5.2.1. 数字弧焊流程图*
[__SOURCE](5_Condition_editing/3_Start_condition/README.md)
# 5.3 焊接起始条件

当弧焊设置为数字化并且光标放置在命令行 `arcon cnd=_` 时，按下 [property] 键将会打开焊接起始条件的编辑界面。

![](../../_assets/5_3_1.png)<br>
*图 5.3.1. Hyosung 焊机设置*  

![](../../_assets/5_3_2.png)<br>
*图 5.3.2. Fronius 焊机设置*  

![](../../_assets/5_3_3.png)<br>
*图 5.3.3. EWM 焊机设置*

编辑条件后，按下 `[ESC]` 键将关闭对话框而不保存更改，而按下 `[OK]` 键将保存设置并关闭对话框。

以下项目适用于所有焊机。有关特定型号的设置，请参阅以下章节。

共同项目的内容可能因焊机而有名称、单位和范围的不同。请参阅各自的表格了解特定型号的差异。

</br>

---

### (1)	条件编号  
指定要编辑的焊接起始条件编号。(最大: 32)

<center>

| 项目 | 名称 | 范围 |
| :---: | :---: | :---: |
| 所有焊机共同 | 条件编号 | 1 ~ 32 |

</center>

</br>  

### (2)	描述  
记录指定焊接起始条件的描述。

<center>

| 支持的焊机 | 名称 |
| :---: | :---: |
| 所有焊机共同 | 注释 |

</center>

</br>  
    
### (3)	协同代码  
设置要传递给焊机的协同代码。代码值在单独的协同选择屏幕中配置。可以通过按下 `[Synergic Selection]` 按钮访问焊接起始条件屏幕的协同选择屏幕。

<center>

| 支持的焊机 | 名称 | 单位 | 范围 | 默认 |
| :---: | :---: | :---: |:---: | :---: |
| Hyosung | 协同代码 | - |- | 040 |
| Fronius </br>(不支持) |-|-|-|-|
| EWM | 协同号 | - |- | 185|

</center>
    
</br>  

### (4)	焊接电流 / 焊接功率 / 焊丝送进速度  
设置焊接电流值。这是在焊接过程中使用的电流。初始和最终条件的电流是以该值的比率来确定的。
<center>

| 支持的焊机 | 名称 | 单位 | 范围 | 默认 |
| :---: | :---: | :---: |:---: | :---: |
| Hyosung | 焊接电流 | A | 40.0 ~ 350.0 | 100.0 |
| EWM | 焊丝送进速度 |  m/min | 0.0 ~ 25.0 | 3.1 |
| Fronius(TPS) | 焊接功率 | % | 0.0 ~ 100.0 | 100.0 |

</center>
    
</br>

### (5)	焊接电压 / 焊接电压修正 / 焊接电压偏置 / 弧长修正  
在数字焊接中，焊接电压通常不会直接输入，而是基于焊接电流从协同数据中自动选择。如果您想修改由协同数据自动选择的焊接电压，请设置用于根据所选焊接电压进行调整的电压偏置值。
<center>

| 支持的焊机 | 名称 | 单位 | 范围 | 默认 |
| :---: | :---: | :---: |:---: | :---: |
| Hyosung(Indiv.) | 焊接电压 | V | 10.0 ~ 38.0 | 10.0 |
| Hyosung(Synergic) | 焊接电压修正 | % | 50.0 ~ 150.0 | 50.0 |
| EWM | 焊接电压偏置 | VP | -10.0 ~ 10.0 | 2.0 |
| Fronius(TPS) | 弧长修正 | % | -30.0 ~ 30.0 | 0 |
</center>
    
</br>

### (6)	气体预流
设置在开始弧焊之前预流保护气体的时间，以隔离和准备焊接区域。

<center>  

| 支持的焊机 | 名称 | 单位 | 范围 | 默认 |
| :---: | :---: | :---: |:---: | :---: |
| 所有焊机共同 | 气体预流 | 秒 | 0.0 ~ 10.0 | 0.5 |  

</center>

</br>  

### (7)	WCR等待时间  
指示等待 WCR 输入的时间。如果在此时间内未接收到 WCR 信号，将执行重试。然而，如果重试计数设置为 0，将显示错误，并且机器人将停止。重试方法和重试计数可以在焊接辅助条件中配置。(参见 [5.5 焊接辅助条件](../5_Aux_condition/README.md))

<center>

| 支持的焊机 | 名称 | 单位 | 范围 | 默认 |
| :---: | :---: | :---: |:---: | :---: |
| 所有焊机共同 | WCR等待时间 | 秒 | 1.0 ~ 10.0 | 2 |

</center>
    
</br>

### (8)	机器人延迟时间  
在正常启动弧焊后，设置机器人在沿焊接线路移动以进行焊接之前的等待时间。这与初始条件无关，机器人可以在处理初始条件时移动。
<center>

| 支持的焊机 | 名称 | 单位 | 范围 | 默认 |
| :---: | :---: | :---: |:---: | :---: |
| 所有焊机共同 | 机器人延迟时间 | 秒 | 0.0 ~ 10.0 | 0 |

</center>
    
</br>

### (9) 初始条件保持时间  
设置在弧焊开始时保持初始电流值的时间。
<center>

| 支持的焊机 | 名称 | 单位 | 范围 | 
| :---: | :---: | :---: |:---: |
| 所有焊机共同 | 初始条件保持时间 | 秒 | 0.0 ~ 10.0 | 

</center>
    
</br>

### (10) 初始焊接电流 / 焊接功率 / 焊丝送进速度  
设置在弧焊开始时初始条件保持时间内输出的焊接电流。
这是相对于主条件的焊接电流设置为百分比(%)。
<center>

| 支持的焊机 | 名称 | 单位 | 范围 | 默认 |
| :---: | :---: | :---: |:---: | :---: |
| Hyosung | 初始焊接电流 | A | 40.0 ~ 350.0 | 120 |
| Fronius | 初始焊接功率 | % | 20 ~ 200 | 120 |
| EWM | 初始焊丝送进速度 | m/min | 0.0 ~ 25.0 | 3.72 |

</center>
    
</br>

### (11) 初始焊接电压 / 焊接电压修正 / 弧长修正  
设置在弧焊开始时初始条件保持时间内输出的焊接电压。
这是相对于协同电压设置的修正值。  
<center>

| 支持的焊机 | 名称 | 单位 | 范围 | 默认 |
| :---: | :---: | :---: |:---: | :---: |
| Hyosung(Indiv.) | 初始焊接电压 | V | 10.0 ~ 38.0 | 10.0 |
| Hyosung(Synergic) | 初始焊接电压修正 | % | 50.0 ~ 150.0 | 50.0 |
| EWM | 初始焊接电压偏置 | VP | -10.0 ~ 10.0 | 2 |
| Fronius | 初始弧长修正 | %| -30.0 ~ 30.0 | 0 |
</center>
    
</br>

### (12) 斜坡时间  
设置在初始条件与该条件之间进行电流变化处理的时间。
<center>

| 支持的焊机 | 名称 | 单位 | 范围 | 
| :---: | :---: | :---: |:---: |
| 所有焊机共同 | 斜坡时间 | 秒 | 0.0 ~ 10.0 | 

</center>
    
</br>

### (13) 允许超出时间  
设置焊接电压/电流和送进电机电流限制超出的允许时间。如果焊接电压/电流或送进电机电流超过限制时间超过此时间，将执行重启。然而，如果重启计数设置为 0，将显示错误，并且机器人将停止。重启方法和重启计数以及其他与重启相关的功能可以在焊接辅助条件中配置。如果此时间设置为 0 秒，则不会使用弧限制监测功能。
<center>

| 支持的焊机 | 名称 | 单位 | 范围 | 默认 | 
| :---: | :---: | :---: |:---: |:---: |
| 所有焊机共同 | 允许超出时间 | 秒 | 0.0 ~ 10.0 | 0 | 

</center>
    
</br>

### (14) 焊接电压上/下限  
设置焊接过程中的上限和下限电压。如果超过限制的时间超过允许时间，将发生错误。
<center>

| 支持的焊机 | 名称 | 单位 | 范围 | 
| :---: | :---: | :---: |:---: |
| 所有焊机共同 | 焊接电压上/下限 | V | 0.0 ~ 100.0 | 

</center>
    
</br>

### (15) 焊接电流上/下限  
设置焊接过程中的上限和下限电流。如果超过限制的时间超过允许时间，将发生错误。
<center>

| 支持的焊机 | 名称 | 单位 | 范围 | 
| :---: | :---: | :---: |:---: |
| 所有焊机共同 | 焊接电流上/下限 | A | 0.0 ~ 1000 | 

</center>

</br>
    
</br>
[__SOURCE](5_Condition_editing/3_Start_condition/1_hyosung.md)
# 5.3.1 焊接起始条件 - 仅限Hyosung设置

### (1) 焊接模式: `Normal, Pulse`  
设置电弧焊接方法。

### (2)	减速调整: [ 100 ] % (范围: 0 ~ 255)  
在电弧启动之前调整送丝速度的偏移量。

### (3)	电感效应: [  100] % (范围: 0 ~ 255)  
设定电感效应。
[__SOURCE](5_Condition_editing/3_Start_condition/2_fronius.md)
# 5.3.2 焊接启动条件 - 仅限Fronius设置

### (1) 操作模式: `Prog-Std, Prog-Pulse, CMT, JOB, TIG`  
设置Fronius焊机支持的焊接模式。每种模式的描述如下：

- **Prog-Std**: 使用焊机中存储的标准焊接程序。
- **Prog-Pulse**: 使用焊机中存储的脉冲焊接程序。
- **CMT**: 使用冷金属转移功能。
- **JOB**: 使用焊机中存储的作业。
- **TIG**: 使用TIG(钨插入气体)焊接功能。

### (2) 程序/作业编号  
设置从焊机中存储的程序或作业编号。如果操作模式设置为作业，则将使用作业编号。

### (3) 动态修正: [ 0 ]% (范围: -5.0 ~ 5.0)  

设置动态修正值。较小的值会产生强而稳定的弧光，但会增加飞溅量。较大的值会产生更平滑的弧光，并减少飞溅量。
[__SOURCE](5_Condition_editing/3_Start_condition/3_ewm.md)
# 5.3.3 焊接起始条件 - EWM仅适用设置

### (1)	作业模式: `禁用, 启用` 
设置EWM AlphaQ焊机支持的作业模式。每种模式的描述如下：
- 禁用: 焊接是基于存储在焊机中的协同数据进行的，采用送丝速度和电压偏移。
- 启用: 焊接是使用存储在焊机中的作业进行的。

### (2)	焊接模式  
设置是否使用脉冲焊接。

### (3)	超级脉冲功能  
当启用脉冲焊接时，配置使用超级脉冲（2阶段脉冲）功能。

### (4)	作业编号（协同）  
输入用于焊接的协同编号或作业编号。按下TP底部的[协同选择]按钮打开对话框，您可以在其中设置与焊接方法、材料、气体类型和焊丝直径相对应的作业编号。

### (5)	动态修正: [ 0 ] （范围: -40.0 ~ 40.0）  
设置动态修正。较小的值会导致强而稳定的电弧，但会增加飞溅量。较大的值则产生更平滑的电弧并减少飞溅量。

### (6)	升弧启动: `不使用, 使用`  
设置是否在焊接开始时使用升弧功能。使用升弧功能可以减少焊接开始时过多飞溅的发生。
[__SOURCE](5_Condition_editing/4_End_condition/README.md)
# 5.4 焊接结束条件

当电弧焊接设置为数字型，并且在焊接起始条件对话框中按下 [结束条件] 标签时，将出现以下焊接结束条件编辑屏幕。

![](../../_assets/5_4_1.png)<br>
*图 5.4.1. 焊接结束条件设置 (例如 EWM)*

编辑完焊接结束条件后，按下 `[ESC]` 键会在不保存更改的情况下关闭对话框，而按下 `[OK]` 键会保存设置并关闭对话框。

</br>

每个项目的描述如下：

</br>

### (1)	条件编号: [1] (范围: 不允许更改)  
显示焊接起始条件编号。在数字电弧焊接中，结束条件编号和起始条件编号作为一个管理。因此，要更改结束条件编号，也必须更改起始条件编号。

### (2)	结束焊接电流 / 焊接功率 / 送丝速度  
设置在凹坑处理期间要输出的电流值。相对于当前焊接条件（焊接电流、焊接功率和送丝速度），以百分比 (%) 的形式进行设置。然而，对于 EWM 焊机，这以 m/min 的形式设置，与焊接条件相同。

<center>

| 支持的焊机 | 名称 | 单位 | 范围 | 默认 |
| :---: | :---: | :---: |:---: | :---: |
| Hyosung | 结束焊接电流 | A | 28.0 ~ 350.0 | 28.0 |
| EWM | 结束送丝速度 | m/min | 0.0 ~ 25.0 | 2.17 |
| Fronius | 结束焊接功率 | % | 10 ~ 100 | 70 |
</center>

### (3)	结束焊接电压 / 焊接电压校正 / 弧长校正  
设置在凹坑处理期间要输出的电压值。根据设定值指定和输出电压。
<center>

| 支持的焊机 | 名称 | 单位 | 范围 | 默认 |
| :---: | :---: | :---: |:---: | :---: |
| Hyosung(Indiv.) | 结束焊接电压 | V | 10.0 ~ 38.0 | 10.0 |
| Hyosung(Synergic) | 结束焊接电压校正 | % | 50.0 ~ 150.0 | 50.0 |
| EWM | 结束焊接电压偏移 | VP | -10.0 ~ 10.0 | 2 |
| Fronius(TPS) | 结束弧长校正 |  % | -30.0 ~ 30.0 | 0 |

</center>

### (4)	下坡时间（凹坑时间）: [0] 秒 (范围: 0.0 ~ 10.0)  
设置从主条件到结束条件电流变化的处理时间为斜坡。

![](../../_assets/5_4_2.png)<br>
*图 5.4.2. 下坡时间和凹坑时间图*

### (5)	条件保持时间: [1] 秒 (范围: 0.1 ~ 10.0)   
设置在焊接结束条件下“电流比”项目中指定的输出值的维持时间。

### (6)	焊丝回退: [ 0 ] 毫秒 (范围: 0.0 ~ 200.0)  
配置回退处理。根据焊机可能有所不同。

### (7)	气体后流: [ 0 ] 秒 (范围: 0.0 ~ 10.0)  
设置在弧熄灭后继续输出保护气体的时间。

### (8)	凹坑移动时间: [ 0 ] 秒 (范围: 0.0 ~ 10.0) / 凹坑移动距离 : [0] 毫米 (范围: 0.0 ~ 100.0)
在凹坑处理期间，设置机器人在下坡时间和条件保持时间内向后移动的距离。速度是根据距离和时间自动确定的。

### (9) 自动回退释放次数 : [0] 次 (范围: 0 到 9) / 条件 : [0] (范围: 0 到 32) / 时间: [0] 秒 (范围: 0.0 到 10.0)  
在电弧焊接期间，焊接丝在焊接结束时可能会粘附在基材上。为防止这种情况，焊接电源在焊接结束时暂时提高电压作为防粘过程。
然而，即使在此过程后仍可能发生粘附。因此，机器人控制器向焊接电源发送焊后粘附检测信号，以检查是否发生了粘附。
自动回退释放功能在检测到焊接后粘附时自动执行回退释放，从而允许机器人在不停顿的情况下继续操作。
此过程会重复配置的次数。如果超过指定次数仍未释放粘附，机器人将停止。

* 计数 : [0] 次 (范围: 0 到 9)
    此参数指定最大回退释放尝试次数。如果在配置的尝试次数内未释放粘附，将会出现错误。 
    特例是，当设置为 0 时，跳过粘附检查，系统直接进入下一步骤。

* 条件 : [0] (范围: 0 到 32)
    此参数指定用于回退释放过程的焊接条件编号。当设置为 0 时，回退释放是使用当前焊接起始条件进行的。

* 时间: [0] 秒 (范围: 0.0 到 10.0)
    此参数指定维持回退释放条件输出的持续时间。
[__SOURCE](5_Condition_editing/5_Aux_condition/README.md)
# 5.5 焊接辅助条件

当电弧焊接设置为数字并且在焊接启动条件对话框中按下[Auxiliary condition]选项卡时，以下焊接辅助条件编辑屏幕将出现。
[__SOURCE](5_Condition_editing/5_Aux_condition/1_retry.md)
# 5.5.1 焊接辅助条件 - 重试

在开始弧焊时，如果基材焊接起点附近附着了异物，可能会导致弧无法点燃。重试功能会在出现弧点燃失败的情况下自动尝试重新点燃弧，确保在不停机的情况下进行连续操作。

  
![](../../_assets/5_5_1.png)<br>
*图 5.5.1. 焊接辅助条件 (重试) 设置(例如 EWM)*

{% hint style="info" %}
[注意]   
当弧点燃尝试失败后重试功能被激活，而在弧焊过程中焊接中断需要恢复时重启功能被激活。
{% endhint %}

[图 5.5.1]的左侧部分表示焊接辅助条件中的重试条件。每个重试条件的描述如下：

### (1)	 retract Time: [0] 秒 (范围: 0.00 ~ 10.00)  
  重试功能是在喂入焊丝并未能点燃弧后执行的。因此，在重试过程中可能会过量喂入焊丝。在这种情况下，焊丝可能会接触基材，并造成熔合，或过于靠近基材，导致弧点燃不稳定。为了解决这个问题，该功能支持在重试之前回收焊丝，以创建一个最佳的焊接环境。此设置指定了回收焊丝的时间。如果该值不是 0，则焊丝将被回收，焊枪将移动，然后尝试点燃弧。

### (2)	Retract speed: [10] % (范围: 0.0 ~ 100.0)  
  指定在重试过程中焊丝回收的速度。根据焊机型号，此功能可能不被支持。(例如：Saprom 焊机)

### (3)	Repetition: [5] 次 (范围: 0 ~ 9)  
  指定在失败后弧点燃将重试的次数。如果在指定重试次数内未能点燃弧，系统将返回到原点（初始弧点燃尝试点或焊接起点）并停止。

### (4)	Retry condition: [0] (范围: 0 ~ 32)  
  指定用于重试弧点燃的焊接条件编号。在重试期间，将根据输入的焊接起始条件的条件（电流、电压等）进行焊接。
  然而，如果输入的条件编号为“0”或操作模式设置为重新进入，则焊接将基于当前活动焊接起始条件的主要条件进行。

### (5)	Operation mode: ReEnter / Shift / Multi-direc.  
  设置在重试期间焊枪移动的方法。支持三种不同的方法，每个设置的焊枪运动如下：（请参考[图 5.5.2]）

- A. ReEnter  
  当弧点燃失败时，焊枪向后退回到上一步，并尝试再次点燃弧。此向后移动的距离在焊接辅助条件重试设置菜单中的“退回/焊接线距离”下设置。在向后退回一定距离后，焊枪将再次向前移动，因此电压/电流条件遵循焊接起始条件。

- B. Shift  
  在焊接辅助条件的重试条件中，根据设置的移动距离，焊枪返回到弧点燃步骤。移动距离可以在相对于焊接线的前后、左右和上下方向进行设置。在重试期间，焊接条件遵循重试设置中的焊接起始条件。如果弧点燃成功，则保持弧，焊枪以设定速度移动到焊接起点，进行焊接。

- C. Multi-direc.  
  在焊接辅助设置的重试条件中，"移动距离"被划分为前后、左右和上下动作。第一次重试尝试沿焊接线按照前后距离移动。第二次重试尝试考虑设定的左右和上下移动的距离。第三次重试沿第二次重试的左右位置反方向移动。对于重试4-6，按照与重试1-3相比的两倍距离执行相同操作，对于重试7-9，执行三倍距离的相同操作。焊接根据重试设置中的焊接起始条件开始，如果弧点燃成功，则保持弧，焊枪以设定速度移动到焊接起点，进行焊接。

### (6)	Speed: [100] cm/min (范围: 1.0 ~ 999.0)  
  指定焊枪在重试期间移动到重试位置或返回焊接起点的速度。

### (7)	Retreat/Weld line dist.: [3] mm (范围: 0.00 ~ 99.99)   
  当操作模式设置为 ReEnter 时，这是焊枪在重试期间移动的距离。

### (8)	Shift distance: FWD/BWD = [ 2 ], L/R = [ 2 ], Up/Down = [ 1 ] mm (范围: -99.99 ~ 99.99)  
  当操作模式设置为 Shift 时，这是焊枪在重试期间移动的距离。  
    

![](../../_assets/5_5_2.png)<br>
*图 5.5.2 重试功能序列*
[__SOURCE](5_Condition_editing/5_Aux_condition/2_restart.md)
# 5.5.2 焊接辅助条件 - 重新启动  

在电弧焊接过程中，可能由于电弧故障、焊接电流和电压超限、气体压力下降、焊丝短缺、冷却水错误等因素导致过程被中断。  
当从中断的地方重新开始焊接时，存在留下未焊接区域的风险。  
在这种情况下，重新启动功能通过进行重叠焊接来补偿未焊接部分。  

焊接中断后，系统会自动重新启动，或在消除中断原因后恢复操作。  
它会沿焊接线向后移动一定距离，然后恢复焊接。这将在焊接停止的点附近产生一个重叠区域，防止产生未焊接区域。  

本节描述了重新启动条件和重叠设置。

![](../../_assets/5_5_3.png)<br>
*图 5.5.3. 焊接辅助条件（重新启动）设置（例如 EWM）*


### (1) 重新启动重复次数: [ 3 ] 次（范围: 0 ~ 9）  
指定在同一焊接部分内的最大重新启动尝试次数。如果超过此计数，将出现错误“**E1274 在同一焊接部分内重新启动计数超过**”。  

### (2) 重新启动条件: [ 0 ]（范围: 0 ~ 32）  
指定在重叠区域重新启动焊接时要使用的焊接条件编号。焊接将依据指定的初始焊接条件（电流、电压等）进行。  
如果输入的条件编号为“0”，焊接将从重叠点的当前焊接起始条件继续进行。  

### (3) 重叠距离: [ 5 ] 毫米（范围: 0.0 ~ 99.9）  
指定重新启动焊接时的重叠长度（重叠距离）。机器人将向后移动指定的距离，然后恢复焊接。  

### (4) 移动速度: [ 50 ] 毫米/秒（范围: 1.0~150.0）  
指定焊炬移动到重叠起始位置的速度。  
这对应于从③到④部分的运动速度[图 5.5.4]  

### (5) 焊接速度: [ 50 ] 厘米/分钟（范围: 10.0~999.0）  
指定机器人在从起始位置到结束位置进行重叠焊接时的速度。这是[图 5.5.4]中④部分的重叠区域内的速度。  

当在从起始点到结束点（⑤）焊接过程中发生错误，并且如果重叠条件为半自动，用户必须识别焊接停止的原因并处理错误（①）。  
在解决问题后（②），按下`开始 (Start)`按钮（③）将恢复焊接。  
机器人将以`移动速度 (Moving speed)`（④）设定的速度自动移动到重叠起始位置。  
一旦到达该位置，将以`焊接速度 (Welding speed)`进行指定距离的重叠焊接，然后以正常速度继续焊接。  
但是，如果在重叠焊接过程中发生错误，机器人将不再重复重叠，而是直接从该点开始焊接。  

---

![](../../_assets/5_5_4.png)<br>
*图 5.5.4. 重新启动功能顺序*


### (6) 重叠条件设置  
[图 5.5.3]的下半部分定义了在由于电弧关闭（电弧故障）、超出限值、气体关闭（气体压力下降）、焊丝关闭（焊丝短缺）或冷却液关闭（冷却液错误）等原因导致焊接过程被中断时如何进行重叠焊接。  

- A. 自动  
此设置会自动执行重叠焊接。只有在因电弧停顿导致焊接中断时才能进行配置。  
在焊接过程中发生电弧停顿时，过程不会停止。相反，重叠焊接将根据焊接辅助条件的重新启动部分中设置的方法进行，之后主要过程将恢复。  
然而，如果在重叠焊接段期间电弧再次停止，焊接将会立即从该位置恢复。  

- B. 半自动  
此设置允许用户手动执行重叠焊接。如果发生电弧关闭、超出限值、气体压力下降、焊丝短缺或冷却液错误等问题时，焊接将被中断，机器人也会停止。  
在处理完原因后，用户必须按下`开始 (Start)`，此时将根据焊接辅助条件的重新启动部分设置的方法执行重叠焊接，然后主要过程恢复。  
此时，如果用户使用手动功能将机器人移至其他位置并按下`开始 (Start)`，则将直接移动到重叠焊接位置并继续焊接。  

- C. 忽略  
此设置会忽略错误。当启用此设置时，即使焊接被中断，机器人也会继续过程。换句话说，无论电弧停止或超出设定限值，过程都会继续。  
此方法只能适用于因电弧停止或超出限值导致焊接过程被中断，并且过程正在重新启动。  

- D. 禁用  
此设置禁止进行重叠焊接。如果发生如电弧停止、超出限值、气体压力下降、焊丝短缺或冷却液错误等问题，焊接将被中断，机器人将停止。  
在处理原因后，用户必须按下`开始 (Start)`，将不执行重叠焊接，并将从机器人停止的位置开始焊接。  


{% hint style="warning" %}
  移动机器人时，按下前进/后退键将重置重新启动信息，阻止重叠焊接的执行。只能使用手动移动来移动机器人。
{% endhint %}
[__SOURCE](6_Weaving_function/README.md)
# 6. 编织功能
[__SOURCE](6_Weaving_function/1_Weaving_function/README.md)
# 6.1 编织功能

编织功能用于弧焊中以加宽焊缝宽度。编织功能的细节由编织条件和参考点决定。可以在编织条件中配置以下设置。  

[__SOURCE](6_Weaving_function/1_Weaving_function/1_condition_.md)
# 6.1.1 编织条件

当光标放置在 `weaving ...` 命令上时，按下 `[Property]` 键将显示如下所示的编织条件编辑屏幕。  

![](../../_assets/6_1_1.png)<br>
*图 6.1.1. 编织条件设置*

---

编织条件中每个字段的详细信息如下：  

### (1) 条件编号: [1] (范围: 1 ~ 1000)  

这是存储编织操作设置的条件编号。  
可以通过按 [+] 或 [-] 按钮添加或删除条件。  
您可以导航到前一个或下一个条件编号以编辑相应的条件。

### (2) 编织类型: <Single, Triangle, L type, Circle, DownCurve>  

此字段指定编织运动的类型。 (请参阅 [[6.1.2 编织类型]](../1_Weaving_function/2_configuration_.md))

### (3) 频率: [2] Hz (范围: 0.0 ~ 10.0)  

此字段设置编织频率，范围为 `0.0 至 10.0 Hz`。当频率设置为 '0' 时，将应用移动时间。  
(请参阅 [[6.1.3 频率]](../1_Weaving_function/3_frequency.md))  

### (4) 默认图案  

此字段设置编织运动的图案。  
(请参阅 [[6.1.4 默认图案]](../1_Weaving_function/4_pattern.md))  

- **左侧距离（墙方向距离）** : [2.5] mm (范围: 1.0 ~ 25.0)  
- **右侧距离（其他方向距离）** : [2.5] mm (范围: 1.0 ~ 25.0)  
- **角度** : [90] 度 (范围: 0.1 ~ 180.0)  
- **偏移角度** : 当使用火炬方向参考时，字段指定火炬从其位置向左或向右倾斜的角度。  
- **墙方向** : <**垂直**, **水平**, **基于火炬**>  

### (5) 前向角度: [0] 度 (范围 : -90.0 ~ 90.0)  

此字段表示相对于前向方向的编织角度。  
当设置为 0 度时，前向和编织方向形成直角。  
(请参阅 [[6.1.4 默认图案]](../1_Weaving_function/4_pattern.md))  

### (6) 边界限制: <启用, 禁用>  

此选项决定编织轨迹是否受到焊接段起始和结束的边界限制。当启用此功能时，编织轨迹限制在焊接区域内。  
(请参阅 [[6.1.4 默认图案]](../1_Weaving_function/4_pattern.md))  

### (7) 编织停止时的机器人行为: <移动, 停止>  

当在编织图案中设置计时器时，编织运动将在编织的左右两端停止。  
在这种情况下，该设置决定机器人在编织停止期间是继续移动还是停止。  

### (8) 移动时间: [1] 秒 (范围: 0.0 ~ 10.0), 计时器（编织停止）: [0] (范围 : 0.00 ~ 2.00)  

如果编织频率设置为 '0'，则编织运动将基于移动时间执行。  
在这种情况下，每个部分的移动时间和部分之间的编织停止时间被配置。  
(请参阅 [[6.1.5 编织区段设置]](../1_Weaving_function/5_weaving_section.md))  

当设置 '编织频率' 时，仅能调整 '计时器（编织停止）' 设置。  
在为指定频率设定的总时间内，机器人在排除 '计时器（编织停止）' 中设置的时间的持续时间内执行编织。编织停止时间内，编织停止。  
机器人在编织停止时间内是否继续移动由 '编织停止时的机器人行为' 的设置决定。

### (9) 编织轴编号: [1]  

此设置决定执行编织运动的部分是机器人还是辅助轴。  
当设置为辅助轴时，机器人将如记录的那样移动，只有辅助轴将根据设定的距离和频率移动以实现编织。  
如果选择辅助轴，'辅助轴编号'字段中指定的辅助轴将执行编织运动。
[__SOURCE](6_Weaving_function/1_Weaving_function/2_configuration_.md)
# 6.1.2 编织类型

设置编织的图案形状，如下图所示。

![](../../_assets/6_1_2_1.png)<br>
*图 6.1.2. 编织图案类型*

![](../../_assets/6_1_2_2.png)<br>
*图 6.1.2. 编织图案类型 - 向下曲线*
[__SOURCE](6_Weaving_function/1_Weaving_function/3_frequency.md)
# 6.1.3 频率

"**频率**" 指的是编织的重复周期。当 "频率" 设置为 '0' 时，重复周期由移动时间方法定义，而不是频率方法。
要使用频率方法指定重复周期，必须设置一个非 '0' 的值。

频率与横向和纵向距离相关。
随着频率的增加，可用的横向和纵向距离减小，导致幅度变小。相反，随着频率的下降，幅度可以增加。
在三角形编织图案的情况下，横向和纵向移动时间的总和等于对角线移动时间。
[__SOURCE](6_Weaving_function/1_Weaving_function/4_pattern.md)
# 6.1.4 默认模式

配置下图所示的每个参数。 
  
<p align="center">
  <img src="../../_assets/6_1_3.png" width="60%"></img>
  <img src="../../_assets/6_1_3_1.png" width="45%"></img>
  <em><p align="center">图 6.1.3 根据墙壁方向的编织参数</p></em>
</p>

- **左侧距离（墙壁方向距离）** : [2.5] mm (范围: 1.0 ~ 25.0)
- **右侧距离（其他方向距离）** : [2.5] mm (范围: 1.0 ~ 25.0)

### (1) 左侧距离（墙壁方向距离）

设置左侧（墙壁）方向的距离。  


### (2) 右侧距离（其他方向距离）

设置右侧方向的距离。  


### (3) 角度

如图 6.3 所示，设置左侧（墙壁）方向与右侧方向之间的角度。
该角度是从左侧（墙壁）方向到右侧方向测量的。
然而，当使用 **REFP 4** 时，此角度将被忽略。


### (4) 偏移角度（参见 [图 6.1.3]）

当墙壁方向基于焊枪姿态设置时，此设置定义编织表面相对于编织进展方向（图 (3) 中标记为 ⊙ 的方向）旋转的角度。
设置为 0° 时，左侧（墙壁）方向与右侧方向之间的角度被二等分。


### (5) 墙壁方向（参见 [图 6.1.3]）

将左侧（墙壁）方向设置为以下选项之一：垂直（图 (1)）、水平（图 (2)）或基于焊枪姿态（图 (3)）
通常，左侧（墙壁）方向设置为垂直，而水平方向通常用于平面上的 180 度角编织。  

对于基于焊枪姿态的编织，左侧（墙壁）方向从编织进展方向逆时针设置（图 (3) 中标记为 ⊙ 的方向）。
基于焊枪姿态的编织可以适应所有左侧（墙壁）方向，并且在编织过程中左侧（墙壁）方向变化时也可以调节。


### (6) 前向角度

这是指编织振动方向相对于焊接线的角度。可调范围为 -90.0 到 90.0 度。
设置为 0° 时，编织将垂直于焊接线移动。


![](../../_assets/6_1_4.png)<br>
*图 6.1.4. 编织前向角度*

    
### (7) 边界限制

对于前向角度不为 0° 的编织，编织可能在编织区域的开始和结束时超出节段的边界。  
边界限制设置允许您选择编织是否应限制在节段边界内，或者是否可以在节段边界之外不受限制地进行。

 
![](../../_assets/6_1_5.png)<br>
*图 6.1.5 编织边界限制* 
[__SOURCE](6_Weaving_function/1_Weaving_function/5_weaving_section.md)
# 6.1.5 编织部分设置

### (1) 编织停止时的机器人行为  

当定时器（编织停止）设置为除0以外的值时，编织模式将在指定持续时间内在编织部分结束时停止。
在这种状态下，您可以配置机器人是否继续移动或停止。

如果设置为**移动**，机器人表现如图左所示；如果设置为**停止**，行为如图右所示。  


![](../../_assets/6_1_6.png)<br>
*图 6.1.6. 编织停止时的机器人行为* 

### (2) 移动时间

当“频率”设置为'0'时，此设置定义每个部分的移动时间。
未使用部分的移动时间（例如，简单振荡中的第3和第4部分）将被忽略。

![](../../_assets/6_1_7.png)<br>
*图 6.1.7. 按编织模式的运动部分* 


### (3) 定时器（编织停止）

在下图所示的每个部分的端点处设置编织停止时间。
此设置在配置编织频率时也适用。
当编织频率设置时，机器人的移动时间在编织周期内计算如下：  
* 机器人移动时间 = (1 / 编织频率) - 总定时器时间

{% hint style="warning" %}
  如果“编织停止时的机器人行为”设置为**移动**，则移动轨迹不会停止，并且将沿直线路径运动，如下图所示。
{% endhint %}
 
 
![](../../_assets/6_1_8.png)<br>
*图 6.1.8. 设置定时器时的轨迹示例*   

{% hint style="warning" %}
  如果“编织停止时的机器人行为”设置为**停止**，则移动轨迹也会停止，但机器人的速度保持不变。
{% endhint %}
[__SOURCE](6_Weaving_function/2_Reference_point/README.md)
# 6.2 参考点(refp)特性

要执行编织，需要一个编织坐标系统来确定将创建编织模式的位置，如[[6.1 编织功能]](../1_Weaving_function/README.md)中所述。配置的编织坐标系统用于设置编织功能的详细参数。默认情况下，当编织动作开始时，机器人的坐标系统的Z轴设置为墙壁方向。编织坐标系统（直角坐标系统）是通过接近焊接起始点的姿势位置和焊接过程中火炬的方向自动创建的。

然而，在某些情况下，例如焊接起始姿势、基材的形状或位置阻止创建编织坐标系统，或者需要对默认编织坐标系统进行修改（例如，当墙壁方向与其他方向之间的角度不是90度时），可以使用参考点功能创建所需的编织坐标系统，并将编织模式与基材对齐。

{% hint style="info" %}
  当**[墙壁方向]**设置为基于火炬姿势时，除了`refp3`外，其他`refp`命令均不使用。
{% endhint %}
[__SOURCE](6_Weaving_function/2_Reference_point/1_sorts.md)
# 6.2.1 参考点类型


![](../../_assets/6_2_1.png)<br>
*图 6.2.1. 编织坐标系* 


### (1)	refp 1  

`refp1` 命令指定编织坐标系的墙面方向。  
如果墙面方向没有被具体定义，机器人将使用垂直方向作为墙面方向来执行编织操作。  
因此，如果墙面方向不是垂直的，则应使用此命令设置墙面方向。  

* **用法**：在墙面方向上记录工件表面的一点作为 `refp 1`。<br> 这点和焊接缝（直线 ⓢⓔ）可以用来确定墙面方向。<br> 如果仅使用 `refp1` 命令，其他方向将通过相对于运动方向的默认模式角度旋转墙面方向来设置。


### (2)	refp 2  

`refp2` 命令在创建编织轨迹时，基于定义墙面方向的平面设置空间的侧面。

* **用法**：在将要进行编织的侧面上记录空间中的任意一点作为 `refp 2`。<br> [图 6.2.2] 显示了在记录 `refp 2` 时位于两个基材料之间的编织坐标系示例。<br> 当仅使用 `refp 2` 命令时，机器人的坐标系统的Z轴被设置为墙面方向，其他方向相应确定。


### (3)	refp 3  

`refp3` 命令指定在静态编织操作中编织的方向，机器人保持静止，仅位置器旋转。  

* **用法**：从机器人的静止位置开始，记录指示移动方向的直线上的任意一点作为 `refp 3`。<br> 机器人将在焊接起始点和 `refp 3` 形成的直线垂直方向上进行编织。

* 示例：设置 `refp3` 后，为焊接起始和结束步骤指定相同的位置。行进速度由时间设置。<br> （注意：如果没有指定 `refp 3`，则不会发生编织，并将触发错误。）


### (4)	refp 4  

`refp 4` 命令设置墙面方向和其他方向之间的角度。  
[图 6.2.3.] 显示了当角度设置为90度时的示例。  
使用此命令指定角度时，将忽略在 `角度 (Angle)` 中设置的值。

    
![](../../_assets/6_2_2.png)<br>
*图 6.2.2. 编织方向和参考点* 
    

<p align="center">
  <img src="../../_assets/6_2_3.png" width="65%"></img>
  <img src="../../_assets/6_2_3_1.png" width="65%"></img>
  <em><p align="center">图 6.2.3. 不同参考点的使用</p></em>
</p>   


{% hint style="info" %}
  - refp 1: 确保与焊接缝的距离至少为5mm。
  - refp 2: 确保与墙面方向平面的距离至少为5mm。
  - refp 3: 确保与起始点的距离至少为5mm。
  - refp 4: 在难以测量编织模式的角度时设置角度。
{% endhint %}
[__SOURCE](6_Weaving_function/2_Reference_point/2_editing.md)
# 6.2.2 参考点编辑

### (1) 记录参考点：类似于移动命令

- ① **移动光标**：将光标移动到将要记录参考点的位置（通常位于 `weaving on` 命令步骤的正上方）。
- ② **记录参考点命令**：按 `[F6: cmd. Input] - arcweld - refp` 记录参考点命令。
- ③ **输入参考点编号**
- ④ 位置方法：
  - *隐藏位置方法* 记录当前机器人位置。
  - 使用 *位置变量输入方法* 时，在参考点编号后输入位置变量。

### (2) 移动到参考点

参考点决定了编织模式，因此通常在回放时机器人不会移动到参考点。
但是，在检查或修改参考点位置时，请遵循以下步骤。

- ① 将光标移动到参考点命令。
- ② 按步进向前键移动到参考点。

移动时，插补类型设置为线性，移动速度、工具和加速度设置将基于编织部分的起始步骤中设定的条件。

### (3) 修改参考点（用于隐藏位置方法）

- ① 将光标移动到参考点命令。
- ② 使用Jog键移动到参考点的新位置。
- ③ 按 **[SHIFT] + [位置修改]** 键更改参考点的位置。

### (4) 删除参考点命令

- ① 将光标移动到参考点命令。
- ② 按 **[SHIFT] + [DEL]** 删除参考点命令。

### (5) 修改参考点编号

- ① 将光标移动到参考点命令。
- ② 按 **[ENTER]** 键。
- ③ 输入新的参考点编号并按 **[ENTER]**。
- ④ 再次按 **[ENTER]** 确认更改参考点编号。
[__SOURCE](6_Weaving_function/3_Weav_sync_out/README.md)
# 6.3 编织同步输出

此功能允许通过调整编织过程中左右两侧的电流和电压，实现平滑的热输入（焊接沉积）控制。

{% hint style="info" %}
  此功能在版本 60.30-00 中得到支持。
{% endhint %}  

![](../../_assets/6_3_1_weav_sync_out.png)<br>
*图 6.3.1. 编织同步输出功能示例*   

如上图所示，当需要在左右编织过程中控制热输入和焊接沉积，或需要调整焊接珠形状时，使用此功能。

要使用此功能，请进入 `weaving` 命令的 `[Property]` 窗口并配置以下设置。

![](../../_assets/6_3_2_weav_sync_out_setting.png)<br>
*图 6.3.2. 编织同步输出功能设置*   

<table>
  <thead>
    <tr>
      <th style="text-align:left">项目</th>
      <th style="text-align:left">描述</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">启用</td>
      <td style="text-align:left">
        启用时，根据用户的设置调整编织过程中的电流/电压输出。
      </td>
    </tr>
    <tr>
      <td style="text-align:left">输出（左/右）</td>
      <td style="text-align:left">
        相对于左右编织设置中的基线条件，电流/电压输出变化的百分比。
      </td>
    </tr>
    <tr>
      <td style="text-align:left">范围</td>
      <td style="text-align:left">
        设置左右编织过程中输出变化的百分比范围。
      </td>
    </tr>
  </tbody>
</table>
[__SOURCE](7_Monitoring/README.md)
# 7. 弧焊数据监测

在弧焊过程中，机器人控制器发送的电流/电压指令值与焊机实际输出到机器人控制器的电流/电压值进行比较的情况是存在的。在这种情况下，可以使用弧焊数据图监测功能实时检查与焊接相关的数据。

</br>

我们的控制器提供2种焊接数据监测功能：

(1) **详细信息监测**：允许您检查所有可用数据。

(2) **弧焊数据图**：启用查看指令和实际电流/电压数据的波形。

(3) **弧轨迹监测**：您可以在焊接时详细查看工具尖端和焊枪的轨迹。
[__SOURCE](7_Monitoring/1_detail_mon.md)
# 7.1 详细信息监控

此功能允许您检查与电弧焊接相关的详细数据。提供的信息可能会根据设置的焊机而有所不同，因此监控窗口可能会根据配置的焊机而有所不同。如果与焊机发生通信错误或没有通信连接，"焊机错误代码"或"焊机通信状态"项目将以红色背景显示。以下数据可以在详细信息监控中进行监控。

![](../_assets/7_1_1.png)<br>
*图 7.1.1. 电弧焊接详细信息监控*

1. 输入电流：从机器人发送到焊机的指令焊接电流 (A)

2. 输出电流：焊机当前实际输出的焊接电流 (A)

3. 输入电压：从机器人发送到焊机的指令焊接电压 (V)

4. 输出电压：焊机当前实际输出的焊接电压 (V)

5. 焊接过程

6. 进给速度：送丝速度 (m/min)

7. 操作模式：电弧焊接模式

8. 程序/作业编号

9. 进给电机电流：驱动实际送丝电机的电流 (A)

10. 焊机错误编号

11. 脉冲动态补偿

12. 额外信息窗口：此部分显示有用的额外信息，例如电流/电压的上下限及其单位。

13. 输入信号：从焊机发送到机器人控制器的信号。(可以在`[F2: 系统] - 5: 初始化 - 3: 使用设置 - 焊机设置 - 输入信号分配 ([F2: System] - 5: Initialization - 3: Usage Setting - Welder Setting - Input signal assign)`下检查)

14. 输出信号：从机器人控制器发送到焊机的信号。(可以在`[F2: 系统] - 5: 初始化 - 3: 使用设置 - 焊机设置 - 输出信号分配 ([F2: System] - 5: Initialization - 3: Usage Setting - Welder Setting - Output signal assign)`下检查)

15. 指令值：可以手动输出的常用指令。
[__SOURCE](7_Monitoring/2_data_graph.md)
# 7.2 焊接电弧数据图

焊接电弧数据图显示与焊接数据波形相关的信息，让您不仅可以实时查看数据，还可以一目了然地查看过去的数据。

要使用此功能，在 TP 上依次按 `[pane layout] - 选择 - 电弧数据 图表 ([pane layout] - select - arc data graph)`。

![](../_assets/7_2_1.png)<br>
*图 7.2.1. 焊接电弧数据图*

可以在监控窗口中检查以下项目：

1. 焊接状态（初始条件、气体预流、结束条件、气体后流、坑运动、主焊接等）

2. 作业/程序编号，协同设置

3. 输入电流 / 指令电流图

4. 输入电压 / 指令电压图

5. 输入电流和电压的移动平均过滤图

6. 焊接电流和电压的上下限

焊接电弧数据图提供左右和上下移动功能。您还可以添加行和列以查看更多数据。通过切换 `[Auto scroll]` 按钮，您可以在当前焊接过程中回顾过去的焊接屏幕。

您可以通过按焊接电弧数据图屏幕底部的 **[Row]** 或 **[Col]** 按钮来增加图中的行数。如果您想进一步放大数据图，可以按 **[SHIFT] + [Row]** 或 **[SHIFT] + [Col]** 来放大显示。
[__SOURCE](7_Monitoring/3_arc_trj_mgr.md)
# 7.3 弧线轨迹管理器

此功能在弧焊过程中实时显示轨迹、电流、电压和焊枪位置（焊接角度、推拉角度）。

通过此功能，您可以在弧焊过程中实时监控焊接角度、电流和电压，从而更容易修改焊接教学。

要启用此功能，请按照以下步骤操作：

在`[F2: 系统] - 4: 应用参数 - 2: 弧焊 ([F2: System] - 4: Application parameter - 2: Arc welding)`中将“弧线轨迹监控”设置为“激活”。

{% hint style="info" %}
此功能在版本60.30-00及以上可用。
{% endhint %}

![](../_assets/7_3_1_arc_trj_mgr.png)<br>
*图 7.3.1. 实时弧线轨迹监控*

您可以从`arcon`到`arcoff`部分实时监控轨迹和焊接信息。

使用箭头键移动平面，或按**[Shift] + [+/-]**键进行放大或缩小。

焊接角度和推拉角是根据焊接方向相对于焊接平面计算的。

{% hint style="info" %}
焊接平面会根据焊接轨迹自动旋转。
{% endhint %}
[__SOURCE](7_Monitoring/4_arc_monitoring/README.md)
# 7.4 电弧监控

{% hint style="info" %}
此功能在版本70.00-00及更高版本中支持。  
{% endhint %}

此功能允许您在单个屏幕上查看与电弧焊接相关的监控功能。  
它集成了以下功能：电弧焊接、实时变化焊接数据、电弧传感和多道工序、电弧操作信息、电弧轨迹监控  

要访问此功能，请导航到 `[(right panel) pane layout] - 选择 - 电弧 监控 ([(right panel) pane layout] - select - arc monitoring)`。  
以下部分描述每个屏幕和可用的监控功能。  
[__SOURCE](7_Monitoring/4_arc_monitoring/1_arc_welding.md)
# 7.4.1 弧焊接


When entering the "Arc Monitoring" screen for the first time, this screen is displayed by default.
To switch to this screen from another screen, click `[F1: 弧 焊接] ([F1: Arc Welding])` on the bottom panel.
This screen displays the analog and digital signals exchanged with the welder.

![](../../_assets/7_4_1_1.png)<br>
*图 7.4.1.1. 弧焊监控*  

On the "Arc Welding" screen, click the `[F7: 选择] ([F7: Select])` button on the bottom panel to change the panel contents and access the following functions:  


### (1) 焊机设置.

![](../../_assets/7_4_1_2.png)<br>
*图 7.4.1.2. 手动焊机设置*  

Click the `[F1: 焊机 设置.] ([F1: welder set.])` button on the bottom panel to open the following window.
In this window, you can manually configure the welding machine.


### (2) 手动输出

![](../../_assets/7_4_1_3.png)<br>
*图 7.4.1.3. 手动输出*  

Select the desired signal from either the analog output signals or digital output signals(e.g. "Stick Check" or "OFF (fb1.12)" as shown in the figure), and then click the `[F2: 手动输出] ([F2: Manual Output])` button on the bottom panel.
A window will appear where you can configure the selected signal to be output.  


### (3) I/O 设置

A wide variety of data is exchanged between the robot controller and the welder in the form of analog and digital signals(refer to `[F2: 系统] - 5: 初始化 - 3: 用途设置 - [F2: 焊机 设置] ([F2: System] - 5: Initialization - 3: Usage setting - [F2: Welder setting])`).
However, the signals that operators need to monitor are typically limited.
Click the `[F3: 设置I/O] ([F3: Set I/O])` button on the bottom panel to open the following window.  

![](../../_assets/7_4_1_4.png)<br>
*图 7.4.1.4. I/O 输出设置*  

This window displays all signals exchanged between the robot controller and the welder.
Select only the required data and click to `确定 (OK)` to monitor the selected signals only.
You can also use the `全选 (Select All)` or `清除所有 (Clear All)` buttons at the top to enable or disable all items at once.  
[__SOURCE](7_Monitoring/4_arc_monitoring/2_arc_sensing.md)
# 7.4.2 弧感应


当从“弧监控”屏幕点击底部面板上的`[F2: 弧 感应] ([F2: Arc Sensing])`按钮时，将显示此屏幕。
有关此屏幕上可用信息的详细信息，请参阅以下链接：[[8.3.5 弧感应监控]](../../8_Application_function/3_Arc_sensing/5_arcsen_monitoring.md)  
[__SOURCE](7_Monitoring/4_arc_monitoring/3_arc_operinfo.md)
# 7.4.3 弧操作信息


此屏幕在从“弧监控”屏幕中点击底部面板上的`[F3: 弧 操作信息] ([F3: Arc OperInfo])`按钮时显示。  
有关此屏幕上可用信息的详细信息，请参阅以下链接：[[1.3.7 Arc Welding Operation Information]](../../1_Basic_information/3_Convenient_functions/7_operation_info.md)  
[__SOURCE](7_Monitoring/4_arc_monitoring/4_arc_trj_monitor.md)
# 7.4.4 弧轨迹监测


要使用此功能，首先导航到 `[F2: 系统] - 4: 应用参数 - 2: 弧焊 ([F2: System] - 4: Application parameter - 2: Arc welding)` 并将 **"Arc Trajectory monitoring"** 设置为 **"Enable"**。
左侧显示从底部面板中选择的表格数据，右侧显示 "Arc Trajectory Monitoring" 屏幕。
此屏幕提供了弧焊过程中焊接轨迹和焊枪姿态（工作角度和推拉角度）的实时可视化。  
（您可以实时监控 `arcon` 到 `arcoff` 的轨迹和焊接信息）


![](../../_assets/7_4_4_1.png)<br>
*图 7.4.4.1. 弧轨迹监测*  

您可以通过点击并拖动中间分隔符来调整表格和画布的大小。
（然而，一个视图不能完全覆盖另一个视图。如果屏幕最小化后再恢复到全屏，布局将被重置）
使用 `+/-` 键与 `[shift]` 键一起放大或缩小。  
在画布内，您可以拖动以调整视图位置。  
[__SOURCE](8_Application_function/README.md)
# 8. 弧焊应用功能

我们提供各种应用功能，以提高弧焊的质量和稳定性。本节简要介绍这些功能。详细的说明和应用可以在单独的功能手册中找到，因此请参考各自的手册以获取更深入的信息。
[__SOURCE](8_Application_function/1_Arc_cond/README.md)
# 8.1 Arccond - 弧焊条件数据库与插值

焊接条件可以存储在数据库 (DB) 中以供使用或在焊接过程中进行插值。该功能的使用方法如下：

`[F6: cmd. input] - arcweld - arccond` 在 JOB 文件中输入命令。

命令格式如下：
```arccond <插值类型>, cnd=<条件编号>, gap=<间隙>, spd=<焊接速度>, rd=<壁向>, ld=<丝向>, freq=<编织频率>, cur=<电流>, vol=<电压>```

<br>

- **插值类型**: D(阶梯，立即应用) / L(线性插值)
- **cnd**: 条件编号 (WDB-焊接数据库-和插值条件可以通过属性窗口进行编辑)
[__SOURCE](8_Application_function/1_Arc_cond/1_cmd_para.md)
# 8.1.1 使用命令因子的阶梯变化

阶梯变化功能可以在命令参数中如下使用：

| 方法 | 示例 |
| :--- | :--- |
| 改变 IV（电流、电压） |move L, spd=60%, ...<br/>move L, spd=10%, ...   <span style="color: green"> # 焊接点（接缝）进入步骤 </span> <br>    arcon cnd=1  <br>    move L, spd=40cm/min, ... <br>   <b>  arccond D, cur=175, vol=20 </b>  <span style="color: green"> # 将电流改为175A，电压改为20V </span> <br>   move L, spd=30cm/min, ...  <br>    arcof <br>   end |
| 改变焊接速度和编织参数 | move L, spd=60%, ...  <br>   move L, spd=10%, ...    <span style="color: green"> # 焊接点（接缝）进入步骤  </span> <br> weaving on, cnd=1 <br>   arcon cnd=1   move L, spd=40cm/min, ... <br> <b>  arccond D, spd=80, rd=20, ld=10, freq=1.5, cur=175, vol=20 </b> <br> <span style="color: green">  # 将焊接速度改为80cm/min，编织宽度改为20/10mm，频率改为1.5HZ，电流改为175A，电压改为20V </span> <br>  move L, spd=30cm/min, ...  <br>   weaving off <br>   arcof  <br> end |
[__SOURCE](8_Application_function/1_Arc_cond/2_wdb_step.md)
# 8.1.2 使用 WDB（焊接数据库）进行步进变化

```python
    arccond D, cnd=1
```

在上述命令中，进入属性窗口，您可以查看以下配置窗口。

 
![](../../_assets/8_1_1.png)<br>
*图 8.1.1. 弧焊条件对话框* 

<br>

您可以添加或删除 **cnd**（焊接条件），允许您将焊接条件存储并在数据库中使用，具体如下：
可以存储在数据库中的条件：焊接速度、电流、电压、编织频率、编织宽度

利用此功能，可以创建以下 JOB 配置：

```python
    move L, spd=60%, ...
    move L, spd=10%, ...	    # 焊点（缝合）进入步骤
    arcon cnd=1
    move L, spd=40cm/min, ...
    arccond D, cnd=1  	    # 立即更改为焊接数据库条件 1
    move L, spd=30cm/min, ...
    arcof
    end
```
[__SOURCE](8_Application_function/1_Arc_cond/3_wdb_continuous.md)
# 8.1.3 使用 WDB (焊接数据库) 进行连续插值变化

例如，该功能允许在焊接工件时对焊接条件（如电流、电压、焊接速度、编织宽度和编织频率）进行线性插值，起始的对接间隙为 5mm，结束时为 25mm。
在这种情况下，焊接条件的连续变化（L 插值）以如下方式以线性方式进行。

 
![](../../_assets/8_1_2.png)<br>
*图 8.1.2. 焊接条件的线性插值* 

<br>

使用来自 DB 1 和 DB 2 的上述项目，利用连续插值变化的 JOB 如下： 

```python
move L, spd=60%, ...
move L, spd=10%, ...	    # 焊接点（接缝）进入步骤
arcon cnd=1
move L, spd=40cm/min, ...
arccond L, cnd=1  	    # 从焊接数据库 1 -> 2 的连续插值变化
move L, spd=30cm/min, ...    # 在此步骤中，条件线性变化从 cnd(DB) 1 -> 2
arccond L, cnd=2  	    # 下一步骤需要 arcof
arcoff
move L, spd=10%, ...	    # 焊接点（接缝）退出步骤
end
```
[__SOURCE](8_Application_function/1_Arc_cond/4_interpolation.md)
# 8.1.4 使用插值条件更改焊接速度和编织宽度

此功能与之前提到的功能是独立的。它允许根据参考间隙设置焊接条件，然后通过实际触觉传感器在起始点和结束点测量间隙，自动计算焊接速度和编织宽度。  
通过在`arccond`命令的属性窗口中输入“间隙修正”选项卡，可以根据每个条件的间隙设置速度和宽度。  
在分割窗口中，单击“弧插值”将以图形形式显示此设置。

![](../../_assets/8_1_3.png)<br>
*图 8.1.3. 弧焊接条件（间隙修正）对话框*

![](../../_assets/8_1_4.png)<br>
*图 8.1.4. 弧插值监控*

<br>

此功能的操作如下：

![](../../_assets/8_1_5.png)<br>
*图 8.1.5. 焊接条件插值操作*

<br>

间隙-速度图可如下表示：

在`arccond`命令的属性窗口的间隙修正选项卡中输入的间隙-spd图被创建。  
在焊接起始点，WDB焊接速度与WDB参考速度之间的速度差（图表上参考间隙的spd值）被假设为bSpd。然后通过将dSpd应用于当前间隙的原始图的Spd值来计算起始速度。

同样，在焊接结束点，WDB焊接速度与WDB参考速度之间的速度差（图表上参考间隙的spd值）被假设为dSpd2。通过将dSpd2应用于当前间隙的原始图的Spd值来计算结束速度。

如上图所示，焊接速度在两个`arccond`命令之间线性增加。

JOB配置的示例如下：

```python
    move L, spd=60%, ...
    move L, spd=10%, ...	    # 焊接点（接缝）入口步骤
    arcon cnd=1
    move L, spd=40cm/min, ...
    arccond L, cnd=1, gap=20  
    move L, spd=30cm/min, ...    # 在此步骤中，焊接速度和编织宽度线性变化
    arccond L, cnd=2, gap=10   
    arcoff
    move L, spd=10%, ...	    # 焊接点（接缝）出口步骤
    end
```
[__SOURCE](8_Application_function/2_Touch_sensing/README.md)
# 8.2	触觉传感

焊接工件由于夹具、定位器或工件安装的误差，并不总是处于固定位置。在这种情况下，可以使用触觉传感来检测焊接起始点、中间点和结束点，从而实现准确焊接。

触觉传感功能通过检测工件的位置和焊接的起始、结束或中间点来帮助获取姿态。

通过使用触觉传感记录参考位置，加载工件时可以计算出工件相对于参考位置的偏移。当使用主模式时，可以通过参考教学保存主姿态，并且在实际操作中，通过触觉传感自动计算偏移量。

![](../../_assets/8_2_1.png)<br>
*图 8.2.1. 触觉传感示例*

### (1) 触觉传感类型

触觉传感支持共计5种类型，如[图 8.2.1]所示（对接焊、角焊、V形槽、LR中心和槽检测）。

![](../../_assets/8_2_2.png)<br>
*图 8.2.2. 触觉传感类型*

### (2) 触觉传感命令和设置参数

触觉传感命令可以通过在TP上输入`[F6: cmd. input] - arcweld - touchsen`进行记录。

假设在命令中条件1设置为角焊，条件2设置为对接焊，条件3设置为V形槽（工件类型在属性中定义），示例如下：

```python
    move L,spd=60%,accu=0,tool=0  # 以加速度0移动到触觉传感位置
    var P10=cpo() # 在触觉传感前将当前姿态保存到局部变量P10。
    touchsen cnd=1, crd="tool_prj", dir=["tf","td"], pose=P10       # 条件1，工具投影方向，2点触碰
    touchsen cnd=1, crd="robot", dir=["+x","-y","-z"], pose=P10     # 条件1，机器人坐标方向，3点触碰
    touchsen cnd=1, crd="tool", dir="+z", pose=P10           # 条件1，工具坐标方向，+Z方向1点触碰
    touchsen cnd=2, crd="tool", dir="+x", lift_up=3, pose=P10, gap=var1 # 条件2，工具坐标方向，触碰底部并上升3mm
    touchsen cnd=3, crd="tool", dir="-y", lift_up=5, pose=P10   # 条件3，工具坐标方向，触碰底部并上升5mm
```

- **传感距离** : 在传感方向上的距离[mm]，并且如果到达此距离时未检测到工件，将发生错误。

- **退回距离** : 在角焊情况下，初步传感后退回的距离，**触碰底部后的上升距离在槽检测类型中**。

- **传感速度和退回速度** : 指定搜索或退回时的速度。  

- **检测类型** : 支持接触和释放接触时的传感。通常使用接触时的传感，几乎没有错误。<br/>
  如果需要考虑因为传感时焊丝弯曲造成的微小误差，只在绝对必要时使用退回时的传感。

<br/>

- **参考**

<center>

| 传感类型 | 最大搜索</br>方向 | 正交XYZ </br>（支持所有类型） | 工具坐标系 | 工具投影</br>坐标系 | 其他输入参数 |
|:---:|	:---: |	:---:	| :---:|	:---: |:---:|
| 角焊 |	3	|O|	O |	O	|	退回距离 |
| 对接焊	| 1 |	X	|O	|X	|  |
| V形槽 |	1 |	X |	O	|X | |
| LR中心 |	1	|O |	O	|X |  |	
| 槽检测 |	2 |	O |	O |	O | 前进距离 1</br> 退回距离 1 </br> 标准 |

</center>

在触觉传感命令中，按下`属性 (Property)`将弹出窗口，如[图 8.2.3]所示。  
您可以设置传感距离、退回距离、前进距离、传感速度、退回速度和检测类型（接触、释放接触）等条件。  

![](../../_assets/8_2_3.png)<br>
*图 8.2.3. 触觉传感条件编辑屏幕*

{% hint style="info" %}
  有关命令和参数的详细说明，请参考[2.13 touchsen](../../2_Command/13_touchsen.md) <br>
  本节解释如何使用该功能。
{% endhint %}

### (3) 触觉传感类型的详细说明

---

#### [1] 角焊

![](../../_assets/8_2_4.png)<br>
*图 8.2.4. 触觉传感示例 - 角焊*

- 命令示例
```python
  touchsen cnd=1, crd="robot", dir=["+x","-y", "-z"], pose=P10
  touchsen cnd=1, crd="tool_prj", dir=["tf", "td"], pose=P10
  touchsen cnd=1, crd="tool", dir=["+z"], pose=P10
```  
  - 1点触碰 : 仅指定一个传感方向。
  - 2点触碰 : 依次指定两个传感方向。
  - 3点触碰 : 依次指定三个传感方向。
- 工具投影方法 (crd="tool_prj") : 出于方便，前、下、左和右方向根据焊枪姿势确定。  <br> 方向可以指定为tf（前），td（下），tl（左），tr（右）。(tl = RotZ(90) * tf, tr = RotZ(-90) * tf)
- 对于具有旋转量（RX、RY、RZ）的工件，例如倾斜角焊，可以使用角度指定选项更改传感方向。请参见手册底部的使用说明。

---

#### [2] V形槽

![](../../_assets/8_2_5.png)<br>
*图 8.2.5. 触觉传感示例 - V形槽*   

- 命令示例
```python
  touchsen cnd=3, crd="tool", dir=[-ty], lift_up=3, pose=P10    # 条件3，工具坐标方向
```  
  - V型槽类型可用于感测具有槽形状的工件。然而，建议在开始传感之前，先将工具姿态教学，使其沿角的平分线进行定位，类似于上面的图。  
  - 方向参数对应于左右序列中的一个方向。向下序列方向相对于工具固定在`+z`方向。  
  - 为了稳定传感，建议将上升量设置为至少3mm。  

- 传感序列  
  - 传感序列如下进行：上左-右 → 中间回退 → 底部 → 底部左-右 → 中间  

![](../../_assets/8_2_6.png)<br>
*图 8.2.6. 触觉传感序列 - V形槽*   

---

#### [3] 对接焊

![](../../_assets/8_2_7.png)<br>
*图 8.2.7. 触觉传感示例 - 对接焊*   

- 命令示例
```python
    touchsen cnd=2, crd="tool", dir="+x", lift_up=3, pose=P10, gap=var_gap   
    # 条件2，工具坐标方向，触碰底部并上升3mm
```  
  - 对接焊类型建议在开始传感之前，将工具姿态垂直于地面，如上图所示。
  - 方向参数对应于左右序列中的一个方向。向下序列方向相对于工具固定在`+z`方向。  
  - 在底部传感后，建议将上升量设置为至少3mm以确保稳定传感。所感测的间隙大小可能会因上升量的不同而变化。  

- 传感序列
  - 传感序列如下进行：上左-右 → 中间回退 → 底部 → 底部左-右 → 中间  

![](../../_assets/8_2_8.png)<br>
*图 8.2.8. 触觉传感序列 - 对接焊*   

### (4) 传感方向角度变换

在角焊和槽检测类型中支持传感方向的角度变换。通过为传感方向指定一个角度，可以更改搜索过程的方向。在命令中，旋转参数输入为"X30"，"Y-30"，"TL20"等。  

角度指定沿所选轴（TL轴或正交XYZ轴）沿指定角度旋转整个搜索方向。[图 8.2.9]显示了沿Y轴或TL轴旋转30度的角焊和槽检测工件的示例。

![](../../_assets/8_2_9.png)<br>
*图 8.2.9. 触觉传感示例 - 角度设置*       

- 命令示例

```python
   touchsen cnd=1, crd="robot", dir=["+x","-z"], rotation="Y30", pose=P100
   touchsen cnd=1, crd="robot", dir=["+x","-z"], rotation="TL30", pose=P100
   touchsen cnd=2, crd="tool_prj", dir=["td","tf"], lift_up=5, rotation="Y-30", pose=P100
   touchsen cnd=2, crd="tool_prj", dir=["td","tf"], rotation="TL-30", pose=P100   # 检测槽 
```

- 根据工件类型和在命令中指定的传感方向坐标系，可以指定的角度旋转轴如下表所示。

<center>

| 传感类型	| 传感方向 </br> 坐标系	| 角度指定轴 |
|:---:|:---:|:---:|
|角焊	| 全部	| 正交XYZ轴 </br> TL轴 |
|检测槽 |	工具 (crd="tool") </br> 工具投影 (crd="tool_prj") |	正交XYZ轴 </br> TL轴 |

</center>

### (5) 触觉传感中的主/执行模式

主模式可以通过用户键开启/关闭。当触觉传感在开启主模式时进行时，可以保存主姿态并用作教学参考。在实际操作中，主模式关闭，并进行触觉传感。在这种情况下，系统根据当前的传感姿态自动计算工件相对于主姿态的偏移量。

在主模式中，所感测的姿态保存在触觉传感命令的`mpose`输入参数指定的变量中。在执行模式（主模式关闭时），当前感测的姿态与主模式下感测的姿态进行比较，并计算偏移量。然后将偏移量记录在`mshift`输入参数指定的变量中。

- 命令示例
```python
   var P10=cpo()
   var sft_var1=Shift(0,0,0,0,0,0,"base")
   ....
   touchsen cnd=1, crd="robot", dir=["+x","-z"], mpose=P10, mshift=sft_var1
```  

- 例如，在主模式下，感测的姿态保存在`P10`姿态变量中，在执行模式下，当进行传感时，主模式姿态与当前感测姿态之间的偏移量会自动计算并存储在sft_var1变量中。
[__SOURCE](8_Application_function/3_Arc_sensing/README.md)
# 8.3 弧感应和多次焊接

{% hint style="info" %}
  - 要使用此功能，需要获得弧感应许可证。<br> 请联系我们以购买和获取许可证。
  - 此外，此功能需要启用 **编织功能**。<br> 在开始之前，请参阅编织部分。 **[6. 编织功能](../../6_Weaving_function/README.md)**
{% endhint %}

弧感应是一种缝合跟踪功能，可用于在厚材料（如厚板）上进行弧焊。当使用此功能时，即使由于工件公差或变形导致缝合偏差，也可以准确地进行焊接。  
<br>

典型的使用方法如下： <br>
1. 通过感应参考工件上的缝合（注册母体姿态）来教导焊接区域的参考点（起点、中间点和终点） 
2. 在实际工件的相同位置进行缝合感应（计算相对于母体姿态的偏移） 
3. 将计算出的偏移应用于每个点 
4. 在焊接过程中使用弧感应进行实时缝合跟踪

{% hint style="info" %}
  - 在使用此功能之前，必须首先进行弧感应延迟时间校准。
  - 缝合感应是指找到焊接区域的起点、中间点和终点的过程。
  - 可以使用触摸感应、LVS 缝合查找、LPS（激光点感应）功能执行缝合感应。
{% endhint %}

本手册解释了 ${cont_model} 中新添加的弧感应功能。  
在 ${cont_model} 中新增的弧感应功能通过进入 `weaving` 命令的属性窗口，并将弧感应（常规）选项卡中的 **'type' 设置为 'seam & cur_diff'** 来激活。

---

**多次焊接** 是一种在焊接需要多次进行而不是单次进行时使用的功能。使用此功能，首先焊接第一层（根焊接），由于感应可能不稳定，因此保存跟踪轨迹。然后，将保存的轨迹移动以生成两个或多个焊接的焊接通道。  

通常，弧感应用于进行多次焊接，多次焊接是使用弧感应进行的。
[__SOURCE](8_Application_function/3_Arc_sensing/1_arcsen_concept.md)
# 8.3.1 弧感应概述

在弧焊过程中，当焊枪在焊接时，焊枪与基材之间的距离会变化。
这种距离的变化会导致电阻的变化，从而改变流动的电流。
换句话说，通过使用在编织部分的电流变化，可以计算出在编织平面的左右方向上需要进行修正的距离，从而实现焊缝的跟踪。

焊接起始位置的高度值作为参考，而编织部分中间的电流值用于在焊接过程中修正垂直方向。
或者，用户可以直接输入自定义电流值作为修正的参考，而不是使用起始位置电流参考值。

<!-- - 左右方向修正 : 通过左右电流差及焊接线提取算法，机器人自动跟踪焊接线移动。
- 上下方向修正 : 以焊接开始时的高度 (CTWD) 为基准，持续保持该值。
                  如果在焊接过程中需要高度变化，用户可以通过以下命令输入基准电流值。  -->


```py
    move L, spd=30cm/min,accu=3,tool=0  # 进入步骤
    move L, spd=30cm/min,accu=3,tool=0  # 焊接开始步骤
    weaving on, cnd=1 # 在[属性]窗口中将“弧感应”功能设置为“启用”
    arc on, cnd=1
    move L, spd=30cm/min,accu=3,tool=0
    _weaving.height_sensing_reference_current=300 # 将高度参考值设置为300A
    move L, spd=30cm/min,accu=3,tool=0
    weaving off
    arc off
    end
```  

![](../../_assets/8_3_1.png)<br>
*图 8.3.1. 弧感应概念*

如图所示，当焊枪向左或向右倾斜时，电流波形会发生变化，这可以用于在左右方向上跟踪焊缝。
此外，编织部分中间的电流可以用于修正垂直方向。
[__SOURCE](8_Application_function/3_Arc_sensing/2_arcsen_spec.md)
# 8.3.2 弧感应支持规格

弧感应缝跟踪不支持所有焊接应用。
对于以下列出的以外的问题，请联系我们获取技术支持。  

以下规格基于我们公司进行的广泛测试获得的数据。
（对于超出指定参数的条件，请联系我们进行基于工件和使用条件的验证测试。）  

### (1) 焊接条件
  - 焊接方法：CO2, MAG, MIG, FCAW  
  - 焊丝直径：1.0 ~ 1.6 mm（实心焊丝，药芯焊丝）  
  - 最大焊接速度：根据焊机特性（10 cm/min ~ 70 cm/min）
  - 焊接电流：160[A] ~ 600[A]  

### (2) 工件条件
  - 最小厚度：2t 或更大  
  - 最大跟踪性能：由灵敏度设置和每秒最大修正距离决定  
     - 在提高跟踪性能时，可能会发生焊接路径振动，因此需要进行验证测试。  

### (3) 编织条件  
  - 编织类型：单次振荡，L型，三角形
  - 频率范围：0.5 ~ 4.0 Hz（单次振荡），0.1 ~ 3.0 Hz（L型，三角形）
  - 振幅范围：1.0 X 1.0 mm 或更多（单次振荡），1.5 X 1.5 mm 或更多（L型），3.0 X 3.0 mm 或更多（三角形）
  - 停留时间：0.0 ~ 2.0[秒]

{% hint style="info" %}
  请检查焊接电源的通信规格。
  焊接电流和缝跟踪数据的通信周期必须为10ms或更短（例如，EWM，Fronius）。
  弧感应保证在稳定焊接条件下（当电流波形稳定时）进行焊缝跟踪。
{% endhint %}

### (4) 插值类型
  - 线性插值：可用
  - 圆形插值：可用
  - 定位器同步（线性）：可用
  - 定位器同步（圆形）：可用

### (5) 接头类型
   - 滴水，V型槽  
   - 最大允许间隙：取决于编织宽度

### (6) 其他功能
  - 感应轨迹偏差限制功能
  - 感应期间的火焰高度设置功能
[__SOURCE](8_Application_function/3_Arc_sensing/3_1_arcsen_condition_general.md)
# 8.3.3.1 弧传感条件（一般）

在`Weaving`命令中，点击[Properties]会打开编织条件编辑屏幕。
此窗口的第二个标签是可以配置编织期间弧传感相关设置的地方，如下所示。

![](../../_assets/8_3_2.png)<br>
*图 8.3.2. 弧传感条件（一般）对话框*

每个项目的设置和操作方法如下：

### (1) 弧传感激活：<Disable, Enable>

此选项允许您设置弧传感功能是否启用或禁用。
设置为"Enabled"时，将从执行"arc on"和"weaving"后的移动命令开始应用弧传感跟踪。

### (2) 传感类型选择：<Welding Seam, Current Difference, Current Difference + Gap, Welding Seam Estimation & Current Difference>

<br/>

```对于${cont_model}，建议使用"Welding Seam Estimation & Current Difference."```<br/>
焊接缝、当前差和当前差 + 间隙的选项与Hi5a相同，请参阅Hi5a控制器手册。

### (3) 左/右传感灵敏度：[0 ~ 10]

此设置调整编织平面上的左侧和右侧传感的灵敏度。<br>
默认值为5，它改变左右传感的强度。<br>
```执行延迟时间校准时，将其设置为-1。```

{% hint style="info" %}
  在弧传感期间，执行系统变量`weavings_.side_sensing_sensitivity=0`将禁用跟踪。要重新启用跟踪，请将此值设置为正数。
{% endhint %}

### (4) 左/右传感开始周期：[0 ~ 9]

此设置确定在编织平面上左/右传感将开始的周期。<br>
```为了稳定运行，将其设置为4或更高。```

### (5) 高度（上下）传感灵敏度：[0 ~ 10]

此设置调整编织平面上上下传感的灵敏度。<br>
默认值为5，它改变上下传感的强度。<br>
```执行延迟时间校准时，将其设置为-1。```

{% hint style="info" %}
  在弧传感期间，执行系统变量`weavings_.height_sensing_sensitivity=0`将禁用跟踪。要重新启用跟踪，请将此值设置为正数。
{% endhint %}

### (6) 高度（上下）传感开始周期：[左/右开始周期 +1 ~ 10]

此设置确定在编织平面上上下传感将开始的周期。<br>
```为了稳定运行，将其设置为4或更高。```

### (7) 高度（上下）传感参考电流：[0 ~ 1000]

此设置确定上下传感的参考电流。<br>
在弧传感焊接线材跟踪期间，焊枪高度基于此设置。<br>
```设置为0时，将使用初始部分电流的平均值作为参考。（如果在焊接开始时有点焊，小心因为意外的高初始电流可能被用作参考。）```

{% hint style="info" %}
  当`weavings_.height_sensing_reference_current=200`在`weaving on`和`arc on`之后立即执行时，将保持跟踪，同时保持200A的高度。
{% endhint %}

### (8) 实时间隙传感灵敏度：[0（禁用）~ 10]

<!-- 该功能根据间隙自动调整焊接速度和编织。当不使用时，将其设置为0。<br>
启用时，此设置调整宽度变化的灵敏度。值应根据焊缝质量和宽度变化的程度进行设置。 -->

设置为0。（不支持）

### (9) 实时间隙传感分辨率：[ ]

### (10) 实时传感间隙：[ ]

### (11) 实时间隙传感速度：[ ]
[__SOURCE](8_Application_function/3_Arc_sensing/3_2_arcsen_condition_advanced.md)
# 8.3.3.2 弧感应条件（高级）

在编织条件编辑屏幕的第三个选项卡中，可以配置高级设置。<br>

```建议在此选项卡中尽可能使用默认值。```

![](../../_assets/8_3_3.png)<br>
*图 8.3.3. 弧感应条件（高级）对话框*

各项的设置和操作方法如下：

### (1) 最大跟踪速度: [0.1~ 20.0] mm/s

此设置定义了在1秒钟内可以跟踪的最大左右/上下距离（或速度）。

### (2) 跟踪限制距离: [0 ~ 200] mm (0: 禁用)

此设置定义了左右/上下弧感应跟踪距离的限制。  
如果跟踪超出弧感应设置的限制，将会发生错误并停止操作。

### (3) 计算范围: [1 ~ 100] % (默认: 50%)

此设置定义了计算左右电流的范围。<br>
```当编织幅度减小时，将此值设置得更小是有利的。（例如，对于1mm幅度，设置为50%；对于0.5 mm幅度，推荐40%。）```

### (4) 不对称感应比: [-50 ~ 50] %

此设置定义了在左侧和右侧焊疤宽度不同的情况下的不对称感应比。<br>
正值表示从焊接方向的火炬后面看是右方向，负值表示左方向。

{% hint style="info" %}
  在弧感应期间，如果执行`weavings_.asymetric_sensing_ratio=10`，将向右发生不对称跟踪，保持右侧电流高出10A。  
  如果此值设置为负数，将向左发生不对称跟踪。
{% endhint %}

---

### (5) 异常数据处理方法: <错误, 警告, 禁用>

此设置定义了当使用“检测余量”计算的正常电流范围超过“检测时间”的限制时如何处理数据。

- 错误: 机器人显示错误并停止。  
- 警告: 机器人显示警告并继续操作。  
- 禁用: 机器人在没有任何中断的情况下继续操作。  

### (6) 检测余量: [100 ~ 200] %

此设置定义了从电流数据中确定异常电流值的余量。默认值为150%。<br>
如下图所示，范围基于“Q1 - 1.5 * IQR”的下限和“Q3 + 1.5 * IQR”的上限。

![](../../_assets/8_3_4.png)<br>
*图 8.3.4. 异常检测余量*
<br>

### (7) 检测时间: [10 ~ 1000] ms

此设置定义了超出异常检测余量的电流输入被允许的时间。<br>
如果超出余量的时间超过此时间，机器人将根据选定的处理方法（错误、警告或禁用）进行操作。

---

### (8) 混合模式 ```(焊接缝估计 + 电流差)``` <br>

此设置决定电流是在每个编织半周期结束时还是在每个完整编织周期结束时进行回归。

### (9) 电流回归误差容忍度 ```(焊接缝估计 + 电流差)``` <br>

此设置定义了回归过程中可以接受的电流误差。对于较小的编织宽度或轻微改善角度，应选择较小的值。默认值为1A。

### (10) 回归期间的数据采样选项 ```(焊接缝估计 + 电流差)``` <br>

此设置定义了回归过程中对采样数据的处理方法：原始、中位数或平均数。

</br>
[__SOURCE](8_Application_function/3_Arc_sensing/3_3_arcsen_calibration.md)
# 8.3.3.3 弧感应校准

要使用弧感应功能，必须先完成校准过程。  
此过程计算延迟时间以同步编织周期和当前数据周期。

{% hint style="info" %}
  弧感应依赖于焊接机设置，包括焊接模式、操作模式、作业/程序编号和协同代码，因此有相应的延迟时间。<br>
  最多可以存储3组校准数据。<br>
  示例：当设置为脉冲、协同185、作业0（禁用）时，相应的校准信息将在弧感应期间加载并使用。
{% endhint %}

### 校准过程

<br>

#### 准备：准备一个平整的样本进行焊接。

#### 步骤 1.  

进入编织命令的 `[Property]` 窗口，并将墙面方向设置为垂直。

#### 步骤 2.  

在编织命令的属性窗口中输入弧感应（一般），将类型设置为“焊缝估算与电流差异”，并将左右和上下的灵敏度均设置为 -1。  


![](../../_assets/8_3_5.png)<br>
*图 8.3.5. 弧感应校准*
<br>


#### 步骤 3. 

创建一个入口步骤，从虚拟墙的相反方向接近，如上图所示，并在起始点和结束点之间保持60厘米的间距。  
在这种情况下，保持焊枪工作角度（滚转角）在30至45度的范围内一致。

#### 步骤 4.  

以自动模式进行实际弧焊。  

#### 步骤 5.  

在编织命令的属性窗口中导航到延迟时间表选项卡。 <br>
单击左下角的“自动校准”选项以检查当前校准的延迟时间。

#### 步骤 6.  

将相应值输入到当前编织频率的字段中（在校准期间应用的频率）。

#### 步骤 7.  

对频率范围从 0.5 Hz ~ 3.0 Hz 的步骤 2 到 5 进行重复。  

<br>

完成此过程后，可以在编织条件编辑屏幕的第四个选项卡上检查弧感应（延迟表跟踪增益）的结果。


![](../../_assets/8_3_6.png)<br>
*图 8.3.6. 弧感应条件选项卡（跟踪增益）对话框*
<br>


此时，延迟时间值表示电流的提前或滞后程度。

![](../../_assets/8_3_6-2.png)<br>
*图 8.3.6-2. 弧感应延迟时间的意义*
<br>


{% hint style="info" %}
  延迟时间必须在 **-40 ~ +40** 的范围内。建议将垂直和水平跟踪增益（mm/A）设置在 **0.2 ~ 0.5** 的范围内。
{% endhint %}

{% hint style="info" %}
  一旦从 0.5 Hz 到 3.0 Hz 的所有编织操作都已执行，请导航到编织命令属性窗口延迟时间表选项卡左下角的“自动校准”选项，并单击“应用”以批量应用所有设置。
{% endhint %}

校准过程完成后，将垂直/水平方向的感应灵敏度改为 5，以启用弧感应功能。
[__SOURCE](8_Application_function/3_Arc_sensing/4_arcsen_command.md)
# 8.3.4 使用命令设置编织和弧传感条件

### (1) 功能的必要性

编织和弧传感条件在操作期间无法自动调整。 <br>
因此，可以使用命令修改条件，这些更改只对特定的编织部分有效。  

### (2) 使用命令的方法  

要插入命令，请在手动模式下输入 `[F6: cmd input] - var_io - assignment`。然后，将光标移至左侧变量并选择 `[F3: System Variables] - arcweld - _weaving.{parameter}`，在这里您可以输入所需的值。 <br>

输入的命令将以以下格式出现：  
```e.g. _weaving.frequency=2.0```  

- 示例)
```py
    weaving on, cnd=1	                # Weaving Command (cmd)
    arcon cnd=1
    move L,S=5mm/s,accu=1,tool=2
    _weaving.right_distance = 4	        # 使用命令设置墙壁方向距离
    _weaving.left_distance = 3	        # 使用命令设置墙壁方向距离
    MOVE L,S=5mm/s,A=1,T=2	            # 参数将从此部分开始修改
```

每个命令的输入值限制在条件文件定义的条件设置范围内。  
对于命令未明确指定的参数，将使用在编织命令中设置的条件。  

_weaving 的每个元素的设置对功能的适用性如下：  

<br>

| 变量名称 | 编织命令之后立即 | 没有弧传感的编织 | 具有弧传感的编织 | 持续变化焊接条件 |
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


<!-- ### (3) 编织参数命令种类及内容请参考以下链接。

[机器人语言 HRScript_weaving文](https://hrbook-hrc.web.app/#/view/doc-hrscript/ko/10-etc/3-sysvar/_weaving)   -->



<!-- 
(2)中说明的各参数种类和说明是 

weave: 编织模式

frequency: 编织频率

left_distance: 墙壁方向距离

right_distance: 另一方向距离

angle: 基本模式的角度

wall_direction: 基本模式的墙壁方向

forward_angle: 前进角度

boundary_limit: 是否使用边界限制

segment_time_1: 使用移动时间时各区间的时间

segment_delay_1: 使用移动时间时编织仅停止的时间

height_sensing_mode: 弧传感中上下传感执行方法

side_sensing_sensitivity: 左右方向弧传感敏感度

height_sensing_sensitivity: 上下方向弧传感敏感度

BaseCur: 上下传感基准电流

此值设置可用于设置焊炬和工件之间的距离。 
要使焊炬和工件之间的距离更远，请降低此值。 
相反，要使焊炬和工件更近，请提高此值。

StickOut: 在弧传感中上下方向移动焊炬的值。 输入的mm数量将改变焊炬高度。 输入正值时，焊炬和工件之间的距离变远，输入负值时，焊炬与工件之间的距离变近。

asymetric_sensing_ratio: 左右不对称传感比率

 -->
[__SOURCE](8_Application_function/3_Arc_sensing/5_arcsen_monitoring.md)
# 8.3.5 弧感测监控

### (1) 监控执行

通过访问 `[pane layout] - 选择 - 电弧传感 ([pane layout] - select - arc sensing)`，将激活弧感测监控窗口。
此功能仅在弧感测许可证有效时可用。

### (2) 监控项目说明

![](../../_assets/8_3_7.png)<br>
*图 8.3.7 弧感测监控*

- 左/右跟踪：基于跟踪速度、距离和左右方向的当前差分，通过感测显示需要修正的左右距离。

- 上/下跟踪：基于跟踪速度、距离和焊接缝的上下方向，通过感测显示需要修正的上下距离。

- XYZ 跟踪：与原始轨迹相比，显示到目前为止跟踪的距离，以基坐标系统的 X、Y 和 Z 方向表示。
[__SOURCE](8_Application_function/3_Arc_sensing/6_multipass_overview.md)
# 8.3.6 多道焊接概述

多道焊接功能用于厚板弧焊时，当所需的焊接长度太宽，无法在一个焊道中完成，或者焊接需要填充的体积太大，需进行多次焊接。

由于弧感应的固有特性，除了根焊道（即第一层）外，感应可能不稳定。因此，仅跟踪根焊道的弧感应。该焊道的轨迹随后被保存，存储的轨迹被移动以创建第二层及更高层的焊道。

由于多道焊接工作程序的位置与根焊道轨迹相同，因此只需复制根焊道工作程序并插入多道焊接命令即可轻松执行多道焊接。


![](../../_assets/8_3_8.png)<br>
*图 8.3.8 根焊道弧感应（左）和 2-3 层的多道焊接*

![](../../_assets/8_3_9.png)<br>
*图 8.3.9 实际多道焊接*

当按上面图 2 所示的叠放倾斜配置创建多道焊缝时，可以通过仅修改焊接的起始点和结束点并稍微偏移它们来进行焊接。  
这将产生如下所示的重叠配置。


![](../../_assets/8_3_10.png)<br>
*图 8.3.10 带倾斜的多道叠加形状*
[__SOURCE](8_Application_function/3_Arc_sensing/7_multipass_command.md)
# 8.3.7 多遍命令


### (1) 命令

感应轨迹可以使用多遍命令进行保存和加载。 
该命令可以以三种不同形式使用：
<br>

```py
    multipass save, trj=<multi-pass trajectory number>, period=<trajectory saving interval distance>
    multipass load, trj=<multi-pass trajectory number>, side=<left-right Shift distance>, height=<up-down Shift distance>, reverse=<multi-pass playback direction>, tas=<torch forward/backward angle shift>, was=<torch left/right angle shift>
    multipass off
```

### (2) 多遍参数

有关多遍命令参数的详细信息，请参考以下链接: <br>
[2.11 multipass](../../2_Command/11_multipass.md)

<br>

本节将仅解释以下两个项目：  


- 左右/上下偏移

这设置了在多遍重现过程中轨迹从原始路径偏移的距离。
由于喷嘴编织与工具垂直，因此每个偏移设置如下：
左/右方向成为编织平面，而上下方向成为与编织平面垂直的平面。

![](../../_assets/8_3_11.png)<br>
*图 8.3.11 多遍偏移方向*


- 角度偏移：TAS, WAS  

在进行多遍焊接时，喷嘴必须倾斜以进行质量控制。此设置用于定义所需的倾斜。
每个项目的角度概念在以下图中阐明：  

![](../../_assets/8_3_12.png)<br>
*图 8.3.12 多遍角度偏移概念*
[__SOURCE](8_Application_function/3_Arc_sensing/8_example_fillet.md)
# 8.3.8 钢焊接示例使用触觉传感和电弧传感

一般来说，电弧传感功能与触觉传感功能一起使用。触觉传感用于准确检测焊接的起始和结束位置，而电弧传感用于在焊接开始后确定正确的焊接方向。

第一个示例演示了基本的钢焊接操作。

工作顺序如下：

1) 设置摆动条件、电弧传感条件和焊接条件。  
2) 使用触觉传感搜索焊接起始位置。  
3) 移动到接近焊接结束区域的位置，然后使用触觉传感搜索焊接结束位置。  
4) 从焊接起始位置执行焊接操作，使用摆动命令和电弧焊接命令。  

![](../../_assets/8_3_13.png)<br>
*图 8.3.13 钢焊接触觉传感和电弧传感*  

示例程序如下所示。

~~~~~~~电弧传感程序 : 0001.JOB~~~~~~~~~~~~~~~  
' 电弧传感程序  
S1   move P,spd=60%,accu=3,tool=1              ' 1: 运动起始点  
S2   move L,spd=30%,accu=3,tool=1              ' 2: 焊接结束点的触觉传感位置  
     var p10=cpo()  
     var p1=cpo()  
     touchsen cnd=1,crd="robot", dir=["x","-z"], pose=p10   ' 3: 焊接结束点的触觉传感。位置存储在 P10  
S3   move L,spd=30%,accu=3,tool=1              ' 4: 焊接起始点的触觉传感位置  
     touchsen cnd=1,crd="robot",dir=["-x","-z"], pose=p1    ' 5: 焊接起始点的触觉传感。位置存储在 P1  
S4   move L,p1,spd=20%,accu=3,tool=1            ' 6: 移动到焊接起始点  
     weaving on, cnd=1                          ' 7: 开始摆动和电弧传感  
     arcon cnd=1                                ' 8: 开始焊接  
S5   move L,p10,spd=60cm/min,accu=3,tool=1      ' 9: 移动到焊接结束点  
     arcoff                                     '10: 结束焊接  
     weaving off                                '11: 结束摆动和电弧传感  
S6   move P,spd=60%,accu=3,tool=1               '12: 运动结束点  
     END  
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
[__SOURCE](8_Application_function/3_Arc_sensing/9_example_butt_gap.md)
# 8.3.9 弧传感示例：使用触觉传感设置自动织造宽度

创建一个适用于下面显示的两个工件的单个作业程序。

![](../../_assets/8_3_14.png)<br>
*图 8.3.14 触觉传感和弧传感的对接接头工件*

假定操作条件  

- 焊接两个工件之间的接头的过程，180° 平面织造，
- 焊接行程方向：X+。在 Y 方向上进行左右触觉传感。
- 弧传感参数设置假定已提前完成。
- 当间隙为 4.0 mm 时，焊接速度为 7.0mm/sec
- 当间隙为 8.0 mm 时，焊接速度为 3.5mm/sec

工作顺序如下：

1) 使用触觉传感命令，在对接接头的 **终点** 处测量焊接中心位置和间隙距离。
2) 使用触觉传感命令，在对接接头的 **起点** 处测量焊接中心位置和间隙距离。
3) 检查 gap_var 值是否在允许范围内。如果间隙在 2.0 mm 到 10.0 mm 之外，停止机器人。
4) 将测得的间隙距离的一半设置为每侧的织造偏移：左侧（墙侧）和右侧（对侧）。
5) 根据 4.0 mm 和 8.0 mm 间隙处的速度通过插值计算焊接速度。如果间隙小于 4.0 mm，应用固定速度 7.0 mm/s。如果间隙超过 8.0 mm，应用固定速度 4.0 mm/s。
6) 自动应用计算出的织造宽度和焊接行程速度，然后进行焊接操作。
7) 操作完成后，返回原始起始位置。

![](../../_assets/8_3_15.png)<br>
*图 8.3.15 对接接头触觉传感和弧传感*

示例程序如下所示。

~~~~~~~弧传感程序: 0002.JOB~~~~~~~~~~~~~~~ 
     ' 对接接头弧传感程序 
     ' 条件 No. 1: 起始条件，条件 No. 10: 结束条件
S1   move P,spd=60%,accu=3,tool=1              ' 1: 动作起点  
S2   move L,spd=30%,accu=3,tool=1              ' 2: 焊接终点的触觉传感位置  
     var p10=cpo()  
     var p1=cpo()  
     var gap_var1=0  
     var gap_var11=0  
     touchsen cnd=2,crd="tool",dir="+ty",lift_up=5,pose=p10,gap=gap_var11  
                                                ' 3: 焊接终点的触觉传感。位置存储在 P10  
S3   move L,spd=30%,accu=3,tool=1              ' 4: 焊接起点的触觉传感位置  
     touchsen cnd=3,crd="+ty",lift_up=5,pose=p1,gap=gap_var1  
                                                ' 5: 焊接起点的触觉传感。位置存储在 P1  

     ' 根据起点的间隙计算焊接速度和织造宽度  
     var V3=0  
     IF gap_var1<2.0 OR gap_var1>10.0 THEN      ' 间隙超出允许范围  
     GOTO *Error  
     ELSEIF gap_var1<4.0 THEN                   ' 如果间隙 ≤ 4 mm，则固定速度为 7 mm/s  
     V3=7.0                                     ' 起始焊接速度  
     ELSEIF gap_var1>8.0 THEN                   ' 如果间隙 ≥ 8 mm，则固定速度为 4 mm/s  
     V3=4.0                                     ' 起始焊接速度  
     ELSE                                       ' 对于间隙范围 4-8 mm 的线性插值  
     V3=(7-3.5)/(4-8)*gap_var1+10.5             ' 起始焊接速度的线性插值  
     ENDIF  

     var V4=gap_var1/2.0                        ' 左侧织造宽度（间隙的一半）  
     var V5=gap_var1/2.0                        ' 右侧织造宽度（间隙的一半）  

     '--------------------------------------------------------  
     ' 根据终点的间隙计算焊接速度和织造宽度  
     var V13=0  
     IF gap_var11<2.0 OR gap_var11>10.0 THEN    ' 间隙超出允许范围  
     GOTO *Error  
     ELSEIF gap_var11<4.0 THEN                  ' 如果间隙 ≤ 4 mm，则固定速度为 7 mm/s  
     V13=7.0                                    ' 结束时的焊接速度  
     ELSEIF gap_var11>8.0 THEN                  ' 如果间隙 ≥ 8 mm，则固定速度为 4 mm/s  
     V13=4.0                                    ' 结束时的焊接速度  
     ELSE                                       ' 对于间隙范围 4-8 mm 的线性插值  
     V13=(7-3.5)/(4-8)*gap_var11+10.5           ' 结束时的焊接速度的线性插值  
     ENDIF  

     var V14=gap_var11/2.0                      ' 左侧织造宽度  
     var V15=gap_var11/2.0                      ' 右侧织造宽度  

     '---------------------------------------------------------  
S4   move L,1,S=20%,A=3,T=1                     ' 6: 移动到焊接起点  
     weaving on, cnd=2                          ' 7: 开始织造和弧传感  
     arcon cnd=2                                ' 8: 开始焊接  
     arc_cond L,spd=V3,ld=V4,rd=V5,freq=2       ' 9: 焊接参数的连续变化（开始）  

S5   move L,p10,spd=60cm/min,accu=3,tool=1      '10: 移动到焊接终点  
     arc_cond L,spd=V13,ld=V14,rd=V15,freq=2    '11: 焊接参数的连续变化（结束）  
     arcoff                                     '12: 结束焊接  
     weaving off                                '13: 结束织造和弧传感  

S6   move P,spd=60%,accu=3,tool=1               '14: 动作终点  
     END  

     *Error                                     '15: 间隙超出范围时的逃生例程  
     DO200=1                                   '16: 输出信号指示错误  
     STOP                                      '17: 停止机器人  
     END  
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
[__SOURCE](8_Application_function/4_Height_sensing/README.md)
# 8.4 高度感应

此功能用于机器人工具需要与工件保持恒定距离的情况，例如 TIG 焊接。在 TIG 焊接中，高度与弧长成正比，这就是为什么此功能被称为弧电压控制（Arc Voltage Control，AVC）。与工件的距离由传感器输入的模拟电压、焊接机检测到的弧长修正参数，以及焊接电流或电压值进行调整。

<!-- 本功能的使用需要将感应功能的数据输入设置为“有效”。 
有关感应功能的数据输入设置的详细信息，请参考“1.3 弧焊应用条件设置”。 -- ???? -->

一旦感应功能输入数据的设置完成，可以通过以下过程使用高度感应功能。

### (1) 命令

要启动高度感应，使用命令 `height on, cnd=1`。
命令后面跟着条件编号。共有 8 种高度感应条件。
要停止高度感应，使用命令 `height off`。
停止命令不需要任何额外的参数。

带有高度感应命令的作业程序示例如下：

```python
    S1   move L,spd=100%,accu=1,tool=0
    S2   move L,spd=20%,accu=1,tool=0
    S3   move L,spd=100mm/s,accu=1,tool=0
         heightsen on, cnd=1		  # 启动高度感应
         arcon cnd=2		       # 启动弧焊接
    S4   move L,spd=10mm/s,accu=1,tool=0
         arcoff			       # 结束弧焊接
         heigghtsen off			  # 结束高度感应
    S5   move L,spd=20%,accu=1,tool=0
         END 
```

### (2) 高度感应功能操作顺序

高度感应在执行 ```arcon``` 命令后开始。由于电流和电压在焊接开始时通常不稳定，因此在其稳定之前，输入数据将被忽略。
一旦输入数据稳定，就根据设置参考数据的方法计算平均值。如果用户手动输入参考数据，则立即进行高度感应。

高度感应的操作顺序如下：

<p align="center">
  <img src="../../_assets/8_4_1.png" width="50%"></img>
  <em><p align="center">图 8.4.1. 高度感应功能操作顺序</p></em>
</p>
[__SOURCE](8_Application_function/4_Height_sensing/1_hsen_condition.md)
# 8.4.1 高度传感条件

按下 **[Property]** 键在 `heightsen` 命令中访问 "高度传感条件" 设置屏幕。条件设置屏幕如下所示。

![](../../_assets/8_4_2.png)<br>
*图 8.4.2. 高度传感条件对话框*

---

每个项目的设置和操作如下：

### (1) 条件编号: [1 ~ 8]

设置高度传感条件编号。

### (2) 输入数据类型

显示输入数据的类型。对于 GMAW，使用焊接电流，而对于 TIG 焊接，使用焊接电压。

### (3) 参考数据设置: <平均输入数据, 用户输入数据>

选择设置参考数据的方法。
- 平均输入数据 : 根据传感初始参考数据的平均值设置参考数据。
- 用户输入数据 : 允许用户直接输入参考数据。

### (4) 输入数据忽略时间: [0.0 ~ 5.0]

在不稳定的初始焊接状态下忽略信号的时间。
如果使用 "平均输入数据" 设置参考数据，则使用此时间计算指定时间内的参考值。
如果使用 "用户输入数据"，高度传感立即开始。

### (5) 输入数据平均时间: [0.5 ~ 10.0]

设置平均输入数据以计算传感参考数据的时间。
当选择 "平均输入数据" 作为参考数据设置方法时，此项目将出现。
（如果准确的参考高度尚未确定）

### (6) 参考数据设置: [-500.0 ~ 500.0]

这是用户直接输入高度传感参考值的项目。当选择 "用户输入数据" 设置参考数据时，此项目将出现。

### (7) 传感系数: [-100.0 ~ 100.0]

这是与输入数据差异对应的距离系数。较小的值会导致跟踪更平滑，对输入数据的响应较小，而较大的值会增加跟踪速度，但可能导致沿轨迹的振荡。

### (8) 跟踪速度限制: [0.1 ~ 10.0]

根据传感设置每秒的最大跟踪值。较小的值导致跟踪更平滑，而较大的值加快跟踪。

<!-- ### (10) 噪声敏感度  
    设置输入数据的噪声敏感度。如果被禁用，则为不支持的版本。 -->

### (9) 跟踪限制距离: [-300.0 ~ 0.0] ~ [0.0 ~ 200.0]

设置高度传感的总跟踪距离限制。

### (10) 误差的积分系数: [0.00 ~ 10.00]

设置高度传感性能中连续误差值的修正量。
设置大于 0 的值可改善跟踪性能，但如果值过大，可能会导致轨迹振荡。
从非常小的值开始，逐渐调整到适合现场的设置。
[__SOURCE](8_Application_function/5_LVS_tracking/README.md)
# 8.5 LVS(激光视觉传感器)缝合查找与追踪
[__SOURCE](8_Application_function/5_LVS_tracking/1_overall.md)
# 8.5.1 LVS 概述与规格

{% hint style="info" %}
该功能在版本 60.30-03 中可用。
{% endhint %}

该功能通过使用 LVS（激光视觉传感器）识别焊缝，实现对工件和夹具误差的实时补偿，从而在焊接过程中进行焊缝追踪。

LVS 必须直接连接到机器人的法兰。传感器检测焊缝，机器人的工具实时跟踪焊缝。

换句话说，通过焊缝追踪，即使焊接目标的位置发生变化并偏离原始参考点，焊接仍然可以进行。


![](../../_assets/8_5_1.png)<br>
*图 8.5.1. LVS 焊缝追踪流程图*

</br>

#### 命令

LVS 焊缝寻找到追踪功能通过 `lvs` 命令执行，可以通过选择 `[F6: cmd. input] - arcweld - lvs` 来输入。

命令的结构如下：

```python
lvs <function argument> cnd=<condition Number>, seam=<profile number to be sensed position>, sp=<pose variable of the sensed position>, mp=<pose variable of the master reference>, ms=<shift variable of the current sensing position relative to the master>
```

<table>
  <thead>
    <tr>
      <th>主要类别</th>
      <th>子类别</th>
      <th>含义</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="9">function argument</td>
    </tr>
    <tr>
      <td style="text-align:left">laser_on</td>
      <td style="text-align:left">打开激光。</td>
    </tr>
    <tr>
      <td style="text-align:left">laser_off</td>
      <td style="text-align:left">关闭激光。</td>
    </tr>
    <tr>
      <td style="text-align:left">seam_find</td>
      <td style="text-align:left">
        传感器当前正在感知的激光焊缝位置被存储在命令的 'sp' 参数指定的位姿变量中（机器人/基坐标系）。 <br>
        请注意，方向 (RX, RY, RZ) 在执行命令时记录为工具的方向。
      </td>
    </tr>
    <tr>
      <td style="text-align:left">seam_find_p</td>
      <td style="text-align:left">
        传感器当前正在感知的激光焊缝位置被存储在命令的 'sp' 参数指定的位姿变量中（机器人/基坐标系）。 <br>
        请注意，方向 (RX, RY, RZ) 保持为原始位姿变量，仅更新 X、Y 和 Z 值。 <br>
        在使用如 'intersection' 的函数时，这特别有用，通过三点计算位姿来决定交点。
      </td>
    </tr>
    <tr>
      <td style="text-align:left">auto_calib</td>
      <td style="text-align:left">
        执行 TCP 和 LVS 之间的自动校准。（参考 <a href="https://hrbook-hrc.web.app/#/view/doc-arc-weld/zh/8_Application_function/5_LVS_tracking/3_calibration?cont_model=${cont_model}">LVS 校准</a>）
      </td>
    </tr>
    <tr>
      <td style="text-align:left">search</td>
      <td style="text-align:left">
        在 +ToolX、-ToolX 方向移动时找到起始点，并进行追踪准备。 <br>
        检测到的起始点存储在命令的 'sp' 参数指定的位姿变量中。
        （参考 <a href="https://hrbook-hrc.web.app/#/view/doc-arc-weld/zh/8_Application_function/5_LVS_tracking/6_search?cont_model=${cont_model}">LVS 搜索功能</a>）
      </td>
    </tr>
    <tr>
      <td style="text-align:left">step_search</td>
      <td style="text-align:left">
        在 +ToolX、-ToolX 方向移动时找到起始点或多焊道的起始点。 <br>
        检测到的起始点存储在命令的 'sp' 参数指定的位姿变量中。
        （参考 <a href="https://hrbook-hrc.web.app/#/view/doc-arc-weld/zh/8_Application_function/5_LVS_tracking/6_search?cont_model=${cont_model}">LVS 搜索功能</a>）
      </td>
    </tr>
    <tr>
      <td style="text-align:left">track</td>
      <td style="text-align:left">
        搜索完成后，必须在执行之前先执行 'arcon' 和 'weaving on' 操作。 <br>
        跟踪将持续进行，直到遇到 'arcoff'。
      </td>
    </tr>
    <tr>
      <td colspan="2">条件号</td>
      <td>
        这是用于应用在 lvs 命令的属性窗口中配置的设置的条件号。 <br>
        属性窗口允许您设置搜索速度、搜索距离、队列间隔、追踪限制和感知坐标系统（机器人/基），以及其他参数。
      </td>
    </tr>
  <tr>
      <td colspan="2">要感知的位置的配置文件编号</td>
      <td>
        这指的是用户在 LVS 控制器中注册的与感知形状和感知条件相对应的编号。
        当执行命令时，LVS 控制器加载与该编号关联的感知形状和条件。
      </td>
    </tr>
    <tr>
      <td colspan="2">感知位置的位姿变量</td>
      <td>
        当前激光位置对应的位置被存储为位姿变量。
      </td>
    </tr>
    <tr>
      <td colspan="2">主位置的位姿变量</td>
      <td>
        这是在主模式下注册的参考位姿变量。
        （参考 <a href="https://hrbook-hrc.web.app/#/view/doc-arc-weld/zh/8_Application_function/5_LVS_tracking/5_lvs_master_mode?cont_model=${cont_model}">8.5.5 LVS 主模式功能</a>）
      </td>
    </tr>
    <tr>
      <td colspan="2">当前感知位置相对于主位置的偏移变量</td>
      <td>
        当前感知位置相对于 mp（主位姿）的偏移存储。
        （参考 <a href="https://hrbook-hrc.web.app/#/view/doc-arc-weld/zh/8_Application_function/5_LVS_tracking/5_lvs_master_mode?cont_model=${cont_model}">8.5.5 LVS 主模式功能</a>）
      </td>
    </tr>
    <tr>
      <td colspan="2">opt</td>
      <td>
        使用 auto_calib 命令时，此值应设置为 0。
      </td>
    </tr>
    <tr>
      <td colspan="2">find_flag</td>
      <td>
        如果为此参数设置了变量，则在成功找到焊缝时将其设置为 1，而在焊缝查找失败时将其设置为 0且没有任何错误。
      </td>
    </tr>
  </tbody>
</table>  


使用 ```lvs``` 命令的追踪功能可以如下使用：


![](../../_assets/8_5_2.png)<br>
*图 8.5.2. LVS 焊缝追踪的教学方法*


---

#### LVS 功能规格

* 支持一般运动追踪功能（线性 L 插值、圆形 C 插值和复合线性与圆形段）
* 支持织布追踪功能（0.5Hz ~ 3Hz）
* 支持定位器同步追踪功能（SMOV 段）
* 支持定位器同步 + 织布追踪功能（0.5Hz ~ 3Hz）


<table>
  <thead>
    <tr>
      <th style="text-align:left">项目</th>
      <th style="text-align:left">LVS 制造商</th>
      <th style="text-align:left">重复精度</th>
      <th style="text-align:left">重复精密度</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left" rowspan="3">seam_find / seam_find_p</td>
      <td style="text-align:left">SCANSONIC (350, 150, 150 advanced)</td>
      <td style="text-align:left">左右 : 0.1 mm (参考 ± 30mm 高度)， 0.4mm<br>高度 : 0.4mm (参考 ± 30mm 高度)， 2mm<br>前后 : 0.4mm (参考 ± 30mm 高度)， 1.5mm</td>
      <td style="text-align:left">0.05 mm</td>
    </tr>
    <tr>
      <td style="text-align:left">OXFORD (OSL-50)</td>
      <td style="text-align:left">左右 : 0.4 mm (参考 ± 30mm 高度)， 0.7mm<br>高度 : 0.6mm (参考 ± 30mm 高度)， 3mm<br>前后 : 0.6mm (参考 ± 30mm 高度)， 2.5mm</td>
      <td style="text-align:left">0.2 mm</td>
    </tr>
    <tr>
      <td style="text-align:left">Full-v</td>
      <td style="text-align:left">左右 : 0.6 mm (参考 ± 30mm 高度)， 2mm<br>高度 : 0.8mm (参考 ± 30mm 高度)， 4.5mm<br>前后 : 0.6mm (参考 ± 30mm 高度)， 4mm</td>
      <td style="text-align:left">0.35 mm</td>
    </tr>
    <tr>
      <td style="text-align:left" rowspan="3">track</td>
      <td style="text-align:left">SCANSONIC (350, 150, 150 advanced)</td>
      <td style="text-align:left">0.2mm (线性)<br>0.4mm (织布)<br>0.25mm (定位器同步)<br>0.5mm (织布 + 定位器同步)</td>
      <td style="text-align:left">0.05 mm</td>
    </tr>
    <tr>
      <td style="text-align:left">OXFORD (OSL-50)</td>
      <td style="text-align:left">0.3mm (线性)<br>0.5mm (织布)<br>0.4mm (定位器同步)<br>0.6mm (织布 + 定位器同步)</td>
      <td style="text-align:left">0.2 mm</td>
    </tr>
    <tr>
      <td style="text-align:left">Full-v</td>
      <td style="text-align:left">0.3mm (线性)<br>0.6mm (织布)<br>0.4mm (定位器同步)<br>0.7mm (织布 + 定位器同步)</td>
      <td style="text-align:left">0.35 mm</td>
    </tr>
  </tbody>
</table>
[__SOURCE](8_Application_function/5_LVS_tracking/2_settings.md)
# 8.5.2 LVS 设置


要使用 LVS 功能，需要传感器安装和通信设置。

现在让我们看看涉及的过程。

### (1) 使用连接支架安装 LVS 传感器

连接支架可以由您自行设计和使用，也可以从 HD Hyundai Robotics 或 LVS 制造商那里获得。 <br>

![](../../_assets/8_5_3_lvs_mount_setup.png)<br>
*图 8.5.3. LVS 安装注意事项*

{% hint style="warning" %}
  - 为实现重复精度和精确度，必须将 LVS 支架直接安装到机器人法兰上<br>
  - 换句话说，机械装配应如下安装：法兰 - LVS 支架，LVS 传感器 - 冲击传感器（如使用） - 焊枪。
{% endhint %}

工具坐标系应如下设置：焊接方向与进度方向相反应设置为 +Tool X 方向，焊丝方向应设置为 +Tool Z 方向，如下图所示。

LVS 传感器必须安装，以便激光垂直于焊缝，且是直的（见图）

![](../../_assets/8_5_4.png)<br>
*图 8.5.4. TCP 和传感器安装，工具坐标系设置*

{% hint style="info" %}
  有关设置工具坐标系的说明，请参阅工具校准和角度校正手册（角度校准）部分。
{% endhint %}

{% hint style="warning" %}
  为了使用 LVS，激光应位于焊接方向的前方，并且工具坐标系必须如上图所示进行设置。
{% endhint %}

---

### (2) 通信设置

使用以太网电缆连接 LVS 传感器控制器和机器人控制器。<br>
导航到 `[F2: 系统] - 4: 应用参数 - 5: LVS 跟踪 - 1: Envrionment setting ([F2: System] - 4: Application parameter - 5: LVS tracking - 1: Envrionment setting)`。<br>

在 **[通信]** 选项卡中，配置以下项目：

- LVS 品牌 : Scansonic, Oxford (或 Meta), Full-v<br>
- IP 地址 : 输入传感器控制器的 IP 地址。
- 本地端口 : 机器人控制器的端口。（对于 Oxford, 8000）
- 远程端口 : 传感器控制器的端口。（对于 Oxford, 8002）

输入上述信息后，点击 **[connect]**。如果状态显示“已连接”，则连接成功建立。

{% hint style="info" %}
- [IP 地址] : 用于将数据从 LVS 控制器发送到机器人控制器的 IP 地址在 LVS 控制器中设置。
  - 如果设置不正确，连接可能会失败。在这种情况下，请参阅 LVS 制造商的手册。
- [端口] : 选择品牌时，默认值将自动应用，因此用户无需修改它们。
  - 如果端口不正确，连接可能会失败。在这种情况下，请参阅 LVS 制造商的手册。
{% endhint %}

---

### (3) 基本设置

在 **[跟踪]** 选项卡中，配置以下项目： 
- P 增益 : 指定 TCP 跟踪转换位置和方向的强度。
- D 增益 : 指定 TCP 对转换位置和方向的响应速度。
- 最大跟踪距离 : 指定每秒的最大跟踪量以 [mm/sec] 为单位。


<table>
  <thead>
    <tr>
      <th style="text-align:left">项目</th>
      <th style="text-align:left">说明</th>
      <th style="text-align:left">推荐设置</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">P, D 增益</td>
      <td style="text-align:left">指定 TCP 跟踪转换位置和方向的强度。</td>
      <td style="text-align:left">
        一般跟踪（不使用编织） : 设置在 1 ~ 10 范围内。 <br>
        编织跟踪（使用编织） : 使用默认值 10。 <br>
        默认值为 P 增益：10，D 增益：10。根据实际工件调整这些值。
      </td>
    </tr>
    <tr>
      <td style="text-align:left">每秒最大跟踪距离 [mm/sec]</td>
      <td style="text-align:left">指定每秒的最大跟踪量，以 [mm/sec] 为单位。</td>
      <td style="text-align:left">
        设置在 1 到 5 之间。默认值为 10。<br>
        LVS 焊缝跟踪旨在修正与教导轨迹的微小偏差，因此无需设置更大的值。
      </td>
    </tr>
  </tbody>
</table>


通过上述过程完成了偏好设置。

---

#### Full-V 传感器配置示例

![](../../_assets/8_5_5_lvs_setting_fullv_1.png)<br>
*图 8.5.5. Full-V 传感器连接设置*

如上图所示，选择 LVS 品牌为 FULL，然后在 Full-V 软件中检查 LVS 传感器的 IP 地址。  <br>
在 `[F2: 系统] - 4: 应用参数 - 5: LVS 跟踪 - 1: Envrionment setting ([F2: System] - 4: Application parameter - 5: LVS tracking - 1: Envrionment setting)` 窗口中输入 IP。  <br> 然后，点击底部的“connect”按钮，并确认连接状态显示。  <br>
如果出现“已断开”字样，请检查硬件连接和 IP 地址。<br>

请参考 Full-V 提供的手册和下图以在 Full-V 软件中注册您希望使用的焊缝。  


![](../../_assets/8_5_6_lvs_setting_fullv_2.png)<br>
*图 8.5.6. Full-V 软件中焊缝设置示例*
[__SOURCE](8_Application_function/5_LVS_tracking/3_calibration.md)
# 8.5.3 LVS 校准


为了使用 LVS 功能，必须首先在 TCP 和传感器坐标系统之间进行校准。

${cont_model} 控制器支持自动校准。

现在我们来看看如何在 TCP 和 LVS 传感器之间进行自动校准。

### (1) 校准样本的准备

准备一个 15 厘米长的搭接接头样本，步长为 3 毫米。


{% hint style="info" %}
如果您希望用于测试，请联系我们准备校准样本。
{% endhint %}

---

### (2) 自动校准教学

![](../../_assets/8_5_7_lvs_autocalib.png)<br>
*图 8.5.7. LVS 自动校准*   
</br>

如上图所示，使用走动功能将 TCP 移动到样本的参考点。

焊枪的方向应垂直于样本（滚转和俯仰方向都应垂直）。

使用走动功能将激光线位置设置为垂直于样本边缘（通常由工具 Z 控制）。

在此状态下（焊枪位置垂直于样本，激光线垂直于样本边缘），按 **[记录]** 插入 `移动 (move)` 命令。

{% hint style="warning" %}
- 使用水平尺精确对齐焊枪的方向，使其垂直于校准样本。
- 焊枪的垂直精度以及激光线与样本边缘垂直的精度将影响校准精度。
{% endhint %}


插入 `delay 0.5` 后，输入 `lvs` 命令。

`lvs` 命令的接缝参数是与 LVS 控制器中注册的形状和条件相对应的编号。

{% hint style="info" %}
对于校准，请在 LVS 控制器的软件中将接缝注册为搭接接头。<br>
在 lvs 命令的接缝参数中设置注册的编号。
{% endhint %}


按上述方式编写的程序如下所示：

```python
    move L,spd=60%,accu=0,tool=0  # 校准样本参考点
    delay 0.5
    lvs auto_calib, cnd=1, seam=1, sp=p1, opt=0
    end
```

---

### (3) 准备工作

自动校准涉及前后、左右、滚转方向旋转和高度调整等运动，因此确保遵循安全措施。

{% hint style="warning" %}
* 调整 LVS 设置（曝光时间、激光强度、形状设置），以便 LVS 即使在较高位置也能识别样本的接缝。
* 当激光指向样本参考点外的平面表面时，LVS 控制器不应能够识别接缝。
{% endhint %}


---

### (4) 执行

一旦校准完成，"comp!" 指示灯将出现在 'LVS 跟踪' 监控表的 '信息' 部分。

---

### (5) 工具和 LVS 校准信息

每个工具编号都有其自身的 LVS 校准，这在使用工具更换时非常有用。

如果您对工具 0 执行自动校准，并想使用工具 1 或工具 2，您还需要对这些工具执行自动校准。

如果您想使用相同的工具信息但编号不同，可以进入以下窗口以复制和应用校准信息。

- 导航至 `[F2: 系统] - 4: 应用参数 - 5: LVS 跟踪 - 2: LVS 校准 ([F2: System] - 4: Application parameter - 5: LVS tracking - 2: LVS Calibration)`.<br>

![](../../_assets/8_5_8_lvs_tool_calibmat.png)<br>
*图 8.5.8. LVS 校准信息*   
</br>
[__SOURCE](8_Application_function/5_LVS_tracking/4_seam_finding.md)
# 8.5.4 LVS 接缝查找功能

### (1) 接缝查找概述

该功能将 LVS 传感器感知到的位置存储为姿态，可以作为接触传感的替代品。

{% hint style="warning" %}
  如果在使用此功能之前未对 TCP-LVS 传感器进行校准，将保存异常的姿态。
{% endhint %}

命令格式如下：  
执行该命令后，如下所示，LVS 传感器感知到的位置将存储在 po_100 变量中。

```python
  var po_100=cpo()  # 当前姿态存储在变量 po_100 中
  lvs seam_find, cnd=1, seam=1, sp=po_100 # 如果 sp 参数中没有输入的名称，则将自动声明为局部姿态变量。
```

{% hint style="warning" %}
  如果 **sp** 参数未声明，则将声明为局部姿态。 <br>
  如果 **mp** 参数未声明，则将声明为全局姿态。 <br>
  如果 **ms** 参数未声明，则将声明为全局偏移。
{% endhint %}


![](../../_assets/8_5_9_lvs_seamfind_ex.png)<br>
*图 8.5.9. LVS 感知位置中的姿态*   
</br>

{% hint style="info" %}
  - 使用 **seam_find** 命令存储在 sp 参数中的姿态的方向将保持在感知前的工具方向 (Rx, Ry, Rz)。
  - 另一方面，使用 **seam_find_p** 命令时，仅记录存储在 sp 参数中的姿态的位置。
{% endhint %}

* 如果您想在姿态中仅存储位置，而不考虑预感知的方向，请使用以下命令格式。<br>
当您希望记录焊接姿态并使位置 (X, Y, Z) 对应于 LVS 感知到的点时，该功能非常有用。

```python
var po_100=cpo()
lvs seam_find_p, cnd=1, seam=1, sp=po_100
```

* 从感知位置向工具 Y 和工具 Z 方向偏移的姿态可以通过以下方式计算。 <br>
该命令计算出在感知期间向工具 Y 方向偏移 10mm 和向工具 Z 方向偏移 10mm 的姿态。

```python
var po_100=cpo()
lvs seam_find, cnd=1, seam=1, side=10, height=10, sp=po_100
```

---

### (2) LVS 接缝查找重试

如果在接缝查找期间无法识别接缝，则将执行重试。

重试的次数在 LVS 命令属性窗口的接缝查找选项下的 **"no of retry"** 中指定。

如果在指定次数的重试后仍然无法感知，将发生错误。

重试过程按以下顺序进行：

![](../../_assets/8_5_10_lvs_seamfind_retry.png)<br>
*图 8.5.10. LVS 接缝查找重试*   
</br>

{% hint style="warning" %}
* 使用主偏移功能时，请注意重试会导致位置前后偏移（+ToolX, -ToolX）。
{% endhint %}

---

### (3) LVS 接缝查找监控

要查看 LVS 接缝查找监控屏幕，请在 TP 中点击 `[pane layout] - 选择 - LVS 焊缝查找 ([pane layout] - select - LVS seamfind)`  


![](../../_assets/8_5_11_seamfind monitoring.png)<br>
*图 8.5.11. LVS 接缝查找监控*   
</br>
<table>
  <thead>
    <tr>
      <th style="text-align:left">项目</th>
      <th style="text-align:left">描述</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">位置 (X, Y, Z)</td>
      <td style="text-align:left">
        显示当前感知的位置（以基坐标表示）<br>
        规格：母体姿态的位置。如果未注册，将显示为 (-1, -1, -1)<br>
        感知：当前感知的位置 
      </td>
    </tr>
    <tr>
      <td style="text-align:left">间隙</td>
      <td style="text-align:left">
        规格：母间隙 [mm]<br>
        感知：当前感知的间隙 [mm]
      </td>
    </tr>
    <tr>
      <td style="text-align:left">面积</td>
      <td style="text-align:left">
        开口或对接形状的内部区域宽度 [mm^2]<br>
        规格：母区域 [mm]<br>
        感知：当前感知的面积 [mm]
      </td>
    </tr>
    <tr>
      <td style="text-align:left">不匹配</td>
      <td style="text-align:left">
        不匹配值通常指左右形状的高度差。
      </td>
    </tr>
  </tbody>
</table>

{% hint style="info" %}
  间隙、面积、不匹配等值仅对制造商的 LVS 控制器支持的接缝显示。
{% endhint %}

如果母体姿态已注册，可以按 prev 或 next 按钮查看当前作业的感知历史。

{% hint style="info" %}
  有关主模式的更多详细信息，请参阅 [8.5.5 LVS 主模式功能](./5_lvs_master_mode.md)。
{% endhint %}
[__SOURCE](8_Application_function/5_LVS_tracking/5_lvs_master_mode.md)
# 8.5.5 LVS 主模式功能

### (1) 主模式概述

主模式功能存储参考位置（主姿态），并在实际生产过程中计算当前感测位置与参考位置之间的偏移。

要启用此功能，必须激活`用户密钥 - 主基准 模式 (user key - Master Mode)`以预先注册参考位置（主姿态）。

![](../../_assets/8_5_12_lvs_seamfind_mastermode.png)<br>
*图 8.5.12. 主模式和实际运动的示例*   
</br>

如图左侧所示，在激活主模式后，主姿态保存到分配给`mp`参数的姿态变量中。

通常，感测点是预先教学的，一旦激活主模式，系统将自动回放以完成主教学。

在厚焊接应用中，通常会注册几十个焊接路径点作为主姿态。

一旦主教学完成，主模式将关闭。完成主教学后无需重新开启主模式。

在生产过程中，机器人在自动或远程模式下操作，并感测每个焊接点以计算偏移。

此时，相对于主姿态的偏移会被自动计算并存储在`(ms)`参数指定的偏移变量中。

然后，将该偏移值应用于`tg`参数的`移动 (move)`命令中，以补偿焊接位置的偏移，使焊接操作能够准确进行。

{% hint style="warning" %}
注册主姿态时的重要注意事项。

* 在主姿态注册期间，确保LVS S/W在感测位置感测到的缝边和高度均接近0。
* 通过上述教学，可以稳定地进行感测，并且主姿态管理以及LVS或工具中的任何对齐错误都可以轻松识别。

{% endhint %}

![](../../_assets/8_5_13_lvs_seamfind_mastermode_warn.png)<br>
*图 8.5.13. 注册主姿态时的重要考虑事项*   
</br>

---

### (2) 相对于主模式的偏移量检查功能

当前感测姿态与主姿态之间的偏移量（以毫米为单位）可以检查，以验证其是否在用户定义的范围内。

要设置范围，请访问lvs命令中的**[property]**窗口，并在“缝合查找选项”下的“距离参考位置”字段中输入所需的距离（以毫米为单位）。

如果在缝合查找期间偏移值超过用户定义的范围，将会发生错误。

{% hint style="warning" %}
如果未声明`sp`参数，它将被视为局部姿态。<br>
如果未声明`mp`参数，它将被视为全局姿态。<br>
如果未声明`(ms)`参数，它将被视为全局姿态。
{% endhint %}
[__SOURCE](8_Application_function/5_LVS_tracking/6_search.md)
# 8.5.6 LVS 搜索功能

### (1) 如何使用搜索功能

LVS 提供搜索功能，主要用于以下目的：

- `搜索 (search)`：搜索起始点结束，当 TCP (Tool Center Point) 移动到起始位置时，将要跟踪的点以设定的间隔存储在缓冲区中，为跟踪做准备。
- `step_search`：用于多通道焊缝检测和步骤检测。

当进行搜索时，系统会搜索目标，如果检测到无效点，最近的有效点会作为姿态存储在 `sp` 参数中。

随后，为了准备跟踪，系统将要跟踪的点存储在缓冲区中，当 TCP 移动到找到的点时。

通过执行搜索功能，系统准备好执行“缝跟踪”。

{% hint style="info" %}
  搜索过程检测无效的焊缝（当 LVS 控制器无法检测到焊缝时）并搜索起始点。
  **搜索** 功能找到起点（或终点），然后移动到该位置，存储要跟踪的点在缓冲区中。
{% endhint %}


```search``` 功能的使用方法如下：

```python
    move L, spd=60%, accu=0, tool=1
    delay 0.1 # 如果起始位置的精确度不是 0，则必须插入。
    var po_100=cpo() # 当前姿态存储在变量 po_100 中
    lvs search, cnd=1, seam=1, sp=po_100
```

要配置搜索功能，请在 `lvs` 命令中输入 **[property]**，搜索设置可以按如下方式进行调整：

![](../../_assets/8_5_14_lvs_search_setting.png)<br>
*图 8.5.14. lvs 搜索设置*   
</br>

| 项目 | 描述 |
|------|------|
| function | 设置搜索功能的使用。<br> 'Disable': 系统移动到 LVS 的激光位置并将目标位置存储在缓冲区。<br> 'Enable': 系统在搜索方向上检测起始和结束点，然后移动到检测到的位置，同时将目标位置存储在缓冲区。 |
| distance | 如果搜索功能设置为 **enable**，则应输入搜索起始点的最大距离 [mm]。 |
| direction | 0: 在 +ToolX 方向搜索。<br> 1: 在 -ToolX 方向搜索。 |
| speed | 搜索速度可以设置为 mm/sec。 |
| offset | 在焊接线方向上找到的点可以从检测到的位置向指定的毫米数偏移。 |

<br>

![](../../_assets/8_5_15_lvs_search_example.png)<br>
*图 8.5.15. lvs 搜索示例*   
</br>

**搜索** 和 **缝跟踪** 功能可以如下教导。

```python
    move L, spd=60%, accu=0, tool=1
    delay 0.3
    var po_100=cpo() # 当前姿态存储在变量 po_100 中
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

### (2) 如何使用多通道焊缝检测功能 (step_search) 

此功能用于检测多通道焊缝的起始点，其使用方法与 `搜索 (search)` 功能相同。

在 `lvs` 命令的 **[property]** 窗口中，将功能设置为 "Enable" 并在 "distance" 字段中配置扫描距离。

可以如下使用：

```python
    move L, spd=60%, accu=0, tool=1 # 设置多通道焊缝检测扫描的起始点。
    delay 0.3
    var po_100=cpo() # 当前姿态存储在变量 po_100 中
    lvs step_search, cnd=1, seam=1, sp=po_100
    move L, tg=po_100, spd=40cm/min, accu=3, tool=1 # 移动到找到的位置。
    end
```
[__SOURCE](8_Application_function/5_LVS_tracking/7_tracking_monitoring.md)
# 8.5.7 LVS 跟踪功能和监控

### (1) LVS 跟踪概述

LVS 跟踪是一个补偿教学轨迹与实际焊接线之间差异的功能。

{% hint style="warning" %}
基准工件的教学应以高精度进行。<br>
在施加移位以修正工件定位误差后，应使用 LVS 功能。<br>
有关详细信息，请参阅 [8.5.5 LVS 主模式功能]。
{% endhint %}

由于激光装置安装在 TCP 前面，必须先进行搜索以执行跟踪。

{% hint style="info" %}
请参阅上一部分，**[8.5.6 LVS 搜索功能]**，以获取有关搜索功能的详细信息。
{% endhint %}


lvs 命令的配置应设置如下：

```python
    move L, spd=60%, accu=0, tool=1
    delay 0.3
    var po_100=cpo() # 当前姿态存储在变量 po_100 中
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

执行搜索命令的过程如下面的图所示（当搜索设置为有效且方向设置为 0 时）。
一个无效点被找到并存储在 `sp` 参数中作为起始点，然后 TCP 移动到起始点，同时填充数据缓冲区。

![](../../_assets/8_5_17.png)<br>
*图 8.5.17. LVS 搜索过程*   
</br>

### (2) 如何使用带偏移值的跟踪

如果您想要在接缝上使用偏移进行跟踪（而不是严格跟随焊接线），可以在 `lvs` 命令中以毫米为单位指定侧向和高度的偏移值。该偏移在工具坐标系统方向上应用。

```python
    move L, spd=60%, accu=0, tool=1
    delay 0.3
    var po_100=cpo() # 当前姿态存储在变量 po_100 中
    lvs search, cnd=1, seam=1, sp=po_100
    weavon cnd=1  
    arcon cnd=1
    lvs track, cnd=1, seam=1, sp=po_100, side=5, height=-5 # 偏移跟踪在 ToolX 中 5mm，在 ToolZ 中 -5mm
    move L, spd=30cm/min, accu=3, tool=1
    move L, spd=36cm/min, accu=3, tool=1
    move L, spd=40cm/min, accu=3, tool=1
    weavoff
    arcof
    end
```

{% hint style="info" %}
* 使用编织时，突出长度会根据角度和振幅增加。为了补偿这一点，在搜索和跟踪操作期间将高度设置为负值。
{% endhint %}

### (3) LVS 监控

![](../../_assets/8_5_18_tracking_monitoring.png)<br>
*图 8.5.18. LVS 监控*   
</br>

LVS 监控可以通过选择 `[pane layout] - 选择 - LVS 跟踪 ([pane layout] - select - LVS tracking)` 来激活。

在监控中，可以检查以下项目：

| 项目 | 描述 |
|------|------|
| 总累计补偿<br> (X, Y, Z) | 如果未使用编织，则此项目表示相对于基准坐标系统的累计补偿。如果使用编织，则表示在编织坐标系统中的累计补偿。 |
| 传感器 | qual: 指示当前激光接缝感应是否有效或无效。<br> Y, Z: 当前感应接缝在传感器图像坐标系统中的位置（2D）。 |
| 工具尖端 | TCP 相对于基准坐标系统的当前位置。 | 
| 跟踪点 | TCP 当前正在跟踪的点，相对于基准坐标系统。 |
| 感应点 | 当前被激光感测位置的基准坐标值。 |
| 缓冲区大小 | 存储在用于跟踪的数据缓冲区中的点数。如果该值不断增加、减少或达到 0，则可能存在跟踪、通信或配置的问题。 |
| 信息 | 显示自动标定的进度和其他相关信息。 |
| 实时图像 | 显示要跟踪的点，以红色圆圈表示，存储在缓冲区中。 |
[__SOURCE](8_Application_function/6_Stitch/README.md)
# 8.6 STITCH 功能
[__SOURCE](8_Application_function/6_Stitch/1_overall_.md)
# 8.6.1  STITCH Func. 概述

缝合焊接是一种间歇性进行焊接的功能，类似于缝纫。在 [Figure 8.6.2] 中，通过在样本上设置起始和结束点来进行缝合焊接。在缝合焊接中，如 [Figure 8.6.1] 所示，参数 ` (a)` 和 ` (b)` 被设置，以确定焊接部分和非焊接部分的长度，从而形成缝合图案。

[Figure 8.6.3] 提供了缝合焊接过程的简单解释。从 P[1] 到 P[4] 的位置被记录。在此图中，使用命令 ```stitch on/off``` 和 ```arcon/arcoff``` 在 P[2] 和 P[3] 部分进行缝合焊接。

</br>

![](../../_assets/8_6_1.png)<br>
*Figure 8.6.1. Stitch Func. 基本参数* 

</br>



![](../../_assets/8_6_2.png)<br>
*Figure 8.6.2. 缝合焊接样本* 
 
</br>


![](../../_assets/8_6_3.png)<br>
*Figure 8.6.3. 缝合焊接过程* 
[__SOURCE](8_Application_function/6_Stitch/2_command.md)
# 8.6.2 STITCH Func. Command
 

![](../../_assets/8_6_4.png)<br>
*图 8.6.4. 缝合命令示例*  


```stitch``` Command: 
在顺序选择 `[F6: 指令输入] - arcweld - stitch ([F6: cmd.input] - arcweld - stitch)` 后，选择开/关并按 **[ENTER]**。


{% hint style="warning" %}
- ```S2 move L, spd=10mm/s, accu=3, tool=1```  
	- L : 确保选择了线性插值。  
	- 200mm/sec : 焊接速度 - 在缝合焊接的开机部分的速度。单位必须设置为 mm/sec
- ```arcon / arcoff``` 一起使用命令开始焊接。
{% endhint %}
[__SOURCE](8_Application_function/6_Stitch/3_parameter.md)
# 8.6.3 STITCH Func. 参数设置


![](../../_assets/8_6_5.png)<br>
*图 8.6.5. 缝焊过程剖面*


[图 8.6.5] 说明了缝焊过程。根据此图表，您可以配置 `stitch` 命令的选项。

![](../../_assets/8_6_6.png)<br>
*图 8.6.6. 缝焊条件对话框1 (常规)*

![](../../_assets/8_6_7.png)<br>
*图 8.6.7. 缝焊条件对话框2 (段落)*


[图 8.6.6] 显示了通过将光标放置在 `stitch` 命令上并按 TP 屏幕左侧的 `[Property]` 按钮访问的屏幕。[图 8.6.7] 是通过从前一个屏幕选择 `[Section]` 标签访问的。
每个图的参数描述如下：

- 条件编号：从右侧的条件列表中选择
- 描述：使用软键盘输入
- 常规
  - (1) 延时开启时间：焊接信号提前开启的时间段
  - (2) 延时关闭时间：焊接信号提前关闭的时间段
  - (3) 启动距离：缝焊开始前的速度输入段的长度（开启段）
  - (4) 关闭速度：非重叠（关闭）段的焊接速度

- 段落
  - (5) 段落：缝焊条件  <br/>
    示例。当在段落 1 的条件下进行缝焊指定次数后，缝焊将在段落 2 的条件下进行。
  - (6) 开启距离：焊接段的长度
  - (7) 关闭距离：非重叠（关闭）段的长度
  - (8) 次数：缝焊重复的次数
  - (9) 开启速度：焊接段的焊接速度

{% hint style="warning" %}
- `(9) 开启速度`：缝段中的焊接（开启）段的速度设置为步幅速度。
{% endhint %}
[__SOURCE](8_Application_function/6_Stitch/4_aux_spec.md)
# 8.6.4 STITCH Func. Additional Specifications

- **紧急停止，重启**  

在缝合焊接过程中，经过紧急停止或回放停止后，工艺可以恢复。然而，如果控制器电源关闭并重启，则无法重新启动缝合焊接。
[__SOURCE](8_Application_function/7_LPS/README.md)
# 8.7 LPS(Laser Point Sensing)  

{% hint style="info" %}
此功能在版本70.00-00及更高版本中受支持。
{% endhint %}

此功能用于实现类似触觉传感的效果，例如检测焊接起点、中间点和终点。  
由于触觉传感要求焊接电线与基材直接接触，因此执行时间较长，并可能因焊炬而导致干扰。  

为了克服这些限制，提供了使用1D型激光距离传感器的激光点传感（LPS）功能。  
通过利用激光，感应时间缩短，干扰约束最小化，使得在简单条件下更容易更快地检测焊点。  

一旦将激光传感器通过支架安装在配备焊炬的工具法兰上，并进行一次工具与传感器的标定，就可以轻松获取激光指示的位置姿态。  
除了步检测外，焊点的姿态可以轻松获取，无需复杂的条件设置，无论基材形状如何。  
与触觉传感类似，可以使用主模式，当工件被引入时，可以自动计算与参考位置的偏移量。  

在接下来的部分中，您将完成传感器设置并开始使用LPS功能。
[__SOURCE](8_Application_function/7_LPS/1_settings.md)
<script id="page-config" type="application/json">
{
	"permittedStrs": ["Hi6", "Hi7"]
}
</script>

# 8.7.1 激光传感器设置  


要使用LPS功能，首先需要安装激光传感器，并配置通信规范和相关设置。
<br/>

### (1) 使用连接支架安装激光传感器

连接支架可以由用户设计和制造，或由我们公司或传感器制造商提供。

![](../../_assets/8_7_1.png)<br>
*图 8.7.1. 使用支架安装激光传感器*

激光距离传感器由发射器和接收器组成。
当机器人与弧焊枪对齐时，请确保激光传感器的发射器/接收器与基于工具的X方向对齐（请参考激光制造商的规格）。
此外，建议将传感器安装在工具Y方向的右侧（面向焊枪时的右侧）。  

安装激光器并通电后，保持工具尖与激光点之间的距离尽可能短，有助于干扰防止和循环时间（CT）。
最后，传感器安装位置相对于工具尖必须适合所使用的激光传感器的规格（测量范围），并应安装在高于最小规定距离的位置。



{% hint style="warning" %}
  建议将传感器支架直接安装到机器人法兰上。换句话说，机械结构的安装顺序为：**法兰 - 激光传感器和支架 - 冲击传感器 - 焊枪。**
{% endhint %}


### (2) 通信设置

可以根据激光传感器的规范通过参考以下链接进行连接。
(参考 [${cont_model} - 工业通信](https://hrbook-hrc.web.app/#/view/doc-industrial-communication/zh-${cont_model}/README?cont_model=${cont_model}))

本页面仅描述所选传感器的示例。

* 在进行设置之前，连接传感器头、控制器、通信单元（如果适用）和SMPS，然后供电。
（如果连接顺序不正确，则可能无法接收传感值。因此，在后续设置中，请确保首先连接传感器。）


#### 串行 - 示例：Keyence LK-G400

首先，配置传感器控制器设置。

* 通信速度设置（必需）  
1. 按住`SET`键，然后按`[UP]`键选择`Enu`。
2. 按`ENT`键，使用`[RIGHT]`键选择功能` (A)`（RS-232C）。
3. 按`ENT`键检查当前值（A-b0到b4；9600 / 19200 / 38400 / 57600 / 115200）。

* 显示单位设置（可选）  
1. 按住`SET`键，然后按`[UP]`键选择`oUt-1`。
2. 按`ENT`键，使用`[RIGHT]`键选择功能`G`。
3. 按`ENT`键并使用`[UP]`键设置所需的小数位数（G-0；0.01, 0.001,...）。

导航到`[F2: 系统] - 4: 应用参数 - 6: 激光点传感 - 1: 环境设置 ([F2: System] - 4: Application Parameters - 6: Laser Point Sensing - 1: Environment Setting)`。

![](../../_assets/8_7_2.png)<br>
*图 8.7.2. 激光通信设置（Keyence LK-G）*
</br>

选择Keyence作为LPS品牌进行设置。
设置完成后，验证**传感距离（mm）**字段中显示的值是否与控制器的输出值匹配。

<br/>


#### EtherNet/IP - 示例：Baumer OM-70

将传感器连接到PC并访问网页界面。
（默认固定IP地址为192.168.0.250。）

![](../../_assets/8_7_3.png)<br>
*图 8.7.3. Baumer传感器网页配置*
</br>  

导航到`设备配置`选项卡，并根据预期目的设置通信方式。
此时，仅启用与当前在过程接口部分使用的通信协议相匹配的方法。

如果使用**Ethernet/IP**，请相应地完成网络设置。在${cont_model}中，默认使用网络范围0、1和2，因此必须分配不同的范围。（例如：192.168.10.250。）

![](../../_assets/8_7_4.png)<br>
*图 8.7.4. Baumer传感器网络设置*
</br>   

然后，按以下链接逐步进行。
请注意，Hi6不支持内置以太网，因此必须使用通信卡（[Hi6 - 工业通信](https://hrbook-hrc.web.app/#/view/doc-industrial-communication/zh-Hi6/1-cifx-pci-communication/3-cifx-pci-settings-industrial-communication/3-EtherNet-IP/README?cont_model=Hi6)）。
从Hi7及以后，支持内置以太网，允许仅使用控制器建立通信（[Hi7 - 工业通信](https://hrbook-hrc.web.app/#/view/doc-industrial-communication/zh-Hi7/2-ethernet-ip/4-scanner/README?cont_model=Hi7)）。



![](../../_assets/8_7_5.png)<br>
*图 8.7.5. Baumer传感器信号分配*
</br>

完成上述步骤后，导航到`[F2: 系统] - 4: 应用参数 - 6: 激光点传感 - 1: 环境设置 - 信号选项卡 ([F2: System] - 4: Application Parameters - 6: Laser Point Sensing - 1: Environment Setting - Signal tab)`。
配置所分配块的输入信号。
然后，可以确认距离（当前值）作为传感器值输出。（如果需要传感与距离的映射，则需要额外设置。）


#### EtherNet/IP - 示例：Keyence IL-300

* 根据制造商手册和我们的手册，以与Baumer传感器相同的方式连接传感器。
如上所述，Ethernet连接方法取决于使用的是Hi6还是Hi7控制器。
[__SOURCE](8_Application_function/7_LPS/2_calibration.md)
# 8.7.2 TCP-传感器校准  

在使用LPS功能之前，必须对TCP和传感器进行校准。  
以下部分描述如何执行TCP到传感器的校准。

<br/>

### (1) 校准样本的准备  

当通过我公司购买许可证时，将提供用于自动校准的校准样本。

<br/>

### (2) 准备  

在执行校准之前，工具必须与校准平面完美对齐。  
根据工具坐标系手动教导工具在X和Y方向上的位置，并检查激光输出保持不变（误差保持在0.5或更低）。根据需要调整RX和RY值。  

工具对齐后，将线缆尖端放置在校准平面的边缘。  
在工具基础的X-Y方向上进行教学时，调整RZ值，使激光点沿着边缘角移动。  

<br/>

![](../../_assets/8_7_2_1.png)<br>
*图8.7.2.1 校准前的准备*<br/>  

完成上述步骤后，进行校准所需的所有准备工作已完成。

### (3) 执行自动校准  

将线缆尖端放置在校准平面的一个顶点。  
此外，确保激光点位于校准平面内部。  

<br/>

![](../../_assets/8_7_2_2.png)<br>
*图8.7.2.2 校准开始*<br/>  

从下方面板中选择`[F6: cmd. input] - arcweld - lps`并插入以下命令。

```py
  lps auto_calib, cnd=<Condition Number>, Tx=<Movement Distance in the X-dir based on the tool>, Ty=<Movement Distance in the Y-dir based on the tool
```

此时，移动距离必须设置为大于激光所需移动的距离。  
如果在指定参数内检测失败，将发生校准错误。  

在自动方式下执行时，校准通过以下操作序列进行：  

1. 激光点向Tx和Ty方向移动，最初朝向工具尖端方向移动。  
2. 根据机器人坐标系，机器人在+Z方向上抬起，并执行与步骤1相同的过程。  
3. 根据机器人坐标系，机器人在-Z方向上向下移动，同时向传输/接收器方向进行插值（当前支架规格Tx）。  

校准完全完成后，步骤左侧出现执行标记，所有运动停止。  

### (4) 校准信息  

导航到`[F2: 系统] - 4: 应用参数 - 6: 激光点传感 - 2: 校准 ([F2: System] - 4: Application Parameters - 6: Laser Point Sensing - 2: Calibration)`以检查校准结果。  
当**校准完成**字段中的值变为“2”时，表示所有校准过程，包括插值，已完成。  
校准信息是按工具编号存储的，这在使用工具更换功能时非常有用。  
如果工具信息相同，但要使用不同的工具编号，则可以复制并重用校准数据。

<br/>

![](../../_assets/8_7_2_3.png)<br>
*图8.7.2.3 校准结果*<br/>
[__SOURCE](8_Application_function/7_LPS/3_function.md)
# 8.7.3 使用 LPS 功能  

{% hint style="warning" %}
如果在使用此功能之前未执行工具与传感器的校准（参见 8.7.2），可能会存储无效的姿态。
{% endhint %}

### 属性窗口

LPS 命令的属性如下。  
<br/>

![](../../_assets/8_7_3_0.png)<br>
*图 8.7.3.0 LPS 属性*<br/>  

#### 间隙系数

此参数用于在 **步进模式 (stepp)** 中检测步骤差异，并允许用户指定检测到的高度差。  
但是，在校准过程中不使用此参数，因为使用了单独的校准样本。

#### 步骤灵敏度

此参数根据重复性设置数据处理的灵敏度。  
在大多数情况下，用户可以使用默认值，不需要额外调整。

#### 倾斜阈值（倾斜度）

此参数用于检测边缘。  
除了步骤系数外，它可以在工具与传感器的校准操作和步骤检测期间进行配置。  
由于边缘不总是垂直，因此此参数允许系统对倾斜表面做出响应。

#### 姿态坐标 / 移位坐标

此设置指定在执行每个模式时存储数据的坐标系统。  
特别是，当启用主模式时，会使用移位坐标。

<br/>

### (1) 点模式  

**点模式**用于验证校准结果或获取激光当前指示位置的姿态。  

<br/>

![](../../_assets/8_7_3_1.png)<br>
*图 8.7.3.1 点模式*<br/>  

```py
  var p10=cpo()
  lps spot,cnd=1,pose=p10
  move L,tg=p10,spd=10%,acc=0,tool=0
```

{% hint style="warning" %}
在这种情况下，仅在 sp 参数指定的姿态中记录位置。  
感应前的工具方向 (Rx, Ry, Rz) 不被保留。
{% endhint %}

<br/>


### (2) 步骤模式

**步骤模式**用于检测基材上发生高度差异的位置。  
根据高度差异的高低，扫描方向应相应保留。  

<br/>

![](../../_assets/8_7_3_2.png)<br>
*图 8.7.3.2 步骤模式*<br/>  

```py
  var p10=cpo()
  lps stepp,cnd=1,Tx=50,spd=5,pose=p10
  move L,tg=p10,spd=10%,acc=0,tool=0
```

系统根据工具在 X 或 Y 方向上以指定距离移动，同时搜索步骤差异。  
如果在指定距离内未检测到步骤，将发生检测错误。  

<br/>


### (3) 扫描模式

![](../../_assets/8_7_3_3.png)<br>
*图 8.7.3.3 在各种几何形状上进行的扫描模式*<br/>  

```py
  var p10=cpo()
  lps scan,cnd=1,Ty=50,spd=5,pose=p10
  move L,tg=p10,spd=10%,acc=0,tool=0
```

扫描模式在根据工具在 X 或 Y 方向上移动指定距离时检测焊点。  
不论是圆角、V型槽还是对接接头，都可以通过单个命令执行。  
检测结果可以通过 REST API 检索，或通过注册并使用我们公司提供的应用程序进行验证。  

有关注册和使用应用程序的说明，请参阅以下链接：[软件开发工具包 (SDK)](https://hrbook-hrc.web.app/#/view/doc-hi6-sdk/zh/README?cont_model=${cont_model})  

{% hint style="warning" %}
将移动距离设置得足够大，以包括焊缝，确保工具运动不与扫描表面平行。
{% endhint %}  


#### (3-1) 监控屏幕  

![](../../_assets/8_7_3_4.png)<br>
*图 8.7.3.4 LPS 图表*<br/>  

注册应用程序后，可以通过以下方法访问监控屏幕：`[Pane layout] - 选择 - LPS Graph ([Pane layout] - select - LPS Graph)` 

<br/>

![](../../_assets/8_7_3_5.png)<br>
*图 8.7.3.5 示例屏幕 - V型槽*<br/>  

![](../../_assets/8_7_3_6.png)<br>
*图 8.7.3.6 示例屏幕 - 对接接头*<br/>  

当执行此功能时，可以如上图所示查看结果。  
目前提供的屏幕具备以下功能：  

1. 可以通过点击左上角的刷新按钮刷新屏幕。
2. 右上角显示的数字值代表激光传感器的实时输出值。
3. 计算的焊点由红点表示。