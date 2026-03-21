# 8.5.1 LVS 概述与规格

{% hint style="info" %}
此功能自版本 60.30-03 开始提供。
{% endhint %}

此功能通过使用 LVS（激光视觉传感器）识别焊缝，实现对工件和夹具误差的实时补偿，从而使焊接过程中可以进行焊缝跟踪。

LVS 必须直接连接到机器人的法兰上。传感器检测焊缝，机器人的工具实时跟踪焊缝。

换句话说，通过焊缝跟踪，即使焊接目标的位置发生变化并偏离原始参考点，仍然可以进行焊接。

![](../../_assets/8_5_1.png)<br>
*图 8.5.1. LVS 焊缝跟踪流程图*

</br>

#### 命令

LVS 焊缝寻找与跟踪功能通过 `lvs` 命令执行，该命令可以通过选择 `[F6: cmd. input] - arcweld - lvs` 在 TP 中输入。

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
        当前被传感器感知的激光焊缝位置被存储在命令的 'sp' 参数指定的姿态变量中（机器人/基坐标系）。<br>
        注意，方向(RX, RY, RZ)在执行命令时记录为工具的方向。
      </td>
    </tr>
    <tr>
      <td style="text-align:left">seam_find_p</td>
      <td style="text-align:left">
        当前被传感器感知的激光焊缝位置被存储在命令的 'sp' 参数指定的姿态变量中（机器人/基坐标系）。<br>
        注意，方向(RX, RY, RZ)保持为原始姿态变量，仅更新 X、Y 和 Z 值。<br>
        在使用 'intersection' 等函数时，这一点尤其有用，因为交点是使用三点来计算姿态。
      </td>
    </tr>
    <tr>
      <td style="text-align:left">auto_calib</td>
      <td style="text-align:left">
        在 TCP 和 LVS 之间执行自动校准。（参考 <a href="https://hrbook-hrc.web.app/#/view/doc-arc-weld/zh/8_Application_function/5_LVS_tracking/3_calibration?cont_model=${cont_model}">LVS 校准</a>）
      </td>
    </tr>
    <tr>
      <td style="text-align:left">search</td>
      <td style="text-align:left">
        在 +ToolX 和 -ToolX 方向移动时找到起始点，并进行跟踪准备。<br>
        检测到的起始点存储在命令的 'sp' 参数指定的姿态变量中。
        （参考 <a href="https://hrbook-hrc.web.app/#/view/doc-arc-weld/zh/8_Application_function/5_LVS_tracking/6_search?cont_model=${cont_model}">LVS 搜索功能</a>）
      </td>
    </tr>
    <tr>
      <td style="text-align:left">step_search</td>
      <td style="text-align:left">
        在 +ToolX 和 -ToolX 方向移动时找到起始点或多焊道的起始点。<br>
        检测到的起始点存储在命令的 'sp' 参数指定的姿态变量中。
        （参考 <a href="https://hrbook-hrc.web.app/#/view/doc-arc-weld/zh/8_Application_function/5_LVS_tracking/6_search?cont_model=${cont_model}">LVS 搜索功能</a>）
      </td>
    </tr>
    <tr>
      <td style="text-align:left">track</td>
      <td style="text-align:left">
        搜索完成后，必须执行 'arcon' 和 'weaving on' 动作后再执行。<br>
        跟踪将持续进行，直到遇到 'arcoff'。
      </td>
    </tr>
    <tr>
      <td colspan="2">条件编号</td>
      <td>
        这是用于应用 lvs 命令属性窗口中配置的设置的条件编号。<br>
        属性窗口允许您设置搜索速度、搜索距离、队列间隔、跟踪限制和感应坐标系（机器人/基），等等。
      </td>
    </tr>
  <tr>
      <td colspan="2">要感应位置的轮廓编号</td>
      <td>
        这是指用户在 LVS 控制器中注册的感应形状和感应条件对应的编号。
        当命令执行时，LVS 控制器会加载与此编号相关的感应形状和条件。
      </td>
    </tr>
    <tr>
      <td colspan="2">被感应位置的姿态变量</td>
      <td>
        当前激光位置对应的位姿存储为姿态变量。
      </td>
    </tr>
    <tr>
      <td colspan="2">主位置的姿态变量</td>
      <td>
        这是在主模式下注册的参考姿态变量。
        （参考 <a href="https://hrbook-hrc.web.app/#/view/doc-arc-weld/zh/8_Application_function/5_LVS_tracking/5_lvs_master_mode?cont_model=${cont_model}">8.5.5 LVS 主模式功能</a>）
      </td>
    </tr>
    <tr>
      <td colspan="2">当前感应位置相对于主位姿的位移变量</td>
      <td>
        当前感应位置相对于 mp（主位姿）的位移存储。
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
        如果为此参数设置了变量，成功找到焊缝时将设置为 1，如果焊缝寻找失败则无错误地设置为 0。
      </td>
    </tr>
  </tbody>
