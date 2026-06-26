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