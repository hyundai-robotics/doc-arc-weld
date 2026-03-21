# 6.3 编织同步输出

此功能通过在编织过程中调整左右两侧的电流和电压，允许平滑控制热输入（焊接沉积）。

{% hint style="info" %}
  该功能在版本60.30-00中得到支持。
{% endhint %}

![](../../_assets/6_3_1_weav_sync_out.png)<br>
*图 6.3.1. 编织同步输出功能示例*

如上图所示，当需要在左右编织过程中控制热输入和焊接沉积，或当需要调整焊缝形状时，可以使用此功能。

要使用此功能，请进入`weaving`命令的`[Property]`窗口并配置以下设置。

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
        启用后，根据用户的设置调节编织过程中的电流/电压输出。
      </td>
    </tr>
    <tr>
      <td style="text-align:left">输出（左/右）</td>
      <td style="text-align:left">
        相对于左、右编织设置的基线条件，电流/电压输出变化的百分比。
      </td>
    </tr>
    <tr>
      <td style="text-align:left">范围</td>
      <td style="text-align:left">
        设置左、右编织过程中的输出变化百分比范围。
      </td>
    </tr>
  </tbody>
</table>