# 8.5.2 LVS 设置

要使用 LVS 功能，必须进行传感器安装和通信设置。

现在让我们看一下所涉及的过程。

### (1) 使用连接支架安装 LVS 传感器

连接支架可以由您自己设计和使用，或者您可以从 HD 现代机器人或 LVS 制造商那里获得一个。<br>

![](../../_assets/8_5_3_lvs_mount_setup.png)<br>
*图 8.5.3. LVS 安装注意事项*

{% hint style="warning" %}
  - 为了实现重复的准确性和精确度，直接将 LVS 支架安装到机器人法兰上<br>
  - 换句话说，机械组件应按如下方式安装：法兰 - LVS 支架，LVS 传感器 - 冲击传感器（如果使用） - 焊枪。
{% endhint %}

工具坐标系应设置如下：焊接方向与进给方向相反的方向应设置为 +Tool X 方向，焊丝方向应设置为 +Tool Z 方向，如下图所示。

LVS 传感器必须安装，以确保激光垂直于焊接接缝，并且接缝是直的（见图）

![](../../_assets/8_5_4.png)<br>
*图 8.5.4. TCP 和传感器安装，工具坐标系统设置*

{% hint style="info" %}
  有关设置工具坐标系的说明，请参见工具校准和角度修正手册（角度校准）部分。
{% endhint %}

{% hint style="warning" %}
  为了使用 LVS，激光应位于焊接方向的前方，工具坐标系必须如上图所示设置。
{% endhint %}

---

### (2) 通信设置

使用以太网电缆连接 LVS 传感器控制器和机器人控制器。<br>
导航至 `[F2: 系统] - 4: 应用参数 - 5: LVS 追踪 - 1: 环境设置 ([F2: System] - 4: Application parameter - 5: LVS tracking - 1: Envrionment setting)`。<br>

在 **[通信]** 标签中，配置以下项目：

- LVS 品牌 : Scansonic, Oxford (或 Meta), Full-v<br>
- IP 地址 : 输入传感器控制器的 IP 地址。
- 本地端口 : 机器人控制器的端口。（对于 Oxford，8000）
- 远程端口 : 传感器控制器的端口。（对于 Oxford，8002）

输入上述信息后，点击 **[连接]**。如果状态显示“已连接”，则连接成功建立。

{% hint style="info" %}
- [IP 地址] : 用于将数据从 LVS 控制器发送到机器人控制器的 IP 地址是在 LVS 控制器中设置的。
  - 如果设置不正确，可能会导致连接失败。在这种情况下，请参阅 LVS 制造商的手册。
- [端口] : 选择品牌时，默认值将自动应用，因此用户无需修改它们。
  - 如果端口不正确，可能会导致连接失败。在这种情况下，请参阅 LVS 制造商的手册。
{% endhint %}

---

### (3) 基本设置

在 **[追踪]** 标签中，配置以下项目：
- P 增益 : 指定 TCP 跟踪转换位置和方向的强度。
- D 增益 : 指定 TCP 响应转换位置和方向的速度。
- 最大追踪距离 : 指定每秒 [mm/sec] 的最大追踪量。

<table>
  <thead>
    <tr>
      <th style="text-align:left">项目</th>
      <th style="text-align:left">描述</th>
      <th style="text-align:left">推荐设置</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">P, D 增益</td>
      <td style="text-align:left">指定 TCP 跟踪转换位置和方向的强度。</td>
      <td style="text-align:left">
        一般追踪（不带编织） : 设置在 1 ~ 10 的范围内。 <br>
        编织追踪（带编织） : 使用默认值 10。 <br>
        默认值为 P 增益：10 和 D 增益：10。根据实际工件调整这些值。
      </td>
    </tr>
    <tr>
      <td style="text-align:left">最大追踪距离/秒 [mm/sec]</td>
      <td style="text-align:left">指定每秒 [mm/sec] 的最大追踪量。</td>
      <td style="text-align:left">
        设置在 1 到 5 的范围内。默认值为 10。<br>
        LVS 接缝追踪旨在纠正小偏差，因此不需要设置更大的值。
      </td>
    </tr>
  </tbody>
</table>

通过上述过程完成了偏好设置。
---

#### Full-V 传感器配置示例

![](../../_assets/8_5_5_lvs_setting_fullv_1.png)<br>
*图 8.5.5. Full-V 传感器连接设置*

如上图所示，在选择 LVS 品牌为 FULL 后，在 Full-V 软件中检查 LVS 传感器的 IP 地址。<br>
在 `[F2: 系统] - 4: 应用参数 - 5: LVS 追踪 - 1: 环境设置 ([F2: System] - 4: Application parameter - 5: LVS tracking - 1: Envrionment setting)` 窗口中输入 IP。<br> 然后，点击底部的“连接”按钮并确认连接状态显示。<br>
如果出现“断开连接”，请检查硬件连接和 IP 地址。<br>

请参考 Full-V 提供的手册和下面的图来注册您希望在 Full-V 软件中使用的接缝。

![](../../_assets/8_5_6_lvs_setting_fullv_2.png)<br>
*图 8.5.6. Full-V 软件中接缝设置示例*