</table> 
使用```lvs```命令的跟踪功能可以如下使用：

![](../../_assets/8_5_2.png)<br>
*图 8.5.2. LVS缝合跟踪的教学方法*

---

#### LVS功能规格

* 支持一般运动跟踪功能（线性L插值，圆形C插值，以及复合线性和圆形段）
* 支持编织跟踪功能（0.5Hz ~ 3Hz）
* 支持定位器同步跟踪功能（SMOV段）
* 支持定位器同步 + 编织跟踪功能（0.5Hz ~ 3Hz）

<table>
  <thead>
    <tr>
      <th style="text-align:left">项目</th>
      <th style="text-align:left">LVS制造商</th>
      <th style="text-align:left">重复精度</th>
      <th style="text-align:left">重复精确度</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left" rowspan="3">seam_find / seam_find_p</td>
      <td style="text-align:left">SCANSONIC (350, 150, 150 advanced)</td>
      <td style="text-align:left">左右：0.1 mm（参考 ± 30mm 高度），0.4mm<br>高度：0.4mm（参考 ± 30mm 高度），2mm<br>前/后：0.4mm（参考 ± 30mm 高度），1.5mm</td>
      <td style="text-align:left">0.05 mm</td>
    </tr>
    <tr>
      <td style="text-align:left">OXFORD (OSL-50)</td>
      <td style="text-align:left">左右：0.4 mm（参考 ± 30mm 高度），0.7mm<br>高度：0.6mm（参考 ± 30mm 高度），3mm<br>前/后：0.6mm（参考 ± 30mm 高度），2.5mm</td>
      <td style="text-align:left">0.2 mm</td>
    </tr>
    <tr>
      <td style="text-align:left">Full-v</td>
      <td style="text-align:left">左右：0.6 mm（参考 ± 30mm 高度），2mm<br>高度：0.8mm（参考 ± 30mm 高度），4.5mm<br>前/后：0.6mm（参考 ± 30mm 高度），4mm</td>
      <td style="text-align:left">0.35 mm</td>
    </tr>
    <tr>
      <td style="text-align:left" rowspan="3">track</td>
      <td style="text-align:left">SCANSONIC (350, 150, 150 advanced)</td>
      <td style="text-align:left">0.2mm（线性）<br>0.4mm（编织）<br>0.25mm（定位器同步）<br>0.5mm（编织 + 定位器同步）</td>
      <td style="text-align:left">0.05 mm</td>
    </tr>
    <tr>
      <td style="text-align:left">OXFORD (OSL-50)</td>
      <td style="text-align:left">0.3mm（线性）<br>0.5mm（编织）<br>0.4mm（定位器同步）<br>0.6mm（编织 + 定位器同步）</td>
      <td style="text-align:left">0.2 mm</td>
    </tr>
    <tr>
      <td style="text-align:left">Full-v</td>
      <td style="text-align:left">0.3mm（线性）<br>0.6mm（编织）<br>0.4mm（定位器同步）<br>0.7mm（编织 + 定位器同步）</td>
      <td style="text-align:left">0.35 mm</td>
    </tr>
  </tbody>
</table>