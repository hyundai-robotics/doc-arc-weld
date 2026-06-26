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