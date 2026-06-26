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