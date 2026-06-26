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