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